# MathMind Codebase Documentation

## 📋 Table of Contents

1. [System Overview](#system-overview)
2. [Architecture](#architecture)
3. [Core System Flow](#core-system-flow)
4. [File Structure & Purposes](#file-structure--purposes)
5. [AI System](#ai-system)
6. [API Endpoints](#api-endpoints)
7. [Components](#components)
8. [Services](#services)
9. [Data Models](#data-models)
10. [Testing](#testing)
11. [Configuration](#configuration)

---

## 🎯 System Overview

**MathMind** is an AI-powered educational platform that creates interactive math lessons with dynamic simulations, personalized content, and adaptive learning experiences. The system uses advanced AI agents to generate educational content, simulations, and assessments while maintaining quality through validation systems.

### Key Features
- **AI-Generated Content**: Dynamic lessons, simulations, and assessments
- **Interactive Simulations**: Real-time math visualizations and experiments
- **Personalized Learning**: Adaptive content based on student progress
- **Teacher Tools**: Lesson creation, analytics, and content management
- **Student Dashboard**: Progress tracking, achievements, and marketplace
- **Admin Panel**: System monitoring, AI model management, and analytics

---

## 🏗️ Architecture

### Technology Stack
- **Frontend**: Next.js 15, React 18, TypeScript
- **Styling**: Tailwind CSS, Radix UI components
- **AI Framework**: Google Genkit, Vertex AI
- **3D Graphics**: Three.js, React Three Fiber
- **Testing**: Jest, React Testing Library, Playwright
- **State Management**: React hooks, context providers

### Architecture Layers
```
┌─────────────────────────────────────────────────────────────┐
│                    Presentation Layer                       │
│  ┌─────────────┐ ┌─────────────┐ ┌─────────────┐          │
│  │   Teacher   │ │   Student   │ │    Admin    │          │
│  │   Interface │ │  Interface  │ │  Interface  │          │
│  └─────────────┘ └─────────────┘ └─────────────┘          │
└─────────────────────────────────────────────────────────────┘
┌─────────────────────────────────────────────────────────────┐
│                    Business Logic Layer                     │
│  ┌─────────────┐ ┌─────────────┐ ┌─────────────┐          │
│  │   Services  │ │    Hooks    │ │   Utils     │          │
│  │             │ │             │ │             │          │
│  └─────────────┘ └─────────────┘ └─────────────┘          │
└─────────────────────────────────────────────────────────────┘
┌─────────────────────────────────────────────────────────────┐
│                      AI Layer                               │
│  ┌─────────────┐ ┌─────────────┐ ┌─────────────┐          │
│  │    Agents   │ │   Prompts   │ │   Genkit    │          │
│  │             │ │             │ │             │          │
│  └─────────────┘ └─────────────┘ └─────────────┘          │
└─────────────────────────────────────────────────────────────┘
┌─────────────────────────────────────────────────────────────┐
│                     Data Layer                              │
│  ┌─────────────┐ ┌─────────────┐ ┌─────────────┐          │
│  │   Storage   │ │  Registry   │ │    Cache    │          │
│  │             │ │             │ │             │          │
│  └─────────────┘ └─────────────┘ └─────────────┘          │
└─────────────────────────────────────────────────────────────┘
```

---

## 🔄 Core System Flow

### 1. Lesson Creation Flow
```
Teacher Input → Document Analysis → AI Content Generation → Validation → Storage → Preview
     ↓              ↓                    ↓                    ↓          ↓         ↓
  Prompt/File   Extract Context    Generate Bricks      Code Quality   Save to   Teacher
  Upload        & Metadata         (Explanation,        & Security     File      Review
                                   Dialogue, Quiz,      Validation     System
                                   Simulation)
```

### 2. Simulation Generation Flow
```
Request → AI Generation → Code Validation → Component Creation → Registry → Rendering
   ↓           ↓              ↓                ↓              ↓           ↓
Teacher    Simulation    Syntax/Security   Dynamic File   Component   Student
Input      Agent         Validation        Generation     Loading     Interface
```

### 3. Student Learning Flow
```
Login → Dashboard → Lesson Selection → Interactive Content → Progress Tracking → Achievements
  ↓         ↓            ↓                ↓                    ↓              ↓
Auth    Progress     Lesson Loader    Brick Rendering      Analytics     Badge System
System   Overview     & Validation    (Simulations,        Service       & Rewards
                                     Quizzes, etc.)
```

---

## 📁 File Structure & Purposes

### Root Configuration Files

#### `package.json`
- **Purpose**: Project dependencies, scripts, and metadata
- **Key Dependencies**: Next.js, React, TypeScript, AI frameworks, UI libraries
- **Scripts**: Development, testing, building, and migration commands

#### `next.config.ts`
- **Purpose**: Next.js configuration with TypeScript support
- **Features**: Image optimization, webpack configuration, build settings
- **Security**: Crypto polyfills for client-side operations

#### `tsconfig.json`
- **Purpose**: TypeScript compiler configuration
- **Settings**: Strict type checking, path mapping, module resolution

### Application Structure

#### `src/app/` - Next.js App Router
```
app/
├── layout.tsx                 # Root layout with providers and global styles
├── page.tsx                   # Landing page with features and signup
├── globals.css               # Global CSS with Tailwind and custom styles
├── login/                    # Authentication pages
├── signup/                   # User registration
├── pricing/                  # Subscription plans
├── teacher/                  # Teacher interface
├── student/                  # Student interface
├── admin/                    # Admin dashboard
└── api/                      # API routes
```

#### `src/lib/` - Core Library
```
lib/
├── types/                    # TypeScript type definitions
├── services/                 # Business logic services
├── providers/                # React context providers
├── hooks/                    # Custom React hooks
├── utils/                    # Utility functions
├── registry/                 # Component and simulation registries
├── prompts/                  # AI prompt management
├── validation/               # Code validation system
└── test/                     # Testing utilities
```

#### `src/components/` - React Components
```
components/
├── ui/                       # Reusable UI components (Radix-based)
├── shared/                   # Shared components across pages
├── simulations/              # Interactive simulation components
├── studio/                   # Lesson creation studio
├── lesson-creation/          # Lesson creation workflow
├── admin/                    # Admin-specific components
├── validation/               # Validation status components
└── lesson/                   # Lesson display components
```

---

## 🤖 AI System

### AI Agents (`src/ai/agents/`)

#### `simulation-agent.ts`
- **Purpose**: Generates interactive math simulations
- **Capabilities**: React component generation, parameter configuration
- **Output**: TypeScript/JSX code with validation

#### `dialogue-agent.ts`
- **Purpose**: Creates conversational learning experiences
- **Features**: Branching conversations, adaptive responses
- **Output**: Dialogue flow structures

#### `explanation-agent.ts`
- **Purpose**: Generates educational content and explanations
- **Features**: Multi-format content, multimedia integration
- **Output**: Rich text with interactive elements

#### `quiz-agent.ts`
- **Purpose**: Creates assessments and quizzes
- **Features**: Multiple question types, scoring, feedback
- **Output**: Question sets with validation

#### `title-agent.ts`
- **Purpose**: Generates lesson titles and descriptions
- **Features**: SEO-optimized, engaging titles
- **Output**: Metadata for lessons

#### `persona-agent.ts`
- **Purpose**: Creates AI teaching personas
- **Features**: Personality customization, teaching styles
- **Output**: Persona configurations

### AI Flows (`src/ai/flows/`)

#### `create-lesson-from-prompt.ts`
- **Purpose**: Orchestrates complete lesson creation
- **Flow**: Prompt → Analysis → Content Generation → Assembly
- **Integration**: All AI agents working together

#### `generate-simulation.ts`
- **Purpose**: Simulation generation workflow
- **Features**: Code generation, validation, fallback handling
- **Output**: Validated simulation components

#### `improve-simulation-from-feedback.ts`
- **Purpose**: Iterative simulation improvement
- **Features**: Feedback analysis, code refinement
- **Output**: Enhanced simulation code

### Prompt Management (`src/lib/prompts/`)

#### `categories/`
- **agent-prompts.ts**: Core AI agent prompts
- **simulation-prompts.ts**: Simulation generation prompts
- **lesson-prompts.ts**: Lesson creation prompts
- **validation-prompts.ts**: Code validation prompts
- **persona-prompts.ts**: Persona creation prompts
- **document-prompts.ts**: Document analysis prompts

#### `templates/`
- **Purpose**: Reusable prompt templates
- **Features**: Variable substitution, conditional logic
- **Management**: Version control and iteration

---

## 🔌 API Endpoints

### Core API Routes (`src/app/api/`)

#### Content Generation
- `POST /api/create-lesson` - Create complete lessons
- `POST /api/generate-simulation` - Generate interactive simulations
- `POST /api/create-lesson-progressive` - Progressive lesson creation
- `POST /api/generate-enhanced-simulation` - Advanced simulation generation

#### Content Management
- `GET /api/load-lesson` - Load lesson data
- `POST /api/save-simulation` - Save simulation components
- `POST /api/save-component` - Save individual components
- `GET /api/load-simulations` - Load simulation library

#### AI Services
- `POST /api/analyze-document` - Document analysis and extraction
- `POST /api/dialogue` - Interactive AI dialogue
- `POST /api/interactive-dialogue` - Real-time conversation
- `POST /api/suggest-content` - Content suggestions

#### Validation & Testing
- `POST /api/validate-simulation` - Code validation
- `POST /api/validate-simulation-runtime` - Runtime testing
- `POST /api/improve-simulation` - Code improvement
- `POST /api/test-simulation` - Simulation testing

#### Persona System
- `POST /api/persona` - Persona management
- `GET /api/persona` - Retrieve personas

#### Admin & Analytics
- `GET /api/ai-models` - AI model management
- `GET /api/list-models` - Available models
- `POST /api/teacher-documents` - Document management

### API Response Patterns
```typescript
interface APIResponse<T> {
  success: boolean;
  data?: T;
  error?: string;
  metadata?: {
    processingTime: number;
    modelUsed: string;
    version: string;
  };
}
```

---

## 🧩 Components

### UI Components (`src/components/ui/`)
- **Radix-based**: Accessible, customizable components
- **Themed**: Dark mode support with Tailwind
- **Responsive**: Mobile-first design approach

### Simulation Components (`src/components/simulations/`)
- **Dynamic Loading**: Runtime component generation
- **Fallback System**: Graceful error handling
- **Performance**: Optimized rendering and animations

### Studio Components (`src/components/studio/`)
- **Lesson Builder**: Drag-and-drop lesson creation
- **Preview System**: Real-time content preview
- **Validation**: Live feedback and error checking

### Admin Components (`src/components/admin/`)
- **Dashboard**: System analytics and monitoring
- **AI Management**: Model configuration and prompts
- **Content Library**: Simulation and lesson management

---

## 🔧 Services

### Core Services (`src/lib/services/`)

#### `simulation-generation-service.ts`
- **Purpose**: Orchestrates simulation creation
- **Features**: Multi-step generation, validation, fallback
- **Integration**: AI agents, validation, storage

#### `brick-generation-service.ts`
- **Purpose**: Creates lesson building blocks
- **Features**: Explanation, dialogue, quiz, simulation bricks
- **Output**: Structured lesson components

#### `document-analysis-pipeline.ts`
- **Purpose**: Analyzes uploaded documents
- **Features**: OCR, content extraction, metadata generation
- **Output**: Structured document data

#### `ai-service.ts`
- **Purpose**: AI model communication
- **Features**: Multiple model support, error handling
- **Integration**: Google AI, Vertex AI

#### `storage-service.ts`
- **Purpose**: Data persistence and retrieval
- **Features**: File system, caching, backup
- **Security**: Access control and validation

#### `validation-service.ts`
- **Purpose**: Code quality and security validation
- **Features**: Syntax checking, security scanning
- **Output**: Validation reports and recommendations

#### `persona-service.ts`
- **Purpose**: AI persona management
- **Features**: Creation, customization, deployment
- **Integration**: AI agents and dialogue system

### Registry Services

#### `component-registry.ts`
- **Purpose**: Dynamic component management
- **Features**: Lazy loading, caching, fallbacks
- **Security**: Sandboxed execution

#### `simulation-registry.ts`
- **Purpose**: Simulation library management
- **Features**: Metadata, categorization, search
- **Integration**: Component registry

---

## 📊 Data Models

### Core Entities (`src/lib/types/`)

#### User System
```typescript
interface User {
  id: string;
  email: string;
  name: string;
  role: 'teacher' | 'student' | 'admin';
  avatar?: string;
  createdAt: Date;
  updatedAt: Date;
}
```

#### Lesson System
```typescript
interface Lesson {
  id: string;
  title: string;
  subject: string;
  grade: string;
  tags: string[];
  status: 'Draft' | 'Published' | 'Archived';
  blueprint?: LessonBlueprint;
}

interface LessonBlueprint {
  id: string;
  title: string;
  bricks: Brick[];
  metadata: LessonMetadata;
}
```

#### Brick System
```typescript
type BrickType = 'Explanation' | 'Dialogue' | 'Quiz' | 'Simulation';

interface BaseBrick {
  id: string;
  type: BrickType;
  title: string;
  difficulty: 'beginner' | 'intermediate' | 'advanced';
  learningObjectives: string[];
  prerequisites: string[];
  estimatedDuration: number;
  progressTracking: boolean;
}
```

#### Simulation System
```typescript
interface SimulationConfig {
  id: string;
  name: string;
  category: SimulationCategory;
  difficulty: 'beginner' | 'intermediate' | 'advanced';
  gradeLevel: string[];
  description: string;
  parameters: SimulationParameter[];
  learningObjectives: string[];
  component: React.ComponentType<any>;
  thumbnail: string;
}
```

---

## 🧪 Testing

### Test Structure (`tests/` and `src/**/__tests__/`)

#### Unit Tests
- **Components**: React component testing with React Testing Library
- **Services**: Business logic testing with Jest
- **Utilities**: Helper function testing
- **Hooks**: Custom React hooks testing

#### Integration Tests
- **API Routes**: End-to-end API testing
- **Service Integration**: Cross-service communication
- **Database Operations**: Storage and retrieval testing

#### End-to-End Tests (`tests/e2e/`)
- **User Workflows**: Complete user journey testing
- **Cross-browser**: Multiple browser compatibility
- **Performance**: Load and stress testing

### Testing Tools
- **Jest**: Unit and integration testing
- **React Testing Library**: Component testing
- **Playwright**: End-to-end testing
- **MSW**: API mocking and testing

---

## ⚙️ Configuration

### Environment Configuration
- **Development**: Local development settings
- **Production**: Production deployment settings
- **Testing**: Test environment configuration

### AI Model Configuration
- **Google AI**: Primary AI service configuration
- **Vertex AI**: Advanced AI model settings
- **Fallback Models**: Backup AI service configuration

### Security Configuration
- **Authentication**: User authentication settings
- **Authorization**: Role-based access control
- **Validation**: Code security and quality settings

---

## 🚀 Deployment & Operations

### Build Process
1. **Type Checking**: TypeScript compilation
2. **Linting**: Code quality checks
3. **Testing**: Automated test suite
4. **Building**: Next.js production build
5. **Optimization**: Asset optimization and bundling

### Monitoring & Analytics
- **Performance**: Real-time performance monitoring
- **Errors**: Error tracking and reporting
- **Usage**: User behavior analytics
- **AI Performance**: AI model effectiveness tracking

### Security Measures
- **Code Validation**: Automated security scanning
- **Input Validation**: User input sanitization
- **Access Control**: Role-based permissions
- **Data Protection**: Secure data handling

---

## 📈 Performance & Optimization

### Frontend Optimization
- **Code Splitting**: Dynamic imports and lazy loading
- **Caching**: Component and data caching strategies
- **Bundle Optimization**: Webpack optimization
- **Image Optimization**: Next.js image optimization

### AI Performance
- **Model Selection**: Optimal AI model selection
- **Prompt Optimization**: Efficient prompt design
- **Caching**: AI response caching
- **Fallback Strategies**: Graceful degradation

### Database Optimization
- **Indexing**: Efficient data retrieval
- **Caching**: Redis and in-memory caching
- **Query Optimization**: Efficient database queries
- **Connection Pooling**: Database connection management

---

## 🔮 Future Enhancements

### Planned Features
- **Real-time Collaboration**: Multi-user lesson editing
- **Advanced Analytics**: Deep learning insights
- **Mobile App**: Native mobile application
- **API Platform**: Public API for integrations
- **AI Model Training**: Custom model training

### Technical Improvements
- **Microservices**: Service decomposition
- **GraphQL**: Advanced data querying
- **Real-time Updates**: WebSocket integration
- **Offline Support**: Progressive web app features

---

## 📚 Additional Resources

### Documentation
- `docs/ARCHITECTURE.md` - Detailed architecture documentation
- `docs/API_REFERENCE.md` - API documentation
- `AI_CODE_VALIDATION_SYSTEM.md` - Code validation system
- `AI_CONTENT_GENERATION_FLOW.md` - Content generation flow

### Scripts
- `scripts/migrate-to-centralized-prompts.ts` - Prompt migration
- `scripts/fix-remaining-prompts.ts` - Prompt fixes
- `scripts/test-persona-feature.ts` - Persona testing

### Configuration Files
- `apphosting.yaml` - Deployment configuration
- `jest.config.js` - Testing configuration
- `tailwind.config.js` - Styling configuration

---

*This documentation provides a comprehensive overview of the MathMind codebase. For specific implementation details, refer to the individual files and their inline documentation.* 
