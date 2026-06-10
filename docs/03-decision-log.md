# Product Decision Log

This document captures the most important product decisions made during the development of the AI CV Parser platform.

The objective is not to document technical implementation details, but to explain the business context, alternatives considered, trade-offs, outcomes, and lessons learned.

---

## Decision 1: Semantic Matching Instead of Traditional Keyword Search

### Business Challenge

Recruiters frequently need to evaluate candidates across highly specialized domains.

Candidates often describe similar skills using different terminology, acronyms, certifications, technologies, or job titles.

Examples:

- Product Owner vs Product Manager
- Generative AI Engineer vs LLM Engineer
- Data Engineer vs Analytics Engineer

Traditional ATS solutions rely heavily on keyword matching, which increases the risk of overlooking qualified candidates.

### Alternatives Considered

#### Option A: Traditional Keyword Search

**Advantages**

- Simple implementation
- Low infrastructure cost
- Easy to explain

**Disadvantages**

- Limited understanding of context
- Sensitive to wording differences
- Poor performance in specialized recruitment scenarios

#### Option B: Semantic Search Using Embeddings

**Advantages**

- Understands contextual similarity
- Supports multilingual candidate discovery
- Reduces dependency on recruiter domain expertise

**Disadvantages**

- Higher infrastructure complexity
- Additional AI processing costs
- Requires vector database infrastructure

### Decision

The platform adopted semantic matching as a core capability.

Candidate profiles and job descriptions are converted into vector embeddings and compared based on semantic similarity rather than exact keyword matches.

### Outcome

The platform became capable of identifying relevant candidates even when qualifications were described differently across CVs and job descriptions.

This significantly improved candidate discovery and aligned with the long-term vision of supporting complex enterprise recruitment scenarios.

### Lessons Learned

Recruitment is fundamentally a knowledge discovery problem rather than a document search problem.

Semantic understanding created significantly more value than traditional keyword-based approaches.

---

## Decision 2: Parallel LLM Processing Instead of Sequential Processing

### Business Challenge

Early versions of the platform processed CV sections sequentially.

As the number of extraction tasks increased, overall processing time became a concern for user experience.

### Alternatives Considered

#### Option A: Sequential Processing

**Advantages**

- Simpler orchestration
- Easier debugging

**Disadvantages**

- High latency
- Poor user experience

#### Option B: Parallel Processing

**Advantages**

- Faster processing times
- Better scalability

**Disadvantages**

- Increased orchestration complexity
- More concurrent API requests

### Decision

Independent extraction tasks were executed in parallel whenever possible.

Examples included:

- Personal information extraction
- Work experience extraction
- Skills extraction
- Language extraction

### Outcome

Processing latency was reduced from approximately 45–60 seconds to 10–15 seconds.

This significantly improved perceived product responsiveness.

### Lessons Learned

In AI products, user-perceived latency is often more important than implementation simplicity.

---

## Decision 3: Multi-Provider AI Architecture

### Business Challenge

AI models evolve rapidly.

Relying on a single provider creates risks related to pricing, availability, model performance, and vendor lock-in.

### Alternatives Considered

#### Option A: Single Provider

**Advantages**

- Simpler architecture
- Lower maintenance effort

**Disadvantages**

- Vendor dependency
- Reduced flexibility

#### Option B: Multi-Provider Strategy

**Advantages**

- Flexibility
- Cost optimization opportunities
- Ability to benchmark models

**Disadvantages**

- Additional engineering effort
- More testing requirements

### Decision

The platform was designed to support multiple AI providers including OpenAI, Gemini, and OpenRouter-based models.

### Outcome

The team gained flexibility in balancing cost, speed, and quality across different use cases.

### Lessons Learned

Model selection should be treated as a continuously evolving product decision rather than a one-time technical choice.

---

## Decision 4: Investing in AI Observability

### Business Challenge

AI systems behave differently from traditional deterministic software systems.

Failures are often difficult to diagnose without visibility into prompts, model responses, token usage, and latency.

One of the earliest lessons I learned while working on AI products was that traditional application logs quickly become insufficient.

In conventional software systems, logs generally provide enough information to identify where a failure occurred.

AI systems are fundamentally different.

A request may technically succeed while still producing an incorrect result. The same input may generate different outputs across executions. A model upgrade can change behavior without any code changes. In many cases, standard application logs only confirm that a request was completed, not whether the outcome was correct.


### Decision
My focus was not on selecting a specific observability vendor, but on ensuring that the platform would provide:

- End-to-end traceability
- Prompt visibility
- Latency monitoring
- Token consumption tracking
- Failure analysis capabilities

I also advocated for solutions that minimized vendor lock-in and additional licensing costs wherever possible.

The engineering team evaluated implementation alternatives and ultimately selected LangSmith as the most practical solution for the initial phase of the project.

### Outcome

The team gained visibility into:

- Prompt performance
- Model behavior
- Latency
- Token consumption
- Failure patterns

### Lessons Learned

Observability is not optional in production AI systems.

Without observability, AI product improvement becomes largely guesswork.

---

## Decision 5: Prompt Injection Protection

### Business Challenge

Production systems exposed new attack surfaces specific to AI applications.

Users could attempt to manipulate model behavior through prompt injection techniques embedded inside uploaded documents.

### Decision

A layered protection strategy was introduced including:

- Input validation
- Prompt hardening
- Output validation
- Anomaly detection

This part was mostly carried out by the engineering team.
### Outcome

The platform became significantly more resilient against AI-specific attack vectors.

### Lessons Learned

AI security should be considered a product requirement, not simply an engineering concern.
