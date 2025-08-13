# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Next.js dashboard application built as part of the Next.js App Router Course. It's a full-stack application with PostgreSQL database integration, TypeScript, and Tailwind CSS for styling.

## Development Commands

- `npm run dev` - Start development server with Turbopack for faster builds
- `npm run build` - Build the application for production
- `npm start` - Start production server

## Project Architecture

### Database Layer
- Uses PostgreSQL with the `postgres` library for direct SQL queries (no ORM)
- Database connection configured via `POSTGRES_URL` environment variable with SSL required
- All data access functions are in `app/lib/data.ts` with proper error handling and TypeScript types

### Type System
- Comprehensive TypeScript types defined in `app/lib/definitions.ts`
- Types cover all data models: User, Customer, Invoice, Revenue
- Includes both raw database types and formatted presentation types

### UI Structure
- Follows Next.js App Router convention with `app/` directory
- UI components organized in `app/ui/` with feature-specific subdirectories:
  - `dashboard/` - Dashboard-specific components
  - `invoices/` - Invoice management components
  - `customers/` - Customer-related components
- Global styles in `app/ui/global.css` with Tailwind CSS
- Custom fonts configured in `app/ui/fonts.tsx`

### Key Features
- Invoice management with CRUD operations
- Customer management and search
- Revenue tracking and visualization
- Pagination for large datasets (6 items per page)
- Search functionality across multiple fields using PostgreSQL ILIKE

### Styling
- Tailwind CSS with custom configuration
- Custom color palette (blue variants: 400, 500, 600)
- Custom grid template for 13 columns
- Shimmer animation keyframes for loading states
- @tailwindcss/forms plugin enabled

## Environment Requirements

- PostgreSQL database with `POSTGRES_URL` environment variable
- SSL connection required for database
- Uses pnpm as package manager (see pnpm-lock.yaml and pnpm config in package.json)