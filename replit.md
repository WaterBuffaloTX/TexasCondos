# Replit.md

## Overview

This is a full-stack web application for a Texas condominium regime attorney's practice. The application includes:
1. **Marketing Website**: Professional React-based site for lead generation and consultation scheduling
2. **Client Portal System**: Comprehensive project management portal with role-based access for clients, attorneys, surveyors, title companies, lenders, insurance agents, and real estate agents
3. **Project Workflow Management**: Multi-phase tracking system covering Engagement, Title Request, Survey Management, Declaration Drafting, and Transfer & Filing phases

The system serves as both a marketing tool and a complete project management solution for condominium regime creation and compliance in Texas.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Routing**: Wouter for client-side routing
- **Styling**: Tailwind CSS with custom design system
- **UI Components**: Radix UI primitives with shadcn/ui component library
- **Build Tool**: Vite for development and production builds
- **State Management**: TanStack React Query for server state management

### Backend Architecture
- **Runtime**: Node.js with Express.js
- **Language**: TypeScript with ESM modules
- **API Style**: RESTful API endpoints
- **Development**: TSX for TypeScript execution in development
- **Production**: ESBuild for server bundling

### Database Architecture
- **ORM**: Drizzle ORM for type-safe database operations
- **Database**: PostgreSQL (configured for Neon serverless)
- **Schema Management**: Drizzle Kit for migrations
- **Storage Interface**: Abstracted storage layer with in-memory fallback

## Key Components

### Frontend Components
- **Marketing Site**: Header with navigation, hero section, service sections, FAQ, contact form
- **Client Portal**: Multi-role dashboard with project phase navigation, document management, progress tracking
- **Interactive Elements**: Consultation modal, contact forms, mobile menu, Lexi AI widget, role-based access controls
- **UI Library**: Complete shadcn/ui component set (buttons, cards, dialogs, forms, tables, progress bars, etc.)

### Client Portal Features
- **Role-Based Access**: 7 distinct user roles (Client, Attorney, Surveyor, Title Company, Lender, Insurance Agent, Real Estate Agent)
- **Project Phases**: 5 comprehensive workflow stages with dedicated pages and functionality
- **Document Management**: Upload, review, approval, and revision tracking system
- **Progress Tracking**: Real-time project status with completion percentages and task management
- **Digital Workflows**: Signature tracking, payment processing, and delivery confirmation

### Backend Services
- **API Routes**: Consultation requests (`/api/consultation`) and contact messages (`/api/contact`)
- **Storage Layer**: Abstracted interface supporting both database and in-memory storage
- **Validation**: Zod schemas for form validation and type safety

### Database Schema
```sql
-- Users table for future authentication
users (id, username, password)

-- Client consultation requests
consultation_requests (id, firstName, lastName, email, phone, propertyAddress, projectType, projectDetails, contactMethod, createdAt)

-- General contact messages
contact_messages (id, name, email, phone, message, createdAt)
```

## Data Flow

1. **Client Interaction**: Users interact with the single-page React application
2. **Form Submissions**: Consultation and contact forms submit to Express API endpoints
3. **Validation**: Server validates incoming data using Zod schemas
4. **Storage**: Data is stored via the abstracted storage interface
5. **Response**: Success/error responses are returned to the client
6. **UI Updates**: React Query manages client-side state updates and error handling

## External Dependencies

### Core Dependencies
- **@neondatabase/serverless**: PostgreSQL database connection
- **drizzle-orm**: Type-safe ORM with PostgreSQL dialect
- **@tanstack/react-query**: Server state management
- **@radix-ui/***: Headless UI components
- **react-hook-form**: Form state management with validation
- **@hookform/resolvers**: Zod integration for form validation

### Development Tools
- **Vite**: Frontend build tool with React plugin
- **TSX**: TypeScript execution for development
- **ESBuild**: Production server bundling
- **Tailwind CSS**: Utility-first CSS framework

## Deployment Strategy

### Environment Configuration
- **Development**: TSX server execution with Vite frontend proxy
- **Production**: ESBuild bundled server serving static Vite build
- **Database**: PostgreSQL via Neon serverless (configured via DATABASE_URL)

### Replit Configuration
- **Modules**: Node.js 20, web server, PostgreSQL 16
- **Ports**: Local port 5000, external port 80
- **Build**: `npm run build` creates production assets
- **Run**: `npm run start` serves production application

### File Structure
```
client/          # React frontend application
server/          # Express.js backend
shared/          # Shared TypeScript schemas and types
migrations/      # Database migration files
dist/           # Production build output
```

## Changelog

```
Changelog:
- June 27, 2025. Initial setup
- June 27, 2025. Built comprehensive client portal system with role-based access for condominium regime project management
```

## User Preferences

```
Preferred communication style: Simple, everyday language.
```