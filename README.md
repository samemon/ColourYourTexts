# HackPrinceton 18
Our project for HackPrinceton 2018. Check out the video for the project here: https://devpost.com/software/colour-your-texts

## Inspiration
We all use messaging apps like Facebook Messenger, WhatsApp, VChat, etc. While some of us like to stay on the main topic of conversation, we often derail from the topic like one of our old professors in the classroom. We also like to juggle multiple conversations at the same time to show off our stamina to talk. With the introduction of new topics into text conversations, it becomes hard to keep track of them. This is where our app comes in. 

"Color your texts" helps you to keep track of the different conversations in a chat. With the recent advancements in Natural Language Processing and Artificial Intelligence, learning semantic representations of language is more than possible. This is what inspired us to create "Color your texts".

## What it does
Color your texts is a chrome extension for the Facebook Messenger app currently. Potentially it can be extended to any other messaging apps, to forums like Reddit and other topic-based websites. As the live conversation goes on, the app assigns a topic to a particular text. It does this by taking into a context window of 3 messages currently, where the previous two and the current message are considered for the topic selection. We decided to represent every topic by a particular color, and so the live conversation text is assigned a topic live. 

## How we built it
We start by scraping user's messenger chat to extract the text. We adopt an unsupervised statistical modeling technique called Latent Dirichlet Allocation to do topic modeling on the texts.  As a preprocessing step, we use word-embeddings to extract and cluster semantically similar words. We keep track of all the topics in a conversation and assess the topic head of a given text. Each topic is represented by a distribution over the words spanned by that topic. The criteria we adopt for creating a new topic head is that of the minimum Jenson-Shannon divergence of the word distribution of the given text being larger than a threshold to the already defined topics' word distribution. 

We build the front end using javascript, HTML, and CSS. All the processing for the app is done on the client side. 
Privacy is also not a concern since all the computation is being done on the client side in the browser. 

## Challenges we ran into
We arrived at Princeton on Saturday morning at 12 am and started working on the project on Saturday morning at noon. Hacking our way through the project in the least amount of time was challenging. 

Figuring out the right parameters for LDA topic modeling also posed a challenge. We experimentally decided (1) a good threshold on the probability distribution divergences to create a new topic, (2) the context history to use for a given text. 

## Accomplishments that we're proud of
We were able to divide the tasks efficiently among the team members. With little to no sleep, all the team members were able to pull of a functioning prototype of the idea. 

## What we learned
We learned about the Latent Dirichlet Allocation (LDA) statistical modeling. We went through a couple of papers on topic modeling and discovered that LDA does a very good job on modeling topics from short-texts, shown over tweets. We carried this idea forward to text-messaging. 

## What's next for Color your texts
We will further try to improve the modeling capacity of our system. Incorporate the feature into other text apps and also other chat forums, or pages like fan-fictions. 
