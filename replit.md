# Overview

This is a modern web-based RPG chat application built as a full-stack TypeScript project. The application combines real-time chat functionality with RPG game mechanics, allowing users to create characters, participate in quests, engage in PvP combat, trade items in a marketplace, and interact through a chat system with role-playing commands. The project features a React frontend with a comprehensive UI component library, an Express.js backend with WebSocket support for real-time features, and uses PostgreSQL with Drizzle ORM for data persistence.

# User Preferences

Preferred communication style: Simple, everyday language.

# System Architecture

## Frontend Architecture
The client is built with React 18 using TypeScript and Vite as the build tool. The UI is constructed using a comprehensive component library based on Radix UI primitives with Tailwind CSS for styling, following the shadcn/ui design system. State management utilizes React Query for server state and React Context for authentication. Routing is handled by Wouter for a lightweight client-side routing solution.

The application follows a modular component structure with dedicated sections for character management, chat functionality, quest systems, inventory management, marketplace, PvP rankings, and admin panels. Real-time updates are managed through WebSocket connections with automatic reconnection logic.

## Backend Architecture
The server uses Express.js with TypeScript, implementing a RESTful API alongside WebSocket connections for real-time features. The architecture follows a layered approach with route handlers, storage abstraction, and middleware for authentication using JWT tokens. Password security is handled with bcrypt for hashing.

WebSocket integration provides real-time chat messaging, game updates, and notification systems. The server includes comprehensive logging middleware and error handling with proper HTTP status codes and JSON responses.

## Database Design
Data persistence uses PostgreSQL as the primary database with Drizzle ORM for type-safe database operations. The schema includes entities for users, characters, chat rooms and messages, quests and user quest progress, items and user inventory, and marketplace listings.

The database design supports complex RPG mechanics including character stats (HP, MP, experience, gold), quest progression tracking, item rarity systems, and PvP statistics. Foreign key relationships maintain data integrity across the gaming ecosystem.

## Authentication & Authorization
Authentication is implemented using JWT tokens stored in localStorage on the client side. The system includes user registration and login endpoints with password hashing. Protected routes use middleware to verify tokens and attach user context to requests.

Authorization includes basic admin role checking for administrative functions like creating quests and items. The WebSocket connection also requires token-based authentication for real-time features.

# External Dependencies

## Database
- **PostgreSQL**: Primary database system configured through Drizzle ORM
- **Neon Database**: Serverless PostgreSQL provider (@neondatabase/serverless)
- **Drizzle Kit**: Database migration and schema management tool

## UI Framework & Styling
- **Radix UI**: Comprehensive set of accessible UI primitives for components
- **Tailwind CSS**: Utility-first CSS framework for styling
- **shadcn/ui**: Pre-built component library with design system
- **Lucide React**: Icon library for consistent iconography

## Real-time Communication
- **WebSocket (ws)**: Native WebSocket implementation for real-time chat and game updates
- **React Query**: Server state management and caching for API interactions

## Development Tools
- **Vite**: Fast build tool and development server
- **TypeScript**: Type safety across the entire application
- **ESBuild**: Fast JavaScript bundler for production builds

## Authentication & Security
- **bcrypt**: Password hashing for secure user authentication
- **jsonwebtoken**: JWT token generation and verification
- **express-session**: Session management capabilities

## Additional Services
- **Replit Integration**: Development environment integration with cartographer and runtime error modal plugins
- **Google Fonts**: Typography using Inter and JetBrains Mono font families