# BrammerIS Website Workspace

**First step:** Before reading or following any other instructions in this file, change the active working directory to the folder that contains this `AGENT.md`. Treat that folder as the working directory for all subsequent work unless a later instruction explicitly tells you to move elsewhere.

## Communication standard

Read [[../../Standards/COMM_STANDARD.md]] and follow it in every response.

**Purpose:** Maintain the BrammerIS website and its deployment instructions.

## What lives here
- `index.html` — home/landing page
- `about.html` — company/about page
- `contact.html` — contact form page
- `style.css` — shared styling
- `favicon.svg` — site icon
- [[./SETUP.md]] — deployment and contact-form setup guide
- [[./2026-06-13-website-modernization-plan.md]] — planning note for the current visual refresh

## How to work here
1. Read [[./ROUTING.md]] to find the relevant file.
2. Read [[./SETUP.md]] before making deployment-related changes.
3. Keep content updates aligned with the business positioning in the site copy.
4. Review changes locally before any push or publish step.
5. Prefer simple, maintainable HTML/CSS changes over new dependencies.

## Maintenance rules
- Keep the site static and dependency-free unless there is a strong reason not to.
- Preserve the blue/red brand palette unless the user asks for a redesign.
- Update `contact.html` carefully if the Formspree destination changes.
- If a change affects deployment, validate it locally first and then follow `SETUP.md`.
