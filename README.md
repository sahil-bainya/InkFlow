# InkFlow — Blog Application using React

InkFlow is a full-stack blog application built with React and Appwrite that allows users to create, manage, and publish rich-text blog posts with image uploads and authentication.
The project demonstrates modern frontend architecture using React, Redux Toolkit, React Router, Tailwind CSS, and Backend-as-a-Service integration with Appwrite.

---
### Home Page
<img width="1352" height="595" alt="image" src="https://github.com/user-attachments/assets/5eca241b-a503-4876-b01c-4ce2be75e75d" />


## Live Demo & Repository

- **Live Application**: [https://inkflow-black.vercel.app](https://inkflow-black.vercel.app)
- **GitHub Repository**: [https://github.com/the2rivage/InkFlow](https://github.com/the2rivage/InkFlow)

---

## Tech Stack

- **Frontend**: React 18 + Vite
- **State Management**: Redux Toolkit
- **Backend / Database / Storage**: Appwrite (Backend as a Service)
- **Styling**: Tailwind CSS (with dark mode via `class` strategy)
- **Routing**: React Router v6
- **Rich Text Editor**: TinyMCE (via `react-hook-form` + `RTE` component)
- **Form Handling**: React Hook Form

---
## Features

- User Authentication (Signup, Login, Logout)
- Protected Routes using AuthLayout
- Create, Edit, and Delete Blog Posts
- Rich Text Editor with TinyMCE
- Image Upload and Storage using Appwrite
- Dark / Light Theme Toggle
- Responsive UI with Tailwind CSS
- Persistent Authentication State using Redux Toolkit
- Dynamic Routing with React Router
- Slug-based Blog URLs
  
## Project Structure

```
src/
├── appwrite/
│   ├── auth.js          # AuthService class (login, signup, logout)
│   └── config.js        # Service class (posts, files)
├── components/
│   ├── Header.jsx
│   ├── Footer.jsx
│   ├── PostCard.jsx
│   ├── PostForm.jsx
│   ├── AuthLayout.jsx   # Route protection wrapper
│   ├── LogoutBtn.jsx
│   ├── ToggleButton.jsx
│   ├── RTE.jsx          # TinyMCE rich text editor
│   ├── Input.jsx
│   └── Select.jsx
├── pages/
│   ├── Home.jsx
│   ├── AllPosts.jsx
│   ├── Post.jsx         # Single post view
│   ├── AddPost.jsx
│   ├── EditPost.jsx
│   ├── Login.jsx
│   └── Signup.jsx
├── store/
│   ├── store.js         # Redux store
│   ├── authSlice.js     # Auth state
│   └── themeSlice.js    # Theme state
├── App.jsx
└── main.jsx
```

---

## Application Flow
<img width="2816" height="1536" alt="Gemini_Generated_Image_87v9tr87v9tr87v9" src="https://github.com/user-attachments/assets/6684947c-b109-41ae-a4dd-006662fa2345" />

## Architecture Overview

- React handles the UI layer
- Redux Toolkit manages global authentication and theme state
- React Router manages client-side routing
- Appwrite provides:
  - Authentication
  - Database
  - File Storage
- Tailwind CSS handles responsive styling

### Route Map

```
/                  → Home          (public)
/login             → Login         (AuthLayout authentication=false)
/signup            → Signup        (AuthLayout authentication=false)
/all-posts         → AllPosts      (AuthLayout authentication=true)
/add-post          → AddPost       (AuthLayout authentication=true)
/edit-post/:slug   → EditPost      (AuthLayout authentication=true)
/post/:slug        → Post          (public)
```

---

### Appwrite

Appwrite is an open-source Backend-as-a-Service (BaaS) platform that provides backend services like authentication, database management, and file storage through easy-to-use SDKs and APIs.

In InkFlow, Appwrite is used for:

- User Authentication
- Database Management
- Image/File Storage
- Session Handling

Using Appwrite removed the need to build a separate custom backend server and allowed faster development of the application.
