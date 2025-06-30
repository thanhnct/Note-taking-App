# Note-Taking App – Mini Project

## Introduction

This is a mini project for practicing **System Design** by building a cross-platform Note-taking App. The project helps you exercise end-to-end system design skills, from database modeling, API construction, to real-time/offline data synchronization across devices. You can extend, deploy, or use this project as a practical interview exercise.

---

## Main Features

- User registration and login
- CRUD operations for notes: create, read, update, delete
- Synchronize notes across multiple devices (optionally in real-time)
- Support for Markdown or Rich Text in note content
- Versioning: track note edit history
- Offline support (users can work without Internet)
- Basic security and access control

---

## High-Level Architecture

```
[Client App] <-> [API Gateway] <-> [Backend Service] <-> [Database]
                                      |
                                   [Cache (Redis)]
                                      |
                                [Message Queue] (for real-time sync)
```

---

## Database Design (Schema)

- **User:** user_id, email, password_hash, created_at
- **Note:** note_id, user_id (FK), content, created_at, updated_at
- **NoteVersion:** version_id, note_id (FK), content, created_at

---

## Example API Endpoints

- `POST /auth/register` – User registration
- `POST /auth/login` – User login
- `GET /notes` – List all user notes
- `POST /notes` – Create a new note
- `PUT /notes/{id}` – Edit a note (creates a new version)
- `DELETE /notes/{id}` – Delete a note
- `GET /notes/{id}/versions` – View note version history

---

## Suggested Tech Stack

- **Backend:** NodeJS (Express/NestJS), Python (FastAPI), Go, Java (Spring Boot)
- **Database:** PostgreSQL/MySQL/MongoDB
- **Cache:** Redis
- **Client:** ReactJS, Flutter, Electron
- **Realtime:** WebSocket/Socket.IO, Redis Pub/Sub

---

## Quick Start (Example with NodeJS + PostgreSQL)

```bash
git clone https://github.com/your-username/note-taking-system-design.git
cd note-taking-system-design

# Install backend dependencies
cd backend
npm install
cp .env.example .env
# Edit DB connection info in .env

# Run DB migrations
npm run migrate

# Start the backend server
npm start

# (Optional) Start the client app
cd ../client
npm install
npm start
```

---

## Suggested Extensions

- Add note sharing between users
- Implement role-based access control (RBAC)
- Real-time sync across devices
- Experiment with conflict resolution for offline edits
- Package as a mobile app (Flutter/React Native)

---

## References

- [System Design Primer](https://github.com/donnemartin/system-design-primer)

---

## License

MIT
