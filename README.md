# Anubha Sharma — Portfolio
<<<<<<< HEAD
It brings together Anubha’s work across data, software, product analytics, and UX design, with an interactive data pipeline, project case studies, an accessible interface, and a local portfolio assistant.
=======

A responsive, editorial-style personal portfolio built with HTML, CSS, and vanilla JavaScript. It brings together Anubha’s work across data, software, product analytics, and UX design, with an interactive data pipeline, project case studies, an accessible interface, and a local portfolio assistant.

The site has no build step, framework, backend, or package installation. It can run as a static website and deploy directly to GitHub Pages. Google Fonts, Lucide, and Simple Icons are loaded from public CDNs; selected SVG marks and photographs are stored locally.

## Preview

Open `index.html` in a browser, or serve the project locally as described below.

## Run locally

From the project folder, run:

```powershell
python -m http.server 8000
```

Then open <http://localhost:8000>. Stop the server with `Ctrl+C` in the terminal. Python is only used to serve the files locally; the website itself does not require Python or Node.js.

## Deploy with GitHub Pages

1. Push the project to the repository’s `main` branch.
2. In GitHub, open **Settings → Pages**.
3. Under **Build and deployment**, select **Deploy from a branch**.
4. Choose `main` and the `/ (root)` folder, then save.
5. Open the deployment URL shown on the Pages settings screen after the workflow completes.

The site uses relative links and is designed to work from the repository root and a GitHub Pages project URL.

## Project structure

```text
.
├── index.html                 Homepage
├── projects.html              Project index
├── about.html                 About, education, awards, and research
├── beyond.html                Beyond-work page
├── journal.html               Learning Journal overview and contribution heatmap
├── journal-entry.html         Individual daily learning article
├── projects/                  Individual project case studies
├── css/style.css              Layout, themes, responsive styles, and animation
├── css/journal.css            Journal and article layouts
├── js/data.js                 Central portfolio content and editable settings
├── js/journal-data.js         Published daily learning entries
├── js/journal.js              Journal heatmap, statistics, and entry rendering
├── js/main.js                 Rendering, navigation, and accessibility controls
├── js/animations.js           Scroll and reveal effects
├── js/chatbot.js              Local portfolio assistant
└── assets/
    ├── icons/                 Local SVG icons and marks
    ├── images/                Portrait and personal photo journal
    └── resume/                Downloadable resume
```

## Update your content

Most editable portfolio content is centralized in [`js/data.js`](js/data.js).

- **Social links and contact details:** set profile URLs in `socials`, and update `email`, `phone`, and `linkedin`. Blank contact fields are intentionally omitted from the site until you configure them.
- **Relocation preference:** update `relocationPreference` when you want the assistant to share a confirmed preference. It currently remains `[TO BE CONFIRMED]`.
- **Resume:** replace `assets/resume/Anubha-Sharma-Resume.pdf` with the new PDF, keeping the same filename so the download links continue to work.
- **Projects:** update the `projects` entries in `js/data.js`. Each case study’s `slug` matches an HTML file under `projects/`; copy a current case study file and set its `data-project` attribute when adding another detailed page. Add GitHub, demo, or documentation URLs only when they are available.
- **Experience, education, certifications, awards, and research:** edit the corresponding objects and arrays in `js/data.js`.
- **Profile photo:** replace `assets/images/anubha-profile.webp` with the intended portrait, keeping the filename to preserve the hero avatar reference.
- **Photo journal:** add photos under `assets/images/` and update `personalPhotos` in `js/data.js`. Each entry contains an image path, descriptive alt text, and an `object-position` value to keep the subject in frame. The horizontal carousel loops continuously, includes a pause control, and respects reduced-motion preferences.
- **Data engineering pipeline:** edit the `pipeline` stages in `js/data.js`. Each technology entry is `[display name, Simple Icons slug, proficiency]`; proficiency values are `used`, `practice`, and `explore`. Use an empty slug for concepts without a brand logo. Technology marks are loaded from Simple Icons where available.
- **Additional toolkit:** update the `toolkit` array using the same entry format. FastAPI and Django are currently labeled as exploring tools. Concept entries can use an empty logo slug and receive a Lucide icon.
- **Portfolio assistant:** edit `chatbotSkills`, `chatbotExtraProjects`, and `chatbotInterests` in `js/data.js`; assistant response logic is in `js/chatbot.js`. It uses a local, keyword-matched knowledge base and is not connected to a live AI service. It only displays contact details you explicitly configure.
- **Learning Journal:** add each published day to `entries` in `js/journal-data.js`. Use a unique `YYYY-MM-DD` date, topic, tags, lesson notes, coding questions, code of the day, and interview questions. Copy the commented object in that file as the entry shape. Entries render newest first; the year heatmap, current and longest streaks, active days, solved-question count, and unique topic count are calculated from these published entries. Leave unpublished days out; do not add placeholder entries just to fill the heatmap. `journal-entry.html?date=YYYY-MM-DD` renders the matching article.
- **Temporarily hidden Selected Work:** the homepage project preview section is retained in `index.html` with the `hidden` attribute. Remove that attribute when you want the section visible again. The project archive and case studies remain available.

## Accessibility and browser support

The accessibility panel offers light, dark, and system themes, text-size adjustment, high contrast, reduced motion, and a reset option. Preferences are stored in the browser’s `localStorage`. Text scaling is applied from the document root so rem-sized typography updates across the site. Reduced-motion preferences are respected for animation and the photo carousel. The layout adapts to desktop, tablet, and mobile screens.

## Content notes

The portfolio is based on Anubha’s supplied resume and project context. The YONO ProductLab case study is marked in development and uses a synthetic dataset. FastAPI and Django are marked as exploring tools. Contact links and unprovided profile URLs remain blank until configured. Personal photos are supplied by Anubha; the site does not assign destinations or personal stories to them.

