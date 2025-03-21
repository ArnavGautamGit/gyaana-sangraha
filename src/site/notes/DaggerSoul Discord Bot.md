---
{"dg-publish":true,"permalink":"/DaggerSoul Discord Bot/","tags":["TTRPG","coding"]}
---


---
# DaggerSoul Discord Bot
> Stores the process of creation, my thought processes while creating the bot. By extension, it also documents [[DaggerSoul Discord Bot#All Internal Versions\|#All Internal Versions]] and [[DaggerSoul Discord Bot#All Release Versions\|#All Release Versions]] of DaggerSoul Discord Bot.

Main part of [[DaggerSoul Project\|DaggerSoul Project]] which completely abides by the [Developers TOS](https://support-dev.discord.com/hc/en-us/articles/8562894815383-Discord-Developer-Terms-of-Service) set by Discord. I express by views about the TOS [[Discord Developers TOS\|here]].

UptimeRobot is a service that is free, which will ping your bot every 5 minutes so that it does not go to sleep. In case it does go to sleep, then click on [this link](https://dashboard.render.com/web/srv-cs55245umphs73anqt20/deploys/dep-cs56fno8fa8c73agors0)

Invite Bot to server using the link: [Invite to your server](https://discord.com/oauth2/authorize?client_id=1294584872526024734&permissions=274877975552&integration_type=0&scope=bot)

Future Plans for the bot:
1. Action Tracking
2. Fear Token Tracking
3. Storing and Searching Stuff with `!soul search <item or spell>`
	1. Weapons
	2. Armour
	3. Spells
4. Attack Rolls = Duality + Hit Dice of Weapon with command `!soul attack <weapon>`


---
## All Internal Versions
### Internal Version 0.1.0 - Can Roll Duality Dice
The Bot needs to be a given dictionary of users with player roles and their User IDs upon which bot can manage their Duality Roles and store Hope Tokens for each unique User via their unique ID.

```Python
import discord
from discord.ext import commands
import random

intents = discord.Intents.default()
intents.message_content = True

bot = commands.Bot(command_prefix='!', intents=intents)

# Dictionary to store player data
players = {}

@bot.event
async def on_ready():
    print(f'{bot.user} has connected to Discord!')

@bot.command(name='soul')
async def soul(ctx, action):
    if action.lower() != 'roll Duality':
        await ctx.send("Invalid command. Use '!soul roll Duality' to roll the Duality Dice.")
        return

    await ctx.send("Rolling the Duality Dice...")
    
    # Roll Hope and Fear dice
    hope_roll = random.randint(1, 12)
    fear_roll = random.randint(1, 12)
    
    await ctx.send(f"Hope Die: {hope_roll}")
    await ctx.send(f"Fear Die: {fear_roll}")
    
    if hope_roll != fear_roll:
        sum_roll = hope_roll + fear_roll
        if hope_roll > fear_roll:
            result = f"Result = {sum_roll} with HOPE!"
            await increment_hope_token(ctx.author.id)
        else:
            result = f"Result = {sum_roll} with FEAR!"
            await ctx.send("Add 1 Fear Token to Action Tracker")
    else:
        result = "Critical Success!"
        await increment_hope_token(ctx.author.id)
        await ctx.send("Increment your Stress Point manually by 1.")
    
    await ctx.send(result)

async def increment_hope_token(user_id):
    if user_id not in players:
        players[user_id] = {"hope_tokens": 0}
    
    players[user_id]["hope_tokens"] += 1
    await ctx.send(f"Hope Token added. You now have {players[user_id]['hope_tokens']} Hope Tokens.")

# Replace 'YOUR_BOT_TOKEN' with your actual bot token
# bot.run('YOUR_BOT_TOKEN')
```

### Internal Version 0.2.0 - Can find and auto-update Player list
Earlier I had to manually add users even after they had the "Player" Role in Discord. New improvement allows automatic addition. 
```Python
import discord
from discord.ext import commands
import random

intents = discord.Intents.default()
intents.message_content = True
intents.members = True  # We need this to fetch all members in the server

bot = commands.Bot(command_prefix='!', intents=intents)

# Dictionary to store player data
players = {}

@bot.event
async def on_ready():
    print(f'{bot.user} has connected to Discord!')
    await update_player_list()

async def update_player_list():
    for guild in bot.guilds:
        player_role = discord.utils.get(guild.roles, name="Player")
        if player_role:
            for member in guild.members:
                if player_role in member.roles:
                    if member.id not in players:
                        players[member.id] = {"hope_tokens": 0, "name": member.name}
    print("Player list updated!")

@bot.command(name='soul')
async def soul(ctx, action):
    if action.lower() != 'roll Duality':
        await ctx.send("Invalid command. Use '!soul roll Duality' to roll the Duality Dice.")
        return

    player_role = discord.utils.get(ctx.guild.roles, name="Player")
    if player_role not in ctx.author.roles:
        await ctx.send("Only players can use this command!")
        return

    await ctx.send("Rolling the Duality Dice...")
    
    # Roll Hope and Fear dice
    hope_roll = random.randint(1, 12)
    fear_roll = random.randint(1, 12)
    
    await ctx.send(f"Hope Die: {hope_roll}")
    await ctx.send(f"Fear Die: {fear_roll}")
    
    if hope_roll != fear_roll:
        sum_roll = hope_roll + fear_roll
        if hope_roll > fear_roll:
            result = f"Result = {sum_roll} with HOPE!"
            await increment_hope_token(ctx.author.id)
        else:
            result = f"Result = {sum_roll} with FEAR!"
            await ctx.send("Add 1 Fear Token to Action Tracker")
    else:
        result = "Critical Success!"
        await increment_hope_token(ctx.author.id)
        await ctx.send("Increment your Stress Point manually by 1.")
    
    await ctx.send(result)

async def increment_hope_token(user_id):
    if user_id not in players:
        await update_player_list()
    
    if user_id in players:
        players[user_id]["hope_tokens"] += 1
        await ctx.send(f"Hope Token added. {players[user_id]['name']} now has {players[user_id]['hope_tokens']} Hope Tokens.")
    else:
        await ctx.send("Error: Player not found. Please contact an administrator.")

@bot.command(name='update_players')
@commands.has_permissions(administrator=True)
async def update_players_command(ctx):
    await update_player_list()
    await ctx.send("Player list has been updated!")

# Replace 'YOUR_BOT_TOKEN' with your actual bot token
# bot.run('YOUR_BOT_TOKEN')
```

### Internal Version 0.3.0 - Realisation & Simplification
Many times, we complicate things with questions like
- What if a player needs to play multiple characters? We should have the rolling be mapped with Characters instead of Discord User IDs. 

We often forget the goal: the goal was to make the bot an Avrae equivalent for Daggerheart. well, Avrae does not create characters. It fetches data from the official website (which we don't have now), it  makes rolls and tracks initiative - initiative is not a thing in Daggerheart. 

I tried making the entire Character Creation Process then decided against it. 
Players already use Demiplane and a lot of things can still change. Even after adding Character Creation the GM will have to do Combat, Action Tracking, Fear Token Tracking Manually and have to trust the player that the stress point slots the player claims is true.

Its better to just do the rolling on the bot and leave the rest to the GM.

Why use a bot then anyway? So that the process of dice rolling is actually transparent.

Character Creation has been removed.
```Python
import discord
from discord.ext import commands
import random

intents = discord.Intents.default()
intents.message_content = True
intents.members = True

bot = commands.Bot(command_prefix='!', intents=intents)

@bot.event
async def on_ready():
    print(f'{bot.user} has connected to Discord!')

@bot.command(name='soul')
async def soul(ctx, action, *args):
    if action.lower() == 'roll' and args[0].lower() == 'duality':
        await roll_duality_dice(ctx)
    else:
        await ctx.send("Invalid command. Use '!soul roll duality'")

async def roll_duality_dice(ctx):
    hope_roll = random.randint(1, 12)
    fear_roll = random.randint(1, 12)

    await ctx.send(f"Rolling the Duality Dice...")
    await ctx.send(f"Hope Die: {hope_roll}")
    await ctx.send(f"Fear Die: {fear_roll}")

    if hope_roll != fear_roll:
        sum_roll = hope_roll + fear_roll
        if hope_roll > fear_roll:
            result = f"Result = {sum_roll} with HOPE!"
            await ctx.send("Add a Hope Token to Character Sheet!")
        else:
            result = f"Result = {sum_roll} with FEAR!"
            await ctx.send("Add 1 Fear Token to Action Tracker")
    else:
        result = "Critical Success!"
        await ctx.send("Increment your Stress Point by 1 and add a Hope.")
        
    await ctx.send(result)

# Replace 'YOUR_BOT_TOKEN' with your actual bot token
# bot.run('YOUR_BOT_TOKEN')

```

### Internal Version 0.4.0 - Dice Rolling Upgrades
Dice-rolling is upgraded to work for dice rolls such as `2d6+3` or `5d4` or something similar whereas it only worked for singular dice rolls like `d20 (1d20)` or `d6` and similar.

It also adds "advantage and disadvantage" on Duality rolls.

```Python
import discord
from discord.ext import commands
import random
import re

intents = discord.Intents.default()
intents.message_content = True
intents.members = True

bot = commands.Bot(command_prefix='!', intents=intents)

@bot.event
async def on_ready():
    print(f'{bot.user} has connected to Discord!')

@bot.command(name='soul')
async def soul(ctx, action, *args):
    if action.lower() == 'roll' and args[0].lower() == 'duality':
        if len(args) > 1:
            if args[1].lower() == 'adv':
                await roll_duality_dice(ctx, advantage=True)
            elif args[1].lower() == 'dis':
                await roll_duality_dice(ctx, disadvantage=True)
            else:
                await ctx.send("Invalid option! Use 'adv' for advantage or 'dis' for disadvantage.")
        else:
            await roll_duality_dice(ctx)
    elif re.match(r'^\d*d\d+(\+\d+)?

### Internal Version 0.5.0 - Duality command changed
All commands were triggered by `!soul <dice>` and it made no sense that only duality dice were rolled like `!soul roll duality` with the extra word "roll" that the players can easily miss.
For the sake of Consistency, I changed the command to `!soul duality` to be less confusing for players.

```Python
import discord
from discord.ext import commands
import random
import re
import os

TOKEN = os.environ['discordkey']

intents = discord.Intents.default()
intents.message_content = True
intents.members = True

bot = commands.Bot(command_prefix='!', intents=intents)

@bot.event
async def on_ready():
    print(f'{bot.user} has connected to Discord!')

@bot.command(name='soul')
async def soul(ctx, dice_input: str):
    if dice_input.lower() == 'duality':
        await roll_duality_dice(ctx)
    elif dice_input.lower() == 'duality adv':
        await roll_duality_dice(ctx, advantage=True)
    elif dice_input.lower() == 'duality dis':
        await roll_duality_dice(ctx, disadvantage=True)
    else:
        match = re.match(r'(\d*)d(\d+)(\+(\d+))?', dice_input)
        if match:
            await roll_dice(ctx, match)
        else:
	        ctx.send(f"Invalid dice format. Please write in 'mdn+x' format (for example: '2d6' or '2d6+3'). If you are trying to roll Duality Dice use the command `!soul duality`.")

async def roll_duality_dice(ctx, advantage=False, disadvantage=False):
    hope_roll = random.randint(1, 12)
    fear_roll = random.randint(1, 12)

    await ctx.send(f"Rolling the Duality Dice...")
    await ctx.send(f"Hope Die: {hope_roll}")
    await ctx.send(f"Fear Die: {fear_roll}")

    if hope_roll != fear_roll:
        sum_roll = hope_roll + fear_roll
        if advantage:
            extra_d6 = random.randint(1, 6)
            await ctx.send(f"Advantage: Rolling extra d6 = {extra_d6}")
            sum_roll += extra_d6
        elif disadvantage:
            extra_d6 = random.randint(1, 6)
            await ctx.send(f"Disadvantage: Rolling extra d6 = {extra_d6}")
            sum_roll -= extra_d6

        if hope_roll > fear_roll:
            result = f"Result = {sum_roll} with HOPE!"
            await ctx.send("Add a Hope Token to Character Sheet!")
        else:
            result = f"Result = {sum_roll} with FEAR!"
            await ctx.send("Add 1 Fear Token to Action Tracker")
    else:
        result = "Critical Success!"
        await ctx.send("Increment your Stress Point by 1 and add a Hope.")
    
    await ctx.send(result)

async def roll_dice(ctx, match):
    num_rolls = int(match.group(1)) if match.group(1) else 1
    dice_size = int(match.group(2))
    modifier = int(match.group(4)) if match.group(4) else 0

    total_roll = 0
    rolls = []
    for _ in range(num_rolls):
        roll = random.randint(1, dice_size)
        rolls.append(roll)
        total_roll += roll

    total_roll += modifier

    await ctx.send(f"Rolling {num_rolls}d{dice_size}{f'+{modifier}' if modifier else ''}: {rolls}")
    await ctx.send(f"Total: {total_roll}")


# bot.run(TOKEN)

```

---
## All Release Versions

### Release Version 0.1.4 - Added files
Addition of `webserver.py` and `requirements.txt` files and changes to `DaggerSoul.py` to make the bot hostable and many bug fixes (4).

`DaggerSoul.py file`
```Python
# DaggerSoul.py

import discord
from discord.ext import commands
import random
import re
import os
import webserver

TOKEN = os.environ['discordkey'] # hides the Diskord token as an environment key

intents = discord.Intents.default()
intents.message_content = True
intents.members = True

bot = commands.Bot(command_prefix='!', intents=intents)

@bot.event
async def on_ready():
    print(f'{bot.user} has connected to Discord!')

@bot.command(name='soul')
async def soul(ctx, dice_input: str):
    if dice_input.lower() == 'adv':
	    await roll_duality_dice(ctx, advantage=True)
    elif dice_input.lower() == 'dis':
        await roll_duality_dice(ctx, disadvantage=True)
    elif dice_input.lower() == 'duality':
        await roll_duality_dice(ctx)
    else:
        match = re.match(r'(\d*)d(\d+)(\+(\d+))?', dice_input)
        if match:
            await roll_dice(ctx, match)
        else:
	        ctx.send(f"Invalid dice format. Please write in 'mdn+x' format (for example: '2d6' or '2d6+3'). If you are trying to roll Duality Dice use the command `!soul duality`.")

async def roll_duality_dice(ctx, advantage=False, disadvantage=False):
    hope_roll = random.randint(1, 12)
    fear_roll = random.randint(1, 12)

    await ctx.send(f"Rolling the Duality Dice...")
    await ctx.send(f"Hope Die: {hope_roll}")
    await ctx.send(f"Fear Die: {fear_roll}")

    if hope_roll != fear_roll:
        sum_roll = hope_roll + fear_roll
        if advantage:
            extra_d6 = random.randint(1, 6)
            await ctx.send(f"Advantage: Rolling extra d6 = {extra_d6}")
            sum_roll += extra_d6
        elif disadvantage:
            extra_d6 = random.randint(1, 6)
            await ctx.send(f"Disadvantage: Rolling extra d6 = {extra_d6}")
            sum_roll -= extra_d6

        if hope_roll > fear_roll:
            result = f"Result = {sum_roll} with HOPE!"
            await ctx.send("Add a Hope Token to Character Sheet!")
        else:
            result = f"Result = {sum_roll} with FEAR!"
            await ctx.send("Add 1 Fear Token to Action Tracker. (action tracker coming soon)")
    else:
        result = "Critical Success!"
        await ctx.send("Increment your Stress Point by 1 and add a Hope.")
    
    await ctx.send(result)

async def roll_dice(ctx, match):
    num_rolls = int(match.group(1)) if match.group(1) else 1
    dice_size = int(match.group(2))
    modifier = int(match.group(4)) if match.group(4) else 0

    total_roll = 0
    rolls = []
    for _ in range(num_rolls):
        roll = random.randint(1, dice_size)
        rolls.append(roll)
        total_roll += roll

    total_roll += modifier

    await ctx.send(f"Rolling {num_rolls}d{dice_size}{f'+{modifier}' if modifier else ''}: {rolls}")
    await ctx.send(f"Total: {total_roll}")

webserver.keep_alive()
bot.run(TOKEN) # key must not be stored in the code, rather in the webserver as an environment key
```

`webserver.py file`
```Python
# webserver.py

from flask import Flask
from threading import Thread

app = Flask('')
@app.route('/')

def home():
	return "Discord bot online"

def run():
	app.run(host="0.0.0.0", port=8080)

def keep_alive():
	t = Thread(target=run)
	t.start()
```

`requirements.txt file`
```text
discord
Flask
```

### Release Version 0.2.0 - Added Help Function
The other two files will remain the same, but only the `DaggerSoul.py` file will change.

```Python
# DaggerSoul.py

import discord
from discord.ext import commands
import random
import re
import os
import webserver

TOKEN = os.environ['discordkey'] # hides the Diskord token as an environment key

intents = discord.Intents.default()
intents.message_content = True
intents.members = True

bot = commands.Bot(command_prefix='!', intents=intents)

@bot.event
async def on_ready():
    print(f'{bot.user} has connected to Discord!')

@bot.command(name='soul')
async def soul(ctx, dice_input: str):
    if dice_input.lower() == 'help':
	    await soul_help(ctx)
    elif dice_input.lower() == 'adv':
	    await roll_duality_dice(ctx, advantage=True)
    elif dice_input.lower() == 'dis':
        await roll_duality_dice(ctx, disadvantage=True)
    elif dice_input.lower() == 'duality':
        await roll_duality_dice(ctx)
    else:
        match = re.match(r'(\d*)d(\d+)(\+(\d+))?', dice_input)
        if match:
            await roll_dice(ctx, match)
        else:
	        ctx.send(f"Invalid dice format. Please write in 'mdn+x' format (for example: '2d6' or '2d6+3'). If you are trying to roll Duality Dice use the command `!soul duality`.")

async def roll_duality_dice(ctx, advantage=False, disadvantage=False):
    hope_roll = random.randint(1, 12)
    fear_roll = random.randint(1, 12)

    await ctx.send(f"Rolling the Duality Dice...")
    await ctx.send(f"Hope Die: {hope_roll}")
    await ctx.send(f"Fear Die: {fear_roll}")

    if hope_roll != fear_roll:
        sum_roll = hope_roll + fear_roll
        if advantage:
            extra_d6 = random.randint(1, 6)
            await ctx.send(f"Advantage: Rolling extra d6 = {extra_d6}")
            sum_roll += extra_d6
        elif disadvantage:
            extra_d6 = random.randint(1, 6)
            await ctx.send(f"Disadvantage: Rolling extra d6 = {extra_d6}")
            sum_roll -= extra_d6

        if hope_roll > fear_roll:
            result = f"Result = {sum_roll} with HOPE! Add a Hope Token to Character Sheet!"
            
        else:
            result = f"Result = {sum_roll} with FEAR! Add a Fear Token to Action Tracker! (Action Tracker Coming Soon)"
            
    else:
        result = f"It's a Critical Success! Increment Stress and Hope by 1!!"
        
    
    await ctx.send(result)

async def roll_dice(ctx, match):
    num_rolls = int(match.group(1)) if match.group(1) else 1
    dice_size = int(match.group(2))
    modifier = int(match.group(4)) if match.group(4) else 0

    total_roll = 0
    rolls = []
    for _ in range(num_rolls):
        roll = random.randint(1, dice_size)
        rolls.append(roll)
        total_roll += roll

    total_roll += modifier

    await ctx.send(f"Rolling {num_rolls}d{dice_size}{f'+{modifier}' if modifier else ''}: {rolls}")
    await ctx.send(f"Total: {total_roll}")

async def soul_help(ctx):
    embed = discord.Embed(
        title="DaggerSoul Bot Commands",
        description="Here are the commands you can use with the DaggerSoul Bot:",
        color=0x2F3136  # Dark gray for the embed box
    )

    embed.add_field(
        name="`!soul <dice>`",
        value="Rolls dice of a specified size (e.g., `!soul 2d6+3`).",
        inline=False
    )
    embed.add_field(
        name="`!soul duality`",
        value="Rolls the Duality Dice (Hope and Fear).",
        inline=False
    )
    embed.add_field(
        name="`!soul adv`",
        value="Rolls the Duality Dice with advantage (extra d6 added).",
        inline=False
    )
    embed.add_field(
        name="`!soul dis`",
        value="Rolls the Duality Dice with disadvantage (extra d6 subtracted).",
        inline=False
    )
    embed.add_field(
        name="`!soul help`",
        value="Displays this help message.",
        inline=False
    )

    embed.set_footer(text="Use the correct format to roll dice (e.g., '2d6+3').")
    
    await ctx.send(embed=embed)


webserver.keep_alive()
bot.run(TOKEN) # key must not be stored in the code, rather in the webserver as an environment key
```

### Feedback from Release Versions
Details the feedback I gathered:
- The bot gives the diceroll in multiple messages, it may cause slowdowns or [[Process Synchronisation\|Process Synchronisation]] issues (each instance overriding the Critical Variables).
	- Possible Fix: Collect Data in variables and display all variables in one message.
- The bot shuts down frequently
	- Problem 1: I use a free plan of Uptime Robot that only pings every 5 minutes which is not a short-enough frequency to keep the bot awake.
	- Problem 2: To ping in less than 5 minute intervals, I will have to pay them.
	- Fix: Create or find  another bot with an infinite loop that pings this bot every 1 minute.
- The bot cannot connect to Character Sheets like Avrae
	- Problem 1: Demiplane does not have an API that I can leverage.
	- Problem 2: To connect and store Character Sheets I need Server Space (which I don't have)
	- Fix: See and copy how Avrae does it. Reverse Engineer Demiplane or ask for help from Demiplane Support Team if needed. 

---
# Footnotes, args[0].lower()):
        await roll_dice(ctx, args[0].lower())
    else:
        await ctx.send("Invalid command. Use '!soul roll duality', '!soul roll duality adv', or '!soul roll duality dis', or roll dice with formats like '2d6+4'.")

async def roll_duality_dice(ctx, advantage=False, disadvantage=False):
    hope_roll = random.randint(1, 12)
    fear_roll = random.randint(1, 12)
    
    await ctx.send(f"Rolling the Duality Dice...")
    await ctx.send(f"Hope Die: {hope_roll}")
    await ctx.send(f"Fear Die: {fear_roll}")

    sum_roll = hope_roll + fear_roll
    if hope_roll != fear_roll:
        if hope_roll > fear_roll:
            result = f"Result = {sum_roll} with HOPE!"
            await ctx.send("Add a Hope Token to Character Sheet!")
        else:
            result = f"Result = {sum_roll} with FEAR!"
            await ctx.send("Add 1 Fear Token to Action Tracker")
    else:
        result = "Critical Success!"
        await ctx.send("Increment your Stress Point by 1 and add a Hope.")

    # Handle advantage and disadvantage
    if advantage:
        extra_d6 = random.randint(1, 6)
        sum_roll += extra_d6
        result += f"\nAdvantage Roll: Added {extra_d6}, new result = {sum_roll}."
    elif disadvantage:
        extra_d6 = random.randint(1, 6)
        sum_roll -= extra_d6
        result += f"\nDisadvantage Roll: Subtracted {extra_d6}, new result = {sum_roll}."

    await ctx.send(result)

async def roll_dice(ctx, dice_input):
    # Parse input like 2d6+4
    match = re.match(r'(\d*)d(\d+)(\+(\d+))?', dice_input)
    if not match:
        await ctx.send("Invalid dice format. Please write in '2d6' or '2d6+3' format.")
        return

    num_rolls = int(match.group(1) or 1)  # default to 1 if no number before 'd'
    dice_type = int(match.group(2))
    modifier = int(match.group(4) or 0)  # default to 0 if no modifier

    # Roll the dice
    rolls = [random.randint(1, dice_type) for _ in range(num_rolls)]
    roll_sum = sum(rolls) + modifier

    # Send the result
    await ctx.send(f"Rolling {dice_input}: Rolls = {rolls}, Modifier = {modifier}, Total = {roll_sum}")

# Replace 'YOUR_BOT_TOKEN' with your actual bot token
# bot.run('YOUR_BOT_TOKEN')

```

### Internal Version 0.5.0 - Duality command changed
All commands were triggered by `!soul <dice>` and it made no sense that only duality dice were rolled like `!soul roll duality` with the extra word "roll" that the players can easily miss.
For the sake of Consistency, I changed the command to `!soul duality` to be less confusing for players.

{{CODE_BLOCK_4}}

---
## All Release Versions

### Release Version 0.1.4 - Added files
Addition of `webserver.py` and `requirements.txt` files and changes to `DaggerSoul.py` to make the bot hostable and many bug fixes (4).

`DaggerSoul.py file`
{{CODE_BLOCK_5}}

`webserver.py file`
{{CODE_BLOCK_6}}

`requirements.txt file`
{{CODE_BLOCK_7}}

### Release Version 0.2.0 - Added Help Function
The other two files will remain the same, but only the `DaggerSoul.py` file will change.

{{CODE_BLOCK_8}}

### Feedback from Release Versions
Details the feedback I gathered:
- The bot gives the diceroll in multiple messages, it may cause slowdowns or [[Process Synchronisation]] issues (each instance overriding the Critical Variables).
	- Possible Fix: Collect Data in variables and display all variables in one message.
- The bot shuts down frequently
	- Problem 1: I use a free plan of Uptime Robot that only pings every 5 minutes which is not a short-enough frequency to keep the bot awake.
	- Problem 2: To ping in less than 5 minute intervals, I will have to pay them.
	- Fix: Create or find  another bot with an infinite loop that pings this bot every 1 minute.
- The bot cannot connect to Character Sheets like Avrae
	- Problem 1: Demiplane does not have an API that I can leverage.
	- Problem 2: To connect and store Character Sheets I need Server Space (which I don't have)
	- Fix: See and copy how Avrae does it. Reverse Engineer Demiplane or ask for help from Demiplane Support Team if needed. 

---
# Footnotes