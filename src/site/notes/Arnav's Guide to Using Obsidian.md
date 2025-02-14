---
{"dg-publish":true,"permalink":"/Arnav's Guide to Using Obsidian/"}
---


---
# Arnav's Guide to Using Obsidian
Hello!
Welcome to my guide to using Obsidian!
Obisidian is a wonderful note-taking app in my opinion and everyone should use it for knowledge management and documentation.

Whatever your reason may be for using Obsidian, we will look at it all!
There are The Basics, which are agnostic to what requirements or expectations you have from Obsidian i.e., you will use these features anyway regardless of what you are using this for.

The Basics: [[Arnav's Guide to Using Obsidian#How to add Links, Headings and Tables?\|How to add Links, Headings and Tables?]]
Specific Functionalities: [[Arnav's Guide to Using Obsidian#How to add Formulae?\|How to add Formulae?]] and [[Arnav's Guide to Using Obsidian#How to add Code Blocks?\|How to add Code Blocks?]]
Advanced Knowledge: [[Arnav's Guide to Using Obsidian#How to create Templates?\|How to create Templates?]]

Now keep in mind, I will keep adding things as I find them out.

### How to add Links, Headings and Tables?
Links are added by placing any string of alphabets and numbers in any order inside square parenthesis i.e., if you add `[[Arnav]]` to a note, it will create a link to another note named "Arnav". The Link will appear greyed out if a note by that name does not exist & will appear brightly coloured if there is a note of that name.
For example: I know a note named [[ABCDEFG\|ABCDEFG]] does not exist & hence this note appears greyed out and leads nowhere in-app but on the website you are probably seeing this on, it leads to an error screen since that is how I programmed the website to avoid someone accidentally mis-clicking. On the other hand, a note named as [[Arnav's Guide to Using Obsidian\|Arnav's Guide to Using Obsidian]] does exist & hence appears brightly coloured.

"But Arnav..." you would ask, "how did you create the links above in this note which link to headings in the same note?" and that would be a great question! For that we need to know how Headings are added.

If you put a Hashtag (#) in front of a piece of text, it creates the largest heading size & the more hashtags you add, the smaller the heading gets.
```
# Largest Heading
## Second Largest Heading
### Third Largest Heading 

and so on.
```

If you know HTML, One Hashtag is basically equal to H1 heading, and adding 2 hashtags means it is the H2 heading & so on.

Now how do we link to individual headings?
Remember how we made Links to notes using Square Brackets? Add a heading in it.
Let's say that instead of `[[Arnav]]` note, you want to navigate to a specific heading inside the note (say you want to see my pictures) frame the link as `[[Arnav#Pictures]]` and that's all.

You can also link to specific lines in the note.
You can also display the said lines by adding a Exclamation Mark before the square brackets.
{ #1}


If I type out:
`
<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/arnav-s-guide-to-using-obsidian/#1" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">



You can also link to specific lines in the note.
You can also display the said lines by adding a Exclamation Mark before the square brackets. 

</div></div>
`

<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/arnav-s-guide-to-using-obsidian/#1" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">



You can also link to specific lines in the note.
You can also display the said lines by adding a Exclamation Mark before the square brackets. 

</div></div>


All I did is add a "^1" at the end of the block of text I wanted to display & linked to it. 
Added a Exclamation Mark (!) in front of the link to display it. 
If I do not add that Exclamation Mark, I can easily create a small clickable link.
[[Arnav's Guide to Using Obsidian#^1\|Arnav's Guide to Using Obsidian#^1]]

I can also rename a link (or display a different text over the link) by adding vertical bar (|)
[[Arnav's Guide to Using Obsidian#^1\|This links to the same text hehe]]

Now coming onto Tables.
For Tables, go ahead and types this
```
| Column 1 | Column 2 | 
|---|---|
```

Keep in mind to put space of one line above and below the tables for them to actually form.
If the app decides to autocomplete your table by the second line but you are missing column names, then clicking any empty cell below the column headings will fix the table. 

### How to add Formulae?
To add Formulae or Equations in Maths or Physics, please use:
If you want your equation in the same line: `$Equation$` 
If you want your equation in a new line: `$$Equation$$`

### How to add Code Blocks
You see the blocks I use to encase commands so that I can show them without triggering them, you need to incase a word or sentence in singular backtick (\`) which is the button on the left of the 1 number and above the Tab button on a regular QWERTY keyboard.

Single backtick encasing is useful if you want to encase a word  while keeping `text` inline

Larger Blocks are automatically generated if you use three backticks without space.
Like: \`\`\`

Use a backslash (\\) to allow placing a backtick, square bracket or another backslash without triggering the command.

### How to create Templates
settings > under the options heading > core plugins > templates (turn it on)
then in the settings there is a section on core plugins > Templates > here you would find an option to set a folder to store your templates. You would need to create a folder inside the vault for storing templates and then put the name of that folder there. Any notes stored in the folder can be used as templates.

Detailed walkthrough on Templates will be updated on this note very soon.

---
# Footnotes