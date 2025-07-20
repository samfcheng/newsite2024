<script>
  import { marked } from 'marked'
  import Metatags from '$lib/components/Metatags.svelte';
  import "$lib/styles/styles.scss";
  import "$lib/styles/case-study.scss";

  const text = `
# Classmate Primary Flow Rework
<span class="subtitle">June - July 2025 | [Classmate.app](www.classmate.app)</span>

<img src="/projects/classmate/mid-flow.png" alt="Classmate Midflow" class="header-image"/>

<div class="highlight-section">
  <h2 class="highlight-title">Overview</h2>

  <div class="highlight-content">
    <h3>Role</h3>
    <p class="right">
      <strong>Product Designer</strong><br/>
      Lead UI & UX Design, Research, Prototyping, User Testing, and Branding<br/><br/>
      <strong>Developer</strong><br/>
      Lead Frontend Development, Backend Development, and Deployment
    </p>
    <h3>Platform</h3>
    <p class="right"><strong>Web</strong></p>
    <h3>Timeline</h3>
    <p class="right"><strong>June - July 2025</strong></p>
    <h3>Status</h3>
    <p class="right"><strong>Completed</strong></p>
    <h3>Overview</h3>
    <p class="right">Classmate is a project that I’ve worked on over the past year. My goal has been constant improvement, working to help students get free, instant, and personalized writing feedback. <br/><br/> I’ve learned a lot throughout the process of designing and developing the app, but even more through implementation. There have been so many surprises and improvements that have come out of talking to and learning from users.</p>
  </div>
</div>

## What is Classmate?
Classmate is a web app that provides free, instant, and personalized writing feedback. It’s designed to help students improve their writing skills by providing them with AI-generated feedback on their essays, papers, and other written assignments. The app is built with a focus on user experience, making it easy for students to get the help they need without any barriers. Because of the focus on user experience, we're always looking for ways to improve Classmate and make it a better experience and tool for users.

![Classmate Feedback](/projects/classmate/feedback.png)

## The Challenge
One of the things that surprised us the most was when we looked at the data and saw dozens of new user signups, but very few users creating and getting feedback on their writing. During this rework, I wanted to explore:
- Why, when, and how are users getting stuck?
- What leads users to create an account, but stop there?
- How might we make the onboarding process more smooth?
- How might we make the process of submitting writing for feedback more understandable and smooth for both new and returning users?

## The Process
During this rework, I tried to be especially detailed and intentional with each of the choices. The process involved going through several key steps.

### User testing
I had had the idea to do a rework in mind for a while, but I never knew if it was something that was actually necessary. Before starting designing the rework, I wanted to understand how users felt about the current system and flow, and how it could be better improved.

For a while, we’ve had this plugin on the site that records user experience interactions. My first step in the process was to go through these recordings and make observations. There were quite a few aspects that surprised me, and a few easy fixes as well, like changing the wording on the sign-in button and removing the link to sign in in the navbar.

![notes](/projects/classmate/dropoff-notes.png)

Making observations of past user behavior was extremely helpful, so I wanted to continue to talk to users and decided to run a series of user interviews.

![post-its](/projects/classmate/user-testing-postits.png)

These user interviews were extremely helpful, and validated that it would be useful to redesign the onboarding and feedback flow.

### Design Process
There were some main challenges that I observed and heard from users:
- Struggles with logging in and figuring out how to make an account
- Difficulty managing documents and creating new ones
- Being confused with how to get feedback, and misunderstanding the inputs

One of the main focuses when I went into redesigning the flow was splitting it up. Previously, everything was all on one page, which led to a bit of information overload. In user interviews, I explored the idea of expanding the flow to take up multiple screens and pages, and got positive reception, although users stressed the importance of the flow still being quick and easy to go through.

Additionally, one of the primary drivers for the redesign was that I observed many users creating accounts, but getting stuck at the blank screen after. With this redesign, I wanted to ensure that it would be easier for users to explore and demo Classmate.

### Implementation
![redesign](/projects/classmate/figma-redesign.png)

After ideation and concept sketching, to implement the design changes, I started with a rough wireframe that eventually transitioned into the full high fidelity prototype that you can see above. Before implementing, I hopped on another call with some users to get feedback, and they let me know that it looked great, which told me that I was good to continue with implementation.

Using the Figma design as a reference, I coded the design into the current app using Svelte and SASS, a CSS post processor. As I’ve been going through this design project and learning more, I’ve been adapting my coding style. With this new update, I worked to make my code extremely modular - creating reusable components and systems that were future proof and effective.

## The Solution
The changes revolved around creating two new pages to replace the previous feedback page, and building in many quality of life and small user experience improvements.

### Your Docs Page
Previously, a user’s past feedback documents were stored at the bottom of the page to get new feedback, and the section functioned kind of like an afterthought.

![old page](/projects/classmate/previous-feedback-page.png)

For this redesign, the new page spins off that section into an entirely separate page, which users are automatically redirected to upon logging in. Below, you can see an image of what the new page looks like to a new user.

![new page](/projects/classmate/new-docs-page.png)

In this new page, there are several key improvements:
- Each previous piece of writing shows up as a document, with a preview
- Tooltips are displayed to new users to explain the primary actions on the page
- Each account for a new user is auto filled with a demo document that users can use to check out or demo Classmate, without having to find a piece of writing to submit themselves
- A large “Create New” button that directs users to the flow to get feedback on a new piece of writing

### New Feedback Flow

![old feedback flow](/projects/classmate/old-feedback-flow.png)

The old feedback flow, shown above, was a basic form-style section where users could submit their writing for feedback. The new flow, along with being much more purposeful, is designed to have more direction for the user.

![new feedback flow](/projects/classmate/new-feedback-start.png)

The new flow splits each of the sections on the previous form into its own screen, making it more scannable and understandable to go through the flow. As the user navigates through the flow, subtle animations show progression.

When I first described the flow to users, one of the things that they appreciated the most about the old flow was the ability to see a full picture of what was going on. They were worried that when splitting the flow up into individual screens, you would lose the full picture. Because of this, I added progression to the sidebar, where users can see what screen they are on and what they have left to do, and can also navigate back to a previous screen.

![new feedback flow screen two](/projects/classmate/mid-flow.png)

This flow also implemented numerous quality of life improvements, like a “paste from clipboard” button and an indicator to show which option was "recommended" on selection menus.

The design is also future proof, leaving space for future features like the ability to upload a photo or screenshot of a rubric and the ability to have “advanced” feedback modes.

### Other Key Improvements
After developing the system for the tooltips on the new docs page, I implemented tooltips for new users on other pages as well to describe how to use the app most effectively. In addition to that, one of the largest changes was the new navbar system. Along with taking up less room, it’s more flexible and adaptable, and shows more information as well.

Through talking to users over the course of this project, I also learned about new features and changes that they’d like to see implemented. One of the largest changes in this category were the changes to overall feedback and how college essays are given feedback. For both, the models and prompts were significantly improved, and overall feedback is now given in sectioned bullet points as opposed to paragraph form, which makes the overall feedback significantly more understandable and readable.

## Results
The results of this redesign were immediately visible. We saw more users signing up and checking out Classmate, and positive feedback from users about how easy and understandable the new flow was to use. 

In addition to this, I’ve been able to make new connections with users who I talked to throughout this process, and Classmate will have more opportunities coming in the future because of the new and improved redesign.

This redesign has also prompted us to send out an email to all users, which we’re working on now, and are hoping to see some great results from that. This case study will be updated as I hear back from more users and get results.
  `
</script>

<Metatags title="Classmate"/>

<main class="page-main">
  <div class="page-content">
    {@html marked(text)}
  </div>
</main>