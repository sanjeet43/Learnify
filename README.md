# Learning Management System(LMS)

## Overview

This Learning Management System is a web application built using Node.js, Express, and MongoDB. It allows users to register, log in, create courses, and manage their progress in various courses. The application also integrates with Cloudinary for media uploads and Stripe for payment processing.

## Features

- User authentication (registration, login, logout)
- Course creation and management
- Lecture management within courses
- User progress tracking for courses
- Media upload for course materials
- Payment processing via Stripe
- RESTful API endpoints

## Technologies Used

- **Backend**: Node.js, Express
- **Database**: MongoDB
- **Authentication**: JSON Web Tokens (JWT)
- **File Storage**: Cloudinary
- **Payment Processing**: Stripe
- **Middleware**: Multer for file uploads
- **Environment Variables**: dotenv

## Getting Started

### Prerequisites

- Node.js
- MongoDB
- Stripe account for payment processing
- Cloudinary account for media storage

### Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/sanjeet43/Learnify.git
   cd Learnify
   ```

2. Install dependencies:

   ```bash
   npm install
   ```

3. Create a `.env` file in the root directory and add the following environment variables:

   ```plaintext
   PORT=3000
   MONGODB_URI=<your-mongodb-uri>
   SECRET_KEY=<your-jwt-secret-key>
   API_KEY=<your-cloudinary-api-key>
   API_SECRET=<your-cloudinary-api-secret>
   CLOUD_NAME=<your-cloudinary-cloud-name>
   STRIPE_SECRET_KEY=<your-stripe-secret-key>
   STRIPE_PUBLISHABLE_KEY=<your-stripe-webhook-secret>
   ```

### Running the Application

To start the server, run:

```bash
npm start
```

The server will run on `http://localhost:3000`.

### API Endpoints

- **User Routes**

  - `POST /api/v1/user/register` - Register a new user
  - `POST /api/v1/user/login` - Log in a user
  - `GET /api/v1/user/logout` - Log out a user
  - `GET /api/v1/user/profile` - Get user profile
  - `PUT /api/v1/user/profile/update` - Update user profile

- **Course Routes**

  - `POST /api/v1/course` - Create a new course
  - `GET /api/v1/course` - Get all courses created by the user
  - `GET /api/v1/course/:courseId` - Get course details by ID
  - `PUT /api/v1/course/:courseId` - Edit course details
  - `POST /api/v1/course/:courseId/lecture` - Create a new lecture in a course

- **Media Routes**

  - `POST /api/v1/media/upload-video` - Upload a video file

- **Purchase Routes**
  - `POST /api/v1/purchase/checkout/create-checkout-session` - Create a checkout session for a course
  - `POST /api/v1/purchase/webhook` - Stripe webhook for payment status updates
