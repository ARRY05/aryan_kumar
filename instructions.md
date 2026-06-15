# Romlex Online Gaming Portal Development Instructions

## Project Overview
You are required to build Romlex, a full stack online gaming portal. The platform features a dynamic grid layout for browsing web-based games, dedicated iframe playback pages for playing demos, user profile management, and a secure admin dashboard. All premium game inquiries operate through a direct chat link system rather than an integrated checkout. The final deliverable must be a fully functional web application containerized using Docker. 

## Core Features and Scope

### 1. Public Facing Frontend
- **Home Page Navigation**: Display a top navigation bar containing the brand text "Romlex" and a functional search input field.
- **Hero Section & Sidebar**: Include a hero slider element at the top of the home page for featured games. The slider must support automatic transitioning. Alongside the main content, display a sidebar specifically for game categories (e.g., Action, Puzzle, Strategy).
- **Game Grid**: Display the available games in a grid format. The grid must be fully responsive, changing the number of columns based on the screen size (e.g., 4 columns on desktop, 2 on tablet, 1 on mobile).
- **Card Hover Effects**: Moving the mouse cursor over a game card must trigger a CSS lift effect (using `transform: translateY`). Additionally, moving the mouse cursor over a game card must apply a CSS drop shadow. 

### 2. Game Playback View
- **Iframe Integration**: Clicking a game card from the home page must open a dedicated playback page. This page must load the selected game inside an HTML `iframe` element.
- **Metadata Sidebar**: The game playback page must display specific metadata about the game: publisher information, player ratings, and the total view count.
- **Action Buttons**: The playback page must feature two distinct interaction buttons: "Add to Favorites" and "Inquire for License".
- **Chat Inquiry Flow**: Clicking the "Inquire for License" button must open a direct chat web link (such as a WhatsApp `wa.me` URL). This chat link must automatically include the exact game title in the pre-filled message text. 
- **Desktop Chat Fallback**: Accessing the chat link on a desktop browser without a native chat application installed must trigger a fallback modal window. This modal window must display a contact phone number.

### 3. User Accounts & Dashboard
- **Authentication**: A user must be able to successfully create an account through a registration form. A registered user must be able to log in to access the user dashboard.
- **Dashboard Data**: The user dashboard must contain a history tab displaying recently played games. Clicking the "Add to Favorites" button on a game playback page must add that specific game to the dashboard's favorites tab.
- **Profile Management**: The user profile page must allow the user to change their display name and upload a new avatar image.

### 4. Admin Dashboard
- **Access**: The application must include a separate, secure login page specifically for the admin dashboard.
- **Game Management**: The admin dashboard must contain a form to add a new game entry to the database. Required fields include title, category, iframe URL, and thumbnail image.
- **List View**: The admin dashboard must display a list of all games currently in the system. This list must include a working delete button and a working edit button for each individual entry.
- **Visibility Toggle**: The admin dashboard must include a toggle switch allowing the administrator to hide a game from the public home page without deleting it from the database.

## Technical Specifications

### Architecture and Data
- **Backend Environment**: The backend source code files must be written in Python (using either FastAPI or Flask).
- **Frontend Environment**: Use HTML, vanilla JavaScript, and CSS. You may use Tailwind CSS or Bootstrap. Do not use heavy JavaScript frameworks like React, Angular, or Vue.
- **Database Schema**: Implement a relational database using SQLite or PostgreSQL. Tables must include Users, Games, Categories, User_Favorites, and User_History. The system must dynamically read and write game listings.

### Media and Performance Requirements
- **WebP Enforcement**: All game thumbnail images in the source files must use the `.webp` format. Furthermore, every thumbnail must stay under 200KB in file size.
- **Lazy Loading**: The HTML image tags used for the game grid must include the `loading="lazy"` attribute.
- **Accessibility**: Include `alt` text on every image and ensure all buttons are keyboard navigable. Respect the `prefers-reduced-motion` CSS media query for animations.
- **Lighthouse Metric**: The application must achieve a Lighthouse performance score of at least 85.

### Docker Containerization
- **Base Image**: The included `Dockerfile` must use Alpine Linux as its base image.
- **Startup Command**: You must provide a `docker-compose.yml` file. Running the exact command `docker compose up` must successfully start the application (frontend, backend, and database). 
- **Port**: The application must expose port 8080 by default.

## Out of Scope Boundaries
- Do not integrate any payment gateways, Stripe, UPI, or automated checkout systems. 
- Do not use any CMS platforms like WordPress, Shopify, or Wix.
- Do not deliver external links to code; everything must be bundled locally.

## Required Deliverables
1. **Source Code**: Complete source code organized strictly into `backend/`, `frontend/`, and `database/` directories, compressed into a single `.zip` file.
2. **Database Seed**: A database seed file (e.g., `schema.sql`) containing entries for at least 10 playable demo games.
3. **Container Files**: A valid `Dockerfile` and `docker-compose.yml`.
4. **Favicon Assets**: Site favicon files provided in exactly `.ico` (16x16) and `.png` (32x32) formats.
5. **SEO Files**: The root folder of the project must contain a `sitemap.xml` file and a `robots.txt` file.
6. **Documentation**: A `README.md` file containing explicit step-by-step instructions for installing Docker and running the application.
