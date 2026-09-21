```text
docs/
├── README.md               # Public-facing docs index & quickstarts
├── backend/                # Internal architecture, state gateways, & protocol specs
│   └── README.md
└── diagrams/               # Visual grammar, patent drawing specs, & SVG assets
    └── README.md
```
----
# VeloxLabs Diagram & Patent Drawing Grammar

Unified visual and architectural grammar for VeloxLabs system diagrams across web documentation, technical specifications, and patent filings.

To maintain visual clarity across both Mac and Windows, all diagrams standardize on **Inter Light** (`font-weight: 300`) with open letter-spacing (`letter-spacing: 0.02em` to `0.04em`) embedded in SVG styles, paired with **JetBrains Mono** for implementation tokens and formal badges.

---

## 1. Interaction Transcript Notation

Standard syntax used across system prompts, diagnostic traces, and interactive documentation:

* **Context Marker (`::`):**
  > Indicates that contextual scope, structural schema, or execution payload follows immediately.
* **Model Quoting (`""...""`):**
  > Captures verbatim, unmodified strings and generative inference outputs.

---

## 2. Typographic Hierarchy

* **Primary Typeface:** `Inter` (Fallback: `Segoe UI`, `system-ui`, `-apple-system`, `sans-serif`)
* **Weights & Letter-Spacing:**
  * **Figure Titles & Headers:** `font-weight: 600`, `letter-spacing: 0.05em`
  * **Card Labels & State Verbs:** `font-weight: 500` or `600`, `letter-spacing: 0.02em`
  * **Body & State Descriptions:** `font-weight: 300` (Light), `letter-spacing: 0.01em`
  * **Constraints & Rules:** `font-weight: 300` (Italic), muted slate
* **Monospace Stack (Tokens & Badges):**
  > `font-family: 'JetBrains Mono', 'Cascadia Mono', Consolas, 'SF Mono', monospace;`

---

## 3. Chromatic Palette & Tonal Balance

To avoid cognitive fatigue and ensure high legibility in formal reviews:

* **60% Whitespace / Base:** `#FFFFFF` or clean neutral canvas.
* **30% Structural Frame:** Neutral slates (`#0F172A`, `#E2E8F0`, `#F8FAFC`).
* **10% Intentional Accent:** Reserved strictly for state transitions, validation checkpoints, or audit triggers.

---

## 4. Architectural Layering & Patent Nomenclature

Diagrams maintain a strict distinction between generic functional claims (patent specification) and runtime embodiments (open-source / proprietary implementations):

* **Structural Nouns First:** Formal roles describe functional architecture (e.g., *State Gateway*, *Runtime Inference Engine*, *Persistent Context Store*).
* **Implementation Badges Second:** Runtime embodiments are displayed as lightweight monospace badges (e.g., `[impl: RAAUE]`, `[impl: PROMPT]`).

### Protocol Mapping Ledger

| Architectural Role | Formal / Patent Classification | Runtime Embodiment |
| :--- | :--- | :--- |
| **Retrieval & Baseline Context** | **RIP** (Retrieval Interaction Protocol) | **RAAUE Protocol** |
| **Recursive Revision Engine** | **RIP-R** (Recursive Loop Protocol) | **RRAAUEE Extension** |
| **Persistent Grounding** | **SPP** (Shared Persistent Protocol) | **SCOPE Engine** |
| **Governed Context Assembly** | **GIP** (Governed Inference Protocol) | **PROMPT Framework Schema** |
| **Verification & State Sync** | **SIP** (State Integrity Protocol) | **PACT Engine** |

> **State Invariant:** Transcripts represent transient session context. Persistent canonical state is never mutated directly by model inference; all state updates require deterministic gating via the RAAUE pathway (`Add` → `Ask` → `Update`).

---

## 5. Asset Export Pipeline

* **Master Working Asset (`.svg`):** Maintained with editable text tags adhering to typography standards.
* **Formal / Patent Export (`.svg` / `.pdf`):** Convert all typography to vector paths (`Cmd/Ctrl + Shift + O` in Illustrator/Figma) prior to publication to guarantee zero font substitution.
==
docs/README.md (Public): Developer guides, skill installation instructions, and public tool usage.

docs/backend/ (Internal/System): Core runtime logic, state-gating rules, schema definitions, and internal API contracts.

docs/diagrams/ (Grammar & Patent Assets): Visual grammar, SVG rules, and patent drawing specs.
    ----
   # VeloxLabs Diagram & Patent Drawing Grammar

Unified visual and architectural grammar for VeloxLabs system diagrams across web documentation, technical specifications, and patent filings.

To maintain visual clarity across both Mac and Windows, all diagrams standardize on **Inter Light** (`font-weight: 300`) with open letter-spacing (`letter-spacing: 0.02em` to `0.04em`) embedded in SVG styles, paired with **JetBrains Mono** for implementation tokens and formal badges.

---

## 1. Interaction Transcript Notation

Standard syntax used across system prompts, diagnostic traces, and interactive documentation:

* **Context Marker (`::`):**
  > Indicates that contextual scope, structural schema, or execution payload follows immediately.
* **Model Quoting (`""...""`):**
  > Captures verbatim, unmodified strings and generative inference outputs.

---

## 2. Typographic Hierarchy

* **Primary Typeface:** `Inter` (Fallback: `Segoe UI`, `system-ui`, `-apple-system`, `sans-serif`)
* **Weights & Letter-Spacing:**
  * **Figure Titles & Headers:** `font-weight: 600`, `letter-spacing: 0.05em`
  * **Card Labels & State Verbs:** `font-weight: 500` or `600`, `letter-spacing: 0.02em`
  * **Body & State Descriptions:** `font-weight: 300` (Light), `letter-spacing: 0.01em`
  * **Constraints & Rules:** `font-weight: 300` (Italic), muted slate
* **Monospace Stack (Tokens & Badges):**
  > `font-family: 'JetBrains Mono', 'Cascadia Mono', Consolas, 'SF Mono', monospace;`

---

## 3. Chromatic Palette & Tonal Balance
To avoid cognitive fatigue and ensure high legibility in formal reviews:

* **60% Whitespace / Base:** `#FFFFFF` or clean neutral canvas.
* **30% Structural Frame:** Neutral slates (`#0F172A`, `#E2E8F0`, `#F8FAFC`).
* **10% Intentional Accent:** Reserved strictly for state transitions, validation checkpoints, or audit triggers.
---

## 4. Architectural Layering & Patent Nomenclature
Diagrams maintain a strict distinction between generic functional claims (patent specification) and runtime embodiments (open-source / proprietary implementations):

* **Structural Nouns First:** Formal roles describe functional architecture (e.g., *State Gateway*, *Runtime Inference Engine*, *Persistent Context Store*).
* **Implementation Badges Second:** Runtime embodiments are displayed as lightweight monospace badges (e.g., `[impl: RAAUE]`, `[impl: PROMPT]`).

### Protocol Mapping Ledger
| Architectural Role | Formal / Patent Classification | Runtime Embodiment |
| :--- | :--- | :--- |
| **Retrieval & Baseline Context** | **RIP** (Retrieval Interaction Protocol) | **RAAUE Protocol** |
| **Recursive Revision Engine** | **RIP-R** (Recursive Loop Protocol) | **RRAAUEE Extension** |
| **Persistent Grounding** | **SPP** (Shared Persistent Protocol) | **SCOPE Engine** |
| **Governed Context Assembly** | **GIP** (Governed Inference Protocol) | **PROMPT Framework Schema** |
| **Verification & State Sync** | **SIP** (State Integrity Protocol) | **PACT Engine** |

> **State Invariant:** Transcripts represent transient session context. Persistent canonical state is never mutated directly by model inference; all state updates require deterministic gating via the RAAUE pathway (`Add` → `Ask` → `Update`).
---

## 5. Asset Export Pipeline
* **Master Working Asset (`.svg`):** Maintained with editable text tags adhering to typography standards.
* **Formal / Patent Export (`.svg` / `.pdf`):** Convert all typography to vector paths (`Cmd/Ctrl + Shift + O` in Illustrator/Figma) prior to publication to guarantee zero font substitution. 
