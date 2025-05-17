# Gen AI Architecture

```mermaid
graph TD;
    ((USER)) --|Query|--> RAG;
    RAG --> [(Database)];
    RAG --> (((Internet)));
    RAG --> PromptCache;
    PromptCache --> InputGuardRail;
    InputGuardRail --> ModelAPI;
    ModelAPI --> OutputGuardRail;
    OutputGuardRail --|Response|--> ((USER));

    PromptCache["Prompt Cache"];
    InputGuardRail["Input GuardRail"];
    ModelAPI["Model API (Generation) (LLM)"];
    OutputGuardRail["Output GuardRail"];

```