# Overview

This is a disc golf score tracking application called "Kicked in the Disc" built with a modern full-stack architecture. The application allows users to create accounts, host games, join games using game codes, track scores in real-time, and view game results. The system supports multiplayer disc golf games with live updates and interactive gameplay features.

# User Preferences

Preferred communication style: Simple, everyday language.

# System Architecture

## Frontend Architecture
- **Framework**: React with TypeScript using Vite as the build tool
- **UI Components**: Radix UI primitives with shadcn/ui component library
- **Styling**: Tailwind CSS with custom CSS variables for theming
- **Routing**: Wouter for client-side routing
- **State Management**: React hooks with custom state management for game logic
- **Real-time Updates**: WebSocket connections for live game updates
- **Data Fetching**: TanStack Query for server state management

## Backend Architecture
- **Runtime**: Node.js with Express.js server
- **Language**: TypeScript with ES modules
- **WebSocket Server**: ws library for real-time game communication
- **Development**: Hot module replacement with Vite middleware in development
- **Build System**: ESBuild for production builds

## Authentication & User Management
- **Primary Auth**: Firebase Authentication for user registration and login
- **Session Management**: Firebase handles user sessions and token management
- **User Data**: Firebase Realtime Database stores user profiles and hosting privileges

## Data Storage Solutions
- **Primary Database**: Dual storage approach
  - PostgreSQL with Drizzle ORM for structured data (configured but may not be actively used)
  - Firebase Realtime Database for real-time game data and user management
- **In-Memory Storage**: Memory-based storage implementation as fallback/development option
- **Schema Management**: Drizzle migrations for PostgreSQL schema versioning

## Real-time Communication
- **WebSocket Server**: Custom WebSocket implementation for game state synchronization
- **Connection Management**: User ID-based connection mapping for targeted messaging
- **Message Types**: Structured message protocol for game events (join_game, update_score, etc.)
- **Broadcasting**: Game-specific message broadcasting to all players in a game

## Game State Management
- **Game Phases**: Lobby → Playing → Finished state machine
- **Score Tracking**: Real-time score updates with par calculations
- **Player Management**: Host privileges, ready states, and player metadata
- **Game Codes**: 6-character alphanumeric codes for easy game joining

## Development Configuration
- **Code Quality**: TypeScript strict mode with comprehensive type checking
- **Build Pipeline**: Separate client and server build processes
- **Path Aliases**: Configured aliases for clean imports (@, @shared, @assets)
- **Development Tools**: Runtime error overlay and Replit-specific tooling integration

# External Dependencies

## Firebase Services
- **Firebase Authentication**: User registration, login, and session management
- **Firebase Realtime Database**: Real-time game state storage and synchronization
- **Configuration**: Environment-based Firebase project configuration

## Database Systems
- **Neon Database**: PostgreSQL hosting service (configured via DATABASE_URL)
- **Drizzle ORM**: Type-safe database operations and migrations
- **Connection**: PostgreSQL dialect with connection pooling

## UI and Styling
- **Radix UI**: Comprehensive set of accessible React components
- **Tailwind CSS**: Utility-first CSS framework with custom design system
- **Lucide React**: Icon library for consistent iconography

## Development and Build Tools
- **Vite**: Fast build tool and development server
- **TypeScript**: Static type checking and enhanced developer experience
- **ESBuild**: Fast JavaScript bundler for production builds
- **PostCSS**: CSS processing with Tailwind and Autoprefixer

## Real-time Communication
- **WebSocket (ws)**: Low-level WebSocket server implementation
- **TanStack Query**: Efficient server state management and caching

## Session and State Management
- **connect-pg-simple**: PostgreSQL session store for Express sessions
- **React Hook Form**: Form validation and management with Zod schema validation