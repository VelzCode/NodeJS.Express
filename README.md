[Repository](https://github.com/VelzCode/NodeJS.Express)<br>
[Live Page](https://week-7-nodejs-express.onrender.com)

# NodeJS.Express — Athena Systems Task Journal & Notes

A full-stack task and note application created for week seven of my coding bootcamp. This project connects a JavaScript frontend to a Node.js and Express backend, using a JSON file to store entries on the server. The live application is hosted on Render.

## Disclaimer

Athena Systems is a fictional company created for this educational project. The business descriptions and services are illustrative and do not represent a real company.

## About the project

The application brings together a **Task Journal** and **Save Notes** panel in a dark interface with neon accents. Both panels communicate with an Express API to create, retrieve, update and delete entries.

This project builds on frontend JavaScript by introducing server routes, HTTP requests, JSON responses and file-based storage.

## Features

- **Task Journal** — Add tasks, edit their text, mark them complete and delete them.
- **Save Notes** — Create, edit and delete notes alongside the task list.
- **Inline editing** — Edit an entry directly in the list; changes save when the text loses focus.
- **Completion styling** — Completed tasks display a strike-through and a highlighted check indicator.
- **Duplicate checks** — The browser checks for matching text, ignoring letter case, within the relevant list when creating or editing entries.
- **Empty-entry checks** — Blank or whitespace-only new entries are rejected.
- **Server-side storage** — Entries are written to `data.json` and loaded through the API.
- **Responsive layout** — Task and note panels sit side by side on wider screens and stack at smaller widths.
- **Custom styling** — Dark panels, neon borders, text glow and hover effects created with CSS.

## Built with

- **HTML5 and CSS3** — Page structure, layout and styling.
- **JavaScript** — DOM updates, inline editing and asynchronous Fetch API requests.
- **Node.js** — Server runtime and file-system access.
- **Express 5** — Static file serving, JSON request parsing and API routes.
- **UUID** — Generating identifiers for new entries.
- **JSON file storage** — Saving tasks and notes without a separate database.

## How to use

1. Open the Live Page link at the top of this README.
2. Enter a task in **Task Journal** and select **Add**, or enter a note in **Save Notes** and select **Save**.
3. Click an entry's text to edit it, then click away to save the change.
4. Click a task row outside its editable text and delete control to toggle its completed state.
5. Select **×** to delete an entry immediately.

## Local setup

Install Node.js with npm, then clone or download the repository.

From the project folder, install dependencies:

```bash
npm install
```

Start the application:

```bash
npm start
```

Open **http://localhost:3001** in your browser. Stop the server with **Ctrl+C** in the terminal.

The supplied server uses port `3001`. No environment variables or database configuration are required for this local setup. Run the application through the Node.js server for its API features to work.

## Project structure

```text
Week-7.NodeJS.Express/
├── public/
│   ├── index.html       # Task and note interface
│   ├── script.js        # Browser interactions and API requests
│   └── style.css        # Custom theme and responsive layout
├── server.js            # Express server and API routes
├── data.json            # Stored tasks and notes
├── package.json         # Dependencies and npm scripts
├── package-lock.json    # Locked dependency versions
├── .gitignore           # Git exclusion rules
├── README.md            # Project documentation
├── rubrics.md           # Assignment reference material
└── error_images/        # Development screenshot
```

## API routes

| Method | Route | Purpose |
| --- | --- | --- |
| GET | `/data` | Retrieve all tasks and notes. |
| GET | `/data/:id` | Retrieve one entry by its ID. |
| POST | `/data` | Create an entry. |
| PUT | `/data/:id` | Update an entry. |
| DELETE | `/data/:id` | Delete an entry. |
| POST | `/echo` | Return the submitted JSON under a `received` property. |

Entries use a `type` field to distinguish tasks from notes and a `text` field for their content. Tasks also have a `completed` state. The browser sends JSON requests to these routes and updates the relevant list.

Missing entry IDs return a `404` response. The data routes include error handling that returns a `500` response if a server operation fails.

## Storage and current scope

Both tasks and notes are stored in the same server-side JSON file. There are no user accounts or separate personal task lists: visitors use the same stored data.

On a local installation, entries remain available across server restarts while `data.json` is retained. Hosted data retention depends on the deployment's storage configuration; this project does not include a separate database or persistent-disk configuration.

The duplicate and blank-new-entry checks run in the browser. The API does not enforce those checks, and inline edits currently allow an entry to be cleared.

The **Call Us** and **Email Us** links are placeholders. The project does not currently include an automated test suite; the `npm test` script is a placeholder.

## Hosting

The live version is hosted on Render at the link above. The project uses `npm install` to install dependencies and `npm start` to launch the Express server. Express serves both the frontend files and the API from the same application.

## Learning focus

- Creating routes with Express and working with HTTP methods.
- Connecting a frontend to a backend using `fetch`, `async` and `await`.
- Implementing create, read, update and delete operations.
- Reading and writing JSON data with Node.js.
- Generating entry IDs and handling missing records.
- Separating frontend assets from server logic.

## Author

**Jason Dewhurst** — [VelzCode on GitHub](https://github.com/VelzCode)
