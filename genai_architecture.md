# Gen AI Architecture

```mermaid
  graph TD;
      USER-->RAG;
      RAG-->Database;
      RAG-->Internet;
      RAG-->"Prompt Cache";
      "Prompt Cache"->"Input GuardRail"
      "Input GuardRail"->"Model API (Generation) (LLM)"
      "Model API (Generation) (LLM)"->"Output GuardRail"
      "Output GuardRail"->USER
```