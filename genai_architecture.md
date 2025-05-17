# Gen AI Architecture

```mermaid
graph TD;
    user((USER)) --|Query|--> RAG;
    RAG --> database[(Database)];
    RAG --> internet["Internet"];
    RAG --> PromptCache;
    PromptCache --> InputGuardRail;
    InputGuardRail --> ModelAPI;
    ModelAPI --> OutputGuardRail;
    OutputGuardRail --|Response|--> user;

    PromptCache["Prompt Cache"];
    InputGuardRail["Input GuardRail"];
    ModelAPI["Model API (Generation) (LLM)"];
    OutputGuardRail["Output GuardRail"];
```