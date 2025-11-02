# Space Research Portal

A modern, interactive web application for exploring space missions, learning about space science, and connecting with the space exploration community. Built with Next.js, React, and TypeScript.

## Project Overview

**Space Research Portal** is an educational platform that makes NASA's complex space data accessible and engaging for everyone. It combines stunning visual design with real-time data, user authentication, and community engagement features.

### Key Features

- **🚀 Mission Explorer** - Browse and filter space missions across multiple categories
- **🎓 Learning Center** - Access simplified research articles and take interactive quizzes
- **👥 Community Hub** - Connect with space enthusiasts, share ideas, and participate in discussions
- **🔐 User Authentication** - Secure email and Google OAuth integration
- **📊 User Progress Tracking** - Track quiz scores and learning achievements
- **📱 Responsive Design** - Works seamlessly on desktop, tablet, and mobile devices

## Technology Stack

### Frontend
- **Next.js 15.5** - React framework for production
- **React 19.1** - UI library
- **TypeScript** - Type-safe development
- **Tailwind CSS v4** - Utility-first CSS framework
- **Framer Motion** - Animation library
- **Recharts** - Data visualization

### UI Components
- **Radix UI** - Headless, accessible component library
- **shadcn/ui** - Pre-built React components
- **Lucide React** - Icon library

### State Management & Forms
- **React Hook Form** - Form management
- **Zod** - TypeScript-first schema validation

### Design System
- **Geist Font** - Custom typeface
- **Design Tokens** - CSS variables for theming
- **Glass Morphism Effects** - Modern UI aesthetics

## Project Structure

\`\`\`
├── app/                          # Next.js app directory
│   ├── page.tsx                 # Home page
│   ├── missions/                # Missions section
│   ├── learn/                   # Learning center
│   ├── community/               # Community hub
│   ├── layout.tsx               # Root layout with auth provider
│   └── globals.css              # Global styles & design tokens
│
├── components/
│   ├── auth/                    # Authentication components
│   │   └── auth-dialog.tsx      # Login/signup modal
│   ├── home/                    # Homepage components
│   │   ├── HeroSection.tsx
│   │   ├── FeatureCards.tsx
│   │   └── FeaturedMissions.tsx
│   ├── missions/                # Mission components
│   │   ├── MissionCard.tsx
│   │   ├── MissionTimeline.tsx
│   │   └── PlanetViewer.tsx
│   ├── learn/                   # Learning components
│   │   ├── ResearchGrid.tsx
│   │   ├── QuizSection.tsx
│   │   └── UserProgress.tsx
│   ├── community/               # Community components
│   │   ├── PostList.tsx
│   │   └── CreatePostDialog.tsx
│   ├── ui/                      # Reusable UI components
│   └── theme-provider.tsx       # Theme configuration
│
├── lib/
│   ├── auth.tsx                 # Authentication logic & hooks
│   ├── data/
│   │   ├── missions.ts          # Mission data & queries
│   │   ├── learn.ts             # Learning data & user progress
│   │   └── community.ts         # Community posts data
│   └── utils.ts                 # Utility functions
│
├── layouts/
│   └── Layout.tsx               # Main app layout with navigation
│
├── entities/                    # TypeScript data models
│   ├── Mission.ts
│   ├── QuizQuestion.ts
│   ├── ResearchArticle.ts
│   └── CommunityPost.ts
│
├── hooks/                       # Custom React hooks
│   ├── useFetch.ts
│   └── use-toast.ts
│
├── public/                      # Static assets
│   ├── images/                  # Space mission photos
│   └── placeholder.svg          # Placeholder assets
│
└── package.json                 # Dependencies & scripts
\`\`\`

## Core Pages & Features

### 🏠 Home Page (`/`)
- Hero section introducing the platform
- Feature cards highlighting key capabilities
- Featured missions carousel
- Call-to-action prompting exploration

### 🚀 Missions (`/missions`)
- Complete mission database with search and filtering
- Filter by category (Planetary, Astrophysics, Earth Observation, etc.)
- Mission timeline visualization
- Detailed mission cards with descriptions
- **Authentication Required**

### 🎓 Learning (`/learn`)
- Research articles library
- Interactive quizzes with scoring
- User progress tracking
- Quiz score persistence
- **Authentication Required**

### 👥 Community (`/community`)
- Create and share posts
- Filter posts by category (Questions, Discussions, Projects, AMA)
- Upvote system for community engagement
- User profiles and activity tracking
- **Authentication Required**

## Authentication System

The app uses a professional authentication flow with two methods:

### Authentication Methods
1. **Email Authentication** - Email/password with OTP verification
2. **Google OAuth** - Single sign-on via Google

### Auth Features
- Session persistence via localStorage
- Automatic redirection after login
- Protected routes with `RequireAuth` component
- User data stored securely
- Logout functionality

### Protected Routes
- `/missions` - Requires authentication
- `/learn` - Requires authentication
- `/community` - Requires authentication

## Design System

### Color Palette
- **Primary Brand Colors:**
  - Cyan (#0dcaf0) - "Star Teal"
  - Pink (#ff006e) - "Plasma Pink"
  - Purple (#2d1b69) - "Nebula Purple"
  
- **Base Colors:**
  - Background: #0a0e27 (Space Black)
  - Text: #ffffff (White)

### Visual Effects
- **Glass Morphism** - Semi-transparent glass panels with blur
- **Glow Effects** - Text and element glows for depth
- **Animations** - Smooth transitions and floating effects
- **Gradient Backgrounds** - Cosmic gradients throughout

### Typography
- **Headings:** Geist Sans (Bold)
- **Body:** Geist Sans (Regular)
- **Monospace:** Geist Mono

## Data Models

### Mission
\`\`\`typescript
{
  id: string;
  name: string;
  year: number;
  category: string;
  description: string;
  imageUrl: string;
  featured: boolean;
}
\`\`\`

### Quiz Question
\`\`\`typescript
{
  id: string;
  question: string;
  options: string[];
  correctAnswer: number;
  topic: string;
}
\`\`\`

### Community Post
\`\`\`typescript
{
  id: string;
  title: string;
  content: string;
  author_name: string;
  category: string;
  upvotes: number;
  created_date: string;
}
\`\`\`

### User Progress
\`\`\`typescript
{
  id: string;
  full_name: string;
  quiz_score: number;
  articles_read: number;
}
\`\`\`

## Getting Started

### Prerequisites
- Node.js 18+
- npm or pnpm

### Installation

1. **Clone or download the project**
\`\`\`bash
cd space-research-portal
\`\`\`

2. **Install dependencies**
\`\`\`bash
npm install
# or
pnpm install
\`\`\`

3. **Run development server**
\`\`\`bash
npm run dev
# or
pnpm dev
\`\`\`

4. **Open browser**
Navigate to `http://localhost:3000`

### Available Scripts
\`\`\`bash
npm run dev      # Start development server
npm run build    # Build for production
npm start        # Start production server
npm run lint     # Run ESLint
\`\`\`

## Component Architecture

### Layout Component
- Fixed navigation bar with responsive mobile menu
- Star field background animation
- Glow effects on logo and active nav items
- Footer with quick links and data sources

### Authentication Dialog
- Two-step authentication flow (Email/Google)
- Email verification with OTP
- Google OAuth integration
- Form validation with error messages
- Automatic redirection after success

### Mission Components
- **MissionCard** - Individual mission display with image and description
- **MissionTimeline** - Timeline visualization of missions by year
- **PlanetViewer** - Interactive planet/mission visualization

### Learning Components
- **ResearchGrid** - Grid layout for articles
- **QuizSection** - Interactive quiz interface
- **UserProgress** - Score and achievement display

### Community Components
- **PostList** - Feed of community posts
- **CreatePostDialog** - Modal for creating new posts

## Styling & Customization

### Design Tokens (CSS Variables)
Located in `app/globals.css`:
- `--space-black` - Main background
- `--star-teal` - Primary accent (cyan)
- `--plasma-pink` - Secondary accent (pink)
- `--nebula-purple` - Tertiary accent (purple)
- `--glow-cyan` - Glow effect color

### Tailwind Configuration
- Custom spacing scale
- Semantic color tokens
- Responsive breakpoints (mobile-first)
- Glass morphism and animation utilities

### Customizing Colors
Edit CSS variables in `app/globals.css` to change the theme globally:
\`\`\`css
:root {
  --star-teal: #0dcaf0;
  --plasma-pink: #ff006e;
}
\`\`\`

## Key Features Explained

### Mission Filtering
- Real-time search across mission names and descriptions
- Category filtering (Planetary, Astrophysics, etc.)
- Sorted by year (newest first)
- Responsive grid layout

### Quiz System
- Multiple choice questions
- Real-time score tracking
- User progress persistence
- Category-based organization

### Community Engagement
- User-generated content
- Upvote system for community validation
- Multiple post categories
- Author information tracking

## Performance Optimizations

- **Next.js Image Optimization** - Automatic image optimization
- **Code Splitting** - Automatic per-route code splitting
- **Lazy Loading** - Components and images load on demand
- **CSS Optimization** - Tailwind CSS purges unused styles
- **Animation Performance** - GPU-accelerated Framer Motion animations

## Browser Support

- Chrome/Edge (latest)
- Firefox (latest)
- Safari (latest)
- Mobile browsers (iOS Safari, Chrome Android)

## Future Enhancements

- Advanced mission filters (duration, cost, success rate)
- User profiles with achievement badges
- Real-time notifications for new content
- Dark/Light theme toggle
- Social sharing features
- Mobile app version
- API integration with NASA Open APIs

## Data Sources

- **Missions Data** - NASA Open APIs and historical mission records
- **Learning Content** - Educational space science resources
- **Images** - NASA imagery and space mission photography

## Troubleshooting

### Auth Issues
- Check if auth dialog is showing up in the layout
- Verify localStorage is enabled in browser
- Clear browser cache if session persists incorrectly

### Loading Issues
- Check network tab for failed data requests
- Verify data endpoints are accessible
- Check console for specific error messages

### Styling Issues
- Ensure Tailwind CSS is properly configured
- Check if custom CSS variables are defined
- Verify glass-effect and glow-text classes are applied

## Contributing

This is an educational project demonstrating Next.js, React, and modern web development practices. Feel free to fork and customize for your own space exploration portal!

## License

Educational purposes only. NASA data is provided under the NASA Open Data policy.

## Credits

Built with v0 AI assistant and modern web technologies. Inspired by NASA's mission to make space exploration accessible to everyone.

---

**Ready to explore the cosmos?** Visit the [Space Research Portal](http://localhost:3000) and start your space journey today!
