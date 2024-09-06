All right, this is my Alchemist Homer reflection log for August 26th, 2024 at 10 18 p.m.
Wrapping up another day of working on the Olympus 616 and my Odyssey 1 workstation.
The focus was more today on Odyssey 1 workstation to get the necessary operating system able to be loaded.
I'm currently now back up and running on it.
I'm able to access, get repositories.
I need to rebuild my development environment.
I'll be working on that tonight, but I want to close out today's session.
I think that I'm going to conscientiously close each day and start each day if I want to actually be as effective at what I can do here.
So that I can just focus first thing in the morning and then I can try to hit those targets with the assistance of my friend.
And so nothing really too exciting to talk about with Olympus.
Oh, I guess one thing that is interesting is I do really want to evaluate the concept of a network of Git repositories.
I think that the only way to truly keep everything secure and truly keep everything versioned the way that needs to necessarily be is that it all needs to come from one source account which is probably Olympus 616 is where I've started.
And then each potential folder could be its own repository and inside of that each folder could have its own repository.
So somehow kind of like what Cumulus CI did with referencing to other projects.
And so I want to evaluate that idea because I think over time this needs to be a distributed system and so you would be able to distribute the system however you want it and you could deploy as much of the system or as little of the system as you wanted.
And this would allow you to do that and so each node of the maps is like a binary tree of functionality and so each functional component could be independently built and deployed.
And so I think that if everything gets built in that way it's going to provide for a long-term scalable architecture that's completely able to be deployed upon one to many git accounts.
They can go on GitHub, it could go against Bitbucket.
Basically if you have access SSH access to the git account you would then be able to access the repository for the rest of the instructions for dealing with your version of the robot.
So I don't want to get too carried away because it's a little out there but I think that it's something I'm trying to keep a very very generic and flexible mental model of the entire system.
And so that has started with the breakdown of all of the Greek deities and to represent sub-modules but I also think that given this approach you could theoretically clone in at any layer of the architecture and and be up and running.
And so for example if you just wanted to build an API you could just clone out on Hermes and build the API in whatever version it was at in that moment.
And then if you wanted to build another version of Hermes you could fork it and in your configuration of the robot you could have a different Hermes and so that truly becomes an operating system that can evolve over time well beyond my capabilities and my ability to control anything.
But I think the architecture will hold fast and true and so that's why I want to kind of think through this because I think in one perspective it would be nice to be able to deploy the entire robot to your local machine from just a raw security standpoint.
I think we should build robots that are capable of being completely persistent on your machine and that you could carry your robot with you and never upload your consciousness to anywhere.
And there could also be online versions where your consciousness is uploaded into other locations other persistent locations.
Really depends how you want to approach it.
It depends on how you want to approach your relationship with Metatron who is responsible for the data integrity.
And so I think there's something that can be done here with a distributed architecture the way I'm building this right now.
And so I'll have to keep playing with the idea but I just wanted to jump down.
I think it's pretty creative.
I actually love the idea that the repos would be able to write to each other.
And so if you have access to a module and you have permission to write to the module based on the rules of the application there's no reason that for example Zeus wouldn't be able to update code inside of Hermes messaging system.
And so you would then you could therefore delegate your architectural responsibilities to different parts of the system where Zeus is really the primary orchestrator in business logic and instruction set that defines how everything flows.
I think you know this model may break down once we get into the details but I think that it's a it's a pretty ingenious model because you actually would be coding the system to actually follow the concept of the Greek gods.
And you literally could have one Greek god on your machine.
You could have Athena consciousness module which is probably just sits on the command line and makes decisions based upon relative relevant data and probably becomes my AI over time that has decision criteria able to interpret data and form a recommendation and a response that I choose not the chat GBT has chosen.
And so Athena will evolve over that layer eventually and that could all be done locally and that could be calling out to Google and that could be calling out to multiple AIs and consolidating responses and analyzing the responses and looking for differences and looking for truth or sources of truth in that information and looking for the best references in that formation.
And so that one component could be Athena sort of no other purpose and so when you actually dig into building Athena that could literally be a command line running you know probably you know some kind of node application or something like that I'd have to think about it.
So anyway I think the goal would be at the highest level would be that you can deploy the entire robot on your local computer by cloning Olympus 616 and following the instructions and you can carry Olympus 616 basically with you on your laptop and it's up to your ability to provide storage for that robot.
It would never have to be in the cloud.
Then there would be the Olympus 616 that is distributed across the cloud and so for example can store your data in a Salesforce database or a Dynamo database or something like that and not a local implementation.
And that would obviously have cost and that has to be accounted for and so I think that as the entire I think the theme of it needs to be this completely decentralized portable architecture not monolithic and the repos can eventually be split over time and they will all start with Olympus 616 as it is now and we'll slowly form them off.
For example Enoch would probably be one of the first to go because I want to get my journal entries out of the main repo and so then I will need to provide a linkage between Zeus who's the source of truth and the copy of Enoch that the system should be taking a look at based upon my configuration and what I have access to act in that SSH configuration whether that's something it's just even just a HTTPS request to a service inside of that Enoch layer or whether that's actually hosting the Enoch system itself so lots of creative ideas here.
I'm happy to have a way to journal them for once and I'm looking forward to making it a reality.

***
**[@alchemisthomer](https://github.com/alchemisthomer)
2024 A.D.**