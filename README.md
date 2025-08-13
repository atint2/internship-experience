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

## Website walkthrough

The standard user has access to the home page, calendar, telephone directory, policies and procedures page, and outside links. All of which are accessible in the website header. 

### Navigating the home page

The home page features announcements about events, new hires, and retirees. All posts can be created, updated, and deleted by admins with the 'EVENTS' role.

<figure>
  <img width="1917" height="958" alt="Home page for standard user" src="https://github.com/user-attachments/assets/ea4214b4-632e-44ba-a104-a5f2809b4fa0" />
  <figcaption>Events view for standard user</figcaption>
</figure>

To view unreleased events, users can click ‘Show Upcoming’. They will then be able to click ‘View Latest’ to return to released events. Events can be filtered by event type ('Event', ‘Holiday’, ‘Spill’, ‘HR Update’, ‘News’) using the event type selector. It defaults to ‘All Types’.

<figure>
  <img width="945" height="542" alt="ee-intranet-home-admin-actions" src="https://github.com/user-attachments/assets/d3dc73b8-4ab3-417c-9aff-16cec321c5b8" />
  <figcaption>Events view for admin</figcaption>  
</figure>

Key:

1. New (create new event post)
2. Edit (update existing event post)
3. Delete (delete existing event post)

Administrators of the 'Announcements' page have the ability to create, update, and delete event posts. All changes are reflected in the database.

<figure>
  <img width="1914" height="956" alt="Add event form" src="https://github.com/user-attachments/assets/f0f2099d-5f4f-494e-9798-cb84c83dea3b" />
  <figcaption>Create event post</figcaption>
</figure>

<figure>
  <img width="1915" height="958" alt="Add event to calendar" src="https://github.com/user-attachments/assets/fef3afb9-6867-4a74-b53b-a745d9228ecb" />
  <figcaption>Add event to calendar</figcaption>
</figure>
**NOTE**: Events can be added to calendar from the home page. However, once an event has been created, the changes made to it will not be reflected on the calendar.

<figure>
  <img width="1917" height="955" alt="Update event form" src="https://github.com/user-attachments/assets/f28dbc98-3913-491d-9469-95a2fd3d54dc" />
  <figcaption>Update event post</figcaption>
</figure>


<figure>
  <img width="1917" height="958" alt="Delete event confirmation" src="https://github.com/user-attachments/assets/75333594-abd6-423e-9327-9778f8a8d967" />
  <figcaption>Delete event post</figcaption>
</figure>



