---
title: You weren’t ready for Design systems
info: |
  And suddenly, Design systems emerged—promising innovation, collaboration, and a bridge between designers, developers, accessibility experts, and security specialists... the stakes for frontend delivery are huge.
  On a homogeneous full-stack JS/TS app, the technical challenge is relatively straightforward. With older backends boasting a solid API, a Backend for Frontend can do the trick, given a bit of sweat. But what about all the rest?
  Join us for insights from implementing a Design System architecture within an aging backend (18 years old, aged in Python casks) that wasn’t intended for a complete rewrite but still manages server-side view rendering (HTML) and frontend asset delivery—all without sacrificing developer experience!
  Integrating modern frontend tools—Vite.js, Stimulus, Storybook...—into an old Django setup: we’re closing that time loop and jumping on board! You weren’t ready for Design systems, but we made it happen anyway!
routerMode: hash
theme: the-unnamed
transition: slide-left
mdc: true
monaco: false
drawings:
  enable: false

layout: cover
background: https://images.pexels.com/photos/7586662/pexels-photo-7586662.jpeg?auto=compress&w=960&h=1080&dpr=1
---

# You weren’t ready for Design systems

Bringing a 20-years old platform to a new Era

---

[Back to the Future]

---

alwaysdata dashboard

---
layout: about-me
helloMsg: A Designer, A Developer, a Product Owner, and a DX Engineer meet at the bar... 
name: Mads
imageSrc: /m4dz.jpg
line1: Systemic Web Dino 🦖
line2: (Also, was optimised for Netscape 4)
social1: m4dz.net
social2: (<logos-linkedin-icon /> m4d-z)[https://www.linkedin.com/in/m4d-z/]
---

---
layout: section
cover:
---

# The Origins

---
class: tiles
---

# The Product Expectations

- Time to modernize the UI/UX
- A team of Engineers
- Only one Frontend Dev
- Not even a UI Kit

---
class: tiles
---

# The Legacy Codebase

- A Django (Python) ecosystem
- A multi-app system
- A Bootstrap-based frontend
- 18 years old codebase
- Some parts with APIs...
- ...but not everywhere

---

How it Works

```mermaid
request
django
render page
django compressor
webpack
linked resources
third-parties
```

---

# The Usual Suspects

- Django-compressor
- Webpack
- External assets
- Bloated styles
- Inline Scripts
- External scripts
- Data
- i18n

---
layout: section
cover:
---

# Objective: Moon

---

# A components-oriented Design

- Composable pages / views
- A nicely crafted architecture
- SOLID Design
- A living documentation
- A distributed core-assets

---

# A Ready-to-use ecosystem

- A library of components
- A system built for the platform
- A set of templates
- A simplified DevX

---

# A workflow for the team

- Works out-the-box
- ... even when boostrapping new views
- Batteries included
- ... with no need for supercharging
- Out-of-scope delivery
- ... but ready to handle their needs and requests

---
layout: center
---

# Let's frame it: [a Design System]{v.mark}

---
class: tiles
---

# Opinionated to avoid

- We'll stick with Django
- We won't migrate to a full API-first architecture
- We need to remove the Django-compressor dependency

---
layout: section
cover:
---

# Tech fondations

---

# The Challengers

- JinjaX
  ```
    
  ```
- Stimulus.js
  ```
    
  ```
- Vite
  ```
    
  ```

---

# The Supporting team

- Figma
  - Collect the legacy
  - Refine components
  - Manage Design Tokens
- Storybook
- Workflow

---

# The Unknowns

How to ...

- ... deal with configuration?
- ... properly architecture components?
- ... made Vite and Django interact?
- ... use the components [outside] of Django?
- ... package everything for production?

---

# The Final Countdown

It's gonna be progressive
not a Big Bang

---
layout: section
cover:
---

# When it all comes together

---

# I take a tour at supermarket

I don't know why but I have to started somewhere
so I started there.

- Creating a new ~~app~~ package for the components: `ui`
- Host
  - configurations
  - helpers
  - plugins
  - templates
  - components
  - assets
- No deps to other apps

---
layout: center
---

# Creating the Sandbox

A simple [demo app]{.v-mark} in the `ui` package

---

# Glueing the parts

- One app == One Workspace == One package
- Vite Custom Plugins
  1. Reading Django config from Vite
  2. Injecting all images as refs
  3. Producing a SVG sprite for icons
  4. Generating a `manifest.dev.json`
- Vite base-common config, ready to be extended by apps
  ```
  
  ```
- Django custom tag to load Vite produced assets
  ```
  
  ```

---

# Making it a bit Magical

- Caching the Django configuration for Vite
- Reading Django templates to extract Vite entrypoints
- Auto-importing components

---

# Enhancing the DevX

- Poetry: environment isolator
- Poe-the-Poet: tasks runner
- pnpm: workspaces wizard

---

# Migrating the Codebase

We don't want to break the system

1. Moving the base templates as commons
2. Replacing Django-compressor by our custom Vite tag in all pages' templates

## For each app

3. Configuring Vite
4. Extracting scripts, leaving data
   ```
    
   ```
5. Creating a cheap-feature-flag system
   ```jinja
    
   ```
   ```js
    
   ```

---

# Handling the Delivery

1. Building using Vite in each app
2. Collectic the statics with Django internals
3. Packing statics
4. Publishing them to a semver CDN

---

# One step at a time

- We move all the existing codebase to Vite
- We put-on the magic to make it compatible with the existing architecture
- We architectured the `ui` package to host components
- We built a simple component ready to be integrated

No Big Bang, just a discrete continuity
(pun intended)

---
layout: section
cover: 
---

# Documenting 'em all

---

# The Storybook Evidence

![](Storybook screenshot)

---

# Enabling the server mode

```
  
```

---

# The rendering part

- A simple Flask app
- Ready to render the JinjaX components
- Simple API to pass Storybook params
  ```
    
  ```

---

# Wrapping our head around

- Using a middleware for injection
- Auto-init Stimulus components context
  ```
    
  ```

---

# Like a 2025 app

- It's just building blocks
- All technologies were ready
- ... but not ready to work together
- We used [a lot]{.v-mark} of glue

---
layout: section
cover:
---

# Final words

---
layout: center
---

# A Complete Ecosystem

---
layout: center
---

# Thanks 🙇 !

---
layout: section
background: https://images.pexels.com/photos/97824/pexels-photo-97824.jpeg?auto=compress&w=1920&h=1080&dpr=1
---

# Questions
