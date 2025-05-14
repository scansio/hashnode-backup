---
title: "My Outreachy Journey: Contributing to Servo and Learning Browser Internals"
seoTitle: "Exploring Servo: My Outreachy Contribution Story"
seoDescription: "A developer shares insights from their Outreachy experience, contributing to Servo, and deepening their understanding of browser internals"
datePublished: Wed May 14 2025 14:25:59 GMT+0000 (Coordinated Universal Time)
cuid: cmao19twf00030al826nw4bit
slug: my-outreachy-journey-contributing-to-servo-and-learning-browser-internals
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1747232594844/add4b44c-7c92-45a2-8f2a-9a6fda88bfcf.png
tags: rust, outreachy, intership, web-platform-test

---

When I first discovered Outreachy, I saw it as a door into the world of open source — not just to gain experience, but to build real software and grow with a community. I chose to apply to Servo because I wanted to better understand how browsers work and contribute to a project that's at the heart of the open web.

Over the course of the Outreachy contribution period, I dove deep into the Servo codebase. I explored:

* **Content Security Policy (CSP) handling**: I helped fix a bug where `<meta>` CSP tags would override headers — against spec. I updated `Document::set_csp_list` to correctly merge policies.
    
* **Input event lifecycle**: I implemented `beforeinput` event dispatching for `<input>` elements, following [UI Events spec](https://w3c.github.io/uievents/#event-type-beforeinput). This taught me how browser event dispatch works under the hood.
    
* **HTML parser quirks**: I updated the HTML parser config to respect quirks mode, scripting flags, and `iframe_srcdoc` handling, aligning more closely with spec-defined behaviors.
    
* **Tests and debugging**: I wrote Web Platform Tests (WPTs), fixed timing issues, and learned to debug remote script loading using Servo’s devtools support.
    

Each bug led to new understanding — not just of Rust and the Servo codebase, but of how real-world browser engines function.

Although I wasn’t selected for the final internship, I gained far more than I expected: deep technical learning, confidence in navigating a large codebase, and mentorship from contributors like [@jdm](https://github.com/jdm), who guided and reviewed patiently.

This isn't the end of my journey with Servo. I’ll continue contributing and applying what I’ve learned, because this work excites me and helps me grow as a developer.

If you're thinking about contributing to Servo or applying to Outreachy: do it. The learning is intense, the community is kind, and the skills you build are real.