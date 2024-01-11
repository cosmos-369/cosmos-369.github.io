---
title: "event modelling"
last_modified_at: 2024-1-11
categories:
  - Blog
tags:
  - learn
---

# event modelling

**what is event modelling?**

event modelling is a simple technique that we use to design a system, event modelling generally takes quite less time to learn and to get started, in event modelling we use sticky notes to write things down,

stickies colour and their purpose:

we use **orange sticky** to represent an event, we write down the event occurrence in past tense, events are generally triggered by the UI or by some external API

example: position updated, request received, response sent

we use **blue sticky** to represent a command, we write down the command as assertive sentence, a command is something which modifies the system state, a command is caused to

example: update player health, send request

we use **green sticky** to represent a view, a view is like a snapshot of the current system state, it can be used to display the current state of the system to the user and can also be used by other system applications

example: display player’s health

lets try to create an event modelling diagram for a simple fitness app that we will be making

lets start with what we want our app to do:

- display today’s to do exercises
- reminder notifications to exercise
- keep track of the streaks

now that we know what our simple app should do let’s think about the event, here are a few that i came up with:

- requested today’s exercises
- completed today's exercises
- alarm set
- notification sent
- requested current streak
- set time reached

![Untitled](/assets/images/2024-1-11-event-modelling/Untitled.png)

now that we have our events let’s see how to these event can be triggered, we use simple wire frames or actual screenshot of app if it’s already developed, to represent the UI, we align the UI wire frame with the event which will be triggered by user interaction

so here what i have got now

<img src="/assets/images/2024-1-11-event-modelling/Untitled%201.png" style="padding:10px"/>

now add the blue sticky notes for the commands which are needed to be executed in order to trigger the events, commands generally act as inputs from the user which change the state of the system

now here is what i have:

![Untitled](/assets/images/2024-1-11-event-modelling/Untitled%202.png)

and now also include green sticky notes, which are generally used to display the state of the system you can also use gears or other diagram to represent work done by the API used by our app, here i have represented it as a cloud as a process and here is my final take

![Untitled](/assets/images/2024-1-11-event-modelling/Untitled%203.png)

to know more about event modelling see: [https://eventmodeling.org/posts/what-is-event-modeling/](https://eventmodeling.org/posts/what-is-event-modeling/)

**why we need to use event modelling?**

i feel like event modelling helps us understand the overall working of the system better

the idea can be communicated more effectively to the non technical people like UI\UX designers and more people can contribute actively to the designing and features of the system

event modelling make building CQRS based systems easier as there is a clear separation between the query an view in the system

**What is CQRS?**

CQRS stands for Command Query Responsibility Segregation. It is a design pattern that separates the read model from the write model. This means using one model for querying data and a separate model for updating data (including creates, updates, and deletes).

**When should we use CQRS?**

CQRS is generally used when there is a nonuniform distribution between queries to the database and updates to the database. When we have a single model for basic CRUD (Create, Read, Update, Delete) operations, scaling is not very efficient. Having two different models helps us scale the query model and update model independently, which makes our application more efficient. Proper scaling can even be done if we use different databases for reads and updates, but we need to make sure that they are in sync.

The CQRS model is also used when the business logic becomes more complex for basic CRUD operations.

**Things to keep in mind before implementing CQRS:**

Implementing CQRS can get complex, and if we are using separate databases for reads and updates, we need to maintain consistency between the databases. It is preferred not to use CQRS when the business logic is simple and simple CRUD models do the job.

sources:

[https://eventmodeling.org/posts/what-is-event-modeling/](https://eventmodeling.org/posts/what-is-event-modeling/)

[https://learn.microsoft.com/en-us/azure/architecture/patterns/cqrs](https://learn.microsoft.com/en-us/azure/architecture/patterns/cqrs)

[https://martinfowler.com/bliki/CQRS.html](https://martinfowler.com/bliki/CQRS.html)
