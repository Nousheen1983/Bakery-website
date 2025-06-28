# SweetCrumbs Bakery Website

## Overview

SweetCrumbs is a full-stack web application for an artisan bakery website built with modern web technologies. The application features a beautiful marketing website with contact form functionality, built using React for the frontend and Express.js for the backend, with PostgreSQL database integration using Drizzle ORM.

## System Architecture

The application follows a monorepo structure with clear separation between client, server, and shared code:

- **Frontend**: React 18 with TypeScript, using Vite as the build tool
- **Backend**: Express.js server with TypeScript
- **Database**: PostgreSQL with Drizzle ORM for schema management
- **Styling**: Tailwind CSS with shadcn/ui component library
- **Deployment**: Configured for Replit autoscale deployment

## Key Components

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Build Tool**: Vite with custom development server setup
- **Routing**: Wouter for lightweight client-side routing
- **State Management**: TanStack Query for server state management
- **UI Components**: shadcn/ui component library built on Radix UI primitives
- **Styling**: Tailwind CSS with custom bakery-themed color palette
- **Animations**: Framer Motion for smooth animations and transitions
- **Forms**: React Hook Form with Zod validation

### Backend Architecture
- **Server**: Express.js with TypeScript
- **Database ORM**: Drizzle ORM with PostgreSQL
- **Session Management**: Prepared for session storage with connect-pg-simple
- **API Design**: RESTful API endpoints for contact form submissions
- **Error Handling**: Centralized error handling middleware
- **Request Logging**: Custom request/response logging middleware

### Database Schema
The application uses two main tables:
- **users**: Basic user authentication structure (id, username, password)
- **contact_messages**: Stores contact form submissions (id, name, email, subject, message, created_at)

### UI/UX Design
- **Theme**: Warm bakery aesthetic with cream, blush, and warm brown color palette
- **Typography**: Playfair Display for headings, Inter for body text
- **Responsive Design**: Mobile-first approach with responsive breakpoints
- **Accessibility**: Built on Radix UI primitives for accessibility compliance

## Data Flow

1. **Contact Form Submission**:
   - User fills out contact form on frontend
   - Form data validated using Zod schema
   - POST request sent to `/api/contact` endpoint
   - Server validates and stores message in database
   - Success/error response sent back to client
   - Toast notification displayed to user

2. **Message Retrieval**:
   - Admin endpoint `/api/contact-messages` retrieves all messages
   - Currently uses in-memory storage in development
   - Will use PostgreSQL database when properly configured

## External Dependencies

### Frontend Dependencies
- **@tanstack/react-query**: Server state management and caching
- **framer-motion**: Animation library for smooth UI transitions
- **react-hook-form**: Form state management and validation
- **@hookform/resolvers**: Zod resolver for form validation
- **wouter**: Lightweight routing library
- **shadcn/ui components**: Pre-built accessible UI components
- **tailwindcss**: Utility-first CSS framework

### Backend Dependencies
- **express**: Web application framework
- **drizzle-orm**: TypeScript ORM for database operations
- **@neondatabase/serverless**: PostgreSQL driver for serverless environments
- **connect-pg-simple**: PostgreSQL session store (configured but not active)
- **zod**: Schema validation library

### Development Dependencies
- **vite**: Build tool and development server
- **typescript**: Type checking and compilation
- **tailwindcss**: CSS framework
- **drizzle-kit**: Database migration and schema management tool

## Deployment Strategy

The application is configured for deployment on Replit with the following setup:

- **Environment**: Node.js 20 with PostgreSQL 16 module
- **Build Process**: 
  - Frontend: Vite build process outputs to `dist/public`
  - Backend: esbuild bundles server code to `dist/index.js`
- **Production Server**: Serves static files and API endpoints
- **Development**: Hot module replacement with Vite dev server
- **Port Configuration**: Runs on port 5000 internally, exposed on port 80

### Database Setup
- Drizzle configuration points to PostgreSQL database
- Schema migrations stored in `./migrations` directory
- Database URL expected in `DATABASE_URL` environment variable

## Changelog

```
Changelog:
- June 27, 2025. Initial setup
```

## User Preferences

```
Preferred communication style: Simple, everyday language.
```