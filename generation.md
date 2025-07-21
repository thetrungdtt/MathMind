# MathMind Lesson Generation System Analysis & Improvement Plan

## 📊 Executive Summary

The MathMind lesson generation system has significant architectural strengths but suffers from several critical issues that impact user experience and content quality. This analysis identifies the problems and proposes a comprehensive redesign with specific implementation requirements.

## 🔍 Current System Analysis

### 📊 **Current System Flow Diagram**

```mermaid
graph TB
    subgraph "👨‍🏫 Teacher Input"
        T1[Teacher enters prompt]
        T2[Teacher uploads document]
        T3[Teacher fills complex form]
    end
    
    subgraph "🔄 Current Processing Flow"
        P1[Single-step document analysis]
        P2[Basic OCR without preprocessing]
        P3[Generic AI prompts]
        P4[Simple simulation generation]
        P5[Basic validation]
    end
    
    subgraph "🎨 Current UI Issues"
        U1[Complex form with 15+ fields]
        U2[No progressive disclosure]
        U3[Poor visual feedback]
        U4[No real-time preview]
    end
    
    subgraph "🧱 Current Brick Generation"
        B1[Title Agent - Basic title]
        B2[Explanation Agent - Generic content]
        B3[Dialogue Agent - Simple Q&A]
        B4[Simulation Agent - Basic components]
        B5[Quiz Agent - Standard questions]
    end
    
    subgraph "🎮 Current Simulation Issues"
        S1[Poor visual design]
        S2[Basic interactions]
        S3[No educational framework]
        S4[Low engagement]
        S5[Poor accessibility]
    end
    
    subgraph "📋 Current Canvas Issues"
        C1[No automatic connections]
        C2[Poor node positioning]
        C3[No flow visualization]
        C4[Missing edge logic]
        C5[No grouping functionality]
    end
    
    subgraph "💾 Current Storage"
        ST1[Basic file storage]
        ST2[No intermediate results]
        ST3[Poor parameter tracking]
        ST4[No consistency validation]
    end
    
    T1 --> P1
    T2 --> P1
    T3 --> P1
    P1 --> P2
    P2 --> P3
    P3 --> B1
    P3 --> B2
    P3 --> B3
    P3 --> B4
    P3 --> B5
    B4 --> S1
    S1 --> S2
    S2 --> S3
    S3 --> S4
    S4 --> S5
    B1 --> C1
    B2 --> C1
    B3 --> C1
    B4 --> C1
    B5 --> C1
    C1 --> C2
    C2 --> C3
    C3 --> C4
    C4 --> C5
    P1 --> ST1
    ST1 --> ST2
    ST2 --> ST3
    ST3 --> ST4
    
    style P1 fill:#ffcccc
    style P2 fill:#ffcccc
    style P3 fill:#ffcccc
    style U1 fill:#ffcccc
    style U2 fill:#ffcccc
    style S1 fill:#ffcccc
    style S2 fill:#ffcccc
    style C1 fill:#ffcccc
    style C2 fill:#ffcccc
    style ST2 fill:#ffcccc
    style ST3 fill:#ffcccc
```

### ✅ **Strengths Identified**

1. **Robust AI Architecture**: Well-structured multi-agent system with specialized agents for different content types
2. **Centralized Prompt Management**: Sophisticated prompt template system with versioning and performance tracking
3. **Comprehensive Validation**: Multi-layered code validation with syntax, security, and quality checks
4. **Flexible Storage System**: Both client-side and server-side storage with document management
5. **Component Registry**: Dynamic simulation component loading and registration system

### ❌ **Critical Issues Identified**

#### 1. **Complex User Interface**
- **Problem**: The current lesson creation interface requires too many mandatory fields and complex configurations
- **Impact**: High cognitive load, poor user experience, low adoption rates
- **Root Cause**: Over-engineered form with too many options presented simultaneously

#### 2. **Document Analysis Pipeline Issues**
- **Problem**: Document analysis doesn't follow a proper step-by-step pipeline
- **Impact**: Poor OCR results, inconsistent XML/JSON output, low quality lesson generation
- **Root Cause**: Single-step analysis without proper preprocessing and validation

#### 3. **Simulation Quality Problems**
- **Problem**: Generated simulations are basic and unengaging
- **Impact**: Poor student engagement, low educational value
- **Root Cause**: Generic prompts, lack of educational design principles, poor visual design

#### 4. **Canvas Flow Visualization Issues**
- **Problem**: ReactFlow canvas doesn't show proper connections between lesson components
- **Impact**: Teachers can't visualize lesson flow, poor lesson structure
- **Root Cause**: Missing edge creation logic, improper node positioning

#### 5. **Parameter Consistency Issues**
- **Problem**: Document analysis parameters aren't properly passed to brick generation
- **Impact**: Inconsistent lesson content, poor alignment with source materials
- **Root Cause**: Disconnected data flow between analysis and generation phases

## 🎯 **Proposed Solution Architecture**

### 📊 **Ideal System Flow Diagram**

```mermaid
graph TB
    subgraph "👨‍🏫 Teacher Input"
        T1[Teacher enters simple prompt]
        T2[Teacher uploads document]
        T3[Teacher toggles components]
        T4[Teacher previews in real-time]
    end
    
    subgraph "🔄 Enhanced Processing Pipeline"
        P1[Step 1: OCR Processing]
        P2[Step 2: Content Structuring]
        P3[Step 3: Educational Extraction]
        P4[Step 4: Quality Validation]
        P5[Step 5: Lesson Generation]
    end
    
    subgraph "🎨 Improved UI Design"
        U1[Simple mode: ≤5 fields]
        U2[Advanced mode: Optional]
        U3[Progressive disclosure]
        U4[Real-time preview]
        U5[Smart suggestions]
    end
    
    subgraph "🧱 Enhanced Brick Generation"
        B1[Title Agent - Contextual titles]
        B2[Explanation Agent - Rich content]
        B3[Dialogue Agent - Interactive conversations]
        B4[Simulation Agent - Educational components]
        B5[Quiz Agent - Adaptive questions]
    end
    
    subgraph "🎮 Enhanced Simulation Design"
        S1[Educational framework]
        S2[Visual design system]
        S3[Interactive patterns]
        S4[Accessibility features]
        S5[Engagement metrics]
    end
    
    subgraph "📋 Smart Canvas Flow"
        C1[Automatic edge creation]
        C2[Optimal node positioning]
        C3[Flow visualization]
        C4[Smart grouping]
        C5[Flow validation]
    end
    
    subgraph "💾 Enhanced Storage"
        ST1[Intermediate results storage]
        ST2[Parameter consistency tracking]
        ST3[Quality metrics storage]
        ST4[Version control]
    end
    
    subgraph "🔗 Parameter Consistency"
        PC1[Document → Analysis mapping]
        PC2[Analysis → Generation mapping]
        PC3[Generation → Canvas mapping]
        PC4[Consistency validation]
    end
    
    T1 --> U1
    T2 --> P1
    T3 --> U3
    T4 --> U4
    
    P1 --> P2
    P2 --> P3
    P3 --> P4
    P4 --> P5
    
    P5 --> B1
    P5 --> B2
    P5 --> B3
    P5 --> B4
    P5 --> B5
    
    B4 --> S1
    S1 --> S2
    S2 --> S3
    S3 --> S4
    S4 --> S5
    
    B1 --> C1
    B2 --> C1
    B3 --> C1
    B4 --> C1
    B5 --> C1
    
    C1 --> C2
    C2 --> C3
    C3 --> C4
    C4 --> C5
    
    P1 --> ST1
    P2 --> ST1
    P3 --> ST1
    P4 --> ST1
    P5 --> ST2
    
    PC1 --> PC2
    PC2 --> PC3
    PC3 --> PC4
    
    style P1 fill:#ccffcc
    style P2 fill:#ccffcc
    style P3 fill:#ccffcc
    style P4 fill:#ccffcc
    style P5 fill:#ccffcc
    style U1 fill:#ccffcc
    style U2 fill:#ccffcc
    style U3 fill:#ccffcc
    style U4 fill:#ccffcc
    style U5 fill:#ccffcc
    style S1 fill:#ccffcc
    style S2 fill:#ccffcc
    style S3 fill:#ccffcc
    style S4 fill:#ccffcc
    style S5 fill:#ccffcc
    style C1 fill:#ccffcc
    style C2 fill:#ccffcc
    style C3 fill:#ccffcc
    style C4 fill:#ccffcc
    style C5 fill:#ccffcc
    style ST1 fill:#ccffcc
    style ST2 fill:#ccffcc
    style ST3 fill:#ccffcc
    style ST4 fill:#ccffcc
    style PC1 fill:#ccffcc
    style PC2 fill:#ccffcc
    style PC3 fill:#ccffcc
    style PC4 fill:#ccffcc
```

### **Phase 1: Simplified User Interface Design**

#### **🔄 Current vs Ideal Flow Comparison**

```mermaid
graph LR
    subgraph "❌ Current Flow"
        C1[Complex Form<br/>15+ Fields]
        C2[Single-Step Analysis]
        C3[Basic OCR]
        C4[Generic Prompts]
        C5[Poor Simulations]
        C6[No Flow Visualization]
        
        C1 --> C2
        C2 --> C3
        C3 --> C4
        C4 --> C5
        C5 --> C6
    end
    
    subgraph "✅ Ideal Flow"
        I1[Simple Form<br/>≤5 Fields]
        I2[5-Step Pipeline]
        I3[Enhanced OCR]
        I4[Educational Prompts]
        I5[Engaging Simulations]
        I6[Smart Flow Visualization]
        
        I1 --> I2
        I2 --> I3
        I3 --> I4
        I4 --> I5
        I5 --> I6
    end
    
    subgraph "📊 Key Improvements"
        K1[User Experience<br/>-90% Complexity]
        K2[Processing<br/>+95% Accuracy]
        K3[Content Quality<br/>+85% Engagement]
        K4[Visualization<br/>+100% Clarity]
        K5[Consistency<br/>+100% Reliability]
    end
    
    C1 -.->|Transform| I1
    C2 -.->|Transform| I2
    C3 -.->|Transform| I3
    C4 -.->|Transform| I4
    C5 -.->|Transform| I5
    C6 -.->|Transform| I6
    
    style C1 fill:#ffcccc
    style C2 fill:#ffcccc
    style C3 fill:#ffcccc
    style C4 fill:#ffcccc
    style C5 fill:#ffcccc
    style C6 fill:#ffcccc
    
    style I1 fill:#ccffcc
    style I2 fill:#ccffcc
    style I3 fill:#ccffcc
    style I4 fill:#ccffcc
    style I5 fill:#ccffcc
    style I6 fill:#ccffcc
    
    style K1 fill:#ffffcc
    style K2 fill:#ffffcc
    style K3 fill:#ffffcc
    style K4 fill:#ffffcc
    style K5 fill:#ffffcc
```

#### **1.1 Dual-Mode Interface**

**Simple Mode (Default)**
```typescript
interface SimpleLessonForm {
  title: string;                    // Auto-generated from prompt
  subject: string;                  // Dropdown: Math, Science, ELA, etc.
  gradeLevel: string;               // Dropdown: K-12
  topic: string;                    // Free text
  description: string;              // Auto-generated
  includeSimulation: boolean;       // Toggle
  includeQuiz: boolean;             // Toggle
  includeDialogue: boolean;         // Toggle
  prompt: string;                   // Main input field
}
```

**Advanced Mode (Optional)**
```typescript
interface AdvancedLessonForm extends SimpleLessonForm {
  difficulty: string;               // Beginner/Intermediate/Advanced
  estimatedDuration: number;        // 15-60 minutes
  learningObjectives: string[];     // Array of objectives
  subtopics: string[];             // Related concepts
  prerequisites: string[];          // Required knowledge
  teachingStyle: string;            // Teaching methodology
  assessmentType: string;           // Assessment approach
}
```

#### **1.2 Progressive Disclosure Design**

```typescript
// Component Structure
<LessonCreationWizard>
  <SimpleMode>
    <QuickPromptInput />           // Main input with smart suggestions
    <SubjectGradeSelector />       // Simplified dropdowns
    <ComponentToggles />           // Visual toggles for simulations/quiz/dialogue
    <PreviewCard />                // Real-time preview
  </SimpleMode>
  
  <AdvancedMode>
    <DetailedForm />               // Full form with all options
    <LearningObjectivesBuilder />  // Interactive objective builder
    <AssessmentConfigurator />     // Assessment type selector
    <TeachingStyleSelector />      // Pedagogy options
  </AdvancedMode>
</LessonCreationWizard>
```

### **Phase 2: Enhanced Document Analysis Pipeline**

#### **2.1 Multi-Step Analysis Process**

```typescript
interface DocumentAnalysisPipeline {
  step1: OCRProcessing;           // Extract text from images/PDFs
  step2: ContentStructuring;      // Convert to structured XML/JSON
  step3: EducationalExtraction;   // Extract lesson parameters
  step4: QualityValidation;       // Validate extracted content
  step5: LessonGeneration;        // Generate lesson from structured data
}
```

#### **2.2 Step-by-Step Implementation**

**Step 1: OCR Processing**
```typescript
interface OCRProcessor {
  async processDocument(file: File): Promise<OCRResult> {
    // 1. Convert to high-resolution image
    // 2. Apply image preprocessing (contrast, noise reduction)
    // 3. Use Google Vision API for OCR
    // 4. Extract text with confidence scores
    // 5. Save OCR result to uploads directory
  }
}
```

**Step 2: Content Structuring**
```typescript
interface ContentStructurer {
  async structureContent(ocrResult: OCRResult): Promise<StructuredContent> {
    // 1. Parse OCR text into sections
    // 2. Identify headers, body text, examples
    // 3. Extract mathematical formulas and diagrams
    // 4. Generate XML/JSON structure
    // 5. Save structured content to uploads directory
  }
}
```

**Step 3: Educational Extraction**
```typescript
interface EducationalExtractor {
  async extractLessonInfo(structuredContent: StructuredContent): Promise<LessonParameters> {
    // 1. Analyze content for educational concepts
    // 2. Determine grade level and difficulty
    // 3. Extract learning objectives
    // 4. Identify prerequisites and subtopics
    // 5. Generate lesson specifications
  }
}
```

### **Phase 3: Improved Simulation Generation**

#### **3.1 Educational Design Framework**

```typescript
interface EducationalSimulationDesign {
  visualDesign: {
    colorScheme: 'accessible' | 'engaging' | 'professional';
    animations: 'subtle' | 'moderate' | 'dynamic';
    layout: 'grid' | 'flow' | 'hierarchical';
  };
  
  interactionDesign: {
    feedbackType: 'immediate' | 'delayed' | 'progressive';
    difficultyProgression: 'linear' | 'adaptive' | 'branching';
    rewardSystem: 'points' | 'badges' | 'achievements';
  };
  
  educationalContent: {
    conceptClarity: 'visual' | 'textual' | 'multimodal';
    realWorldConnections: boolean;
    multipleRepresentations: boolean;
    scaffolding: 'minimal' | 'moderate' | 'extensive';
  };
}
```

#### **3.2 Enhanced Simulation Prompts**

```typescript
interface SimulationGenerationPrompt {
  educationalContext: {
    subject: string;
    gradeLevel: string;
    learningObjectives: string[];
    commonMisconceptions: string[];
    prerequisiteSkills: string[];
  };
  
  designRequirements: {
    visualComplexity: 'simple' | 'moderate' | 'complex';
    interactionType: 'drag-drop' | 'click' | 'type' | 'multi-touch';
    feedbackStyle: 'encouraging' | 'neutral' | 'challenging';
    accessibility: 'basic' | 'comprehensive' | 'advanced';
  };
  
  technicalSpecifications: {
    framework: 'React 18+';
    styling: 'Tailwind CSS';
    animations: 'Framer Motion';
    stateManagement: 'React Hooks';
    accessibility: 'WCAG 2.1 AA';
  };
}
```

### **Phase 4: Canvas Flow Visualization**

#### **4.1 Enhanced ReactFlow Implementation**

```typescript
interface LessonFlowCanvas {
  nodes: LessonNode[];
  edges: LessonEdge[];
  flowLogic: {
    autoConnect: boolean;          // Auto-connect sequential bricks
    flowDirection: 'horizontal' | 'vertical' | 'radial';
    spacing: number;               // Distance between nodes
    grouping: boolean;             // Group related bricks
  };
}
```

#### **4.2 Smart Edge Creation**

```typescript
interface SmartEdgeCreation {
  async createLessonFlow(nodes: LessonNode[]): Promise<LessonEdge[]> {
    // 1. Analyze node types and content
    // 2. Determine logical flow sequence
    // 3. Create appropriate edge types
    // 4. Position nodes optimally
    // 5. Add flow indicators and transitions
  }
}
```

## 🤖 **AI Model Selection Strategy & Prompt Engineering**

### **Current AI Model Usage Analysis**

After examining the codebase, I've identified several issues with the current AI model selection approach:

#### **1. Static Model Assignment**
- **Problem**: Most components use `googleai/gemini-2.0-flash` regardless of task complexity
- **Impact**: Complex tasks like simulation generation receive the same model as simple title generation
- **Root Cause**: Hardcoded model selection without task-based optimization

#### **2. Limited Model Fallback**
- **Problem**: Only the `AIModelManager` has fallback capabilities, but it's rarely used
- **Impact**: When generation fails, the system doesn't automatically retry with more capable models
- **Root Cause**: Missing integration between agent-specific code and the model manager

#### **3. Prompt-Model Mismatch**
- **Problem**: Complex prompts are sent to less capable models, while simple tasks use expensive models
- **Impact**: Poor quality for complex tasks, wasted resources on simple tasks
- **Root Cause**: No systematic approach to matching prompt complexity with model capabilities

#### **4. Inconsistent Model References**
- **Problem**: Different files reference different model versions (2.0-flash, 2.0-flash-exp, 1.5-pro)
- **Impact**: Inconsistent performance and unpredictable resource usage
- **Root Cause**: Decentralized model selection without governance

### **Proposed Dynamic Model Selection Strategy**

```typescript
interface TaskComplexity {
  type: 'simple' | 'moderate' | 'complex' | 'critical';
  description: string;
  examples: string[];
  recommendedModels: string[];
  fallbackModels: string[];
  timeout: number; // milliseconds
  retryAttempts: number;
}

const taskComplexityMatrix: Record<string, TaskComplexity> = {
  'title-generation': {
    type: 'simple',
    description: 'Generate short, creative titles',
    examples: ['Lesson titles', 'Section headings'],
    recommendedModels: ['gemini-2.0-flash'],
    fallbackModels: ['gemini-1.5-flash'],
    timeout: 5000,
    retryAttempts: 2
  },
  'explanation-generation': {
    type: 'moderate',
    description: 'Generate educational explanations',
    examples: ['Concept explanations', 'Step-by-step guides'],
    recommendedModels: ['gemini-2.0-flash'],
    fallbackModels: ['gemini-2.0-flash-exp', 'gemini-1.5-pro'],
    timeout: 10000,
    retryAttempts: 2
  },
  'simulation-generation': {
    type: 'complex',
    description: 'Generate interactive code components',
    examples: ['React simulations', 'Interactive visualizations'],
    recommendedModels: ['gemini-2.5-pro', 'gemini-2.0-flash-exp'],
    fallbackModels: ['gemini-1.5-pro'],
    timeout: 30000,
    retryAttempts: 3
  },
  'document-analysis': {
    type: 'critical',
    description: 'Extract structured data from documents',
    examples: ['OCR processing', 'Curriculum analysis'],
    recommendedModels: ['gemini-2.5-pro'],
    fallbackModels: ['gemini-2.0-flash-exp', 'gemini-1.5-pro'],
    timeout: 45000,
    retryAttempts: 3
  }
}
```

### **Tiered Model Selection Implementation**

```typescript
class EnhancedAIModelManager {
  /**
   * Select the optimal model based on task type and complexity
   */
  selectModelForTask(taskType: string, context: any = {}): string {
    const task = this.taskComplexityMatrix[taskType] || this.taskComplexityMatrix['moderate'];
    
    // Consider context factors
    const contextualFactors = this.analyzeContextFactors(context);
    
    // Adjust based on content length, complexity, etc.
    if (contextualFactors.contentLength > 5000 || contextualFactors.complexity > 0.7) {
      // Upgrade to a more capable model
      return task.type === 'simple' ? 
        this.taskComplexityMatrix['moderate'].recommendedModels[0] : 
        task.recommendedModels[0];
    }
    
    return task.recommendedModels[0];
  }
  
  /**
   * Execute with automatic fallback to more capable models
   */
  async executeWithFallback(taskType: string, prompt: string, context: any = {}): Promise<any> {
    const task = this.taskComplexityMatrix[taskType];
    let attempts = 0;
    let lastError;
    
    // Try recommended models first
    for (const modelId of task.recommendedModels) {
      if (attempts >= task.retryAttempts) break;
      
      try {
        const result = await this.executeWithModel(modelId, prompt, context, task.timeout);
        return { result, modelUsed: modelId, attempts: attempts + 1 };
      } catch (error) {
        lastError = error;
        attempts++;
      }
    }
    
    // Try fallback models if recommended models failed
    for (const modelId of task.fallbackModels) {
      if (attempts >= task.retryAttempts) break;
      
      try {
        const result = await this.executeWithModel(modelId, prompt, context, task.timeout);
        return { result, modelUsed: modelId, attempts: attempts + 1 };
      } catch (error) {
        lastError = error;
        attempts++;
      }
    }
    
    throw new Error(`All models failed after ${attempts} attempts: ${lastError}`);
  }
}
```

### **Prompt Engineering Analysis & Improvements**

After analyzing all prompts in the system, I've identified several areas for improvement:

#### **1. Document Analysis Prompt**

**Current Issues:**
- Single-step processing without intermediate validation
- Lacks explicit OCR guidance
- Missing structured output format requirements
- No handling for low-quality images or partial text

**Proposed Improvements:**
```typescript
const improvedDocumentAnalysisPrompt = `
You are an expert educational content analyst with OCR capabilities. Your task is to analyze an uploaded document in a STEP-BY-STEP process:

STEP 1: OCR PROCESSING
- Carefully examine the image quality (resolution, contrast, alignment)
- Identify text regions vs. visual elements
- Extract ALL visible text with high precision
- Note any uncertain text with [?] markers
- Save extracted text as structured content

STEP 2: CONTENT STRUCTURING
- Organize extracted text into hierarchical sections
- Identify headers, subheaders, body text, and captions
- Recognize tables, lists, and special formatting
- Preserve mathematical notation and formulas
- Generate XML/JSON representation of the document structure

STEP 3: EDUCATIONAL EXTRACTION
${existingPrompt.documentAnalysis}

OUTPUT FORMAT:
You MUST return a valid JSON object with the following structure:
{
  "ocrResults": {
    "extractedText": string,
    "textConfidence": number,
    "uncertainRegions": string[]
  },
  "structuredContent": {
    "sections": Array<{title: string, content: string, type: string}>,
    "format": "XML" | "JSON",
    "content": string // XML or JSON representation
  },
  "educationalContent": {
    "documentType": string,
    "lessons": Array<LessonDetails>,
    "totalLessons": number,
    "confidence": number
  }
}
`;
```

#### **2. Simulation Generation Prompt**

**Current Issues:**
- Lacks educational design principles
- Generic instructions without subject-specific guidance
- Missing accessibility requirements
- Limited guidance on student engagement

**Proposed Improvements:**
```typescript
const improvedSimulationPrompt = `
You are an expert educational software developer creating interactive React simulations for K-12 education. 

SUBJECT-SPECIFIC DESIGN PRINCIPLES:
${getSubjectSpecificGuidance(subject)}

EDUCATIONAL ENGAGEMENT PATTERNS:
1. **Cognitive Load Management**: Balance complexity with clarity
2. **Progressive Challenge**: Start simple, gradually increase difficulty
3. **Immediate Feedback**: Provide visual and textual feedback on actions
4. **Multiple Representations**: Show concepts in different formats
5. **Guided Discovery**: Lead students to discover concepts themselves
6. **Metacognitive Prompts**: Encourage reflection on learning

${existingPrompt.simulationGeneration}

ACCESSIBILITY REQUIREMENTS:
- WCAG 2.1 AA compliance
- Keyboard navigation for all interactions
- Screen reader compatibility
- Color contrast ratios ≥ 4.5:1
- Text alternatives for visual elements
- No reliance on color alone for information

STUDENT ENGAGEMENT TECHNIQUES:
- **Gamification**: Points, badges, levels, challenges
- **Storytelling**: Narrative context for learning
- **Personalization**: Adaptable difficulty and interests
- **Social Elements**: Sharing results, collaborative features
- **Agency**: Meaningful choices and exploration
`;
```

### **Prompt Template Versioning System**

To ensure continuous improvement of prompts while maintaining backward compatibility:

```typescript
interface PromptVersion {
  version: string;
  createdAt: string;
  performance: {
    averageRating: number;
    successRate: number;
    totalUses: number;
  };
  prompt: string;
}

interface VersionedPrompt {
  id: string;
  currentVersion: string;
  versions: Record<string, PromptVersion>;
  selectVersion: (context: any) => string;
}

// Example implementation
const documentAnalysisPrompt: VersionedPrompt = {
  id: 'document-analysis',
  currentVersion: '3.0.0',
  versions: {
    '1.0.0': {
      version: '1.0.0',
      createdAt: '2023-01-01',
      performance: {
        averageRating: 3.5,
        successRate: 75,
        totalUses: 500
      },
      prompt: 'Basic document analysis prompt...'
    },
    '2.0.0': {
      version: '2.0.0',
      createdAt: '2023-06-01',
      performance: {
        averageRating: 4.2,
        successRate: 82,
        totalUses: 750
      },
      prompt: 'Improved document analysis prompt...'
    },
    '3.0.0': {
      version: '3.0.0',
      createdAt: '2024-01-01',
      performance: {
        averageRating: 4.7,
        successRate: 91,
        totalUses: 300
      },
      prompt: 'Advanced multi-step document analysis prompt...'
    }
  },
  selectVersion: (context) => {
    // Logic to select appropriate version based on context
    if (context.isLegacy) return '1.0.0';
    if (context.requiresHighAccuracy) return '3.0.0';
    return '2.0.0';
  }
};
```

## 📋 **Detailed Implementation Requirements (SRD)**

### **🔄 Ideal Lesson Creation Sequence Flow**

```mermaid
sequenceDiagram
    participant T as 👨‍🏫 Teacher
    participant UI as 🖥️ Frontend
    participant API as 🔌 API Routes
    participant AI as 🤖 AI System
    participant OCR as 🔍 OCR Service
    participant Storage as 💾 Storage
    participant Canvas as 📋 Canvas
    
    Note over T,Canvas: Simple Mode Flow
    T->>UI: Enter simple prompt
    UI->>UI: Show smart suggestions
    T->>UI: Select subject & grade
    UI->>UI: Show component toggles
    T->>UI: Toggle simulations/quiz/dialogue
    UI->>UI: Display real-time preview
    
    Note over T,Canvas: Document Upload Flow
    T->>UI: Upload document
    UI->>API: POST /api/document-analysis/ocr
    API->>OCR: Process document
    OCR->>OCR: Preprocess image
    OCR->>OCR: Extract text with confidence
    OCR->>Storage: Save OCR results
    OCR->>API: Return structured text
    API->>UI: Display extracted content
    
    Note over T,Canvas: Enhanced Analysis Pipeline
    UI->>API: POST /api/document-analysis/structure
    API->>AI: Structure content
    AI->>AI: Parse sections & headers
    AI->>AI: Extract formulas & diagrams
    AI->>AI: Generate XML/JSON
    AI->>Storage: Save structured content
    AI->>API: Return structured data
    
    UI->>API: POST /api/document-analysis/extract
    API->>AI: Extract lesson parameters
    AI->>AI: Analyze educational concepts
    AI->>AI: Determine grade level
    AI->>AI: Extract learning objectives
    AI->>Storage: Save lesson parameters
    AI->>API: Return lesson specs
    
    Note over T,Canvas: Quality Validation
    UI->>API: POST /api/parameter-consistency/validate
    API->>AI: Validate extracted data
    AI->>AI: Check consistency
    AI->>AI: Verify completeness
    AI->>API: Return validation results
    
    Note over T,Canvas: Lesson Generation
    T->>UI: Click "Generate Lesson"
    UI->>API: POST /api/lesson-generation/simple
    API->>AI: Generate lesson with parameters
    AI->>AI: Title Agent - Contextual title
    AI->>AI: Explanation Agent - Rich content
    AI->>AI: Dialogue Agent - Interactive Q&A
    AI->>AI: Simulation Agent - Educational component
    AI->>AI: Quiz Agent - Adaptive questions
    AI->>Storage: Save lesson blueprint
    AI->>API: Return complete lesson
    API->>UI: Display generated lesson
    
    Note over T,Canvas: Canvas Flow Creation
    UI->>Canvas: Create lesson flow
    Canvas->>Canvas: Auto-create edges
    Canvas->>Canvas: Position nodes optimally
    Canvas->>Canvas: Group related bricks
    Canvas->>Canvas: Validate flow
    Canvas->>UI: Display flow visualization
    
    Note over T,Canvas: Enhanced Simulation
    UI->>API: POST /api/simulation-generation/enhanced
    API->>AI: Generate educational simulation
    AI->>AI: Apply educational framework
    AI->>AI: Use visual design system
    AI->>AI: Implement interactions
    AI->>AI: Add accessibility features
    AI->>Storage: Save simulation component
    AI->>API: Return enhanced simulation
    API->>UI: Display engaging simulation
    
    Note over T,Canvas: Final Preview & Save
    T->>UI: Review complete lesson
    UI->>UI: Show final preview
    T->>UI: Click "Save Lesson"
    UI->>Storage: Save final lesson
    Storage->>UI: Confirm save
    UI->>T: Lesson created successfully!
```

### **SRD-001: Simplified Lesson Creation Interface**

**Priority**: Critical
**Effort**: 2 weeks
**Dependencies**: None

**Requirements**:
1. Create dual-mode interface (Simple/Advanced)
2. Implement progressive disclosure
3. Add smart prompt suggestions
4. Create real-time preview
5. Add one-click lesson generation

**Acceptance Criteria**:
- Simple mode requires ≤5 fields
- Advanced mode accessible via toggle
- Smart suggestions improve with usage
- Preview updates in real-time
- Generation completes in ≤30 seconds

### **SRD-002: Enhanced Document Analysis Pipeline**

**Priority**: Critical
**Effort**: 3 weeks
**Dependencies**: Google Vision API integration

**Requirements**:
1. Implement 5-step analysis pipeline
2. Add OCR preprocessing
3. Create XML/JSON structuring
4. Add quality validation
5. Save intermediate results

**Acceptance Criteria**:
- OCR accuracy ≥95% for clear documents
- Structured output follows schema
- Quality validation catches errors
- Intermediate files saved to uploads/
- Processing time ≤60 seconds

### **SRD-003: Improved Simulation Generation**

**Priority**: High
**Effort**: 4 weeks
**Dependencies**: SRD-002

**Requirements**:
1. Implement educational design framework
2. Create enhanced simulation prompts
3. Add visual design system
4. Implement interaction patterns
5. Add accessibility features

**Acceptance Criteria**:
- Simulations are visually engaging
- Educational value is high
- Accessibility compliance achieved
- Performance is smooth (60fps)
- Code quality score ≥85%

### **SRD-004: Canvas Flow Visualization**

**Priority**: High
**Effort**: 2 weeks
**Dependencies**: ReactFlow library

**Requirements**:
1. Implement smart edge creation
2. Add flow indicators
3. Create optimal node positioning
4. Add grouping functionality
5. Implement flow validation

**Acceptance Criteria**:
- Edges show proper connections
- Flow is visually clear
- Nodes are optimally positioned
- Groups are logical
- Validation prevents invalid flows

### **SRD-005: Parameter Consistency System**

**Priority**: Medium
**Effort**: 1 week
**Dependencies**: SRD-002

**Requirements**:
1. Create parameter mapping system
2. Implement data flow validation
3. Add consistency checks
4. Create parameter inheritance
5. Add override capabilities

**Acceptance Criteria**:
- Parameters flow correctly
- Validation catches inconsistencies
- Inheritance works properly
- Overrides are respected
- Data integrity maintained

### **SRD-006: Dynamic AI Model Selection & Prompt Engineering**

**Priority**: Critical
**Effort**: 3 weeks
**Dependencies**: None

**Requirements**:
1. Implement task complexity classification system
2. Create tiered model selection strategy
3. Develop automatic fallback mechanisms
4. Implement context-aware model selection
5. Overhaul prompt templates with improved versions
6. Create prompt versioning and performance tracking
7. Implement subject-specific prompt variations

**Acceptance Criteria**:
- Complex tasks automatically use more capable models (Gemini 2.5 Pro)
- Simple tasks use efficient models (Gemini 2.0 Flash)
- Failed generations retry with more capable models
- Document analysis uses multi-step prompting
- Simulation generation includes educational design principles
- All prompts have versioned templates with performance tracking
- Generation quality improves by ≥30% across all content types

## 🚀 **Implementation Timeline**

### **Week 1-2: Simplified Interface & AI Model Selection**
- [ ] Design dual-mode interface
- [ ] Implement simple mode
- [ ] Add smart suggestions
- [ ] Create preview system
- [ ] Implement task complexity classification
- [ ] Create tiered model selection strategy

### **Week 3-5: Document Analysis Pipeline & Prompt Engineering**
- [ ] Implement OCR processing
- [ ] Create content structuring
- [ ] Add educational extraction
- [ ] Implement quality validation
- [ ] Overhaul document analysis prompts
- [ ] Create prompt versioning system
- [ ] Implement performance tracking

### **Week 6-9: Simulation Generation & Enhanced Prompts**
- [ ] Design educational framework
- [ ] Create enhanced simulation prompts
- [ ] Implement subject-specific prompt variations
- [ ] Implement visual design system
- [ ] Add accessibility features
- [ ] Integrate automatic model fallback

### **Week 10-11: Canvas Flow & Parameter Consistency**
- [ ] Implement smart edge creation
- [ ] Add flow indicators
- [ ] Create optimal positioning
- [ ] Add grouping functionality
- [ ] Implement parameter mapping
- [ ] Create consistency validation

### **Week 12-13: Integration & Testing**
- [ ] Integrate all components
- [ ] Perform end-to-end testing
- [ ] Optimize performance
- [ ] Conduct prompt quality evaluation
- [ ] Measure AI model efficiency
- [ ] Deploy to production

## 📊 **Success Metrics**

### **User Experience Metrics**
- Lesson creation time: <5 minutes (simple mode)
- User satisfaction score: ≥4.5/5
- Error rate: <5%
- Adoption rate: ≥80% of teachers

### **Quality Metrics**
- Document analysis accuracy: ≥95%
- Simulation engagement score: ≥4.0/5
- Code quality score: ≥85%
- Accessibility compliance: WCAG 2.1 AA

### **Performance Metrics**
- Generation time: <30 seconds
- Canvas rendering: 60fps
- API response time: <2 seconds
- System uptime: ≥99.9%

## 🔧 **Technical Implementation Details**

### **File Structure Changes**
```
src/
├── components/
│   ├── lesson-creation/
│   │   ├── simple-mode/
│   │   │   ├── quick-prompt-input.tsx
│   │   │   ├── subject-grade-selector.tsx
│   │   │   └── component-toggles.tsx
│   │   ├── advanced-mode/
│   │   │   ├── detailed-form.tsx
│   │   │   └── learning-objectives-builder.tsx
│   │   └── shared/
│   │       ├── preview-card.tsx
│   │       └── progress-indicator.tsx
│   └── studio/
│       ├── enhanced-canvas/
│       │   ├── smart-edge-creator.tsx
│       │   ├── flow-indicators.tsx
│       │   └── node-positioning.tsx
│       └── simulation-creator/
│           ├── educational-framework.tsx
│           ├── visual-design-system.tsx
│           └── interaction-patterns.tsx
├── lib/
│   ├── services/
│   │   ├── document-analysis-pipeline.ts
│   │   ├── parameter-consistency.ts
│   │   └── simulation-quality.ts
│   └── utils/
│       ├── ocr-processor.ts
│       ├── content-structurer.ts
│       └── educational-extractor.ts
└── uploads/
    ├── ocr-results/
    ├── structured-content/
    └── lesson-parameters/
```

### **API Endpoints**
```typescript
// New endpoints to implement
POST /api/document-analysis/ocr
POST /api/document-analysis/structure
POST /api/document-analysis/extract
POST /api/lesson-generation/simple
POST /api/lesson-generation/advanced
POST /api/simulation-generation/enhanced
POST /api/canvas-flow/create
POST /api/parameter-consistency/validate
```

## 🎯 **Conclusion**

This comprehensive redesign addresses all identified issues while maintaining the system's architectural strengths. The phased approach ensures manageable implementation while delivering immediate value to users. The focus on simplicity, quality, and consistency will significantly improve the MathMind platform's effectiveness and user satisfaction.

**Next Steps**:
1. Review and approve this plan
2. Prioritize SRD requirements
3. Begin Phase 1 implementation
4. Set up monitoring and metrics
5. Plan user testing and feedback collection 
