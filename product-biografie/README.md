# Product Biografie

## Week 1
In the first week of the project for [Wallscope](https://wallscope.co.uk/) [Antero Duarte](https://www.linkedin.com/in/anterod/) visited Amsterdam to explain some of concepts of the project like 'Linked data'. 

### Linked data  ⃡
A little explanation about linked data (what I remember from his talk): Be sure to check out the [medium article](https://medium.com/wallscope/linked-data-a-conceptual-exploration-9860a1f44d68) Antero made, where he also explains linked data.
So linked data is a way in which data is stored in the database. Nowadays we have table based databases but with linked data you have to look at it like a graph based database. 

**Example**

So for example we have two persons: 'John' and 'Heather'. John has a mother named Heather. So we now know that John and Heather are Linked. This is the basics but we can take it one step further.

Heather also has a daughter named Emma. So all the database now knows is that John has a mother named Heather and Heather has a daughter named Emma. Because of the fact that the data is linked we can now say that John has a sister named Emma! 

This last thing is what I find one of the most interesting this about linked data. Where you actually create new data based on the existing data. 

*Also this week...*

### Edinburgh! ✈
We arrived wednesday afternoon, and got to be your average tourist for the rest of the day 😎. On thursday we attended the Wallscope event at the University in Edinburgh. Here we spoke with the people who store all the public data and the ones who enable people to search this data. But the usability of this search website is very bad which is one of the reasons why we started this project. 

After some presentations we started brainstorming and trying to understand the linked data and how we could fit it in our ideas. 

When starting a new project I always have a lot of ideas. So I just start sketching to try and explain my ideas:
Here the idea is that you start by searching for tags, by which you get certain results. The user can configure the way the tags are linked to get different results. 
![scan1](./img/scan1.jpg)

This idea is focused on the people who don't know what they're looking for. It starts with a button to randomize the query and you directly see the results. The results can also be shuffled.
This way the user can get many different unexpected results. 
![scan2](./img/scan2.jpg)

In this idea the user sees a summary of the article as a result, instead of the 'Google' way of showing results with hyperlinks. This way the user asks their question like a story and also receives a story as a result. 
![scan3](./img/scan3.jpg)

**Start of our concept**

This is the sketch which led to our current concept.
Here the user searches for something through an input field. The results have the option to give it a like so it will be stored in their personal 'Topics' (which was later named 'Boards'). In the overview of the different topics the user can see how many articles are stored in the topic by looking at the different sizes. 
![scan4](./img/scan4.jpg)

On the final day of the event we chose to present an idea where the user can search with large sentences. While I was still sketching different ideas the rest of the project group made some first designs of how it might look like. The attendees where pleased with what we came up with in two days. 

## Week 2
This week was a little harder, when we had a talk with our coach we realized that we just made an input field to search a database accessible to the public. So basically a simple concept for the target group: 'everyone'. We chose to go for a more focused target group: 'medical students'. We chose to go for the idea I came up with in Edinburgh: ![scan4](./img/scan4.jpg) 

So now we have a good target group with an exciting concept. Now we had to choose how we were going to realise it. [Maikel van Veen](https://github.com/Maikxx) suggested to work with React and Typescript for our workflow. I've never worked with React or Typescript before, but I think it's very interesting and I want to learn more about it. 

The biggest part of this week was setting up and working out how to app is going to work. The rest of the group was mainly focused on the more technical side of the project, but I focused more on the UI/UX. I always try to know at every moment of the project: Why are we making this? Who is going to use it? How is anyone going to use this? etc. So I started drawing and making sense of the concept: 
![scan4](./img/scan6.jpg) 

This week I also started learning react and the component based workflow. I wrote an article about my view on React [here](https://github.com/jesperingels/weekly-nerd-1819/blob/master/articles/react/README.md). It was quite hard to understand React and also effectively work with it in such a short time span. It was a little frustrating for me, since I was thinking/typing/searching for React 80% of the time and I only spent 20% actually typing effective working code. So for example when making a header it would maybe take a few seconds to type it in HTML: `<header></header>`. But in React you have to create an entire component just to produce the same line of code. You also have to think what you want to do with the component, when implementing it in other components or rendering it eventually. 

## Week 3
This week I continued with Learning React and started to create one of my first components. To start working on a project I first look at our git hub [project board](https://github.com/Maikxx/360-wallscope/projects/1) and choose a todo I can pickup. I drag the card to the 'in progress' board and create a new feature branch for the component I'll be working on. 
Next thing is to put the React standard component code in the file. I took notes on my learning process with React [here](https://github.com/jesperingels/meesterproef-1819/tree/master/360-wallscope) 

I learned a lot from the workflow we used in this project, since it was sort of the same workflow Maikel van Veen used at [Lifely](https://lifely.nl/) it's a workflow professionals use. So I think it's good to have experience with a workflow like this, when working for a company like Lifely in the future. 



