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
To completely bypass the structural limits of a single-field WYSIWYG editor, I designed a server-side parsing architecture using Liquid Markup. I created a system called Page Stacks, which are completely separated content components managed cleanly via tag structures and centralized config templates.

Instead of allowing raw text dumps, my layout layer intercepts page permalinks to automatically construct dynamic component tag loops (such as `{{ page_permalink }}-stack`). The code processes these tags and maps them directly into custom layouts using specialized conditional checkpoints:

**Automated Content Separation**<br />
I wrote a parsing script using advanced string text filters (like `split: '---'` and remove: `<p class="job-list">`) to read simple text fields from the CMS, break them down at designated points, and output clean, faceted job lists on the fly.

**Smart Asset Overrides**<br />
I implemented strict parameters that evaluate file counts and types (`page.images.size > 2`). If a recruiter uploads multiple files, the code shifts image grids into layered layouts automatically, wraps text containers into fully fluid responsive wrappers (`class="embed-responsive-item"`), and appends accessibility hooks (`class="sr-only sr-only-focusable"`).

**Layout Swapping Loops**<br />
If the system catches a specific tag layout, like a job family block, it completely bypasses standard text layouts and initiates an automated multi-column element loop. This loop hooks into search variables to transform raw routing parameters into active client-side JSON channels.


### 3. Custom Enterprise Frontend Features
To turn static layout files into an interactive web application, I integrated several high-performance scripts directly into the template loops:

**Centralized Parent Theme:**<br />
To run the universal site alongside other separate specialized brand portals, I developed a master theme. Instead of copying source files across multiple platforms, which introduces human error and code omissions, updates were written once to this theme and re-applied universally. This guaranteed absolute functional consistency and seamless cross-site interactions.

**Dynamic Header/Footer:**<br />
Because a master theme forces global header and footer structures, I solved this problem by coding a hook. The theme intercepts individual site IDs and dynamically reads separate, tagged content pages containing localized navigation managed by non-technical HR teams. This gave them full control over separate site layouts and deep linking hierarchies without touching core template files.

**Google API Integrations:**<br />
I integrated Google Maps and Google Locations APIs into the theme. This powered intelligent location autocomple, radius search functionality, and custom map pinning directly across individual facility pages and Job Detail pages.

**Simple A/B Testing Logic::**<br />
To see which layouts performed better on Job Detail pages, I wrote a simple conditional switch. The logic evaluates the specific job category parameter of the posting: if the category matches the target test criteria, the engine renders a separatae layout; else, it defaults to the standard layout. This provided a clean, database-free testing framework.

**Real-Time Data Output**<br />
To display exact, live job openings metrics on top-level category cards without page lag, I wrote asynchronous jQuery hooks inside the Liquid layout engine. The system fires off JSON requests against the generated page-specific paths, extracts the total dataset entries array, and cleanly overwrites default container flags with live numbers.

### 4. Saving Jobs and Facilities Natively
Because we didn't have a database to handle logged-in user states, I built a custom system entirely on the front-end using the browser's localStorage and background jQuery ($.get) calls to manage the bookmarking features:

**Saved Jobs Workflow (detectsavedjob / savejob)**<br />
I wrote a tracking script that watches an array of bookmarked jobs. When a user saves a job, the script records the job's ID, updates the site-wide search path dynamically, and changes the browser URL smoothly without forcing a hard page reload using window.history.pushState. It then runs an asynchronous background call to update the job counts and lists behind a clean alert fade-in animation for accessibility.

**Saved Facilities Workflow (detectsavedfacility / savefacility)**<br />
Following a similar logic, the script checks if a candidate has bookmarked a specific medical facility while the page is loading. It instantly handles button visibility toggles (hiding the "Save" button and revealing the "Unsave" button by managing the d-none utility class), preventing the layout from flashing or looking cluttered to the user.

### 5. Quality Assurance, Accessibility, and Compatibility
Because a massive healthcare career network serves millions of diverse candidates, ensuring the platform was fully accessible and stable across all devices was a top priority:

**Rigorous Web Accessibility (WCAG) Checks**<br />
Working with the stakeholders, we built strict accessibility checks. I ensured all custom structural elements were semantically coded, includes screen-reader navigation hooks (`class="sr-only sr-only-focusable"`), and proper keyboard navigation capabilities to guarantee the site passed standard web accessibility audits.

**Fluid Responsive Infrastructure**<br />
I ensured every single one of the 15+ custom Page Stack components was fully mobile-responsive. Layout blocks dynamically adjusted content grids, image sections, and embedded video wrappers (`class="embed-responsive-item"`) seamlessly across all mobile devices, tablets, and desktop screen sizes.

**Cross-Browser Compatibility**<br />
I extensively tested and optimized the code to ensure flawless rendering and functional stability across all modern web browsers. This guaranteed that interactive elements, like the localized Google Maps pins and the client-side localStorage bookmarking scripts behaved consistently no matter what browser a candidate used.

<br />

## Results & Impact
✅ **Successful Enterprise Migration**<br />
Consolidated a massive network of separate healthcare facility sites into a single, high-performance web platform that is easy to maintain.

✅ **Centralized Design & Maintenance:**<br />
Developed a master theme system that eliminated the need to duplicate code across individual sites. By controlling global elements from a central theme, design updates were pushed across multiple separate sites simultaneously, cutting down hours of maintenance and preventing manual code omission errors entirely.

✅ **Empowered Non-Technical Operations**<br />
Created a robust, modular "Page Stack" page-builder tool and successfully transitioned platform ownership to HCA’s HR teams through live training workshops and custom-authored Content Management Documentation. This comprehensive handover strategy saved hundreds of annual developer support hours by enabling non-technical staff to easily manage custom pages, complex layouts, emergency alerts, and event systems completely independently.

✅ **Validated Technical Strategy**<br />
Championed modern accessibility and semantic engineering guidelines. My technical foresight was verified by post-launch quality audits, establishing my reputation as an authoritative guide on high-fidelity, web-accessible development.

✅ **Smooth Application Workflows**<br />
Successfully executed complex multi-conditional logic, handling seamless transitions between complex iCIMS BID-mapping URL reconstructions, standard automated Talemetry application workflows, and event registrations without data dropping.

<br /><strong><a href="https://careers.hcahealthcare.com/" rel="noopener noreferrer">View project</a></strong>
