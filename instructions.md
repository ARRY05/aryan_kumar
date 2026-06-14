# Romlex Online Gaming Portal Development Instructions

## Project Overview
You are required to build Romlex, a full stack online gaming portal. The platform features a dynamic grid layout for browsing games, dedicated iframe playback pages, user profile management, and a secure admin dashboard. All premium game inquiries operate through a direct chat link system. The final deliverable must be fully containerized using Docker.

## Core Features and Scope

### 1. Public Facing Frontend
- **Home Page**: Display a top navigation bar with the Romlex brand and a search input. Include a hero slider for featured games and a category sidebar (Action, Puzzle, Strategy). Show games in a responsive grid.
- **Game Playback Page**: Embed a secure iframe to play the demo game. Include a sidebar showing publisher info, player ratings, and view count. Add two primary action buttons: "Add to Favorites" and "Inquire for License".
- **Chat Integration**: The "Inquire for License" button must open a direct chat link (like a wa.me link) with a pre filled message stating the exact game title. Provide a fallback modal with a copyable phone number for desktop users without the chat application.

### 2. User Accounts
- Build a registration and login flow.
- Create a dashboard with a history tab for recently played games and a favorites tab for saved games.
- Allow users to update their username and avatar.

### 3. Admin Dashboard
- Restrict access to a secure admin login.
- Provide a form to add new games. Required fields: title, category, iframe URL, and a WebP thumbnail upload.
- Display a list view to edit, delete, or toggle the visibility status of games.

## Technical Specifications

### Architecture and Data
- **Backend**: Use Python with FastAPI or Flask.
- **Frontend**: Use HTML, CSS (Tailwind or Bootstrap permitted), and vanilla JavaScript.
- **Database**: Use SQLite or PostgreSQL. The system must dynamically read and write game listings, user data, and favorites.

### Media and Performance
- All game thumbnails must use the WebP format and stay under 200KB per image.
- Implement lazy loading for the game grid.
- Achieve a Lighthouse performance score of at least 85.
- Ensure the layout is fully responsive across mobile, tablet, and desktop screens.

### Containerization
- Provide a Dockerfile based on Alpine Linux.
- Provide a docker-compose.yml file.
- Running `docker compose up` must start the backend, frontend, and database services together on port 8080.

## Out of Scope (Do Not Include)
- Do not integrate any payment gateways or automated checkout systems.
- Do not use any CMS platforms like WordPress, Shopify, or Wix.
- Do not use heavy JavaScript frameworks like React, Angular, or Vue.
- Do not include unauthorized or scraped iframes. All seed games must be properly licensed for third party distribution.

## Provided Assets
You will receive the following files to guide your work:
- `assets.pdf`: Contains specific text copy, data structures, and styling guidelines.
- `reference_image.png`: A visual layout guide for the grid and playback pages.

## Required Deliverables
1. Complete source code organized into backend, frontend, and database folders.
2. A database seed file (SQL or JSON) containing sample data for at least 10 playable demo games.
3. `Dockerfile` and `docker-compose.yml` configuration files.
4. Standard sizes for the site favicon.
5. `sitemap.xml` and `robots.txt` files for search engine indexing.
6. A detailed `README.md` file explaining how to install Docker, run the containers, and manage the database.
