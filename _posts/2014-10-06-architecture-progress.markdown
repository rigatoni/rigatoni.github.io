---
layout:     post
title:      Developing the architecture and preparing for the beginning of the iterations
date:       2014-10-06
summary:    With a successful proof of concept and the team scheduled to begin iterating on the code soon, we're getting the architectural details down on paper to be prepared for next week.
---

On Thursday, October 2nd, we had a successful meeting with Cissi, the project sponsor, to talk about project details and implementations. First we covered the notion of storing user projects persistently on our server, tied to some sort of user account - something Cissi has been concerned about due to the security implications. She sounded concerned, but told us that as long as we are diligent about getting the code audited and telling users not to upload confidential data, it should be alright.

We talked over licensing details for the project (since last year's project, built for Eclipse RCP, used an Eclipse license), and decided that the MIT license will be the best setup for us to use. We're working on a formal document breaking down the usage of the MIT license and why we chose it.

Kristen successfully demoed the project architecture as a proof of concept to Cissi and the other group members. Using a Node.js web layer, she was able to get user input as raw text, pass it through a TCP connection, and send it to a simple Python script, which diagrammed it as a sentence tree using one of the premade NLTK functions, sending back the results as JSON data to the web layer. This proved that we didn't need to limit ourselves to a Python framework for the web layer, allowing Peter and Kristen, who have plenty of experience with Node and other Javascript libraries, to avoid needing the extra ramp-up time. It also allows us to abstract away the analysis into a set of scripts with a common text-input->JSON-output interface. It even allows the project to support libraries written in languages other than Python, if that were to be brought into scope later in the project. Cissi did tell us that she preferred we work primarily in Python for the analysis scripts, so that others who work on the project in the future would have an easier time digesting the codebase.

We also had some discussion about preliminary user interface mockups (wireframes) for the import/corpus selection interface. The feedback there will help us as we build the user experience for our application.

One area of concern that has come up with our architecture is the issue of concurrency. Since this application is partially intended to be used in a classroom setting, it's important that the analysis tasks (some of which can take a significant amount of time depending on the text length) are managed in a way that prevents everyone from being slowed down waiting for input. We discussed some methods for mitigating this risk, including a queuing system, breaking down the tasks with MapReduce, spinning up extra copies of a script to finish concurrent tasks faster, and caching results from scripts. The team is still thinking about the best way to tackle this issue.

For this week, our plan is to patch up the project website with some updated documentation information and to work on the project architecture document in preparation for iteration one.