# Commet AI 🚀

**AI-assisted assessment and group project management platform for university students.**

Commet AI helps student teams turn complex assessment briefs into structured, manageable project plans. Students can upload an assessment brief, generate task suggestions using AI, review and edit those suggestions, assign work based on team preferences and workload, and track progress through a shared realtime task board.

The platform was developed as a four-person university software project with a focus on practical AI integration, secure full-stack development, collaborative workflows and human oversight.

---

## ✨ Key Features

- 🔐 User authentication and protected team access
- 👥 Create and join project teams
- 🎯 Set individual work and skill preferences
- 📄 Upload assessment briefs in PDF format
- 🤖 Generate structured task suggestions using the OpenAI API
- ✏️ Review and edit AI-generated tasks before saving
- ⚖️ Suggest task assignments using preferences and current workload
- 👤 Manually override suggested assignees
- ➕ Create tasks manually without using AI
- 📋 Shared task board with To Do, In Progress and Done workflows
- ⚡ Realtime task updates across multiple users
- 📊 Effort-weighted progress tracking
- 🗑️ Edit and delete project tasks
- 🔄 Manual fallback when AI generation is unavailable

---

## 🧠 How It Works

1. A user signs in and creates or joins a team.
2. Team members select their preferred areas of work.
3. A student uploads an assessment brief as a PDF.
4. The backend extracts and processes the relevant document content.
5. The OpenAI API generates structured task suggestions.
6. Students review and edit the generated tasks.
7. Commet AI suggests assignees using:
   - skill/preference matching
   - existing workload
   - tie-breaking when required
8. Students can override any suggested assignment.
9. Confirmed tasks are stored in the database.
10. The shared board updates in realtime for connected team members.

AI is used as a **planning assistant rather than a decision-maker**. Users remain responsible for reviewing, editing and approving tasks and assignments before anything is saved.

---

## 🛠️ Tech Stack

### Frontend
- React
- TypeScript
- Vite
- Tailwind CSS
- React Router

### Backend
- Python
- FastAPI
- Pydantic
- PyMuPDF

### Database & Platform
- Supabase
- PostgreSQL
- Supabase Authentication
- Supabase Storage
- Supabase Realtime
- Row Level Security

### AI
- OpenAI API

### Deployment
- Vercel — frontend
- Render — backend

### Development
- Git
- GitHub
- Pull Requests
- Feature branches

---

## 🏗️ Architecture

Commet AI follows a three-tier client-server architecture.

**Frontend**  
React + TypeScript application responsible for the user interface, authentication flow, team management, task review and realtime board.

⬇️

**Backend**  
FastAPI service responsible for protected API operations, PDF processing, AI orchestration, task allocation and privileged database operations.

⬇️

**Data & Services**  
Supabase provides authentication, PostgreSQL database storage, private file storage, realtime updates and Row Level Security.

The OpenAI API is accessed through the backend so API credentials are never exposed to the browser.

> Add the architecture diagram here.

![Commet AI Architecture](docs/commet-architecture.png)

---

## 🤖 AI-Assisted Task Generation

When an assessment brief is uploaded:

- the backend validates the PDF
- PyMuPDF extracts the document text
- relevant content is prepared for AI processing
- the OpenAI API generates structured task suggestions
- generated tasks are displayed for human review

The AI does **not** make final allocation decisions.

Task generation and team-member allocation are deliberately separated. Team-member identities and personal work preferences do not need to be provided to the AI model.

Users can also create tasks manually if they prefer not to use AI or if AI generation fails.

---

## ⚖️ Preference-Aware Task Allocation

Commet AI uses a simple and transparent allocation approach.

For each task, the backend:

1. looks for team members whose preferences match the task
2. compares their current workloads
3. selects the least-loaded suitable member
4. uses random selection only when there is a genuine tie

If no preference matches, the least-loaded team member is suggested.

Every suggestion can be manually changed before the task plan is confirmed.

---

## 📸 Application Screenshots

### Authentication

![Login](screenshots/login.png)

### Team Creation

![Team Creation](screenshots/team-create.png)

### Assessment Brief Upload

![PDF Upload](screenshots/pdf-upload.png)

### AI Processing

![AI Processing](screenshots/ai-processing.png)

### AI Task Review & Assignment

![AI Review](screenshots/ai-task-review.png)

### Manual Task Creation

![Manual Tasks](screenshots/manual-task-creation.png)

### Realtime Task Board

![Task Board](screenshots/task-board.png)

---

## 🧪 Testing & Quality Assurance

Testing was a major part of the project rather than being left until the end of development.

### Backend

**231 / 231 automated backend tests passed**

Tests covered areas including:

- authentication and membership validation
- AI extraction and response validation
- task allocation logic
- PDF validation and extraction
- bulk task persistence
- task editing and deletion
- privacy and security controls
- team isolation
- long-document processing
- failure handling and AI fallback behaviour

### Frontend & Production Testing

**20 / 20 final manual production scenarios passed**

Testing included:

- authentication
- team switching
- preference persistence
- PDF AI generation
- AI task review
- allocation suggestions
- human assignment override
- bulk task saving
- task persistence
- realtime multi-user synchronisation
- effort-weighted progress
- protected routes
- task deletion
- security checks

Final verification recorded:

**231 automated tests passed**  
**20 manual production scenarios passed**  
**0 unresolved frontend errors**

---

## 🔒 Security & Privacy

Security-sensitive operations are handled by the FastAPI backend.

Key safeguards include:

- Supabase access-token verification
- team-membership validation
- Row Level Security
- private file storage
- server-side OpenAI credentials
- server-side privileged Supabase credentials
- separation of AI task generation from user allocation
- minimal personal information sent to AI services

API secrets are never exposed to the frontend.

---

## 👩‍💻 My Contribution

This project was developed collaboratively by a four-person university team.

My work included:

- contributing to the full-stack application development
- working across frontend and backend functionality
- supporting Supabase authentication, database and application workflows
- testing integrated features and identifying defects
- coordinating QA and feature verification
- supporting sprint planning and project coordination
- reviewing the end-to-end application workflow
- contributing to issue resolution and final production testing

**Project roles:** QA Lead and Project Manager

---

## 🚧 Challenges & What We Learned

Several technical challenges appeared during development, including:

- integrating independently developed frontend and backend components
- validating unpredictable AI responses
- handling AI service failures
- maintaining consistent task and preference schemas
- managing database constraints
- protecting team-specific data
- maintaining realtime synchronisation
- balancing project scope against delivery deadlines

The project reinforced an important software-engineering lesson: a feature is not complete simply because it works independently. It also needs to integrate correctly with authentication, data storage, other features and the overall user workflow.

---

## 🔮 Future Improvements

Potential future development includes:

- OCR support for scanned or image-only PDFs
- deadline reminders and notifications
- more detailed project analytics
- improved frontend automated testing
- larger-team realtime testing
- improved reconnection handling
- further evaluation of task-allocation fairness
- support for an alternative AI provider for additional resilience

---

## 👥 Team

Commet AI was developed by a four-person student team as part of the **Advanced Tech: Work-Integrated Learning** project at Torrens University Australia.

---

## 📌 Project Status

✅ Core MVP completed  
✅ Full-stack deployment completed  
✅ AI-assisted task generation implemented  
✅ Realtime collaboration implemented  
✅ Backend automated testing completed  
✅ Final production workflow verified
