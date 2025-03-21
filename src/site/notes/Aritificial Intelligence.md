---
{"dg-publish":true,"permalink":"/Aritificial Intelligence/","tags":["coding"]}
---

----
# List of Contents
[[Aritificial Intelligence#What is Artificial Intelligence (AI)?\|What is Artificial Intelligence (AI)?]]
[[Aritificial Intelligence#Terminologies related to AI\|Terminologies related to AI]]
[[Aritificial Intelligence#What makes an AI Company?\|What makes an AI Company?]]
[[Aritificial Intelligence#What can't Machine Learning accomplish?\|What can't Machine Learning accomplish?]]
[[Aritificial Intelligence#Workflow of a Machine Learning Project\|Workflow of a Machine Learning Project]]
[[Aritificial Intelligence#Why AI cannot always get 100% Accuracy\|Why AI cannot always get 100% Accuracy]]
[[Aritificial Intelligence#Famous OpenSource ML Frameworks\|Famous OpenSource ML Frameworks]]
[[Aritificial Intelligence#Famous Research Publications\|Famous Research Publications]]
[[Aritificial Intelligence#Case Study 1 - *Smart Speakers*\|Case Study 1 - *Smart Speakers*]]
[[Aritificial Intelligence#Case Study 2 A Self-Driving Car\|Case Study 2: A Self-Driving Car]]
[[Aritificial Intelligence#Working in an AI team - Roles in the team\|Working in an AI team - Roles in the team]]
[[Aritificial Intelligence#How do AI teams fit in a corporation?\|How do AI teams fit in a corporation?]]
[[Aritificial Intelligence#DO's and DON'Ts - Pitfalls to avoid\|DO's and DON'Ts - Pitfalls to avoid]]
[[Aritificial Intelligence#Realistic View on AI\|Realistic View on AI]]
[[Aritificial Intelligence#Taking First Steps in AI\|Taking First Steps in AI]]

----

Note: Artificial Intelligence often uses Python. Since the development time is low and syntax is simple.
Hence [[Python\|Python]] is imperative for Artificial Intelligence.
# What is Artificial Intelligence (AI)?
AI is majorly divided into 2 parts: 
1. Aritificial Narrow Intelligence (ANI) 
2. Artificial General Intelligence (AGI)
### Artificial Narrow Intelligence - ANI
ANI is the more common form of AI that we see all around us in smart speakers, self-driving cars, web search. In one line, it can do any 1 thing better than a human or at least as good as a human.
Even chess bots like Stockfish are examples of ANI when they are trained on all these chess games that have occurred over the years.
### Artificial General Intelligence -  AGI 
AGI is - simply put - that kind of AI that is theorised to do anything a human can do.
We are constantly trying to work towards it but we have hardly made anything remotely similar.
We have made something like ChatGPT but I don't think that it is an AGI since it cannot walk, run etc.
It cannot code well, It cannot draw a circle...
It cannot solve Math well either.
ChatGPT is still an ANI or atleast an ANI posing/trying to be AGI.
### Should we fear AI?
A lot of people in the field of AI think that AGI is hundreds of years away...
But if we start getting multiple ANIs for most of our intellectual tasks anyway and drones and other robotic implements don't require humans to physically move then humans will be unnecessary weight on society which this AI may try to "fix".
The fear is still somewhat rational.
### What is AI built on?
Artificial Intelligence is built on:
1. Machine Learning
2. Data
   - The Data the AI is trained on
   - The Data used to get valauable results after the AI is trained
   - The Data used to update the AI for upcoming days if a new change has occurred in the market

### How is efficiency of any AI measured?
If you were to plot a Performance vs Data graph, you would find that Data is logarithmically proportional to the performance of the AI.
In simpler terms, as the amounts of data increases, the performance of the AI gets better logarithmically which is just like a log(n) graph.

The downside to this is that the AI will perform much poorer the lesser amount of data it is fed. (Recall the graph of a log(x) function)

If you use Deep Leaning (also called Neural Networks) the AI's efficiency gets better BUT on the data sets where lesser amounts of data is fed, the AI may be only *marginally* better since the graph still remains logarithmic.

Logarithmic Graphs are not very good for lower data sets, ==hence to obtain ***max efficiency*** one ought to use as many neural networks with as much of training data as possible!==

This highlighted line is what layed the foundations of [[Big Data\|Big Data]] because you need the power to handle that massive amounts of data you are supoosed to train the AI on!
### What is Data?
Data is stored in Datasets - tables of data.
Maybe even used in Excel sheets.
AI works by mapping Data A-->B that is, it maps data stored as A (input) to data B (output).
In training data however, B will need to be provided.
Data cannot be in form of plain text, images or audio... that is known as unstructured data.
Data in form of Spreadsheets and tables is called as the structured data.

# Terminologies related to AI
### Machine Learning (ML) vs Data Science (DS):
Machine Learning refers to a type of A : B (or A-->B) mapping. You give it some inut, it will give you some output. We discussed it in [[Aritificial Intelligence#What is Data?\|Aritificial Intelligence#What is Data?]]
ML is often used in Running AI machines like Websites, Apps that run 24x7 and can take input anytime and output the answer any time. It memorises tags of things. For example: Delhi is tagged to India so if you were to input Delhi in the system (A = Delhi) then output would be India (B = India)
Data Science on the other hand has a team of Humans which will analyse the same data to reveal insights such as "Did you know 2 houses in the same part of city are being sold, but one is on a price which is 20% below the Market Rate?" or "Did you know that even if the house is of the same square footage, the price nearly doubles if it has one extra room from 2 BHK to 3 BHK?"
### Deep Learning vs Neural Network
Deep Learning is a newer name given to the Neural Networks. Neural Networks are named after the biological brain although it has no similarity to the biological brain in how the AI tool works. Hence they are called "Artificial Neural Networks" to emphasize that these are just a bunch of code and not like any human brain.
*Neural Networks are made of nodes called Neurons which are basically interconnnected pieces of data which the AI system uses and due to the interconections, it makes it more complicated (also more "intelligent") than Machine Learning - providing much more deep insights*. Hence it is also called Deep Learning. ***Deep Learning and Neural Networks are the same thing***, just Deep Learning is a markting term and Neural Network is a term used by people who wanna sound smart about their creation.
### Reinforced Learning
This Learning technique is similar to how we train dogs with good boy and bad boy remarks followed by reward. Give AI a positive value (+1 , for example) if it does its job correctly, and a negative number (like -1) if it does not. Make it so that it maximises reward, and the AI will try and do the right thing each time. Eventually it will learn.
Example: It is used extensively in building Chess, Checkers, Go or any other sport-playing engines.
### Unsupervised Learning
When the training data is provided, A (input) is given but B (output) is not. Making the AI to find B and its relation with B on its own. This is the next frontier if breakthroughs happen in this field.
The AI algorithmj is essentially given the data and asked to give insights in the data (similar to Data Science and Data Analytics employees).
### Supervised Learning
Anything a human can do in less than 1 minute can be done by AI as well. For example: Translation from one language to another (machine translation), speech recognition, visually identify scratched/broken mobile screens from photos etc.
Sometimes, if training data is not enough then Supervised Learning AI models can create Gibberish output.
### Transfer Learning
It is an AI Technique where once the AI model learns Task A, it can use the knowledge gained from A and apply it to learn B, needing less training data for B.
Example: Once your Self-Driving car can recognise cars in the environment after a training data of 10,000 pictures, it should be able to learn to recognise Golf Carts with just 100 pictures or less than 100 pictures... 
### Computer Vision
AI is able to recognise flowers and their types, for example.
AI can use this tech in Face Recognition.
Detection of Cars, Pedestrian and their positions with respect to each other and/or their position with respect to the AI itself.
### GANs - Generative Adversarial Networks
Generating random faces/pictures of things/people that never existed before. GANs are used extensively in Graphic intensive environment like Games, AI Generated Images etc.
### Knowledge Graphs
Have you noticed separate sections on the side of a screen when you search for eminent personalities like Da Vinci? It is a knowledge graph.
These have interconnected tables. Each table is connected to another and each table contains some info about the subject. See it as very similar to the Obsidian's Knowledge Graph.
# What makes an AI Company?
Any company + Deep Learning $\large\neq$ AI Company
You need the following to be called a AI company:
- ***Strategic Data Collection***: Collecting the right, useful data only.
- ***Unified Data Warehouse***: A unified place where all required Data is stored for the AI tools to run with fastest speeds.
- ***Pervasive Automation***: Automate as many things as possible within the organisation.
- ***Introduction of new roles*** specific to AI-ML like MLE (Machine Learning Engineer)
If your company isn't one, then follow the steps recommended by Andrew Ng in his 5 step AI transformation playbook.
# What can't Machine Learning accomplish?
Anything that is complex enough that Humans take more than a few seconds or 1 minute to solve.
Machine learning Problems are made easier by having a large amount of data and the learning task being simple enough (like playing Checkers).
AI is the new Electricity in this age. We can be its Tesla (pun intended).
AI and ML cannot (as of now, at least it is very hard to do if even possibe to) interpret human gestures and output what the human is trying to convey. AI cannot differentiate between a person raising their hand on the side of the road to ask for a lift or a cyclist trying to indicate a turn using their arm.
ML Algorithms can be used to diagnose Pneumonia given an X-ray once it has been trained on 10k or 100k labelled X-rays images (known as training data). They cannot do the same if the labelled training data is 10 X-ray images.
# Example Technology: Face Recognition
The Face reciognition technology is an example of Neural Network/Deep Learning Technology's prowess.
To train it, you need to give the AI model pictures along with the name of the person in the picture, do keep in mind that a picture should only contain one person.
The Network will (on its own), after 1000s of photos start to understand what you want and will form neurons based on that. In short, if you provide Input 'A' and Output 'B', the AI will figure out how it needs to map the two. The AI also creates its own neurons inside. Some might only recognise some lines or pixels, the next may underline individual eyes, nose, mouth and then the next ones will start recognising the contours of what a face looks like. Leading to a level where AI can distinguish 2 faces. Process is described as a photo below:
![Face Recognition.png](/img/user/Vaulted%20Images/Face%20Recognition.png)
For a picture of size $\large1000\times1000$ pixels, there are $\large 1,000,000$ values in case of a grayscale image and $\large 3,000,000$ values in case of a coloured image (since coloured images have 3 R,G and B values while B&W ones have only Pixel Brightness value)
# Workflow of a Machine Learning Project
Workflow of a project is simply explained in 3 key points:
1. Collection of Data
2. Training the model
3. Deploy Model
We shall look at all these points separately wth an example.
Andrew Ng gave the example of the Amazon Alexa (also called "Amazon Echo"). 
For simplicity's sake, we shall be using the same example. 
We can first easily collect data of different people first speaking 'Alexa' in their accents and then collect data about them talking about something different.
We can Label this data and organise it. This is ***Collection of Data*** done.
We then, using this data, can ***train our model*** in multiple iterations and then until it is good enough and that it works. Once the model is trained very well, we can ***deploy the model*** on a website or app or even a web-app! Only thing to note here is that deployment also means that you'll need to keep it updated and have it report the data back to you so you can update the AI service even better... although some people may be averse to that due to privacy reasons.

Using a new example like Self Driving Cars...
You need to feed the picture data of cars and photos of roads and signs etc.
Then you need the photos to highlight cars in red or neon green rectangles that will be added using photoshopped data to make your labelled data. Each car in the photo needs to "labelled".
it slowly will learn whether a picture has a car or a bollock cart etc.
the process needs to be repated with signs of different types with different (or same) coloured boxes.
Then we deploy this model as well. Tesla took 5 years to do this... from Tesla Roadster to Tesla Model S. 
### Types of Deployment
In the case of a car, the depployment is always Edge. Edge Deployment allows that the car has an in-built small processor inside which can process data on its own since there is not enough time to send the data to a cloud server and then have the server reply to the request and the car process the request. Before Edge, the most used one was on-prem (on-premises) i.e., the code is inside the car along with some data storage device hooked to a bigger full-fledged processor. Cloud deployment is used in other projects where the code is deployed on rented cloud server space (like AWS, Microsoft Azure etc.) Smart speakers (cheaper ones) use Cloud Deployment. Although some of the more expensive ones may use Edge for smaller tasks and Cloud for bigger ones.
# How to choose an AI Project?
The AI Experts know best about AI and the domain experts know best about the field whose problem you want to solve with your project. You need best of both worlds.
You would always want the intersection of both the given sets in the Venn Diagram.
Before you begin working on the project however, you need to perform a strong anf thorough due diligence on the project idea.
![Choose AI Project.png](/img/user/Vaulted%20Images/Choose%20AI%20Project.png)
What is Due Diligience? Checking whether the project is feasible and valuable - by checking the Technical Diligence and Business Diligence respectively.

| ***TECHNICAL DILIGENCE*** | ***BUSINESS DILIGENCE*** |
|---|---|
| Can AI system meet desired performance? | Does the AI system reduce the costs involved? Can it boost revenue? |
| How much data does the AI need? | Build the AI system or Buy the pre-built? |
| Engineering Timeline: Number of Required People and The Required Amount of Time | Can this AI System aid me in the launch of a new product or line of business? Can the AI itself become a line of business? |

Don't fear using Spreadsheets to check if an AI system is viable in terms of business.
Also, do check if the AI system is Ethically Viable using Ethical Diligence.

For the Build vs Buy problem, Don't build something that is not specific to you or if it doesn't give you a competitive edge. Keep away from industry standards since they'll be built by someone else and will be more efficient and you can go ahead and buy their licenses... making it a much more efficient process. There is a very popular saying in Computer Science circles, ***"DO NOT SPRINT IN FRONT OF THE TRAIN, NEVER RUN AFTER THE TRAIN... BE INSIDE IT, CHAUFFERED BY IT."***
Give each project a Due Diligence of at least 2-4 weeks before beginning a project.
# Why AI cannot always get 100% Accuracy
AI systems claiming to have 100% accuracy are all lying.
There are several reasons why even for AI, $\geq 95\%$ is almost impossible to achieve.
These reasons include:
- ***==Limitations of the ML model itself==*** - there are something ML just cannot do as well as other things. Such as: Estimating Aperture, ISO, Depth of field ands similar values used to click a given photograph.
- ***==Insufficient Data==*** - more data means more detailed analysis but computers don't have eyes and cannot see 3D, so they can never really go beyond judging 3D images using 2D pixels for which there is no amount of data that is "sufficeient" since it is a logarithmic curve.
- ***==Mislabelled Data==*** - honest mistakes on the human error while training the model... even one wrong entry can destroy the model completely... bring its accuracy from $97\%$ to $85\%$!
- ***==Ambiguous Data==*** - Not clear which of the available labels to give to a specific data.
# Famous OpenSource ML Frameworks
Frameworks that can be directly used in your code without any leagal issues as they are fully open source projects that can be reused by anyone. Like a Creative Commons (CC) License for Music.
FOSS (Free and Open Source Software) Frameworks incude:
- TensorFlow
- PyTorch
- Keras
- MXNet
- CNTK
- PaddlePaddle
- Caffe
- Scikit-learn (some call it "sk learn")
- R
- Weka
# Famous Research Publications
Places where Research Publications are most easily found.
1. Arxiv
2. GitHub
More to be added soon....
# Case Study 1 - *Smart Speakers*
A smart speaker reads your sentence in two sections: Catchphrase and Command
Catchphrase is also called "Wake Word"... but we won't use that term.
$$\large^"Hey\ Device,\ tell\ me\ a\ joke^"$$
$\large^"Hey\ Device^"$ is the Catchphrase and $\large^"tell\ me\ a\ joke^"$ is the Command.
Steps to execute the sentence given above:
1. ***==Trigger Word/Catchphrase Detection==***: Detects/Recognises the "Hey Device"
2. ***==Speech Recognition==***: Recognises Command.
3. ***==Intent Recognition==***: Processes Command; recognising and processing what the user is asking.
4. ***==Execute Command==***: After recognising and processing the command, the command is run.

Note, that there are multiple ways to ask a smart speaker to tell a joke. "Tell me a joke", "Do you know a  joke" and similar variants should all yield the same result.

These string of operations on the sme data is called an AI pipeline.
When there is a process/ML algorithm which processes one piece of data after the other.

Another Example Sentence:
$$\large^"Hey\ Device,\ set\ timer\ for\ 10\ minutes.^"$$
Here all the first 3 steps will be the same, but the third step will have two parts.
1. ***==Extract Duration==***: "Set timer for 10 minutes" should give same results as saying "let me know when 10 minutes are up" or "set an alarm for 10 minutes".
2. ***==Start the timer==***: Or set the alarm, or perform any command that was given.
### Challenge faced with this technology
- Each function (like Play Music, Current Time, Units Conversion, Tell Weather) needs a team of people engineers to write specialised software.
- ***User training is sometimes needed*** to tell the consumers that Smart Speakers cannot do certain tasks... like fixing appointments in a free slot on your calendar after consulting the guests on call.
# Case Study 2: A Self-Driving Car
Key steps:
1. Car Detection using cameras around the car.
2. Pedestrian Detection using Cameras.
3. Motion Planning - finds a safe path which also takes in mind the driving laws of a country.

Inputs:
- ***==Camera and Optical Sensors==***: Images, RADAR, LIDAR, GPS/Maps, Traffic Light Detection, Roadsign Detection, Lane Detection, Obstacle Detection
- ***==On-board Processor==***: Trajectory Prediction (needed for predicting trajectory of Cars, cyclists, motorcyclists even pedestrians etc.)
Outputs:
- Drive FFS.
![Self-Driving Car Pipeline.png](/img/user/Vaulted%20Images/Self-Driving%20Car%20Pipeline.png)
# Working in an AI team - Roles in the team
Some AI Projects may take 100s of engineers to complete. Others are just 5 people strong. Some projects are done solo.
Note: Job Titles and their consistency is slightly disputed since the field of AI is still stabilizing.
Example Roles:
1. Software Engineer (SE) is the classic position. Versatile and hence lower salary.
2. Machine Learning Engineer (MLE) - MLE is responsible to implement Machine Learning Concepts and Algorithms to solve problems. Higher paid and more niche-skilled.
3. Machine Learning Researcher (MLR) - rarely is an actual researcher but is the senior of the MLE
4. Applied ML Scientist - senior of the MLE but junior to MLR.
5. Data Scientist (DS) - examine data and provide insights via routine presentations.
6. Data Engineer (DE) - Make sure data is saved in an easily accessible, secure & cost-effective way.
7. AI Product Manager (AIPM) - Help decide what to byuild and what not to build. The AI team version of a regular Project Manager.
### Small Team Example:
- 1x SE
- 1x MLE and/or 1xDS
- 1x AIPM (optional)

Radical Idea: Go Solo (for people who are pioneers of AI in their companies or not employed yet, i.e., Students)
# How do AI teams fit in a corporation?
There are 5 steps to doing this. We shall discuss them all in detail
### Step 1: Executing Pilot Projects
- More important for the initial project is to succeed rather than being the most valuable.
- Show traction in the first 6-12 months
- Open Source if needed.
### Step 2: Building in-house AI teams
- Build separate unit for AI
- The AI unit must take in talent from all departments and directly report to the CEO and be centralised (i.e., independent from any other department)
- Introduce the post like CAIO (Chief AI Officer) or VP, AI (Vice President, AI)
- Initial Funding should come directly from the CEO, whether the unit is making itself financially beneficial or giving a worthy ROI is a different thing entirely.
### Step 3: Providing Broad AI Training
| ***ROLE*** | ***TYPE OF TRAINING*** |
|---|---|
| Executives & Senior Business Leaders | What AI can do for the company, AI Strategy, Resource Allocation |
| Leaders of Divisions working on AI projects | Set project direction (Due Diligence), Resource Allocation and Progress Monitoring |
| AI Engineers and Trainees | Build and Ship AI software, gather data, execute on specific AI projects |
### Step 4: Develop AI Strategy
- Leverage AI to get an advantage specific to industry.
- Pilot before Strategy to avoid useless news headline keyword-clatter in emails.
- Use Virtuous Cycle of AI to enter new verticals and make them defensible.
- Data Strategy must consider strategic data collection and unified data warehouses.
### Step 5: Develop internal and external comms
- AI may change/alter a lot of products/services offered by companies
- Investors Relations
- Government Relations - increase Public-Private-Partnership Model usage with them to have good rep.
- Consumer Education about features and pricing needs to be clear. Also transparency about support staff and emails
- Talent/Recruiment may need some success stroies to bring better and better freshers.
- Internal Comms - Address any concerns employees may have about AI (rational or not).
# DO's and DON'Ts - Pitfalls to avoid
| ***DO's*** | ***DON'Ts*** |
|---|---|
| Be realistic with what AI can and cannot do| Expect AI to do everything.|
|Pair Engineers with Business Talent| Hire 2-3 MLEs and call it a day.|
| Plan for development to be iterative and projectsnot working in the first attempt | Expect Project to work flawlessly on the very first try| 
| Ask and consult team for possible milestones, timelines etc. | Expect Tradional Plans, Knowledge and Wisdom to work the same way here |
| Keep Building your team | Think you only need 1 superstar MLE|
# Realistic View on AI
The best way to keep a level headed, realistic view of any technology (AI included) is to always use the Goldilocks Rule, don't be too soft nor too firm.

Don't be too optimistic that people are going through to make AI that will turn sentient and go Terminator T-1000 on all humans. AI gainning sentience is several decades (if not centuries) away from happening. Human technology has progressed far but hasn't progressed nearly far enough to create a new form of intelligent life on Earth! What is this? Detroit: Become Human?

Don't be too pessimistic/firm that an AI winter is going to arrive (similar to the Bitcoin and Crypto Crash) i.e., there is hype now and someday we'll figure out AI is just a hyped mess and they can't really do everything and then this field will die like YoYos, although there is no denying that this thought has facts to it, but the "AI Winter" aspect of it is too extreme. Even if AI turns out to be hype on a big chunk, that won't be enough since it is the best technology that we have built in a long time.

It is also important to note one of the biggest flaws with AI - its inability to explain itself.
AI can scan an X-ray and say that a paticular lung is collapsed, but it cannot be said with precision what it was looking at and looking for (even with heat maps). Let alone AI, sometimes even Humans are not able to explain our hypothesis and hence terms like "intuition" and "hunch" have developed overtime... ask someone why do they call something a mug and not a cup, chances are... they'll need to Google the bookish difference and what they'll say themselves is very surface level gibberish.
If the AI can explain how they reached the hypothesis in a step-by-step manner (without rambling like Generative-AI such as ChatGPT and Phind) then it can be considered a breakthrough in this technology.

Certain AI systems have been known to be biased due to a biased training dataset. Not due to an inherent bias in the program. Initially, ChatGPT was biased against Hinduism and was pro-Aryan Migration but it is nice to know that the AI community is working on preparing the most unbiased data possible. The Bias is problematic  since if you build a hiring tool that discriminates against women, then your company will get cancelled. It will be considered disciminatory by the leftist media (which is in power in the US) unless it gives women more favourable and unfair results OVER the men since that's how diversity hiring has been working in the CS space in India. Too many companies hire women that have great soft skills with zero coding knowledge and men with "worse soft skills" end up covering for them (Developers India subreddit is filled with these stories). So much for women empowerment. Biased laws and biased interviewers. Everyone is biased towards them yet all of them think they are constantly being discriminated against.
# Taking First Steps in AI
- Get Friends/Colleagues to learn about AI... either with this course or another. Form a reading group.
- Start Brainstorming Projects together (no project is too small)
- Hire a few MLEs or DS experts to help
- Hire/appoint AI leader (VP AI, CAIO etc.)
- Discuss w/ CEO and Board about possibilities of AI Transformation.