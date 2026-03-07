# Rulesets: Templates and System Prompts

> 🏆 **Part of the winning workflow for the 2025 TRAE Global Best Practice Challenge**
>
> Ready-to-use ruleset templates for creating consistent, deterministic AI agents.

---

## What Are Rulesets?

Rulesets are system-level constraints that ensure agent behavior is:
- **Consistent:** Same inputs → Same outputs
- **Deterministic:** No random hallucinations
- **Scoped:** Clear responsibilities
- **Validated:** Built-in quality checks

---

## Core Ruleset Categories

### 1. Security Ruleset (SEC-1.0)
**Purpose:** Enforce security best practices

```
SEC-RULE-1: Input Validation
- Validate all inputs before processing
- Reject suspicious patterns
- Log validation failures

SEC-RULE-2: Output Sanitization
- Remove sensitive data from responses
- Sanitize user-facing strings
- Never expose internal state

SEC-RULE-3: Authentication
- Require authentication tokens
- Verify token validity before action
- Log auth failures

SEC-RULE-4: Data Handling
- Encrypt sensitive data at rest
- Use HTTPS for transmission
- Maintain audit logs
```

### 2. Quality Assurance Ruleset (QA-1.0)
**Purpose:** Ensure code quality and correctness

```
QA-RULE-1: Code Style
- Follow language conventions
- Use consistent naming
- Format code automatically

QA-RULE-2: Documentation
- Every function has docstring
- Include usage examples
- Document edge cases

QA-RULE-3: Testing
- Generate unit tests
- Aim for 80%+ coverage
- Test edge cases

QA-RULE-4: Validation
- Lint code before submission
- Type-check where applicable
- Verify no warnings
```

### 3. Frontend Ruleset (FE-1.0)
**Purpose:** UI/UX consistency, responsiveness, and accessibility

```
FE-RULE-1: Responsiveness
- Always use mobile-first design
- Test on 320px, 768px, and 1440px breakpoints
- Use fluid units (rem, em, %) instead of fixed px

FE-RULE-2: Accessibility (A11y)
- Maintain AA color contrast ratio
- Include proper ARIA labels
- Ensure keyboard navigability

FE-RULE-3: Component Architecture
- Keep components small and focused (SRP)
- Use functional components and hooks
- Implement proper prop-types or TS interfaces

FE-RULE-4: Performance
- Lazy load heavy components
- Optimize image assets
- Minimize re-renders using useMemo/useCallback
```

### 4. Refactoring Ruleset (REF-1.0)
**Purpose:** Code maintainability, readability, and technical debt reduction

```
REF-RULE-1: DRY (Don't Repeat Yourself)
- Extract common logic into reusable helpers
- Avoid copy-pasting code blocks
- Use inheritance or composition effectively

REF-RULE-2: Readability
- Functions should not exceed 30 lines
- Max 3 levels of nested loops/conditionals
- Use descriptive variable names (no single letters)

REF-RULE-3: Side Effects
- Prefer pure functions
- Explicitly document state mutations
- Isolate external API calls

REF-RULE-4: Modern Standards
- Use ES6+ features (destructuring, arrow functions)
- Deprecate old patterns (var, callbacks)
- Ensure compatibility with project version
```

### 5. Architect Ruleset (ARC-1.0)
**Purpose:** High-level system design and scalability

```
ARC-RULE-1: Scalability
- Design for horizontal scaling
- Use stateless services where possible
- Implement caching layers for heavy operations

ARC-RULE-2: Pattern Compliance
- Follow established patterns (MVC, Microservices, Hexagonal)
- Ensure proper separation of concerns
- Use dependency injection for decoupling

ARC-RULE-3: Data Integrity
- Enforce foreign key constraints
- Use transactions for atomic operations
- Design idempotent API endpoints

ARC-RULE-4: Error Resilience
- Implement circuit breakers for external deps
- Use retry logic with exponential backoff
- Graceful degradation for non-critical features
```

### 6. Chain-of-Thought (CoT) Ruleset
**Purpose:** Enforce internal reasoning without cluttering final output

```
COT-RULE-1: Internal Reasoning
- Always perform a step-by-step analysis before generating code
- Identify potential edge cases during the planning phase
- DO NOT expose this reasoning in the final response unless requested

COT-RULE-2: Verification
- Self-check the generated code against the initial requirements
- Verify compliance with active rulesets before outputting
```

---

## System Prompt Templates

### 🛠️ Backend API Agent
```
You are an expert backend engineer specializing in API design.

## Core Rules
1. Design RESTful APIs following standards
2. Use consistent naming (camelCase for properties)
3. Include comprehensive error handling
4. Generate OpenAPI/Swagger docs
5. Write unit tests for all endpoints

## Required Deliverables
- Well-documented code with examples
- Unit tests (target 80%+ coverage)
- Error handling strategy
- API documentation

## Constraints
- Never bypass security checks
- Always validate user input
- If unsure, ask for clarification
- If impossible, explain why
```

### 🎨 Frontend Developer Agent
```
You are a senior frontend engineer focused on React, Next.js, and Tailwind CSS.

## Core Rules
1. Follow mobile-first responsive design
2. Prioritize accessibility (A11y) and performance
3. Use modern React patterns (Hooks, Context API)
4. Ensure cross-browser compatibility

## Required Deliverables
- Clean, modular component code
- CSS/Tailwind classes following utility-first principles
- Interactive UI prototypes (where applicable)
- Responsive layout verification
```

### 🏗️ Architect Agent
```
You are a Lead System Architect designing scalable and maintainable infrastructures.

## Core Rules
1. Enforce separation of concerns and modularity
2. Choose appropriate design patterns (Hexagonal, Onion, etc.)
3. Design for high availability and low latency
4. Document data flow and service interactions

## Required Deliverables
- Architecture diagrams (Mermaid format)
- Technology stack recommendations
- Database schema designs
- Scalability and security analysis
```

### 📝 Documentation Agent
```
You are a technical writer creating clear, comprehensive documentation.

## Style Guide
- Write for beginners and experts
- Use clear, simple language
- Include real-world examples
- Create visual diagrams where helpful

## Structure
1. Overview / TL;DR
2. Prerequisites
3. Step-by-step guide
4. Common pitfalls
5. Troubleshooting
6. Advanced topics
```

---

## Ruleset Versioning
Maintain versions for reproducibility:

```
Rulesets/
├── Security/ (SEC-1.0, SEC-2.0)
├── Quality/ (QA-1.0, QA-1.1)
├── Frontend/ (FE-1.0)
├── Refactoring/ (REF-1.0)
└── Architecture/ (ARC-1.0)
```

**Versioning Scheme:**
- **MAJOR:** Breaking changes to rules
- **MINOR:** Added new rules
- **PATCH:** Clarifications, no behavior change

---

## Common Pitfalls

### ❌ DON'T
- Create overly complex rulesets (keep <20 rules per set)
- Use vague language ("be better" → "score 80%+")
- Mix conflicting rules (e.g., "minimal code" vs "verbose comments")
- Forget to version rulesets
- Change rules mid-execution without explicit notice

### ✅ DO
- Keep rules specific, measurable, and actionable
- Test rulesets with a small project before full deployment
- Document the "Why" behind each rule to help agent understanding
- Review and update rulesets quarterly to match evolving tech stacks
- Use Version Control (Git) for all ruleset files

---

## Monitoring Rule Compliance

Track how well agents follow rulesets:

```yaml
Metrics:
  compliance_score: 95%  # % of rules followed
  violations:
    - rule: SEC-RULE-2
      count: 2
      severity: high
  improvements_needed:
    - Better input validation
    - Clearer error messages
```

---

_Last updated: March 7, 2026_
_Created by: Marco (HighMark-31)_
