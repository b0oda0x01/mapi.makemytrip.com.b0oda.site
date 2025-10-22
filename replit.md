# Web Crawler Testing Hub

## Overview

This is a web crawler testing environment designed to validate link checking tools and web crawlers. The application provides a 25-page test suite with intentionally mixed static resources (working and broken links) across different categories including business, technology, education, lifestyle, and entertainment. Each page contains a mixture of working and broken static file references (JS, CSS, images) to test crawler detection capabilities.

The application serves as a controlled testing ground where developers can validate their web crawling tools against known broken links and resources, with a sitemap, robots.txt, and API endpoints to retrieve broken file information.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture

**Framework**: React with TypeScript using Vite as the build tool and development server

**Routing**: Wouter for client-side routing (lightweight React router alternative)

**UI Component System**: 
- Shadcn UI components (New York style variant)
- Radix UI primitives for accessible, unstyled components
- Tailwind CSS for styling with custom design tokens
- Class Variance Authority (CVA) for component variant management

**State Management**:
- TanStack Query (React Query) for server state and API data fetching
- React hooks for local component state
- Custom hooks for mobile detection and toast notifications

**Design System**:
- Bootstrap-inspired minimal approach
- Custom color palette supporting light/dark modes
- Typography: Inter (primary) and JetBrains Mono (monospace)
- Spacing system based on Tailwind units

### Backend Architecture

**Server Framework**: Express.js running on Node.js

**Server-Side Rendering**: Vite middleware mode for development with HMR support

**API Endpoints**:
- `/api/broken-files` - Returns list and statistics of all broken static file references
- `/sitemap.xml` - Dynamic XML sitemap generation for all pages
- `/robots.txt` - Robots.txt file for crawler testing

**Logging**: Custom request/response logging middleware for API routes

### Data Storage Solutions

**Database ORM**: Drizzle ORM configured for PostgreSQL via Neon serverless driver

**Schema Location**: `shared/schema.ts` contains TypeScript interfaces and Zod schemas

**Storage Pattern**: 
- In-memory storage implementation (`MemStorage` class) for user data
- Interface-based storage abstraction (`IStorage`) for potential future database implementation
- Currently uses Map-based storage for users

**Data Models**:
- `PageInfo` - Page metadata (25 pages with paths, titles, categories, descriptions)
- `StaticFile` - Static resource references with broken/working status
- `User` - User authentication data (stored in memory)

### Authentication and Authorization

**Session Management**: Express sessions with connect-pg-simple for PostgreSQL session storage

**User Storage**: In-memory user store with interface for future database persistence

**Session Configuration**: Configured for PostgreSQL but currently using memory store as fallback

### External Dependencies

**UI Component Libraries**:
- Radix UI primitives (accordion, dialog, dropdown, select, tabs, toast, tooltip, etc.)
- Embla Carousel for carousels
- Lucide React for icons
- CMDK for command palette
- Vaul for drawer components

**Data Fetching & Forms**:
- TanStack Query for API data management
- React Hook Form with Zod resolvers for form validation
- Date-fns for date manipulation

**Styling**:
- Tailwind CSS with PostCSS
- Tailwind Merge and CLSX for class merging
- Google Fonts (Inter, JetBrains Mono) via CDN

**CDN Resources**:
- Font Awesome 6.5.1 for icons
- Lodash 4.17.21 for utilities

**Database**:
- Neon Serverless PostgreSQL driver
- Drizzle ORM with Drizzle Kit for migrations
- Drizzle Zod for schema validation

**Development Tools**:
- Replit-specific plugins (vite-plugin-runtime-error-modal, cartographer, dev-banner)
- TypeScript for type safety
- ESBuild for production server bundling

**Build Process**:
- Development: TSX for running TypeScript directly
- Production: Vite builds client, ESBuild bundles server with ESM output
- Database: Drizzle Kit for schema management and migrations