---
layout:     post
title:      Making decisions about requirements and architecture
date:       2014-10-02
summary:    Our planning continues with more details being worked into the project's design
---

Last week, we announced the decision to move to a web-based framework, which would allow us to continue developing the Linguine project while avoiding the limitations and lack of domain knowledge that existed in the Eclipse RCP project that came before us. Over the last week and a half, we have continued filling out the documentation to describe exactly what our project will entail. The more complete this documentation is at the start, the easier the workload will be once we begin coding.

Our current schedule with adjustments has us kicking off our first iteration of code on October 9th. We'll complete three iterations in time to begin user testing.

Our requirements document has been filled out with our initial in-scope use cases and their workflows. This includes importing text files, tweets, text from a predefined corpus, cleaning up the text, running analysis on the text, and importing and exporting a session's results for a user.

The architecture work is continuing to develop. While originally we converged on Django as a Python-based web framework solution, we were concerned that it may be too well-defined and might not be able to fit all of our use cases easily. Also, none of the group members had experience with it, and we don't want to jump into a new library unless we absolutely have to.

Our alternative solution involves abstracting out the communication between the web front-end and the processing back-end as much as possible, creating two layers which don't couple too closely. This approach would allow the processing back-end to run any code, not just Python - as long as the text data was being passed in and JSON or otherwise understandable data was being passed to the front-end, any language library could be utilized. Kristen has developed a proof of concept app for this architecture, which will be demoed at today's sponsor meeting.