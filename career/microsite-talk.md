---
layout: mylayout.njk
title: Microsite Talk
---

# From Legacy to Modern: Our Experience Migrating a Complex Application with Microfrontends

## Abstract

Have you ever felt stuck with a legacy frontend, knowing
that an update is long overdue, but unsure how to tackle the daunting task? You're
not alone. Join me as I share our team's journey from AngularJS to React, and how we leveraged
microfrontends to bring modernity and scalability to our application.

In this case study, I'll reveal how we avoided a full rewrite of our application,
and succeeded in migrating users to a new frontend over time. You'll discover strategies
for breaking up large frontend applications into smaller, independently deployable pieces.

Other takeaways from this talk include:

* Real-world use case for microfrontends
* Using a monorepo to manage multiple applications with shared components
* Versioning and CI/CD techniques for frontend applications using GitHub Actions

This will be an excellent opportunity to learn from a real-world use case of migrating
to a modern frontend using microfrontends.

## I. Introduction

- Brief overview of the legacy frontend framework (AngularJS) and its limitations
  - Describe when AngularJS broke off and became Angular, put it in context of other things happening at that time
    - Docker, .NET Core, React adoption, etc.
    - Subtly make the case that this led to the rise of React and fall of Angular
  - Ask the audience who in the room wasn't a developer at this time
    - Just for my own curiosity
  - Ask audience if anyone is still maintaining an AngularJS codebase today
- Explanation of why migrating to React was necessary
  - Describe security releases that have hanppened since Angular was released
- Thesis statement: "In this talk, I'll share our journey from AngularJS to React,
highlighting the challenges we faced and the innovative solution we implemented
using microfrontends."

### Extra Notes
- Please interrupt and ask questions. I’m sharing my experience and want to hear yours. That’s what motivated me to give this talk
- Bring stickers for people to grab after with questions
- 2016
- Anyone developing in 2016?
- Anyone remember angular js?
- Still using angular js?
- I had an angular js and browserify pipe line that was sweet
- Show deprecation of angular along with other tech news in 2016

- Who has found themselves in this situation where you perhaps need to rewrite to get off of an old or unsupported platform?
- Not everything may be applicable, but I hope this talk inspires you or gives you ideas

## II. The Problem

- Cannot continue to maintain and develop on AngularJS
  - No new features. Limited security updates
  - Supporting libraries are unmaintained and even being pulled from GitHub, Bower, or NPM
    - Double check that for examples
  - Leads to low developer moral, which leads to worse user experience and inferior product
    - Maybe feature my tweet, or a headline of Poor DX leads to poor UX
- Two options
  - Full rewrite
    - Could take years
    - Would have to stop or drastically limit the amount of new development on the AngularJS app
      - Means not keeping current clients happy
    - Would be difficult to get feedback from users
      - Core tenet of our Agile practice
      - Would have to supplement with demos, which aren't very good
  - New app on a new domain
    - I've seen this strategy be successful for other companies
    - Not an option for us as we have multiple clients tied in on that domain via IT support, and integrations with EMR systems
  - Curious if others have been in a similiar position

## III. Our Solution: Microfrontends

- Introduction to microfrontends idea
  - Is sometimes referred to as an idea for mixing different frameworks in the same "app"
  - This is probably a bad idea and not what we did
- Show an animation of one large AngularJS app being broken into multiple smaller apps on the same domain
  - The old app becomes "/classic"
  - Allows us to easily shuttle users between these new apps as they are ready
- Other benefits
  - Smaller bundle size per app
  - Greater ability to section off users and charge per domain/app. Makes our product offering stronger
  - Easier deploys
- Other points I will hit in this talk
  - Code organization (monorepo, Nx, react-router)
  - Infrastructure
    - S3, Cloudfront, terraform

## IV. Details

- High level architecture
- Cloudfront, S3 settup
- Code organization detail
  - Generating changesets for changes to apps
  - NX for code organization
  - React router, MUI are core deps
  - Pros and cons of a monorepo vs multiple repos owned by different teams
  - Our shared libraries are not published as npm packages, but in a bigger team, this may be preferrable
- Lessons Learned

## V. Conclusion

* Recap of the key takeaways from our migration journey
* Final thoughts on the benefits and potential drawbacks of using microfrontends in
complex application migrations
