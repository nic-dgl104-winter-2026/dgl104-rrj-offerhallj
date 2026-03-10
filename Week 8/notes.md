# Week 8
### Notes about this assignment:
**Starting Week 9, coding assignments each week should include references in their reflections.**
Make sure things are well organized: organized folder structure, headings and subheadings in the documents, etc.

TODO: Look up the community coding assignment.

## Functional User Requirements
When you want to develop an application, you need to understand the requirements of your users. Who are they? What do they need? What problem are you trying to solve?

Based on these questions, you develop a solution and determine your User Persona. 


## Video: Functional Requirements and User Stories
The first thing we tend to assess when critically examining an app is the inerface and the UX. But try to consider how these apps are working from a technical standpoint, as well.

As a developer, think about your programming knowledge when assessing apps.

### User Stories

User stories are a common tool employed in the design of user-facing systems.
User stories are written in natural language from the perspectie of the user. "As a user, I can ____."

These stories facilitate intra-team communication. They tend to be clearer and easier to understand than a wordy design document. 

However, they tend to lack implementation details. Sometimes, technical details considerations can be overlooked in the process of implementing features based on user stories.

User stories can be written with technical concerns in mind, but this can be less appealing to staakeholders who jsut want to understand the functionality of the app. Technical details often require many more user stories.

### Technical Design Document (TDD)
A TDD is a written artefact that addresses technical concerns in a design context.

The goal is to produce an unambiguous document detailing:
- Architecture
- Feature implementation
- Testing plan
- Performance criteria

These documents should maintain a high-level scope. This is intended as a guide, and is not the main source of truth.

Often, these documents are only relevant in the earliest stages of development. Once actual implementation happens and code is in place, that becomes the main source of truth.

There is no accepted standard for how this document should be constructed. Content, size, length, etc. may vary across uses.

### Functional Requirements
Functional requirements describe software feature on an input/output basis, similar to a function.

These requirements may be included in the TDD or a related document.

Typically, these requirements are derived from user stories or use cases.

We can use the input/output approach to develop clear specifications for our apps.

If our use story says "as a forum user, I can see posters' profile pictures," this might imply the following functional requirements:
- Update profile: enter required profile data (name, email) and option data (profile pic, address, website, etc.) -> return profile page with default content for incomplete data

There are a lot of functional requirements which may not be readily apparent from the story.
