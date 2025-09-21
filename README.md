# Cloud Enabled Deployment with GCP

This repository contains four projects:

- course-service (Spring Boot + MySQL)
- student-service (Spring Boot + MongoDB)
- media-service (Spring Boot + Local file storage, can be extended to S3/MinIO)
- frontend-app (React + TypeScript)

## Student Details
- **Name:** Dinelka Lakshan
- **Student Registration Number:** 2301671039
- **Email Address:** dinelkalakshan150@gmail.com

## Live Demo Video
[▶ Watch Demo Video](https://drive.google.com/file/d/1sxCUMgiXhgwRCnJ1JWf9KUMYi9uLoFzf/view?usp=drive_link)

## Backend Services

### 1. course-service
## 🚀 Course Service - MySQL Configuration (GCP)

Below is the configuration for connecting **Spring Boot + MySQL** with a **Google Cloud SQL instance**:

spring.datasource.host="34.66.233.178"  
spring.datasource.port=3306
spring.datasource.url="jdbc:mysql://${spring.datasource.host}:${spring.datasource.port}/courses?createDatabaseIfNotExist=true"  
spring.datasource.username=your username  
spring.datasource.password=your password

### 2. student-service
- Document: Student(registrationNumber, fullName, address, contact, email)
- Endpoints:
  - GET /students
  - GET /students/{id}
  - POST /students
  - DELETE /students/{id}
- Default port: 8082
- Configure MongoDB settings

### 3. media-service
- Resource: files
- Endpoints:
  - POST /files (multipart/form-data: file)
  - GET /files (list)
  - GET /files/{id} (fetch)
  - DELETE /files/{id} (delete)
- Default port: 8083
- Uses local disk storage at `./data/media` by default (override with env var `MEDIA_STORAGE_DIR`).

## Frontend (frontend-app)
- React + TypeScript + MUI + Axios + Vite app with 3 sections: Courses, Students, Media
- Scripts:
  - npm run dev (Vite dev server)
  - npm run build (TypeScript build + Vite build)
  - npm run preview (Preview built app)

## Build

- Backend: run `mvn -q -e -DskipTests package` at repo root to build services.
- Frontend: run `npm install` then `npm run dev` inside `frontend-app`.
