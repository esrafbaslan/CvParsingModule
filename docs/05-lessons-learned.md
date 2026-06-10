# Lessons Learned

This project was the first production-grade AI capability developed within the Digital HR SuperApp ecosystem.

Beyond solving a recruitment problem, the project provided valuable lessons about building, operating, and scaling AI-powered products in an enterprise environment.

---

## Traditional Product Thinking Does Not Fully Apply to AI Products

One of the earliest realizations was that AI products introduce new challenges that do not exist in traditional software systems.

In conventional software, deterministic behavior is expected.

In AI systems:

- The same input may produce different outputs
- Model behavior may change without code changes
- Accuracy is probabilistic rather than deterministic
- Product quality becomes a continuous optimization process

This fundamentally changes how products are designed, measured, and maintained.

---

## Traditional Logs Are Not Enough

Very early in the project, I realized that traditional application logs provide limited value when diagnosing AI system behavior.

A request may technically succeed while still producing an incorrect result.

In AI systems, understanding:

- Prompts
- Responses
- Token usage
- Latency
- Intermediate outputs

becomes as important as tracking application errors.

This led to an increased focus on observability and traceability.

---

## Observability Is a Product Requirement

AI observability should not be treated as a technical implementation detail.

Without visibility into model behavior, product teams cannot answer critical questions:

- Did accuracy improve?
- Which prompt caused the failure?
- Did a model update introduce regressions?
- Why did processing costs increase?

Observability became a prerequisite for product improvement rather than an operational convenience.

---

## Vendor Decisions Should Remain Reversible

The AI ecosystem evolves rapidly.

Models, pricing structures, capabilities, and providers change continuously.

One important lesson was the importance of maintaining architectural flexibility and avoiding unnecessary vendor lock-in wherever possible.

The ability to evaluate and switch providers creates long-term advantages in:

- Cost management
- Performance optimization
- Risk reduction
- Negotiation leverage

---

## AI Cost Management Is a Product Responsibility

AI costs are not purely an engineering concern.

Every product decision has cost implications:

- Model selection
- Prompt design
- Number of LLM calls
- Caching strategies
- Processing workflows

Understanding AI unit economics became an important part of product decision making.

---

## Build for Current Scale, Not Hypothetical Scale

One of the most valuable lessons came from introducing and later removing additional system complexity.

It is tempting to design for future growth.

However, infrastructure complexity introduces:

- Maintenance overhead
- Operational risk
- Slower delivery cycles

Future scale should be addressed when supported by real usage patterns rather than assumptions.

---

## Security Has New Dimensions in AI Systems

AI products introduce attack surfaces that do not exist in traditional applications.

Prompt injection attacks demonstrated that AI-specific security considerations must be addressed from the beginning.

Security requirements expanded beyond traditional concerns such as authentication and authorization.

AI behavior itself became part of the security model.

---

## AI Adoption Is an Organizational Learning Journey

The CV Parser project delivered business value as a recruitment capability.

At the same time, it served a broader purpose.

The initiative helped establish organizational knowledge around:

- AI product development
- Evaluation frameworks
- AI observability
- AI security
- Model lifecycle management
- Cost optimization

In many ways, the project became the foundation for future AI initiatives within the Digital HR SuperApp roadmap.

---

