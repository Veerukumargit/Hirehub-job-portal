# HireHub – Job Portal Website

HireHub is a responsive job portal frontend built with **React**, **Vite** and **React Router**. Candidates can browse, filter, save and apply to jobs. Employers can post jobs and review applicants. All data is stored in the browser's `localStorage`, so the app runs without a backend.

## Features

**For everyone**
- Home page with hero search, job categories and latest jobs
- Jobs listing with keyword and location search
- Filters for job type, category and experience level
- Sorting (newest, title)
- Job details page with responsibilities, requirements and skills
- Companies page
- Custom 404 page and a responsive layout

**For candidates**
- Register and log in with the Candidate role
- Apply to jobs through a modal form with validation and resume upload (PDF/DOC/DOCX, max 2 MB)
- Save and unsave jobs
- Dashboard showing applied jobs and saved jobs

**For employers**
- Register and log in with the Employer role
- Post new jobs (employer-only protected route)
- Dashboard showing posted jobs and applicants for each job
- Delete posted jobs

## Tech Stack

| Area | Technology |
|------|------------|
| UI library | React 18 |
| Build tool | Vite 5 |
| Routing | React Router DOM 6 |
| State management | Context API and custom `useLocalStorage` hook |
| Styling | Plain CSS |
| Storage | Browser localStorage |

## Project Structure

```
client/
├── public/            # favicon
├── src/
│   ├── components/    # Navbar, Footer, JobCard, SearchBar, FilterSidebar, ApplyModal, ProtectedRoute
│   ├── pages/         # Home, Jobs, JobDetails, Companies, Login, Register, Dashboard, PostJob, NotFound
│   ├── context/       # AuthContext, JobsContext
│   ├── hooks/         # useLocalStorage
│   ├── data/          # seed jobs and filter options
│   ├── utils/         # helper functions
│   ├── App.jsx
│   ├── main.jsx
│   └── index.css
├── index.html
├── vite.config.js
└── package.json
```

## Getting Started

**Prerequisites:** Node.js 18 or later

```bash
# clone the repository
git clone https://github.com/<your-username>/hirehub-job-portal.git
cd hirehub-job-portal/client

# install dependencies
npm install

# start the dev server (http://localhost:5173)
npm run dev
```

Build for production:

```bash
npm run build
npm run preview
```

## Routes

| Path | Page | Access |
|------|------|--------|
| `/` | Home | Public |
| `/jobs` | Jobs listing | Public |
| `/jobs/:id` | Job details | Public |
| `/companies` | Companies | Public |
| `/login`, `/register` | Authentication | Public |
| `/dashboard` | Dashboard | Logged-in users |
| `/post-job` | Post a job | Employers only |

## How to Try It

1. Register as an **Employer** and post a job.
2. Log out, then register as a **Candidate**.
3. Open a job, save it and apply with a resume.
4. Log back in as the employer to see the applicant on the dashboard.

## Limitations

- Data lives in the browser's localStorage, so it is not shared between devices or users.
- Passwords are stored in plain text in localStorage. This is for demo purposes only and is not secure for production.
- Uploaded resume details are stored locally and are not sent to a server.

## Future Improvements

- Node.js/Express and MongoDB backend with JWT authentication
- Password hashing and real file storage
- Application status updates by employers
- Email notifications
- Pagination and company profiles

## Backend Integration

Replace the localStorage logic in `src/context/AuthContext.jsx` and `src/context/JobsContext.jsx` with API calls (fetch or axios) when your server is ready.

## Screenshots

Add screenshots of the home page, jobs listing and dashboard here.

## Author

**Your Name**
GitHub: (https://github.com/Veerukumargit)

## License

Released under the [MIT License](LICENSE).
