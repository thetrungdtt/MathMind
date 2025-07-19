# MathMind Project Design & Architecture

## Overview
MathMind is a sophisticated AI-powered educational platform built with Next.js 15, featuring an advanced simulation system with AI-powered improvement capabilities, dynamic component generation, and a comprehensive lesson building studio.

## **Current Application State**

MathMind has evolved into a highly sophisticated AI-powered educational platform with the following key architectural highlights:

### **AI-First Design with Advanced Simulation System**
- **AI-Powered Simulation Generation**: Complete simulation creation from text prompts
- **AI-Powered Simulation Improvement**: Iterative improvement system based on teacher feedback
- **Dynamic Component System**: Runtime generation and loading of React components
- **Multi-Agent Architecture**: Specialized AI agents for different educational tasks

### **Advanced Simulation Management**
- **Dynamic Simulation Registry**: Real-time registration and loading of AI-generated simulations
- **Server-Side Storage**: Persistent storage of simulations and component code
- **Component Code Generation**: AI generates complete React/TypeScript components
- **Simulation Improvement Pipeline**: Teacher feedback → AI analysis → Improved simulation

### **Modern Tech Stack**
- **Next.js 15** with App Router and server actions
- **TypeScript** with strict typing throughout
- **Google AI Gemini 2.0 Flash** via Genkit framework
- **ReactFlow** for visual lesson building
- **Tailwind CSS** with comprehensive design system

## Technology Stack

### Core Technologies
- **Framework**: Next.js 15.3.3 with App Router
- **Language**: TypeScript 5 with strict mode
- **Styling**: Tailwind CSS 3.4.1 with custom design system
- **UI Components**: Radix UI primitives with shadcn/ui components
- **AI Integration**: Google AI (Gemini 2.0 Flash) via Genkit framework
- **State Management**: React hooks and server actions
- **Flow Editor**: ReactFlow for lesson building
- **Charts**: Recharts for data visualization
- **Forms**: React Hook Form with Zod validation

### Key Dependencies
- **AI/ML**: `@genkit-ai/googleai`, `@genkit-ai/next`, `genkit`
- **UI Framework**: `@radix-ui/*` components, `lucide-react` icons
- **Forms**: `react-hook-form`, `@hookform/resolvers`, `zod`
- **Flow Editor**: `reactflow`, `react-use-measure`
- **Charts**: `recharts`
- **Utilities**: `clsx`, `tailwind-merge`, `date-fns`

## Project Architecture

### Directory Structure

```
MathMind/
├── src/
│   ├── ai/                          # AI/ML functionality
│   │   ├── agents/                  # Specialized AI agents
│   │   │   ├── simulation-agent.ts  # Simulation brick generation
│   │   │   ├── quiz-agent.ts        # Quiz generation
│   │   │   ├── dialogue-agent.ts    # Dialogue generation
│   │   │   ├── explanation-agent.ts # Explanation generation
│   │   │   └── title-agent.ts       # Lesson title generation
│   │   ├── flows/                   # Genkit AI flows
│   │   │   ├── create-lesson-from-prompt.ts
│   │   │   ├── generate-dynamic-problems.ts
│   │   │   ├── generate-simulation.ts
│   │   │   ├── improve-simulation-from-feedback.ts
│   │   │   ├── pythaverse-agent.ts
│   │   │   └── suggest-brick-content.ts
│   │   ├── dev.ts                   # Development AI setup
│   │   └── genkit.ts                # Genkit configuration
│   ├── app/                         # Next.js App Router pages
│   │   ├── api/                     # API routes
│   │   │   ├── create-lesson/       # Lesson creation API
│   │   │   ├── generate-simulation/ # Simulation generation API
│   │   │   ├── improve-simulation/  # Simulation improvement API
│   │   │   ├── load-simulations/    # Simulation loading API
│   │   │   ├── save-component/      # Component storage API
│   │   │   └── save-simulation/     # Simulation storage API
│   │   ├── (auth)/                  # Authentication pages
│   │   │   ├── login/
│   │   │   └── signup/
│   │   ├── educators/               # Educator landing page
│   │   ├── pricing/                 # Pricing page
│   │   ├── students/                # Student landing page
│   │   ├── teacher/                 # Teacher dashboard & tools
│   │   │   ├── analytics/           # Analytics dashboard
│   │   │   ├── create/              # Lesson creation
│   │   │   ├── dashboard/           # Teacher dashboard
│   │   │   ├── edit/                # Lesson editing
│   │   │   ├── personas/            # AI persona management
│   │   │   ├── preview/             # Lesson preview
│   │   │   ├── publish/             # Lesson publishing
│   │   │   └── studio/              # Visual lesson builder
│   │   ├── student/                 # Student learning interface
│   │   │   ├── achievements/        # Student achievements
│   │   │   ├── dashboard/           # Student dashboard
│   │   │   ├── marketplace/         # Content marketplace
│   │   │   └── tutor/               # AI tutoring sessions
│   │   ├── globals.css              # Global styles
│   │   ├── layout.tsx               # Root layout
│   │   └── page.tsx                 # Landing page
│   ├── components/                  # Reusable components
│   │   ├── shared/                  # Shared components
│   │   │   ├── app-shell.tsx        # Main app layout
│   │   │   ├── auth-form.tsx        # Authentication forms
│   │   │   ├── dialogue-brick.tsx   # Dialogue component
│   │   │   ├── header.tsx           # Site header
│   │   │   ├── lesson-card.tsx      # Lesson display cards
│   │   │   ├── progress-chart.tsx   # Progress visualization
│   │   │   └── pythaverse-agent.tsx # AI agent interface
│   │   ├── simulations/             # Interactive simulations
│   │   │   ├── generated/           # AI-generated simulations
│   │   │   │   ├── index.ts         # Dynamic component registry
│   │   │   │   └── *.tsx            # Generated simulation files
│   │   │   ├── custom-simulation.tsx # Custom simulation wrapper
│   │   │   ├── dynamic-simulation.tsx # Dynamic component loader
│   │   │   ├── enhanced-thermometer.tsx # Enhanced thermometer
│   │   │   ├── fallback-simulation.tsx # Fallback simulation
│   │   │   ├── fraction-visualizer.tsx # Fraction visualization
│   │   │   └── thermometer.tsx      # Basic thermometer
│   │   ├── studio/                  # Lesson building tools
│   │   │   ├── brick-nodes.tsx      # Flow editor nodes
│   │   │   ├── debug-view.tsx       # AI debugging interface
│   │   │   ├── lesson-studio.tsx    # Main studio component
│   │   │   └── simulation-creator.tsx # Simulation creation UI
│   │   ├── ui/                      # Base UI components (shadcn/ui)
│   │   │   ├── accordion.tsx
│   │   │   ├── alert-dialog.tsx
│   │   │   ├── button.tsx
│   │   │   ├── card.tsx
│   │   │   ├── dialog.tsx
│   │   │   ├── form.tsx
│   │   │   ├── input.tsx
│   │   │   ├── select.tsx
│   │   │   ├── tabs.tsx
│   │   │   └── ... (30+ components)
│   │   └── logo.tsx                 # Application logo
│   ├── data/                        # Static data and mock content
│   │   ├── index.ts                 # Data exports
│   │   ├── lessons.json             # Sample lesson data
│   │   └── pricing.json             # Pricing information
│   ├── hooks/                       # Custom React hooks
│   │   ├── use-mobile.tsx           # Mobile detection
│   │   └── use-toast.ts             # Toast notifications
│   └── lib/                         # Utility libraries
│       ├── client-storage.ts        # Client-side storage utilities
│       ├── server-storage.ts        # Server-side storage utilities
│       ├── simulation-registry.ts   # Simulation registry singleton
│       ├── types.ts                 # TypeScript type definitions
│       └── utils.ts                 # Utility functions
├── data/                            # Server-side data storage
│   ├── components/                  # Generated component storage
│   ├── lessons.json                 # Lesson data
│   └── simulations.json             # Simulation data
├── docs/                            # Documentation
├── blueprint.md                     # Project requirements
├── components.json                  # shadcn/ui configuration
├── next.config.ts                   # Next.js configuration
├── package.json                     # Dependencies and scripts
├── postcss.config.mjs               # PostCSS configuration
├── tailwind.config.ts               # Tailwind CSS configuration
└── tsconfig.json                    # TypeScript configuration
```

## Core Features & Components

### 1. AI-Powered Simulation System
**Location**: `src/ai/flows/` and `src/ai/agents/`

#### **Simulation Generation**
- **`generate-simulation.ts`**: Creates complete simulations from text prompts
- **`simulation-agent.ts`**: Specialized agent for simulation brick generation
- **Dynamic Component Creation**: AI generates complete React/TypeScript components
- **Registry Integration**: Automatic registration in simulation registry

#### **Simulation Improvement**
- **`improve-simulation-from-feedback.ts`**: AI-powered simulation improvement
- **Teacher Feedback Processing**: Analyzes feedback and generates improvements
- **Iterative Enhancement**: Up to 3 improvement attempts per simulation
- **Context Preservation**: Maintains original educational focus while improving

#### **AI Agents**
- **`simulation-agent.ts`**: Simulation brick generation and selection
- **`quiz-agent.ts`**: Quiz question generation
- **`dialogue-agent.ts`**: Interactive dialogue creation
- **`explanation-agent.ts`**: Educational content explanation
- **`title-agent.ts`**: Lesson title generation

### 2. Dynamic Simulation Management
**Location**: `src/components/simulations/` and `src/lib/`

#### **Simulation Registry**
- **`simulation-registry.ts`**: Centralized simulation management
- **Dynamic Loading**: Runtime loading of AI-generated simulations
- **Server Storage Integration**: Persistent storage with fallback
- **Component Resolution**: Automatic component assignment based on type

#### **Generated Components**
- **`generated/index.ts`**: Dynamic component registry
- **`dynamic-simulation.tsx`**: Runtime component loader
- **`custom-simulation.tsx`**: Custom simulation wrapper
- **Auto-Registration**: Generated components automatically registered

#### **Built-in Simulations**
- **`thermometer.tsx`**: Temperature-based math concepts
- **`enhanced-thermometer.tsx`**: Advanced thermometer with features
- **`fraction-visualizer.tsx`**: Fraction visualization tool
- **`fallback-simulation.tsx`**: Fallback for missing simulations

### 3. API Infrastructure
**Location**: `src/app/api/`

#### **Simulation APIs**
- **`/api/generate-simulation`**: AI-powered simulation generation
- **`/api/improve-simulation`**: Simulation improvement with feedback
- **`/api/load-simulations`**: Load simulations from server storage
- **`/api/save-simulation`**: Save simulations to server storage
- **`/api/save-component`**: Store generated component code

#### **Lesson APIs**
- **`/api/create-lesson`**: Complete lesson generation with AI
- **Multi-Agent Integration**: Uses specialized agents for each brick type

### 4. Server-Side Storage
**Location**: `src/lib/server-storage.ts`

#### **Simulation Storage**
- **File-Based Storage**: JSON files for simulations and lessons
- **Component Storage**: Separate storage for generated component code
- **Data Persistence**: Server-side persistence with client fallback
- **Storage Management**: Add, update, and retrieve simulations

### 5. Visual Lesson Builder (Studio)
**Location**: `src/components/studio/` and `src/app/teacher/studio/`

#### **ReactFlow Integration**
- **Drag-and-Drop**: Visual lesson building interface
- **Brick System**: Four types of learning components
- **Real-time Preview**: Live lesson preview during creation
- **AI Integration**: Content suggestions and auto-generation

#### **Brick Types**
- **Explanation**: Text-based educational content
- **Dialogue**: Interactive AI conversations
- **Quiz**: Assessment questions with AI generation
- **Simulation**: Interactive visualizations with AI creation

#### **Simulation Creator**
- **`simulation-creator.tsx`**: UI for creating new simulations
- **AI-Powered Generation**: Generate simulations from descriptions
- **Parameter Configuration**: Customize simulation parameters
- **Learning Objectives**: Define educational goals

### 6. User Interface System
**Location**: `src/components/ui/` and `src/components/shared/`

#### **Design System**
- **Color Palette**: Custom blue/cyan theme with dark mode support
- **Typography**: Space Grotesk for headlines, Inter for body text
- **Component Library**: 30+ reusable UI components
- **Responsive Design**: Mobile-first approach

#### **Shared Components**
- **`app-shell.tsx`**: Main application layout
- **`header.tsx`**: Site navigation and branding
- **`lesson-card.tsx`**: Lesson display and interaction
- **`progress-chart.tsx`**: Data visualization
- **`pythaverse-agent.tsx`**: AI agent interface

## Data Flow Architecture

### Simulation Creation Flow
1. **Teacher Input**: Description of desired simulation
2. **AI Generation**: `generate-simulation.ts` creates complete simulation
3. **Component Creation**: AI generates React/TypeScript component code
4. **File Storage**: Component saved to `src/components/simulations/generated/`
5. **Registry Update**: Component registered in dynamic registry
6. **Server Storage**: Simulation metadata saved to server storage
7. **Studio Integration**: Available in lesson studio for use

### Simulation Improvement Flow
1. **Teacher Feedback**: Rating and comments on simulation
2. **AI Analysis**: `improve-simulation-from-feedback.ts` analyzes feedback
3. **Original Code Loading**: Loads original simulation component code
4. **Context Preservation**: Maintains educational focus and objectives
5. **Component Generation**: Creates improved React component
6. **File Creation**: Saves new component to generated directory
7. **Registry Update**: Registers improved component
8. **Storage Update**: Updates server storage with new simulation

### Lesson Creation Flow
1. **Teacher Prompt**: Text description of lesson
2. **Title Generation**: `title-agent.ts` generates lesson title
3. **Brick Generation**: Specialized agents create each brick type
   - **Explanation**: `explanation-agent.ts`
   - **Dialogue**: `dialogue-agent.ts`
   - **Simulation**: `simulation-agent.ts`
   - **Quiz**: `quiz-agent.ts`
4. **Studio Integration**: Bricks available in visual editor
5. **Preview & Edit**: Real-time preview and editing
6. **Publishing**: Save and publish lesson

## AI Integration Architecture

### Genkit Framework
- **Model**: Google AI Gemini 2.0 Flash
- **Flows**: Structured AI workflows with input/output schemas
- **Server Actions**: Next.js server-side AI processing
- **Type Safety**: Zod schema validation throughout

### AI Capabilities
- **Content Generation**: Dynamic lesson and simulation creation
- **Problem Generation**: Personalized math problems
- **Conversational AI**: Interactive tutoring and dialogue
- **Content Improvement**: Iterative enhancement based on feedback
- **Code Generation**: Complete React component creation

### AI Agents
Each agent specializes in a specific educational task:
- **Simulation Agent**: Creates and improves interactive simulations
- **Quiz Agent**: Generates assessment questions
- **Dialogue Agent**: Creates interactive conversations
- **Explanation Agent**: Generates educational content
- **Title Agent**: Creates lesson titles

## Simulation System Architecture

### Dynamic Component System
```
┌─────────────────┐    ┌──────────────────┐    ┌─────────────────┐
│   AI Generation │───▶│  Component Code  │───▶│  File Storage   │
└─────────────────┘    └──────────────────┘    └─────────────────┘
         │                       │                       │
         ▼                       ▼                       ▼
┌─────────────────┐    ┌──────────────────┐    ┌─────────────────┐
│  Registry Entry │    │  Dynamic Loader  │    │  React Component│
└─────────────────┘    └──────────────────┘    └─────────────────┘
         │                       │                       │
         ▼                       ▼                       ▼
┌─────────────────┐    ┌──────────────────┐    ┌─────────────────┐
│  Studio Access  │    │  Runtime Loading │    │  User Interface │
└─────────────────┘    └──────────────────┘    └─────────────────┘
```

### Simulation Registry
- **Singleton Pattern**: Centralized simulation management
- **Dynamic Loading**: Runtime component resolution
- **Server Integration**: Fallback to server storage
- **Type Safety**: Full TypeScript integration

### Component Generation
- **AI-Powered**: Complete React component creation
- **TypeScript**: Full type safety and interfaces
- **Tailwind CSS**: Consistent styling
- **Educational Focus**: Maintains learning objectives

## Development Workflow

### Scripts
- `npm run dev`: Development server with Turbopack
- `npm run genkit:dev`: AI development server
- `npm run build`: Production build
- `npm run lint`: Code linting
- `npm run typecheck`: TypeScript validation

### Configuration
- **Next.js**: Optimized for performance and SEO
- **TypeScript**: Strict type checking enabled
- **Tailwind**: Custom design system integration
- **ESLint**: Code quality enforcement

## Deployment & Hosting

### Environment Setup
- **Port**: 9002 (development)
- **Build**: Optimized for production deployment
- **Static Assets**: Optimized image handling
- **API Routes**: Server-side AI processing

### Performance Optimizations
- **Turbopack**: Fast development builds
- **Code Splitting**: Automatic route-based splitting
- **Image Optimization**: Next.js image optimization
- **Bundle Analysis**: Optimized dependency management

## Future Enhancements

### Planned Features
- **Advanced Analytics**: Detailed learning insights and progress tracking
- **Collaborative Features**: Multi-user lesson creation and sharing
- **Mobile App**: Native mobile experience with offline capabilities
- **API Integration**: Third-party educational tools and LMS integration
- **Advanced AI Models**: Support for multiple AI providers and models

### Scalability Considerations
- **Database Integration**: Persistent data storage with PostgreSQL/MongoDB
- **User Authentication**: Secure user management with OAuth
- **Content Management**: Advanced lesson organization and versioning
- **Performance Monitoring**: Real-time analytics and error tracking
- **CDN Integration**: Global content delivery for simulations

## Key Architectural Decisions

### 1. AI-First Design
- **Centralized AI Integration**: All AI functionality through Genkit
- **Specialized Agents**: Domain-specific AI agents for different tasks
- **Type Safety**: Full TypeScript integration with Zod validation
- **Server-Side Processing**: AI processing on server for security and performance

### 2. Dynamic Component System
- **Runtime Generation**: AI generates components at runtime
- **Registry Pattern**: Centralized component management
- **Fallback System**: Multiple fallback mechanisms for reliability
- **File System Integration**: Direct file system access for component storage

### 3. Simulation Improvement Pipeline
- **Iterative Enhancement**: Up to 3 improvement attempts
- **Context Preservation**: Maintains educational focus
- **Feedback Integration**: Teacher feedback drives improvements
- **Version Management**: Tracks improvement history

### 4. Server-Side Storage
- **File-Based Storage**: Simple, reliable storage solution
- **Component Persistence**: Separate storage for component code
- **Client Fallback**: LocalStorage fallback for offline capability
- **Data Consistency**: Consistent data structure across storage layers

This architecture provides a solid foundation for an AI-powered educational platform with sophisticated simulation capabilities, comprehensive AI integration, and a scalable design for future growth.

# MathMind Design Flow Diagrams

## 1. Application Architecture Overview
- Shows the layered architecture with Frontend, AI, Data, and Components layers
- Illustrates how different parts of the system interact

```mermaid
graph TB
    subgraph "Frontend Layer"
        LP[Landing Page]
        TD[Teacher Dashboard]
        SD[Student Dashboard]
        LS[Lesson Studio]
        SC[Simulation Creator]
        MP[Marketplace]
    end
    
    subgraph "AI Layer"
        AI[Genkit AI Framework]
        GEM[Gemini 2.0 Flash]
        CL[Create Lesson Flow]
        GS[Generate Simulation Flow]
        IS[Improve Simulation Flow]
        GP[Generate Problems Flow]
        PA[Pythaverse Agent]
        SC_Flow[Suggest Content Flow]
    end
    
    subgraph "AI Agents"
        SA[Simulation Agent]
        QA[Quiz Agent]
        DA[Dialogue Agent]
        EA[Explanation Agent]
        TA[Title Agent]
    end
    
    subgraph "Data Layer"
        LD[Lesson Data]
        UD[User Data]
        PD[Progress Data]
        AD[Achievement Data]
        SD_Data[Simulation Data]
        CD[Component Code]
    end
    
    subgraph "Components Layer"
        UI[UI Components]
        SIM[Simulations]
        DS[Dynamic Simulation]
        GC[Generated Components]
        CH[Charts]
        FOR[Forms]
    end
    
    subgraph "Storage Layer"
        SS[Server Storage]
        CS[Client Storage]
        FS[File System]
        RG[Registry]
    end
    
    LP --> AI
    TD --> AI
    SD --> AI
    LS --> AI
    SC --> AI
    MP --> AI
    
    AI --> GEM
    AI --> CL
    AI --> GS
    AI --> IS
    AI --> GP
    AI --> PA
    AI --> SC_Flow
    
    AI --> SA
    AI --> QA
    AI --> DA
    AI --> EA
    AI --> TA
    
    CL --> LD
    GS --> SD_Data
    IS --> SD_Data
    GP --> PD
    PA --> UD
    SC_Flow --> LD
    
    SD_Data --> CD
    CD --> FS
    SD_Data --> SS
    SS --> CS
    
    UI --> LP
    UI --> TD
    UI --> SD
    UI --> LS
    UI --> SC
    UI --> MP
    
    SIM --> LS
    DS --> SIM
    GC --> DS
    RG --> GC
    CH --> TD
    CH --> SD
    FOR --> TD
    FOR --> SD
```

## 2. User Journey Flow

- Maps the complete user experience for both teachers and students
- Shows decision points and user pathways through the application

```mermaid
flowchart TD
    Start([User Lands on Site]) --> Role{User Type?}
    
    Role -->|Teacher| TSignup[Teacher Signup]
    Role -->|Student| SSignup[Student Signup]
    Role -->|Visitor| Landing[Explore Landing Page]
    
    TSignup --> TDash[Teacher Dashboard]
    SSignup --> SDash[Student Dashboard]
    Landing --> Pricing[View Pricing]
    
    subgraph "Teacher Journey"
        TDash --> TCreate[Create Lesson]
        TCreate --> Studio[Lesson Studio]
        Studio --> AI[AI Generates Blueprint]
        AI --> Edit[Edit & Refine]
        Edit --> Preview[Preview Lesson]
        Preview --> Publish[Publish to Marketplace]
        Publish --> Analytics[View Analytics]
        
        TDash --> SimCreate[Create Simulation]
        SimCreate --> SimStudio[Simulation Creator]
        SimStudio --> SimAI[AI Generates Simulation]
        SimAI --> SimCode[Generate Component Code]
        SimCode --> SimTest[Test Simulation]
        SimTest --> SimSave[Save to Registry]
        SimSave --> Studio
    end
    
    subgraph "Student Journey"
        SDash --> Browse[Browse Marketplace]
        Browse --> Select[Select Lesson]
        Select --> Learn[Start Learning]
        Learn --> AI_Tutor[AI Tutor Session]
        AI_Tutor --> Quiz[Take Quiz]
        Quiz --> Progress[Track Progress]
        Progress --> Achievements[Unlock Achievements]
        
        Learn --> SimPlay[Play Simulations]
        SimPlay --> SimFeedback[Provide Feedback]
        SimFeedback --> SimImprove[AI Improves Simulation]
    end
    
    Pricing --> TSignup
    Pricing --> SSignup
    Analytics --> TCreate
    Achievements --> Browse
    SimImprove --> SimPlay
```

## 3. AI Integration Flow

- Detailed sequence diagram showing how AI processes user requests
- Covers lesson creation, simulation generation, and improvement flows

```mermaid
sequenceDiagram
    participant T as Teacher
    participant S as Student
    participant UI as Frontend
    participant AI as Genkit AI
    participant GEM as Gemini 2.0
    participant DB as Data Store
    participant FS as File System
    
    Note over T,FS: Lesson Creation Flow
    T->>UI: Enter lesson prompt
    UI->>AI: createLessonFromPrompt()
    AI->>GEM: Generate lesson blueprint
    GEM->>AI: Return structured lesson
    AI->>UI: Display lesson bricks
    UI->>T: Show visual editor
    
    T->>UI: Edit brick content
    UI->>AI: suggestBrickContent()
    AI->>GEM: Generate content suggestions
    GEM->>AI: Return suggestions
    AI->>UI: Update brick content
    UI->>T: Show updated content
    
    Note over T,FS: Simulation Creation Flow
    T->>UI: Create simulation
    UI->>AI: generateSimulation()
    AI->>GEM: Generate simulation config
    GEM->>AI: Return simulation data
    AI->>GEM: Generate component code
    GEM->>AI: Return React component
    AI->>FS: Save component file
    AI->>DB: Save simulation metadata
    AI->>UI: Display simulation
    
    Note over T,FS: Simulation Improvement Flow
    S->>UI: Provide feedback
    UI->>AI: improveSimulation()
    AI->>DB: Load original simulation
    AI->>FS: Load original code
    AI->>GEM: Analyze feedback
    GEM->>AI: Return improvement plan
    AI->>GEM: Generate improved code
    GEM->>AI: Return new component
    AI->>FS: Save improved component
    AI->>DB: Save improved simulation
    AI->>UI: Display improved simulation
    
    Note over T,FS: Student Learning Flow
    S->>UI: Start lesson
    UI->>AI: pythaverseAgent()
    AI->>GEM: Generate tutoring response
    GEM->>AI: Return response
    AI->>UI: Display AI tutor
    UI->>S: Interactive dialogue
    
    S->>UI: Request practice problems
    UI->>AI: generateDynamicProblems()
    AI->>GEM: Generate personalized problems
    GEM->>AI: Return problems & solutions
    AI->>UI: Display problems
    UI->>S: Interactive practice
    
    UI->>DB: Save progress
    DB->>UI: Update analytics
```

## 4. Simulation System Architecture

- Visualizes the complete simulation generation and improvement pipeline
- Shows how AI creates, stores, and improves simulations

```mermaid
graph TB
    subgraph "Simulation Creation"
        TInput[Teacher Input]
        AIGen[AI Generation]
        CompGen[Component Generation]
        FileSave[File Storage]
        RegUpdate[Registry Update]
    end
    
    subgraph "Simulation Storage"
        ServerStore[Server Storage]
        ClientStore[Client Storage]
        FileSystem[File System]
        Registry[Component Registry]
    end
    
    subgraph "Simulation Loading"
        DynamicLoad[Dynamic Loader]
        StaticLoad[Static Load]
        FallbackLoad[Fallback Load]
        ComponentResolve[Component Resolution]
    end
    
    subgraph "Simulation Improvement"
        Feedback[Teacher Feedback]
        AIImprove[AI Improvement]
        CodeAnalysis[Code Analysis]
        ContextPreserve[Context Preservation]
        NewComponent[New Component]
    end
    
    subgraph "Simulation Rendering"
        StudioRender[Studio Rendering]
        PreviewRender[Preview Rendering]
        StudentRender[Student Rendering]
        ErrorBoundary[Error Boundary]
    end
    
    TInput --> AIGen
    AIGen --> CompGen
    CompGen --> FileSave
    FileSave --> RegUpdate
    
    FileSave --> FileSystem
    RegUpdate --> Registry
    AIGen --> ServerStore
    ServerStore --> ClientStore
    
    Registry --> DynamicLoad
    FileSystem --> StaticLoad
    DynamicLoad --> FallbackLoad
    StaticLoad --> ComponentResolve
    FallbackLoad --> ComponentResolve
    
    Feedback --> AIImprove
    AIImprove --> CodeAnalysis
    CodeAnalysis --> ContextPreserve
    ContextPreserve --> NewComponent
    NewComponent --> FileSave
    
    ComponentResolve --> StudioRender
    ComponentResolve --> PreviewRender
    ComponentResolve --> StudentRender
    StudioRender --> ErrorBoundary
    PreviewRender --> ErrorBoundary
    StudentRender --> ErrorBoundary
```

## 5. Lesson Studio Component Flow

- Visualizes the ReactFlow-based lesson builder with simulation integration
- Shows how the brick system and AI integration work together

```mermaid
graph TB
    subgraph "Lesson Studio Interface"
        Canvas[ReactFlow Canvas]
        Toolbar[Toolbar]
        Inspector[Inspector Panel]
        Preview[Live Preview]
        SimCreator[Simulation Creator]
    end
    
    subgraph "Brick System"
        EB[Explanation Brick]
        DB[Dialogue Brick]
        QB[Quiz Brick]
        SB[Simulation Brick]
    end
    
    subgraph "AI Integration"
        AIS[AI Suggestions]
        AIG[AI Generation]
        AIP[AI Preview]
        SimAI[Simulation AI]
    end
    
    subgraph "Simulation Integration"
        SimRegistry[Simulation Registry]
        DynamicSim[Dynamic Simulation]
        GeneratedSim[Generated Simulations]
        BuiltInSim[Built-in Simulations]
    end
    
    subgraph "Data Flow"
        Blueprint[Lesson Blueprint]
        Content[Content Data]
        Config[Configuration]
        SimData[Simulation Data]
    end
    
    Toolbar --> Canvas
    Canvas --> Inspector
    Canvas --> Preview
    SimCreator --> Canvas
    
    EB --> Canvas
    DB --> Canvas
    QB --> Canvas
    SB --> Canvas
    
    Inspector --> AIS
    AIS --> AIG
    AIG --> Content
    Content --> Preview
    
    Canvas --> Blueprint
    Blueprint --> Config
    Config --> Preview
    
    AIP --> Preview
    
    SB --> SimRegistry
    SimRegistry --> DynamicSim
    SimRegistry --> GeneratedSim
    SimRegistry --> BuiltInSim
    
    DynamicSim --> SimAI
    GeneratedSim --> SimAI
    BuiltInSim --> SimAI
    
    SimAI --> SimData
    SimData --> Preview
```

## 6. Component Architecture

- Hierarchical view of all major components
- Shows relationships between different component categories

```mermaid
graph TB
    subgraph "App Shell"
        Layout[Root Layout]
        Shell[App Shell]
        Nav[Navigation]
        Header[Header]
    end
    
    subgraph "Teacher Components"
        TDash[Teacher Dashboard]
        Studio[Lesson Studio]
        Analytics[Analytics]
        Personas[Personas]
        SimCreator[Simulation Creator]
    end
    
    subgraph "Student Components"
        SDash[Student Dashboard]
        Tutor[AI Tutor]
        Marketplace[Marketplace]
        Achievements[Achievements]
    end
    
    subgraph "Shared Components"
        UI[UI Components]
        Forms[Forms]
        Charts[Charts]
        Cards[Cards]
    end
    
    subgraph "AI Components"
        Agent[Pythaverse Agent]
        Dialogue[Dialogue Brick]
        Suggestions[AI Suggestions]
    end
    
    subgraph "Simulation Components"
        DynamicSim[Dynamic Simulation]
        CustomSim[Custom Simulation]
        Thermometer[Thermometer]
        FractionViz[Fraction Visualizer]
        GeneratedSims[Generated Simulations]
        FallbackSim[Fallback Simulation]
    end
    
    subgraph "Storage Components"
        Registry[Simulation Registry]
        ServerStorage[Server Storage]
        ClientStorage[Client Storage]
        ComponentStorage[Component Storage]
    end
    
    Layout --> Shell
    Shell --> Nav
    Shell --> Header
    
    Shell --> TDash
    Shell --> SDash
    
    TDash --> Studio
    TDash --> Analytics
    TDash --> Personas
    TDash --> SimCreator
    
    SDash --> Tutor
    SDash --> Marketplace
    SDash --> Achievements
    
    Studio --> UI
    Studio --> Forms
    Studio --> Agent
    Studio --> SimCreator
    
    Tutor --> Dialogue
    Tutor --> Agent
    
    UI --> Cards
    UI --> Charts
    
    Studio --> DynamicSim
    Studio --> CustomSim
    Studio --> Thermometer
    Studio --> FractionViz
    Studio --> GeneratedSims
    Studio --> FallbackSim
    
    DynamicSim --> Registry
    GeneratedSims --> Registry
    Registry --> ServerStorage
    Registry --> ClientStorage
    Registry --> ComponentStorage
```

## 7. Data Flow Architecture

- Illustrates how data moves through the system
- Shows input, processing, storage, and output layers

```mermaid
flowchart LR
    subgraph "User Input"
        TInput[Teacher Input]
        SInput[Student Input]
        AInput[AI Input]
        FInput[Feedback Input]
    end
    
    subgraph "Processing Layer"
        AI[AI Processing]
        Val[Validation]
        Trans[Transformation]
        CodeGen[Code Generation]
    end
    
    subgraph "Storage Layer"
        LD[(Lesson Data)]
        UD[(User Data)]
        PD[(Progress Data)]
        AD[(Analytics Data)]
        SD[(Simulation Data)]
        CD[(Component Code)]
    end
    
    subgraph "Registry Layer"
        SimReg[Simulation Registry]
        CompReg[Component Registry]
        FileReg[File Registry]
    end
    
    subgraph "Output Layer"
        UI[UI Updates]
        Notif[Notifications]
        Export[Data Export]
        SimRender[Simulation Rendering]
    end
    
    TInput --> AI
    SInput --> AI
    AInput --> AI
    FInput --> AI
    
    AI --> Val
    Val --> Trans
    Trans --> CodeGen
    
    CodeGen --> SD
    CodeGen --> CD
    Trans --> LD
    Trans --> UD
    Trans --> PD
    Trans --> AD
    
    SD --> SimReg
    CD --> CompReg
    CompReg --> FileReg
    
    LD --> UI
    UD --> UI
    PD --> UI
    AD --> UI
    SD --> UI
    CD --> UI
    
    SimReg --> SimRender
    CompReg --> SimRender
    FileReg --> SimRender
    
    UI --> Notif
    UI --> Export
    SimRender --> UI
```

## 8. AI Flow Detailed Architecture

- Deep dive into the AI processing pipeline
- Shows how Genkit and Gemini work together with specialized agents

```mermaid
graph TB
    subgraph "Input Layer"
        Prompt[Text Prompt]
        File[File Upload]
        Context[User Context]
        Feedback[Teacher Feedback]
        Code[Original Code]
    end
    
    subgraph "AI Processing Layer"
        Genkit[Genkit Framework]
        Gemini[Gemini 2.0 Flash]
        Schema[Zod Schema Validation]
    end
    
    subgraph "AI Agents"
        SimAgent[Simulation Agent]
        QuizAgent[Quiz Agent]
        DialogueAgent[Dialogue Agent]
        ExplanationAgent[Explanation Agent]
        TitleAgent[Title Agent]
    end
    
    subgraph "AI Flows"
        CL[Create Lesson Flow]
        GS[Generate Simulation Flow]
        IS[Improve Simulation Flow]
        GP[Generate Problems Flow]
        PA[Pythaverse Agent Flow]
        SC[Suggest Content Flow]
    end
    
    subgraph "Output Layer"
        Blueprint[Lesson Blueprint]
        Simulation[Simulation Config]
        Component[React Component]
        Problems[Math Problems]
        Response[AI Response]
        Content[Generated Content]
    end
    
    Prompt --> Genkit
    File --> Genkit
    Context --> Genkit
    Feedback --> Genkit
    Code --> Genkit
    
    Genkit --> Gemini
    Gemini --> Schema
    
    Schema --> SimAgent
    Schema --> QuizAgent
    Schema --> DialogueAgent
    Schema --> ExplanationAgent
    Schema --> TitleAgent
    
    SimAgent --> GS
    SimAgent --> IS
    QuizAgent --> GP
    DialogueAgent --> PA
    ExplanationAgent --> CL
    TitleAgent --> CL
    
    GS --> Simulation
    GS --> Component
    IS --> Component
    CL --> Blueprint
    GP --> Problems
    PA --> Response
    SC --> Content
    
    Blueprint --> UI[UI Components]
    Simulation --> UI
    Component --> UI
    Problems --> UI
    Response --> UI
    Content --> UI
```

## 9. Simulation Improvement Pipeline

- Detailed flow of how simulations are improved based on feedback
- Shows the complete improvement cycle

```mermaid
flowchart TD
    Start([Teacher Provides Feedback]) --> LoadSim[Load Original Simulation]
    LoadSim --> LoadCode[Load Original Component Code]
    LoadCode --> AIImprove[AI Analysis & Improvement]
    
    AIImprove --> ContextCheck{Maintain Context?}
    ContextCheck -->|No| Reject[Reject Improvement]
    ContextCheck -->|Yes| GenerateCode[Generate Improved Code]
    
    GenerateCode --> ValidateCode{Valid Component?}
    ValidateCode -->|No| Regenerate[Regenerate Code]
    ValidateCode -->|Yes| SaveCode[Save Component File]
    
    SaveCode --> UpdateRegistry[Update Component Registry]
    UpdateRegistry --> SaveMetadata[Save Simulation Metadata]
    SaveMetadata --> RegisterSim[Register in Simulation Registry]
    
    RegisterSim --> TestSim[Test Simulation]
    TestSim --> Success{Works Correctly?}
    Success -->|No| Rollback[Rollback to Original]
    Success -->|Yes| Deploy[Deploy Improved Simulation]
    
    Deploy --> Notify[Notify Teacher]
    Notify --> End([Improvement Complete])
    
    Reject --> Escalate[Escalate to Human]
    Regenerate --> AIImprove
    Rollback --> Escalate
```

## 10. Dynamic Component Loading System

- Shows how AI-generated components are loaded and rendered
- Illustrates the fallback mechanisms and error handling

```mermaid
graph TB
    subgraph "Component Request"
        UI[User Interface]
        SimID[Simulation ID]
        CompFile[Component File]
    end
    
    subgraph "Loading Strategy"
        StaticLoad[Static Registry Load]
        DynamicLoad[Dynamic Server Load]
        FileLoad[File System Load]
        FallbackLoad[Fallback Component]
    end
    
    subgraph "Component Sources"
        GeneratedComp[Generated Components]
        BuiltInComp[Built-in Components]
        ServerComp[Server Components]
        FallbackComp[Fallback Component]
    end
    
    subgraph "Error Handling"
        ErrorBoundary[Error Boundary]
        LoadingState[Loading State]
        ErrorState[Error State]
    end
    
    subgraph "Rendering"
        SuccessRender[Successful Render]
        ErrorRender[Error Render]
        LoadingRender[Loading Render]
    end
    
    UI --> SimID
    SimID --> CompFile
    
    CompFile --> StaticLoad
    StaticLoad --> GeneratedComp
    StaticLoad --> BuiltInComp
    
    GeneratedComp --> SuccessRender
    BuiltInComp --> SuccessRender
    
    StaticLoad -->|Not Found| DynamicLoad
    DynamicLoad --> ServerComp
    ServerComp --> SuccessRender
    
    DynamicLoad -->|Not Found| FileLoad
    FileLoad --> GeneratedComp
    
    FileLoad -->|Not Found| FallbackLoad
    FallbackLoad --> FallbackComp
    FallbackComp --> SuccessRender
    
    SuccessRender --> ErrorBoundary
    ErrorBoundary --> ErrorState
    ErrorState --> ErrorRender
    
    StaticLoad --> LoadingState
    DynamicLoad --> LoadingState
    FileLoad --> LoadingState
    LoadingState --> LoadingRender
```

## 11. Server-Side Storage Architecture

- Illustrates the file-based storage system
- Shows how data persists across sessions

```mermaid
graph TB
    subgraph "Client Side"
        UI[User Interface]
        LocalStorage[Local Storage]
        SessionStorage[Session Storage]
    end
    
    subgraph "API Layer"
        LoadAPI[Load Simulations API]
        SaveAPI[Save Simulation API]
        CompAPI[Save Component API]
        ImproveAPI[Improve Simulation API]
    end
    
    subgraph "Server Storage"
        SimFile[simulations.json]
        LessonFile[lessons.json]
        CompDir[components/]
        DataDir[data/]
    end
    
    subgraph "File System"
        GeneratedDir[src/components/simulations/generated/]
        RegistryFile[index.ts]
        ComponentFiles[*.tsx files]
    end
    
    subgraph "Memory Cache"
        ComponentCache[Component Cache]
        SimCache[Simulation Cache]
    end
    
    UI --> LocalStorage
    UI --> SessionStorage
    
    UI --> LoadAPI
    UI --> SaveAPI
    UI --> CompAPI
    UI --> ImproveAPI
    
    LoadAPI --> SimFile
    LoadAPI --> LessonFile
    SaveAPI --> SimFile
    CompAPI --> CompDir
    ImproveAPI --> SimFile
    ImproveAPI --> CompDir
    
    SimFile --> DataDir
    LessonFile --> DataDir
    CompDir --> DataDir
    
    CompAPI --> GeneratedDir
    ImproveAPI --> GeneratedDir
    
    GeneratedDir --> RegistryFile
    GeneratedDir --> ComponentFiles
    
    LoadAPI --> ComponentCache
    LoadAPI --> SimCache
    SaveAPI --> SimCache
    CompAPI --> ComponentCache
```

## 12. Performance Optimization Flow

- Build-time and runtime optimizations
- Asset and AI response optimization strategies

```mermaid
flowchart LR
    subgraph "Build Optimization"
        Turbopack[Turbopack]
        CodeSplit[Code Splitting]
        BundleOpt[Bundle Optimization]
        TreeShaking[Tree Shaking]
    end
    
    subgraph "Runtime Optimization"
        LazyLoad[Lazy Loading]
        Memoization[Memoization]
        Virtualization[Virtualization]
        DynamicImport[Dynamic Import]
    end
    
    subgraph "Asset Optimization"
        ImageOpt[Image Optimization]
        FontOpt[Font Optimization]
        StaticOpt[Static Optimization]
        ComponentOpt[Component Optimization]
    end
    
    subgraph "AI Optimization"
        Caching[AI Response Caching]
        Streaming[Streaming Responses]
        Batching[Request Batching]
        ModelOpt[Model Optimization]
    end
    
    subgraph "Storage Optimization"
        FileCache[File System Cache]
        MemoryCache[Memory Cache]
        RegistryOpt[Registry Optimization]
        CompCache[Component Cache]
    end
    
    Turbopack --> CodeSplit
    CodeSplit --> BundleOpt
    BundleOpt --> TreeShaking
    
    LazyLoad --> Memoization
    Memoization --> Virtualization
    Virtualization --> DynamicImport
    
    ImageOpt --> FontOpt
    FontOpt --> StaticOpt
    StaticOpt --> ComponentOpt
    
    Caching --> Streaming
    Streaming --> Batching
    Batching --> ModelOpt
    
    FileCache --> MemoryCache
    MemoryCache --> RegistryOpt
    RegistryOpt --> CompCache
    
    TreeShaking --> Performance[Performance Metrics]
    DynamicImport --> Performance
    ComponentOpt --> Performance
    ModelOpt --> Performance
    CompCache --> Performance
```

These diagrams provide a comprehensive view of the MathMind application's design flow, covering the advanced simulation system, AI integration, dynamic component loading, storage architecture, and performance optimization. Each diagram focuses on different aspects of the system to help understand the overall design and implementation approach. 
