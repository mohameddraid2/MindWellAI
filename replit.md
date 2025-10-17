# Mental Health AI Analysis Platform

## Overview

This is a mental health assessment web application that provides AI-powered analysis of users' mental wellbeing. Users complete a questionnaire about their mood, stress levels, sleep quality, and other mental health indicators, then receive compassionate, non-diagnostic feedback with personalized recommendations. The platform emphasizes emotional safety, accessibility, and reducing mental health stigma through thoughtful design inspired by leading wellness platforms like Calm and Headspace.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture

**Framework & Build System:**
- React with TypeScript for type-safe component development
- Vite as the build tool and development server for fast hot module replacement
- Wouter for lightweight client-side routing (single-page application with / and 404 routes)

**UI Component System:**
- shadcn/ui component library (New York style variant) providing pre-built, accessible React components
- Radix UI primitives for accessibility-compliant interactive elements
- Tailwind CSS for utility-first styling with custom design tokens
- Class Variance Authority (CVA) for managing component variants
- Google Fonts (Inter) for consistent, readable typography

**State Management & Data Fetching:**
- TanStack Query (React Query) for server state management, caching, and API request handling
- React Hook Form with Zod resolver for form validation and state management
- Custom hooks pattern for reusable logic (use-mobile, use-toast)

**Design System:**
- Comprehensive theming with light/dark mode support via CSS custom properties
- Calming color palette focused on trust and emotional safety (blues, teals, soft neutrals)
- Accessible spacing system using Tailwind's 4px grid
- Custom design guidelines documented in design_guidelines.md for maintaining visual consistency

### Backend Architecture

**Server Framework:**
- Express.js REST API server
- TypeScript for type safety across the full stack
- Custom middleware for request logging and error handling
- Development-only Vite integration for seamless HMR during development

**API Design:**
- RESTful endpoint structure (/api/analyze for mental health assessment)
- Zod schema validation for request/response payloads ensuring type safety
- Structured error handling with appropriate HTTP status codes
- JSON-based request/response format

**AI Integration:**
- OpenAI GPT-5 integration for mental health analysis
- Structured prompts designed for compassionate, non-diagnostic responses
- Parsed JSON responses with risk levels, findings, and actionable recommendations
- Safety measures emphasizing the tool is for insights, not medical diagnosis

### Data Storage Solutions

**Current Implementation:**
- In-memory storage (MemStorage class) for user data
- Interface-based storage abstraction (IStorage) allowing easy migration to persistent databases
- No assessment history storage - each analysis is stateless

**Database Schema (Prepared):**
- Drizzle ORM configured for PostgreSQL with Neon Database serverless driver
- Schema defined in TypeScript with Zod integration for runtime validation
- Migration system configured via drizzle-kit
- User model prepared but not actively used in current implementation

**Rationale:** The application currently operates statelessly without persisting assessment data, prioritizing user privacy. The database infrastructure is prepared for future features like user accounts, assessment history, or progress tracking.

### External Dependencies

**AI Services:**
- OpenAI API (GPT-5 model) - Core service for mental health analysis, providing empathetic assessments and recommendations

**Database & Hosting:**
- Neon Database (@neondatabase/serverless) - Serverless PostgreSQL configured but not actively used
- Prepared for deployment on Replit infrastructure

**Development Tools:**
- Replit-specific plugins for enhanced development experience (cartographer, dev-banner, runtime-error-modal)
- TypeScript compiler for type checking
- ESBuild for production server bundling

**UI Libraries:**
- Comprehensive Radix UI component collection for accessible interactions
- Embla Carousel for potential multi-step forms or content display
- Lucide React for consistent iconography
- date-fns for any date formatting needs

**Styling & Utilities:**
- Tailwind CSS with PostCSS for processing
- clsx and tailwind-merge for conditional class management

**Rationale for Architecture Choices:**
- **React + Vite + TypeScript:** Provides modern developer experience with fast builds, type safety, and excellent tooling
- **Shadcn/ui + Radix:** Delivers accessible, customizable components without heavy framework lock-in
- **Express REST API:** Simple, well-understood pattern suitable for the straightforward API needs
- **Stateless design:** Prioritizes user privacy by not storing sensitive mental health data
- **OpenAI integration:** Leverages state-of-the-art language models for nuanced, compassionate analysis while maintaining clear boundaries about non-diagnostic nature