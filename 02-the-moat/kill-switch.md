# Kill Switch Audit

## Vendor Dependency Assessment

| Dimension | Current State | Risk Level | 48-Hour Action |
|-----------|---------------|------------|----------------|
| **Provider** | Primary LLM provider is OpenAI with no production backup currently configured. | **M** | Establish accounts and API credentials with Anthropic and Google Gemini to prepare an alternate provider. |
| **Abstraction** | AI calls are routed through a centralized service layer rather than embedded throughout the application. | **L** | Verify that all AI functionality uses the abstraction layer and remove any provider-specific logic from the application. |
| **Routing** | All AI requests are currently routed to a single provider with no dynamic model selection. | **M** | Implement configuration-based model routing so requests can be redirected to another provider without code changes. |
| **Eval** | Basic functional testing exists, but no automated evaluation compares output quality across providers. | **H** | Create an evaluation suite using representative attendance scenarios to validate accuracy, consistency, explainability, and intervention recommendations before switching models. |

## Portability Score

**Partial**

Attendance Insight could migrate to another enterprise LLM within a few weeks because the AI is abstracted from the application, but additional routing and evaluation capabilities are needed before a seamless provider switch is possible.

## If OpenAI doubles pricing tomorrow:

Immediately redirect non-critical AI tasks to a lower-cost provider, benchmark alternative models for attendance risk prediction and recommendations, and migrate production workloads once they meet established quality thresholds.

## If OpenAI ships a competing product:

Differentiate through district-specific attendance policies, explainable AI, configurable intervention workflows, and a privacy-preserving federated learning network that continuously improves predictions using anonymized education outcomes while maintaining FERPA compliance.
