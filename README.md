# Fafo Social Post Preview

# AI Agent Prompt

## Project Overview

PinPost is a web-based SaaS application that provides real-time, accurate previews of social media posts across Instagram, LinkedIn, X (formerly Twitter), and Facebook. The platform enables users to draft content once and instantly visualize how that content will render on each platform's native interface, including text truncation, image cropping, link preview cards, and platform-specific formatting rules. The tool serves content creators, marketing teams, and small business owners who manage multi-platform social presence and need to optimize content before publication.

## Core Functionality

- **Multi-Platform Draft Editor**: Single unified text editor with character counting and platform-specific character limit indicators

- **Visual Asset Management**: Upload, crop, and position images with platform-specific aspect ratio guides and preview overlays

- **Real-Time Preview Engine**: Simultaneous live previews of posts across all four platforms with accurate rendering of text, images, hashtags, mentions, and links

- **Platform-Specific Formatting**: Automatic detection and visualization of platform rules (Instagram caption length, LinkedIn article preview, X thread formatting, Facebook link preview cards)

- **Copy Optimization Suggestions**: AI-powered recommendations for character count optimization and platform-specific best practices

- **Template Library**: Pre-built templates for common post types (announcements, product launches, testimonials, educational content)

- **Collaboration Features**: Share draft links with team members for feedback before final publication

## User Journey

1. **Onboarding**: User signs up, connects social media accounts (read-only for preview purposes), and completes platform preference setup

2. **Draft Creation**: User navigates to editor, selects post type or starts from blank canvas

3. **Content Input**: User enters copy in unified editor and uploads visual assets

4. **Real-Time Preview**: System renders live previews across all four platforms as user types and uploads

5. **Optimization**: User reviews platform-specific suggestions and adjusts content accordingly

6. **Collaboration**: User shares draft link with team members for feedback (optional)

7. **Finalization**: User reviews final previews, makes last-minute adjustments, and exports or manually publishes to desired platforms

8. **Analytics**: User can optionally track post performance after manual publication

## Technical Requirements

- **Frontend**: React 18+ with TypeScript, Tailwind CSS for styling, Redux for state management

- **Backend**: Node.js with Express.js or Python with FastAPI for API endpoints

- **Database**: PostgreSQL for user data, posts, and templates; Redis for caching preview data

- **Image Processing**: Sharp or Pillow for image manipulation, aspect ratio conversion, and optimization

- **Authentication**: OAuth 2.0 integration with social platforms (Instagram, LinkedIn, X, Facebook)

- **Deployment**: Docker containerization, Kubernetes orchestration, AWS or GCP infrastructure

- **Performance**: Target <500ms preview render time, support concurrent editing for up to 100 users per instance

- **Security**: End-to-end encryption for draft data, GDPR/CCPA compliance, secure token storage for social media connections

## API Integrations

- **Instagram Graph API**: Retrieve account metadata, validate image specifications, fetch account insights

- **LinkedIn API**: Validate post formatting rules, retrieve organization pages, fetch engagement metrics

- **X API v2**: Validate tweet length, retrieve account information, support thread preview

- **Facebook Graph API**: Retrieve page information, validate link preview card rendering, fetch page insights

- **OpenAI API**: Power copy optimization suggestions and AI-driven content recommendations

- **Stripe API**: Handle subscription billing and payment processing

- **Slack API**: Optional integration for team notifications on draft completion

## Real-Time Features

- **Live Preview Updates**: Debounced preview rendering as user types (100ms debounce)

- **Collaborative Editing**: WebSocket-based real-time collaboration for team members viewing same draft

- **Instant Feedback**: Character count updates, platform limit warnings, and formatting validation in real-time

- **Live Suggestion Engine**: AI suggestions appear as user completes sentences, with accept/reject functionality

- **Notification System**: Real-time notifications for team feedback, collaboration invites, and scheduled post reminders

## Implementation Details

- **Preview Rendering**: Use headless browser instances (Puppeteer) to capture actual platform rendering or build custom rendering engines that mirror platform CSS/layout rules

- **State Management**: Implement optimistic updates for draft changes with server synchronization every 30 seconds

- **Image Handling**: Support drag-and-drop upload, automatic format conversion (WebP for web, native formats for platforms), and client-side compression before upload

- **Draft Versioning**: Maintain version history with ability to revert to previous drafts (last 10 versions stored)

- **Offline Support**: Service Worker implementation for offline draft editing with sync on reconnection

- **Accessibility**: WCAG 2.1 AA compliance, keyboard navigation support, screen reader optimization

## MVP Features

- Single unified editor with character counting for all four platforms

- Real-time preview rendering for Instagram, LinkedIn, X, and Facebook

- Image upload and basic cropping with platform-specific aspect ratio guides

- Platform-specific character limit indicators and warnings

- User authentication and draft save/load functionality

- Basic template library (5-10 templates)

- Export draft as image or text

- Mobile-responsive design for tablet and desktop (mobile app deferred to post-MVP)

## Future Features

- **Advanced Analytics**: Post-publication performance tracking and A/B testing suggestions

- **Content Calendar**: Multi-week planning view with drag-and-drop scheduling

- **AI Content Generation**: Full post generation from brief prompts

- **Hashtag Research**: Trending hashtag suggestions and performance metrics

- **Competitor Analysis**: Monitor competitor posts and engagement patterns

- **Mobile App**: Native iOS and Android applications with offline editing

- **Video Preview**: Support for video uploads and platform-specific video preview rendering

- **Bulk Upload**: Import CSV of posts for batch preview and scheduling

- **Custom Branding**: Team-level brand guidelines and color palette enforcement

- **Zapier/IFTTT Integration**: Automation workflows for post distribution

## User Experience Guidelines

- **Simplicity First**: Minimize cognitive load with a clean, uncluttered interface focused on the preview task

- **Real-Time Feedback**: All user actions should provide immediate visual feedback (no spinners for preview updates)

- **Platform Accuracy**: Previews must match actual platform rendering within 95% accuracy to build user trust

- **Progressive Disclosure**: Advanced features (templates, collaboration, analytics) should be discoverable but not intrusive

- **Keyboard Efficiency**: Power users should be able to complete draft-to-preview workflow entirely via keyboard shortcuts

- **Mobile-First Preview**: Ensure preview panels are optimized for mobile viewing (since many users will view on phones)

- **Undo/Redo**: Full undo/redo stack for all edits with keyboard shortcuts (Ctrl+Z, Ctrl+Shift+Z)

- **Consistent Terminology**: Use platform-agnostic language (e.g., "post" instead of "tweet" or "status")

## Code Quality Standards

- **Testing**: Minimum 80% code coverage with unit tests (Jest), integration tests (Supertest), and E2E tests (Cypress)

- **Linting**: ESLint with Airbnb config, Prettier for code formatting, pre-commit hooks to enforce standards

- **Type Safety**: TypeScript strict mode enabled, no `any` types without explicit justification

- **Documentation**: JSDoc comments for all public functions, README with setup instructions, API documentation with Swagger/OpenAPI

- **Performance**: Lighthouse score target of 90+, Core Web Vitals within "Good" range, bundle size <500KB (gzipped)

- **Security**: OWASP Top 10 compliance, regular dependency audits, security headers (CSP, HSTS, X-Frame-Options)

- **Code Review**: All PRs require minimum two approvals, automated checks must pass before merge

- **Git Workflow**: Feature branches, semantic commit messages, squash commits before merge

## Deliverable Format

- **Repository Structure**: Monorepo with `/frontend`, `/backend`, `/shared` directories

- **Documentation**: Markdown files in `/docs` including architecture decisions, API specifications, deployment guides

- **Docker Setup**: `docker-compose.yml` for local development with all services (frontend, backend, database, Redis)

- **Environment Configuration**: `.env.example` template with all required variables

- **CI/CD Pipeline**: GitHub Actions workflows for testing, linting, and deployment to staging/production

- **Release Notes**: Semantic versioning with CHANGELOG.md documenting all features, fixes, and breaking changes

- **Demo Environment**: Publicly accessible staging instance with sample data for stakeholder review

- **Video Walkthrough**: 5-10 minute demo video showing core user workflows and key features

This project was built with [Lovable](https://lovable.dev).

## Build with Lovable

Continue developing this project in the [Lovable editor](https://lovable.dev/projects/f2d8fd75-1f1e-4c59-9216-49dc6d1e32ef).

- **Ship faster**: describe what you want to build and Lovable handles the code.
- **Stay in sync**: every change made in Lovable is committed straight to this repository.
- **Full ownership**: this code is yours. Push to `main` on GitHub and your changes sync back into Lovable, ready for your next prompt.

## Development

Prefer working locally? You need Node.js and npm — [install with nvm](https://github.com/nvm-sh/nvm#installing-and-updating).

```sh
git clone <this-repository-url>
cd <repository-name>
npm i
npm run dev
```
