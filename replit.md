# GenAI Legal Simplifier

## Overview

This is a full-stack web application that uses AI to analyze legal documents and provide simplified insights. Users can upload legal documents (PDF, TXT, DOC, DOCX) and receive AI-generated analysis including risk assessments, summaries, next steps, and document type classification. The application features a community section where users can view aggregated insights from document analyses.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React with TypeScript using Vite as the build tool
- **Routing**: Wouter for client-side routing with pages for landing, upload, results, and community
- **UI Components**: Shadcn/ui component library built on Radix UI primitives with Tailwind CSS for styling
- **State Management**: TanStack Query (React Query) for server state management and caching
- **Form Handling**: React Hook Form with Zod validation for type-safe form processing
- **File Upload**: React Dropzone for drag-and-drop file upload functionality

### Backend Architecture
- **Framework**: Express.js with TypeScript running on Node.js
- **API Design**: RESTful API with endpoints for document upload, retrieval, and analysis
- **File Processing**: Multer middleware for handling multipart file uploads with file type validation
- **Text Extraction**: Basic text extraction from uploaded files (simulated for demo purposes)
- **Data Storage**: In-memory storage implementation with interface for future database integration
- **Error Handling**: Centralized error handling middleware with structured error responses

### Data Storage Solutions
- **Current Implementation**: In-memory storage using Map data structures for documents and analyses
- **Database Schema**: Drizzle ORM schema defined for PostgreSQL with tables for documents and analyses
- **Schema Design**: 
  - Documents table stores file metadata, content, and upload timestamps
  - Analyses table stores AI-generated insights linked to documents via foreign key
  - JSON fields for storing arrays of risks and next steps

### Authentication and Authorization
- **Current State**: No authentication implemented (open access)
- **Session Management**: Express session configuration present but not actively used
- **Security**: Basic file upload restrictions and CORS handling

### AI Integration
- **Text Analysis**: Simulated AI analysis that generates document summaries, risk assessments, and next steps
- **Document Classification**: Automatic categorization of document types (lease agreements, contracts, etc.)
- **Risk Scoring**: Numerical risk assessment on a scale for quick evaluation

## External Dependencies

### Core Framework Dependencies
- **React Ecosystem**: React 18 with TypeScript, Vite for development and building
- **UI Framework**: Radix UI primitives for accessible components, Tailwind CSS for styling
- **Backend Framework**: Express.js with TypeScript support via tsx

### Database and ORM
- **Database**: PostgreSQL (configured but not actively used)
- **ORM**: Drizzle ORM with Drizzle Kit for migrations and schema management
- **Database Driver**: Neon Database serverless driver for PostgreSQL connections

### File Processing
- **File Upload**: Multer for handling multipart form data and file uploads
- **File Validation**: Built-in MIME type checking for document formats

### Development Tools
- **Build Tools**: Vite with React plugin, ESBuild for server-side bundling
- **TypeScript**: Full TypeScript support across frontend and backend
- **Development**: Replit-specific plugins for runtime error handling and cartographer

### Styling and UI
- **CSS Framework**: Tailwind CSS with custom design system
- **Icons**: Lucide React for consistent iconography
- **Fonts**: Google Fonts integration for typography
- **Component Variants**: Class Variance Authority for component styling patterns

### Utilities and Helpers
- **Date Handling**: date-fns for date manipulation and formatting
- **Validation**: Zod for runtime type validation and schema definition
- **Query Client**: TanStack Query for API state management and caching
- **Routing**: Wouter for lightweight client-side routing