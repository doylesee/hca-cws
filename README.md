## Project Overview
<pre>
<b>Project:</b>  HCA Careers
<b>Role:</b>     Lead UI Developer & System Architect
<b>Tools:</b>    InVision, Liquid, HTML5, CSS3, JS/jQuery, Bootstrap
          JSON, ATS Integrations, LocalStorage, Google APIs
</pre>
&nbsp;<strong><a href="https://careers.hcahealthcare.com/" rel="noopener noreferrer">View project</a></strong>

<p><a href="https://careers.hcahealthcare.com/" rel="noopener noreferrer"><img src="https://doylesee.github.io/hca-cws/thumbnail.jpg" /></a></p>
<br />

## The Challenge
HCA Healthcare required a complete overhaul of their talent acquisition portal. The core objective was to consolidate an immense network of independent medical facilities and regional locations into a single, unified enterprise career web platform. This presented massive, competing technical challenges:

**Multi-Tenant Brand Consistency vs Core Layout Control:**<br />
The platform had to support distinct branding profiles, specialized layout variations, and completely independent web properties for sister brands, and a specialized Career Events portal. Each required unique navigation architectures, individual logos, and custom data schemas while sharing a localized base layout engine.

**Severe CMS Restrictions**<br />
The underlying vendor platform restricted content administrators to a single WYSIWYG text field per page layout. Non-technical HR teams needed a way to easily build multi-tiered, component-heavy pages without writing HTML.

**Design Usability & Accessibility Gaps**<br />
The client’s creative marketing agency delivered beautiful highly customized InVision mockups, but it also introduced several real-world usability flaws and Web Content Accessibility Guidelines (WCAG) compliance issues.

**Hyper-Complex Business Logic**<br />
The front-end needed to handle enterprise-level functional parameters natively, ranging from custom multi-conditional Application Tracking System (ATS) workflows to real-time asynchronous API content parsing.

<br />

## Core Objectives
🟠 **Unified Enterprise Governance**<br />
Build a single global theme framework using specialized tag-detection logic to render custom page types (Job Families, Facilities, Locations, and Campaigns).

🟠 **The "Page Stacks" Engine**<br />
Transform a single restrictive text field into a modular layout engine featuring over 15 distinct components (banner carousels, accordion FAQs, multi-column cards).

🟠 **Technical Quality Advocacy**<br />
Perform front-end audits to correct structural semantic issues introduced by the third-party agency.

🟠 **State Management & Data Persistence**<br />
Deploy client-side scripting and cross-domain tracking to persist user searches, bookmarks, and targeted media delivery.

🟠 **Scalable Theme Inheritance Matrix:**<br />
Engineer a centralized parent theme to run all domains simultaneously, eliminating code drift, preventing human omission errors during manual deployment cycles, and easing systemic architecture updates.

🟠 **Component-Driven A/B Performance Testing:**<br />
Implement structural conditional routing rules within the Job Detail template files to automatically set layouts based on the listing's category, enabling precise conversion performance audits.

🟠 **Post-Launch Client Enablement:**<br />
Conduct live, hands-on administrative training workshops and author comprehensive technical documentation to fully transition content ownership to non-technical HR teams.

<br />

## My Approach & Implementation
### 1. Phased Delivery & Client Advisory
This project was executed across two distinct phases. To facilitate HCA’s rapid departure from their legacy vendor, I initially designed and engineered an accelerated, stripped-back consolidated proof of concept. The client was incredibly impressed by the rapid turnaround and strategic problem-solving, with internal stakeholders noting that my ability to continuously say "Yes" to highly complex architectural requests kept the enterprise launch on schedule.

During the full scale-up, I performed a rigorous accessibility and user-experience audit on the InVision design deliverables. I identified and aggressively flagged systemic flaws. For example, the design agency attempted to enforce standard HTML `<button>` elements utilizing complex JavaScript click actions for basic page linking, rather than semantic anchor tags (`<a>`). I advocated directly for the non-technical administration team, demonstrating that native `<a>` elements seamlessly integrate with standard WYSIWYG editors, reducing any friction.

Furthermore, when the agency insisted on locking button text containers to absolute lengths, I fought for fluid design adaptability to protect the non-technical administration team from broken text layouts when utilizing longer localized phrases. While the client initially deferred to their creative agency, an independent post-launch quality audit verified all of my initial warnings, prompting immediate structural remediations that perfectly matched my original recommendations.

### 2. Engineering the "Page Stacks" Component Architecture
To completely bypass the structural limits of a single-field WYSIWYG editor, I designed a server-side parsing architecture using Liquid Markup. I, along with the stakeholders and their design agency created a system called Page Stacks, which are completely separated content components managed cleanly via tag structures and centralized config templates.

Instead of allowing raw text dumps, my layout layer intercepts page permalinks to automatically construct dynamic component tag loops (such as `{{ page_permalink }}-stack`). The code isolates page logic via conditional checkpoints. As an example, If the system catches the pages-our-job-families block, it avoids layout blocks entirely and instead kicks off an automated multi-column element loop.

This architecture also programmatically transforms standard job search routing parameters into active client-side JSON output.

### 3. Asynchronous APIs & Client-Side Engineering
To turn static layout files into an interactive web application, I integrated several high-performance scripts directly into the template loops:

**Centralized Parent Theme Architecture:**<br />
To run the universal site alongside the separate specialized brand portals, I developed a master theme. Instead of copying source files across multiple platforms, which introduces human error and code omissions, updates were written once to this theme and re-applied universally. This guaranteed absolute functional consistency and seamless cross-site interactions.

**Dynamic Header/Footer:**<br />
Because a master theme forces global header and footer structures, I solved this problem by coding a hook. The theme intercepts individual site IDs and dynamically reads separate, tagged content pages containing localized navigation managed by non-technical HR teams. This gave them full control over separate site layouts and deep linking hierarchies without touching core template files.

**Geo API Integrations:**<br />
I integrated Google Maps and Google Locations APIs into the theme. This powered intelligent location autocomple, radius search functionality, and custom map pinning directly across individual facility pages and Job Detail pages.

**Asynchronous A/B Experimentation:**<br />
To optimize conversion rates on the Job Detail pages, I built a server-side template routing switch. The logic evaluates the specific job category parameter of the posting: if the category matches the target test criteria, the engine renders a separatae layout; else, it defaults to the standard layout. This provided a clean, database-free testing framework.

**Real-Time Data Output**<br />
To display exact, live job openings metrics on top-level category cards without page lag, I wrote asynchronous jQuery hooks inside the Liquid layout engine. The system fires off JSON requests against the generated page-specific paths, extracts the total dataset entries array, and cleanly overwrites default container flags with live numbers.

**Automated Data Separation**<br />
I built a parsing script that uses advanced string manipulation filters (like `split: '---'` and remove: `<p class="job-list">`) to read text arrays, extract localized endpoints, and seamlessly output faceted job modules right within the template.

**Component-Driven Layouts & Overrides**<br />
I implemented robust conditional parameters that evaluate asset sizing metrics (`page.images.size > 2`). This logic shifts image grids into layered visual configurations, swaps iframe elements into fully fluid responsive wrappers (`class="embed-responsive-item"`), appends strict screen-reader navigation hooks (`class="sr-only sr-only-focusable"`), and maps proximity event listings down from separate regional nodes via targeted parameters.

### 4. Client-Side State Engines & Data Persistence
To handle enterprise-grade personalization without a state-driven database, I designed client-side storage frameworks powered by modern browser localStorage and background asynchronous UI reconciliation ($.get):

**Bi-Directional Saved Job Workflows (detectsavedjob / savejob):**<br />
I wrote a tracking module that monitors target arrays. When a user interacts with a bookmark trigger, the script saves product parameters, updates site-wide query pathways dynamically, pushes states without triggering hard page reloads using HTML5 history loops (window.history.pushState), and performs smooth AJAX layout updates behind an alert animation wrapper.

**Facility Clustering States (detectsavedfacility / savefacility):**<br />
Mirroring the save job fucntionality, the platform utilizes custom browser strings inside template execution loops to check if an active medical facility page is bookmarked. The architecture removes UI clutter by instantly hiding unneeded buttons during initial page evaluation, providing candidates with a unified tracking experience.

### 5. Automated Performance Optimization & Auditing
With hundreds of pages densely packed with heavy corporate media assets, web optimization was critical. I built asset performance rules into the core layout loop that targeted text and image sections. The code dynamically audited elements and appended native loading="lazy" tags to images, forcing the browser to defer downloading below-the-fold graphics until scrolled into view.

I rigorously monitored performance metrics using Google Lighthouse. My semantic, modular frontend code achieved exceptional raw performance scores between 85 and 95, ensuring a highly performant and stable foundation despite heavy tracking scripts and external CMS application layers.

<br />

## Results & Impact
✅ **Massive Enterprise Consolidation**<br />
Successfully migrated a sprawling digital footprint of independent healthcare facility websites into a single, high-performance, universally maintainable web framework.

✅ **Empowered Non-Technical Operations**<br />
Created a robust, modular "Page Stack" page-builder tool and successfully transitioned platform ownership to HCA’s HR teams through live training workshops and custom-authored Content Management Documentation. This comprehensive handover strategy saved hundreds of annual developer support hours by enabling non-technical staff to easily manage custom pages, complex layouts, emergency alerts, and event systems completely independently.

✅ **Validated Technical Strategy**<br />
Championed modern accessibility and semantic engineering guidelines. My technical foresight was verified by post-launch quality audits, establishing my reputation as an authoritative guide on high-fidelity, web-accessible development.

✅ **Platform Processing Stability**<br />
Successfully executed hyper-complex multi-conditional checkout logic—handling seamless transitions between native career registration prompts, complex iCIMS BID-mapping URL reconstructions, and standard automated Talemetry application workflows without data dropping.

<br /><strong><a href="https://careers.hcahealthcare.com/" rel="noopener noreferrer">View project</a></strong>
