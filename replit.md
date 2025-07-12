# StackIt - Q&A Platform

## Overview

StackIt is a modern, minimalistic Q&A platform built to encourage collaborative learning and structured knowledge sharing within a community. The application features a clean design with a cream and orange color scheme, providing an intuitive user experience for asking questions, providing answers, and engaging with the community through voting and notifications.

**Security Status**: ✅ PRODUCTION READY - Comprehensive security audit completed (July 12, 2025) with all critical vulnerabilities fixed.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
The frontend is built using React with TypeScript, utilizing a modern component-based architecture:
- **Framework**: React 18 with TypeScript
- **Routing**: Wouter for lightweight client-side routing
- **Styling**: Tailwind CSS with custom cream/orange theme
- **UI Components**: Radix UI primitives with shadcn/ui components
- **State Management**: TanStack Query for server state management
- **Rich Text Editing**: TipTap editor for question and answer content
- **Build Tool**: Vite for fast development and optimized builds

### Backend Architecture
The backend follows a RESTful API design pattern:
- **Runtime**: Node.js with Express.js
- **Language**: TypeScript
- **Database ORM**: Drizzle ORM for type-safe database operations
- **Authentication**: Replit Auth with OpenID Connect integration
- **Session Management**: Express sessions with PostgreSQL storage
- **Real-time Features**: WebSocket support for live updates

### Database Design
PostgreSQL database with the following core entities:
- **Users**: Authentication and profile information
- **Questions**: Main content with voting, views, and tags
- **Answers**: Responses to questions with acceptance status
- **Tags**: Categorization system for questions
- **Votes**: User voting on questions and answers
- **Notifications**: Real-time user notifications
- **Sessions**: Authentication session storage

## Key Components

### Authentication System
- Replit Auth integration for secure user authentication
- OpenID Connect protocol implementation
- Session-based authentication with PostgreSQL storage
- Middleware for protecting authenticated routes

### Content Management
- Rich text editor using TipTap for creating questions and answers
- Tag system for categorizing content
- Vote system for community-driven content quality
- Answer acceptance mechanism for question resolution

### User Interface
- Responsive design with mobile-first approach
- Custom cream and orange color scheme
- shadcn/ui component library for consistent design
- Loading states and error handling throughout the application

### Real-time Features
- WebSocket integration for live updates
- Notification system for user engagement
- Real-time vote counting and content updates

### Personalization Features
- User tag preferences with localStorage and database persistence
- Trending tags based on question count and activity
- Explore more tags for discovering niche topics
- Personalized tag favorites with heart/unheart functionality
- Cross-session preference synchronization for authenticated users

## Data Flow

### Question Creation Flow
1. User navigates to /ask page (authentication required)
2. Form submission with title, content, and tags
3. Server validates input and creates question record
4. Database stores question with associated tags
5. User redirected to question detail page

### Voting System Flow
1. User clicks vote buttons on questions/answers
2. Client sends vote request with authentication
3. Server validates user permissions and updates vote counts
4. Database updates vote records and content scores
5. UI updates reflect new vote totals in real-time

### Notification Flow
1. Actions trigger notification creation (new answers, votes, etc.)
2. Server creates notification records in database
3. WebSocket pushes real-time updates to affected users
4. Client displays notification badges and dropdown

## External Dependencies

### Database
- **Neon Database**: Serverless PostgreSQL for production
- **Drizzle ORM**: Type-safe database operations and migrations

### Authentication
- **Replit Auth**: Integrated authentication service
- **OpenID Connect**: Industry-standard authentication protocol

### UI/UX Libraries
- **Radix UI**: Accessible component primitives
- **Tailwind CSS**: Utility-first CSS framework
- **TipTap**: Rich text editor with extensibility
- **Lucide React**: Icon library for consistent iconography

### Development Tools
- **Vite**: Fast build tool and development server
- **TypeScript**: Type safety and developer experience
- **ESBuild**: Fast JavaScript bundler for production

## Deployment Strategy

### Development Environment
- Vite development server with hot module replacement
- TypeScript compilation with strict type checking
- Replit-specific development tooling integration

### Production Build
- Vite builds optimized client bundle to `dist/public`
- ESBuild compiles server code to `dist/index.js`
- Static assets served from Express server
- Environment variables for database and authentication configuration

### Database Management
- Drizzle migrations for schema versioning
- Push-based deployment with `db:push` command
- Connection pooling with Neon serverless database

### Authentication Configuration
- Replit Auth integration with environment variables
- OIDC configuration with automatic discovery
- Session security with HTTP-only cookies and CSRF protection

The application is designed as a production-ready prototype that demonstrates clear value proposition through its clean interface, robust feature set, and scalable architecture suitable for community-driven Q&A platforms.