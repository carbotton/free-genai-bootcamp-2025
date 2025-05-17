# Gen AI Architecture

RAG = Retreival Augmented Generation

Guardrails are mechanisms and frameworks designed to ensure that AI systems operate within ethical, legal, and technical boundaries. They act as a safety net.

Cache for optimization: there are a lot of places where we can put this depending on the size of the stuff the user sends, or if we want to cache some answers from the model, etc...

```mermaid
graph TD;
    user((USER)) --Query--> RAG;
    RAG --> database[(Database)];
    RAG --> Internet;
    RAG --> PromptCache;
    PromptCache --> InputGuardRail;
    InputGuardRail --> ModelAPI;
    ModelAPI --> OutputGuardRail;
    OutputGuardRail --Response--> user;

    PromptCache["Prompt Cache"];
    InputGuardRail["Input GuardRail"];
    ModelAPI["Model API 
    (Generation) 
    (LLM)"];
    OutputGuardRail["Output GuardRail"];
```