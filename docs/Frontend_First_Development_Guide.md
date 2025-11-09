# Frontend-First Development Guide

## Overview

This guide defines the recommended development approach for user-facing web applications using APM Enhanced v0.5.2. The frontend-first methodology prioritizes UI/UX development with mock data before backend implementation, ensuring user validation early while maintaining technical feasibility through API contract definition.

---

## When to Use Frontend-First Approach

### ✅ Recommended For:

- **SaaS products** with significant UI/UX requirements

- **Dashboard applications** and admin panels

- **B2C web applications** where user experience drives product success

- **Component-driven architectures** (Next.js, React, Vue)

- **MVPs and prototypes** requiring rapid user validation

- **Projects with design-first workflows** (Figma → Development)

### ⚠️ Consider Alternatives For:

- **API-first products** (B2B integrations, backend services)

- **Data-heavy applications** where backend structure dictates UI possibilities

- **Performance-critical systems** with significant backend constraints

- **Complex business logic systems** where backend feasibility is uncertain

---

## Phase Structure

### Phase 0: Infrastructure Setup

**Automated by APM Enhanced Infrastructure Setup Agent**

Configures:

- MCP servers (Supabase, GitHub, Context7)

- Payment providers (Stripe, PayPal, Square, Paddle)

- Development environment

- Environment variables

- Version detection and documentation

**Duration:** 5-10 minutes (automated)

---

### Phase 1: Design System & Component Library

**Objective:** Establish visual foundation and reusable components before feature development.

**Task Structure:**

**Phase 1: Design System & Component Library**

**Task 1.1: Design Tokens & Tailwind Configuration**

**Type:** Configuration & Setup

**Complexity:** Simple

**Recommended Model:** Haiku 4.5 or GPT-5 High

**Deliverables:**

- Configure Tailwind CSS with project-specific design tokens

- Define color palette (primary, secondary, accent, neutral, semantic)

- Setup typography scale (headings, body, captions)

- Configure spacing, border radius, shadows

**Files Created:**

- `tailwind.config.ts` (extended configuration)

- `app/globals.css` (CSS variables for design tokens)

- `lib/design-tokens.ts` (TypeScript design token exports)

**Task 1.2: Component Library Setup (Shadcn UI)**

**Type:** Library Integration

**Complexity:** Simple

**Recommended Model:** Haiku 4.5

**Deliverables:**

- Install and configure Shadcn UI

- Setup component customization approach

- Configure component.json for project structure

- Install core components (button, input, card, dialog, dropdown)

**Files Created:**

- `components/ui/` (Shadcn base components)

- `components.json` (Shadcn configuration)

- `lib/utils.ts` (cn utility and helpers)

**Task 1.3: Custom Component Library**

**Type:** Component Development

**Complexity:** Moderate

**Recommended Model:** GPT-5 High or Sonnet 4.5

**Deliverables:**

- Build project-specific composed components

- Create layout components (Header, Sidebar, Footer, Container)

- Implement form components (FormInput, FormSelect, FormCheckbox)

- Build feedback components (Toast, Alert, LoadingSpinner)

- Create data display components (Table, Card, Badge, Avatar)

**Files Created:**

- `components/layout/` (layout components)

- `components/forms/` (form components)

- `components/feedback/` (feedback components)

- `components/data-display/` (data display components)

**Testing:**

- Create Storybook or component showcase page

- Verify responsive behavior

- Test accessibility (keyboard navigation, screen readers)

**Task 1.4: Design System Documentation**

**Type:** Documentation

**Complexity:** Simple

**Recommended Model:** Haiku 4.5

**Deliverables:**

- Document design tokens usage

- Create component usage examples

- Document composition patterns

- Accessibility guidelines

**Files Created:**

- `docs/design-system.md`

- `app/components-showcase/page.tsx` (optional demo page)

**Phase 1 Duration:** 2-3 development sessions

---

### Phase 2: UI Implementation with Mock Data

**Objective:** Build all user-facing interfaces with mock data to validate UX and define data requirements.

**Task Structure:**

**Phase 2: UI Implementation with Mock Data**

**Task 2.1: API Contract Definition**

**Type:** Planning & Documentation

**Complexity:** Moderate

**Recommended Model:** GPT-5 High or Sonnet 4.5

**Deliverables:**

- Define API endpoints based on UI requirements

- Document request/response schemas

- Create TypeScript types for all API interactions

- Define authentication flow and protected routes

**Files Created:**

- `types/api.ts` (API type definitions)

- `docs/api-contract.md` (API documentation)

- `lib/api/types.ts` (shared types)

**Task 2.2: Mock API Setup (MSW)**

**Type:** Tooling Setup

**Complexity:** Moderate

**Recommended Model:** GPT-5 High

**Deliverables:**

- Install and configure Mock Service Worker (MSW)

- Create mock handlers for all API endpoints

- Setup realistic mock data generators

- Configure MSW for development environment

**Files Created:**

- `mocks/handlers.ts` (MSW request handlers)

- `mocks/data/` (mock data generators)

- `mocks/browser.ts` (MSW browser configuration)

- `app/layout.tsx` (updated with MSW provider)

**Task 2.3: Authentication & Protected Routes**

**Type:** Feature Implementation

**Complexity:** Moderate

**Recommended Model:** Sonnet 4.5

**Deliverables:**

- Build login/signup pages with mock auth

- Implement auth context and session management

- Create protected route middleware

- Build user profile and settings pages

**Files Created:**

- `app/(auth)/login/page.tsx`

- `app/(auth)/signup/page.tsx`

- `contexts/AuthContext.tsx`

- `middleware.ts` (route protection)

- `app/(protected)/profile/page.tsx`

- `app/(protected)/settings/page.tsx`

**Task 2.4: Core Feature Pages (Dashboard)**

**Type:** Feature Implementation

**Complexity:** Complex

**Recommended Model:** Sonnet 4.5

**Deliverables:**

- Build main dashboard layout

- Implement data visualization components

- Create feature-specific pages

- Implement navigation and routing

**Files Created:**

- `app/(protected)/dashboard/page.tsx`

- `app/(protected)/[feature]/page.tsx`

- `components/dashboard/` (dashboard-specific components)

**Task 2.5: Forms & Data Entry**

**Type:** Feature Implementation

**Complexity:** Moderate

**Recommended Model:** GPT-5 High or Sonnet 4.5

**Deliverables:**

- Build all data entry forms

- Implement form validation (React Hook Form + Zod)

- Create form submission with mock API

- Implement optimistic UI updates

**Files Created:**

- `app/(protected)/[feature]/new/page.tsx`

- `app/(protected)/[feature]/[id]/edit/page.tsx`

- `lib/validations/` (Zod schemas)

- `hooks/useForm.ts` (form utilities)

**Task 2.6: Interactive Features & State Management**

**Type:** Feature Implementation

**Complexity:** Complex

**Recommended Model:** Sonnet 4.5

**Deliverables:**

- Implement search, filtering, sorting

- Build pagination components

- Create modal/drawer interactions

- Setup client-side state management (Zustand/Jotai if needed)

**Files Created:**

- `components/search/` (search components)

- `components/filters/` (filter components)

- `hooks/useSearch.ts`, `hooks/useFilters.ts`

- `store/` (state management if needed)

**Phase 2 Duration:** 4-6 development sessions

---

### Phase 3: Backend API Development

**Objective:** Implement backend APIs according to contract defined in Phase 2.

**Task Structure:**

**Phase 3: Backend API Development**

**Task 3.1: Database Schema & Migrations**

**Type:** Database Design

**Complexity:** Moderate

**Recommended Model:** Sonnet 4.5

**Deliverables:**

- Design database schema (Supabase/PostgreSQL)

- Create migrations

- Setup database types generation

- Create seed data for development

**Files Created:**

- `supabase/migrations/` (SQL migrations)

- `types/database.ts` (generated types)

- `supabase/seed.sql` (seed data)

**Task 3.2: Authentication API**

**Type:** API Implementation

**Complexity:** Moderate

**Recommended Model:** Sonnet 4.5

**Deliverables:**

- Implement Supabase auth integration

- Create session management utilities

- Build protected API routes

- Implement role-based access control (if needed)

**Files Created:**

- `lib/supabase/auth.ts` (auth utilities)

- `app/api/auth/[...supabase]/route.ts` (auth endpoints)

- `middleware.ts` (updated with real auth)

**Task 3.3: CRUD API Endpoints**

**Type:** API Implementation

**Complexity:** Moderate to Complex

**Recommended Model:** Sonnet 4.5

**Deliverables:**

- Implement all CRUD endpoints per API contract

- Add input validation (Zod)

- Implement error handling

- Add API route protection

**Files Created:**

- `app/api/[resource]/route.ts` (GET, POST)

- `app/api/[resource]/[id]/route.ts` (GET, PATCH, DELETE)

- `lib/api/[resource].ts` (business logic)

**Task 3.4: Payment Integration (Stripe)**

**Type:** API Implementation

**Complexity:** Complex

**Recommended Model:** Sonnet 4.5

**Deliverables:**

- Implement Stripe checkout endpoints

- Setup webhook handlers

- Create subscription management

- Implement payment verification

**Files Created:**

- `app/api/checkout/route.ts`

- `app/api/webhooks/stripe/route.ts`

- `lib/stripe/checkout.ts`

- `lib/stripe/webhooks.ts`

**Task 3.5: API Testing & Documentation**

**Type:** Testing & Documentation

**Complexity:** Simple to Moderate

**Recommended Model:** GPT-5 High

**Deliverables:**

- Write API integration tests

- Document all endpoints (OpenAPI/Swagger)

- Create Postman/Thunder Client collection

- Setup API monitoring

**Files Created:**

- `tests/api/` (API tests)

- `docs/api.md` (API documentation)

- `postman/collection.json` (API collection)

**Phase 3 Duration:** 4-6 development sessions

---

### Phase 4: Frontend-Backend Integration

**Objective:** Replace mock APIs with real backend, handle edge cases, optimize performance.

**Task Structure:**

**Phase 4: Frontend-Backend Integration**

**Task 4.1: Remove MSW & Connect Real APIs**

**Type:** Integration

**Complexity:** Moderate

**Recommended Model:** GPT-5 High or Sonnet 4.5

**Deliverables:**

- Remove MSW configuration

- Update API client to use real endpoints

- Implement real Supabase client queries

- Handle authentication state with real sessions

**Files Modified:**

- `app/layout.tsx` (remove MSW provider)

- `lib/api/client.ts` (updated to real endpoints)

- `contexts/AuthContext.tsx` (real auth integration)

- Delete `mocks/` directory

**Task 4.2: Error Handling & Loading States**

**Type:** Polish & UX

**Complexity:** Moderate

**Recommended Model:** GPT-5 High

**Deliverables:**

- Implement comprehensive error boundaries

- Add loading skeletons and spinners

- Handle network errors gracefully

- Implement retry logic

- Add toast notifications for API feedback

**Files Created/Modified:**

- `components/error-boundary.tsx`

- `components/loading/` (loading components)

- `hooks/useApi.ts` (API hook with error handling)

- `lib/api/errors.ts` (error utilities)

**Task 4.3: Real-time Features (if applicable)**

**Type:** Feature Enhancement

**Complexity:** Complex

**Recommended Model:** Sonnet 4.5

**Deliverables:**

- Implement Supabase real-time subscriptions

- Add optimistic UI updates

- Handle real-time synchronization

- Implement presence indicators

**Files Created:**

- `hooks/useRealtime.ts`

- `lib/supabase/realtime.ts`

**Task 4.4: Performance Optimization**

**Type:** Optimization

**Complexity:** Moderate

**Recommended Model:** GPT-5 High or Sonnet 4.5

**Deliverables:**

- Implement data caching (React Query/SWR)

- Add image optimization

- Implement route prefetching

- Optimize bundle size

- Add performance monitoring

**Files Created/Modified:**

- `lib/api/cache.ts` (caching configuration)

- `next.config.js` (updated optimizations)

- `app/layout.tsx` (analytics integration)

**Phase 4 Duration:** 2-3 development sessions

---

### Phase 5: Testing & Optimization

**Objective:** Comprehensive testing, accessibility, SEO, performance tuning.

**Task Structure:**

**Phase 5: Testing & Optimization**

**Task 5.1: Unit & Integration Testing**

**Type:** Testing

**Complexity:** Moderate

**Recommended Model:** GPT-5 High

**Deliverables:**

- Write component unit tests (Jest + Testing Library)

- Write integration tests for critical flows

- Setup test coverage reporting

- Implement CI/CD test automation

**Files Created:**

- `tests/components/` (component tests)

- `tests/integration/` (integration tests)

- `jest.config.js`, `jest.setup.js`

**Task 5.2: E2E Testing**

**Type:** Testing

**Complexity:** Complex

**Recommended Model:** Sonnet 4.5

**Deliverables:**

- Setup Playwright or Cypress

- Write E2E tests for critical user flows

- Implement visual regression testing

- Setup E2E test automation

**Files Created:**

- `tests/e2e/` (E2E tests)

- `playwright.config.ts` or `cypress.config.ts`

**Task 5.3: Accessibility Audit**

**Type:** Quality Assurance

**Complexity:** Moderate

**Recommended Model:** GPT-5 High

**Deliverables:**

- Run automated accessibility tests (axe, Lighthouse)

- Fix accessibility issues

- Implement keyboard navigation

- Add ARIA labels where needed

- Test with screen readers

**Files Modified:**

- Various component files (accessibility fixes)

- `docs/accessibility.md` (accessibility documentation)

**Task 5.4: SEO Optimization**

**Type:** Optimization

**Complexity:** Simple to Moderate

**Recommended Model:** GPT-5 High

**Deliverables:**

- Implement meta tags and OpenGraph

- Setup sitemap generation

- Add robots.txt

- Implement structured data (Schema.org)

- Optimize Core Web Vitals

**Files Created/Modified:**

- `app/layout.tsx`, `app/page.tsx` (metadata)

- `app/sitemap.ts` (sitemap generation)

- `public/robots.txt`

**Task 5.5: Performance Tuning & Launch Prep**

**Type:** Optimization

**Complexity:** Moderate

**Recommended Model:** Sonnet 4.5

**Deliverables:**

- Run Lighthouse audits

- Optimize images and assets

- Implement lazy loading

- Setup error tracking (Sentry)

- Setup analytics (PostHog, Plausible)

- Configure production environment variables

**Files Created/Modified:**

- `next.config.js` (production optimizations)

- `lib/analytics.ts` (analytics setup)

- `lib/sentry.ts` (error tracking)

- `.env.production` (production config)

**Phase 5 Duration:** 2-4 development sessions

---

## Setup Agent Integration

### Context Synthesis Prompts

When Setup Agent detects a user-facing web application project, guide them to specify:

**Development Approach Question:**

What development approach would you prefer for this project?

- **Frontend-First** (Recommended for user-facing apps)
  - Build UI with mock data first
  - Validate UX early
  - Backend implements to UI requirements

- **Backend-First**
  - Build API infrastructure first
  - Frontend adapts to backend capabilities

- **Parallel Development**
  - Frontend and backend develop simultaneously
  - Requires strict API contract upfront

[If user selects Frontend-First, apply this guide]

### Implementation Plan Generation

When generating Implementation Plan for frontend-first projects:

1. **Always include Phase 0** (Infrastructure Setup - automated)

2. **Structure phases as:** Design System → UI (Mock) → Backend → Integration → Testing

3. **Include API contract definition** early in Phase 2

4. **Specify MSW setup** for mock APIs

5. **Mark integration phase** as dependency on Phase 3 completion

---

## Task Assignment Best Practices

### Model Recommendations by Phase

**Phase 1 (Design System):**

- Simple tasks (config, setup): Haiku 4.5

- Component development: GPT-5 High or Sonnet 4.5

**Phase 2 (UI Implementation):**

- MSW setup, simple pages: GPT-5 High

- Complex interactive features: Sonnet 4.5

**Phase 3 (Backend):**

- Database schema, auth: Sonnet 4.5

- CRUD endpoints: GPT-5 High or Sonnet 4.5

- Payment integration: Sonnet 4.5 (complex)

**Phase 4 (Integration):**

- Error handling, loading states: GPT-5 High

- Real-time features: Sonnet 4.5

**Phase 5 (Testing):**

- Unit tests: GPT-5 High

- E2E tests: Sonnet 4.5

### Dependencies Management

**Strict phase dependencies:**

- Phase 2 cannot fully complete until Phase 1 done

- Phase 3 can start parallel to Phase 2 (after API contract defined)

- Phase 4 requires Phase 3 completion

- Phase 5 requires Phase 4 completion

**Manager Agent should enforce:**

- No Phase 2 tasks until design system established

- Phase 3 starts after API contract documented (Task 2.1)

- Phase 4 only after all Phase 3 endpoints implemented

---

## Memory Log Requirements

### Phase-Specific Documentation

**Phase 1 Memory Logs should include:**

- Design tokens documented

- Component library inventory

- Accessibility compliance notes

**Phase 2 Memory Logs should include:**

- Mock API endpoints documented

- UI/UX decisions and rationale

- Deviations from initial mockups

**Phase 3 Memory Logs should include:**

- Database schema changes

- API endpoint documentation

- Performance characteristics

**Phase 4 Memory Logs should include:**

- Integration issues encountered

- Performance optimizations applied

- Real-time feature behavior

**Phase 5 Memory Logs should include:**

- Test coverage metrics

- Accessibility audit results

- Performance benchmarks

---

## Success Criteria

### Phase Completion Validation

**Phase 1 Complete when:**

- ✅ All design tokens defined and documented

- ✅ Core component library built

- ✅ Components responsive and accessible

- ✅ Storybook/showcase page created

**Phase 2 Complete when:**

- ✅ All UI pages built and functional with mock data

- ✅ API contract fully documented

- ✅ MSW handlers implemented for all endpoints

- ✅ Forms validated and submitted to mock APIs

**Phase 3 Complete when:**

- ✅ Database schema deployed

- ✅ All API endpoints implemented per contract

- ✅ API tests passing

- ✅ Payment integration functional in test mode

**Phase 4 Complete when:**

- ✅ All mock APIs replaced with real endpoints

- ✅ Authentication working with real sessions

- ✅ Error handling comprehensive

- ✅ Loading states polished

**Phase 5 Complete when:**

- ✅ Test coverage >70%

- ✅ Accessibility audit passed

- ✅ Lighthouse scores >90

- ✅ Production deployment successful

---

## Troubleshooting

### Common Issues

**Issue:** API contract changes during Phase 3

**Solution:** Update TypeScript types, mock handlers, and affected UI components. Create sub-task for updates.

**Issue:** Mock data doesn't match real data structure

**Solution:** Review API contract definition. Update mocks or adjust UI components as needed.

**Issue:** Performance issues after integration

**Solution:** Implement caching, optimize queries, add pagination where needed.

**Issue:** Real-time features causing state sync issues

**Solution:** Review optimistic update strategy, implement conflict resolution.

---

## References

- **APM Documentation:** {GUIDE_PATH:Introduction.md}

- **Model Selection:** {GUIDE_PATH:Model_Selection_Guide.md}

- **Tech Stack Setup:** {GUIDE_PATH:Tech_Stack_Setup_Guide.md}

- **Task Assignment:** {GUIDE_PATH:Task_Assignment_Guide.md}

