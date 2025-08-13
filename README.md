# Internal Employee Website

This repository is meant to show off the internal employee website I made during my co-op.

## Technical Information

**I designed and deployed a secure, full-stack internal employee portal using React.js, Express, and SQLite3, with automatic Kerberos-based authentication via Active Directory.** The website was hosted on a Linux server, served via Nginx with SSL encryption, and managed using PM2. I built a Gitlab CI/CD pipeline supporting multi-environment workflows (dev, staging, prod), each isolated with scoped environment variables. I implemented security checks on the frontend and backend, including input sanitization, credential handling (Kerberos), role-based access control, and session storage. I documented RESTful APIs using Swagger OpenAPI. I mirrored production locally using Docker in VSCode. Testing of the final product included user acceptance, manual, and unit.

### Development stack

- Frontend: React.js using Vite build system
- Backend: Express with Node.js
- Database management: SQLite3 

### Notable dependencies

Frontend:
- tailwindcss
  - Stripped all default styling on elements.
  - Created a 'Styles' dictionary which was used to define custom styles used throughout frontend components.
- antd
  - Calendar
  - Modal
- dompurify
  - Input sanitization on frontend.
- axios
  - Making HTTP requests with Node.js.

Backend:
- better-sqlite3
  - SQlite library for database management.
  - Handling session storage with express-session.
- kerberos
  - Credential handling via Active Directory.
- multer
  - Handling file upload. Images were uploaded and accessed via frontend's `public` folder.
- mocha + chai
  - Unit testing backend endpoints.

<img width="1914" height="959" alt="Home Page" src="https://github.com/user-attachments/assets/c714ea0d-cb07-43fd-8ea6-b67b4f1d0fc1" />

## Navigating the home page

The home page features announcements about events, new hires, and retirees. All posts can be created, updated, and deleted.
