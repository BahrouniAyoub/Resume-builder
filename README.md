# Resume Builder

**Work in progress.** This repository contains the current React frontend implementation, and the final version will support a full client/server architecture as described below.

## What it is

A resume builder application prototype built with:
- React + Vite
- Tailwind CSS
- React Router
- lucide-react icons

The current app includes:
- Dashboard for saved resumes
- Create resume flow
- Upload existing resume flow
- Resume builder interface with section navigation and progress tracking
- Resume preview templates
- User image upload support

## Project status

This project is still under development. The current repository contains the frontend prototype in `client/`, and the final design is intended to include a backend API, authentication, resume persistence, and AI-assisted resume enhancement.

## Final architecture (planned)

```text
resume-builder/
├── client/                 # React Frontend Application
│   ├── src/
│   │   ├── app/           # Redux store configuration
│   │   ├── features/      # Redux slices and state management
│   │   │   ├── authSlice.js    # Authentication state
│   │   │   └── store.js        # Redux store setup
│   │   ├── assets/        # Static assets (images, icons)
│   │   ├── components/    # Reusable UI components
│   │   │   ├── templates/      # Resume template components
│   │   │   │   ├── ClassicTemplate.jsx
│   │   │   │   ├── MinimalImageTemplate.jsx
│   │   │   │   ├── MinimalTemplate.jsx
│   │   │   │   └── ModernTemplate.jsx
│   │   │   ├── forms/          # Form components
│   │   │   │   ├── ColorPicker.jsx
│   │   │   │   ├── EducationForm.jsx
│   │   │   │   ├── ExperienceForm.jsx
│   │   │   │   ├── PersonalInfoForm.jsx
│   │   │   │   ├── ProfessionalSummaryForm.jsx
│   │   │   │   ├── ProjectForm.jsx
│   │   │   │   └── SkillsForm.jsx
│   │   │   ├── ui/             # General UI components
│   │   │   │   ├── Loader.jsx
│   │   │   │   ├── Navbar.jsx
│   │   │   │   ├── ResumePreview.jsx
│   │   │   │   └── TemplatesSelector.jsx
│   │   │   └── home/           # Home page components
│   │   ├── configs/       # Configuration files
│   │   │   └── api.js          # API configuration and endpoints
│   │   ├── pages/         # Route components
│   │   │   ├── Dashboard.jsx        # User dashboard
│   │   │   ├── Home.jsx            # Landing page
│   │   │   ├── Layout.jsx          # App layout
│   │   │   ├── Login.jsx           # Authentication
│   │   │   ├── Preview.jsx         # Resume preview
│   │   │   └── ResumeBuilder.jsx   # Main builder interface
│   │   ├── App.jsx        # Root application component
│   │   ├── index.css      # Global styles
│   │   └── main.jsx       # Application entry point
│   └── package.json       # Dependencies and scripts
│
├── server/                # Express Backend Application
│   ├── configs/          # Configuration modules
│   │   ├── ai.js              # AI service configuration
│   │   ├── db.js              # Database connection setup
│   │   ├── imageKit.js        # ImageKit integration
│   │   └── multer.js          # File upload configuration
│   ├── controllers/      # Business logic handlers
│   │   ├── aiController.js         # AI resume optimization
│   │   ├── resumeController.js     # Resume CRUD operations
│   │   └── userController.js       # User authentication & management
│   ├── middlewares/      # Custom middleware functions
│   │   └── authMiddleware.js       # JWT authentication
│   ├── models/          # Database schemas and models
│   │   ├── Resume.js             # Resume data structure
│   │   └── User.js               # User data structure
│   ├── routes/          # API route definitions
│   │   ├── aiRoutes.js           # AI enhancement endpoints
│   │   ├── resumeRoutes.js       # Resume management endpoints
│   │   └── userRoutes.js         # User authentication endpoints
│   ├── package.json     # Server dependencies
│   └── server.js        # Server entry point
└── README.md            # Project documentation
```

## Current project structure

- `client/` - main React application
- `client/src/pages/` - application pages like `Dashboard`, `ResumeBuilder`, `Preview`, `Login`, and `Home`
- `client/src/components/` - reusable UI components such as `Navbar` and `PersonalInfoFrom`
- `client/src/assets/` - static assets, templates, and dummy data

## Getting started

From the project root:

```bash
cd client
npm install
npm run dev
```

Then open the local Vite URL shown in the terminal, normally `http://localhost:5173/` or the next available port.

## Available commands

Inside `client/`:

- `npm run dev` - start the development server
- `npm run build` - build the production bundle
- `npm run preview` - preview the built production bundle locally
- `npm run lint` - run ESLint against the source files

## Notes

- The app uses the `client/src/assets/assets.js` dummy data source for resume content.
- The builder page uses section state to drive navigation and progress bar percentage.
- The `PersonalInfoFrom` component manages local image uploads and calls a parent `onChange` handler to update resume data.

## License

This project is provided as-is.
