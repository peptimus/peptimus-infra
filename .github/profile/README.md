<div align="center">

<img src="https://raw.githubusercontent.com/peptimus/.github/main/profile/banner.png" alt="Peptimus" width="100%" />

# Peptimus

**Decentralized AI Peptide Design on Solana**

[![License](https://img.shields.io/badge/license-MIT-00f5ff?style=for-the-badge&labelColor=0a0f1c)](https://github.com/peptimus/peptimus/blob/main/LICENSE)
[![Solana](https://img.shields.io/badge/Solana-Mainnet-9945FF?style=for-the-badge&logo=solana&logoColor=white&labelColor=0a0f1c)](https://solana.com)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.9-3178C6?style=for-the-badge&logo=typescript&logoColor=white&labelColor=0a0f1c)](https://www.typescriptlang.org)
[![Node](https://img.shields.io/badge/Node.js-24-339933?style=for-the-badge&logo=node.js&logoColor=white&labelColor=0a0f1c)](https://nodejs.org)
[![React](https://img.shields.io/badge/React-18-61DAFB?style=for-the-badge&logo=react&logoColor=white&labelColor=0a0f1c)](https://react.dev)
[![pnpm](https://img.shields.io/badge/pnpm-workspace-F69220?style=for-the-badge&logo=pnpm&logoColor=white&labelColor=0a0f1c)](https://pnpm.io)

---

*Design. Evolve. Own. The future of peptide research is on-chain.*

</div>

---

## What is Peptimus?

Peptimus is an AI-powered platform for peptide sequence design, evolution, and intellectual property ownership on the Solana blockchain. Researchers use natural language to design novel peptides, evolve them through AI-guided iterations, and mint them as IP-NFTs using the Molecule Protocol standard.

```mermaid
flowchart TD
    A([Researcher]) -->|Natural language prompt| B[AI Design Studio]
    B -->|OpenAI dual-call| C{Peptide Engine}
    C -->|Sequence generation| D[Peptide Candidate]
    C -->|Variant evolution| E[Evolution Tree]
    D --> F[Library]
    E --> F
    F -->|Wallet connected| G[IP-NFT Mint]
    G -->|Gasless - platform pays fees| H[(Solana Mainnet)]
    H -->|cNFT ownership| A
    F -->|Discover| I[Community Feed]
    F -->|Search| J[Full-text Search]

    style A fill:#00f5ff,color:#0a0f1c,stroke:none
    style B fill:#8b5cf6,color:#fff,stroke:none
    style C fill:#0a0f1c,color:#00f5ff,stroke:#00f5ff
    style D fill:#1a2035,color:#00ff9f,stroke:none
    style E fill:#1a2035,color:#00ff9f,stroke:none
    style F fill:#1a2035,color:#fff,stroke:none
    style G fill:#8b5cf6,color:#fff,stroke:none
    style H fill:#9945FF,color:#fff,stroke:none
    style I fill:#1a2035,color:#fff,stroke:none
    style J fill:#1a2035,color:#fff,stroke:none
```

---

## Architecture

```mermaid
graph LR
    subgraph Frontend ["peptimus/peptimus"]
        FE[React 18 + Vite]
        TW[Tailwind CSS]
        FM[Framer Motion]
        R3F[React Three Fiber]
        ZU[Zustand]
        JUP[Jupiter Wallet]
    end

    subgraph API ["peptimus/peptimus-api"]
        EX[Express 5]
        DZ[Drizzle ORM]
        PG[(PostgreSQL)]
        OA[OpenAI]
        SOL[Solana Web3]
    end

    subgraph Shared ["peptimus/peptimus-shared"]
        SPEC[OpenAPI Spec]
        ZOD[Zod Schemas]
        CLIENT[React Query Hooks]
    end

    subgraph Infra ["peptimus/peptimus-infra"]
        CI[GitHub Actions]
        APP[GitHub App]
        MONO[pnpm Workspace]
    end

    Frontend --> Shared
    API --> Shared
    Infra --> Frontend
    Infra --> API
    Infra --> Shared
    API --> PG
    API --> OA
    API --> SOL

    style Frontend fill:#0a0f1c,stroke:#00f5ff,color:#00f5ff
    style API fill:#0a0f1c,stroke:#8b5cf6,color:#8b5cf6
    style Shared fill:#0a0f1c,stroke:#00ff9f,color:#00ff9f
    style Infra fill:#0a0f1c,stroke:#f59e0b,color:#f59e0b
```

---

## Tech Stack

```mermaid
mindmap
  root((Peptimus))
    Frontend
      React 18
      Vite
      Tailwind CSS
      Framer Motion
      React Three Fiber
      Wouter
      Zustand
    Blockchain
      Solana Mainnet
      Metaplex Bubblegum
      Jupiter Wallet
      cNFT IP-NFT
    Backend
      Express 5
      PostgreSQL
      Drizzle ORM
      OpenAI GPT
      Pino Logger
    Shared
      TypeScript 5.9
      OpenAPI Spec
      Zod v4
      React Query
    Infrastructure
      pnpm Workspace
      GitHub Actions
      GitHub App CI
      Node.js 24
```

---

## Repositories

<div align="center">

| Repository | Description | Stack |
|---|---|---|
| [peptimus](https://github.com/peptimus/peptimus) | Main web application | ![React](https://img.shields.io/badge/-React-61DAFB?style=flat-square&logo=react&logoColor=black) ![Vite](https://img.shields.io/badge/-Vite-646CFF?style=flat-square&logo=vite&logoColor=white) ![Tailwind](https://img.shields.io/badge/-Tailwind-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white) |
| [peptimus-api](https://github.com/peptimus/peptimus-api) | REST API and database layer | ![Node](https://img.shields.io/badge/-Node.js-339933?style=flat-square&logo=node.js&logoColor=white) ![Express](https://img.shields.io/badge/-Express-000000?style=flat-square&logo=express&logoColor=white) ![Postgres](https://img.shields.io/badge/-PostgreSQL-336791?style=flat-square&logo=postgresql&logoColor=white) |
| [peptimus-shared](https://github.com/peptimus/peptimus-shared) | Shared TypeScript packages | ![TypeScript](https://img.shields.io/badge/-TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white) ![OpenAPI](https://img.shields.io/badge/-OpenAPI-6BA539?style=flat-square&logo=openapiinitiative&logoColor=white) ![Zod](https://img.shields.io/badge/-Zod-3E67B1?style=flat-square) |
| [peptimus-infra](https://github.com/peptimus/peptimus-infra) | Monorepo root and infrastructure | ![pnpm](https://img.shields.io/badge/-pnpm-F69220?style=flat-square&logo=pnpm&logoColor=white) ![GitHub Actions](https://img.shields.io/badge/-Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white) |

</div>

---

## Peptide Lifecycle

```mermaid
sequenceDiagram
    actor R as Researcher
    participant S as AI Studio
    participant A as API Server
    participant DB as PostgreSQL
    participant SOL as Solana Mainnet

    R->>S: Enter therapeutic prompt
    S->>A: POST /api/peptides/design
    A->>A: Dual OpenAI call (interpretation + variants)
    A->>DB: Save peptide candidate
    A-->>S: Sequence + evolution score + metrics
    S-->>R: Show peptide card

    R->>S: Mint as IP-NFT
    S->>A: POST /api/peptides/:id/mint
    A->>SOL: Gasless cNFT mint via platform wallet
    SOL-->>A: Mint address
    A->>DB: Save mint address
    A-->>S: IP-NFT confirmed
    S-->>R: Ownership on-chain
```

---

## Roadmap

```mermaid
timeline
    title Peptimus Platform Roadmap
    Q2 2025 : AI Peptide Design Studio
            : IP-NFT Minting on Solana Mainnet
            : Community Feed and Discovery
    Q3 2025 : PTMS Token Launch
            : Bounty Program with Token Rewards
            : Peptide Comparison Tool
    Q4 2025 : DAO Governance
            : Smart Contract Bounty Validation
            : Researcher Reputation System
    Q1 2026 : Partner Protocol Integrations
            : Cross-chain IP-NFT Bridging
            : Enterprise Research API
```

---

<div align="center">

[![X](https://img.shields.io/badge/Follow_on_X-000000?style=for-the-badge&logo=x&logoColor=white)](https://x.com/peptimusdev)
[![GitHub](https://img.shields.io/badge/GitHub_Org-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/peptimus)

**Built by [peptimusdev](https://github.com/peptimusdev)**

</div>
