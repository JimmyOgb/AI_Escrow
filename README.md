# AI_Escrow
# AI-Powered Escrow Network on GenLayer

An autonomous, Intelligent Contract escrow system that replaces traditional, centralized human dispute layers with a decentralized quorum of AI validators.

Traditional blockchains excel at processing deterministic rules (e.g., *if block timestamp > X, release funds*). However, they fail completely when faced with subjective evaluation (e.g., *did this freelancer build a responsive website that includes a working contact form?*).

**GenLayer Escrow** bridges this gap. By utilizing GenLayer's unique **Natural Language Blockchain** capabilities, this network allows code to understand, evaluate, and reach consensus on non-deterministic real-world deliverables.

---

## 🚀 Live Deployments

* **Intelligent Contract Code:** View and simulate the deployed smart contract directly in the [GenLayer Studio (0x6d63c8eD...)](https://studio.genlayer.com/?import-contract=0x6d63c8eD36cca2e2E692E36e805BBbF9a4e4D7aa).
* **Web Frontend Dashboard:** Experience the interactive client and freelancer workspace live at [genaiescrow.lovable.app](https://genaiescrow.lovable.app/).

---

## 🛠 How It Works

The network lifecycle removes human bias, shifting verification responsibility to a decentralized committee of LLM-backed validator nodes.

```
[1. Client Creates Job]       ───► Deposit payment into escrow contract with strict criteria text.
           │
           ▼
[2. Freelancer Submits Work]  ───► Upload URL, code repo, design file links, or document references.
           │
           ▼
[3. AI Validator Quorum]      ───► Randomly selected GenLayer nodes read the requirements and the submission.
           │
           ▼
[4. State Evaluation Layer]   ───► Nodes execute gl.eq_principle.prompt_comparative to establish consensus.
           │
     ┌─────┴────────────────────────┐
     ▼ (Vote Approved > 66%)        ▼ (Vote Rejected)
[Funds Released Instantly]     [Job Re-opened + Automated Punchlist Sent to Freelancer]

```

### Core Architecture Features

* **Deterministic Requirements via JSON Schemas:** Prompts and job objectives are stored securely on-chain.
* **The Equivalence Principle:** Rather than relying on a single isolated AI instance—which introduces risks of hallucinations or individual node biases—GenLayer nodes run execution prompts independently. They must match identical output values (e.g., `APPROVED` or `REJECTED`) across a supermajority quorum to progress contract execution states.
* **Automated Failure Remediation:** If a milestone submission is rejected, the AI validators extract a machine-readable punch-list specifying exactly what elements missed the original benchmark criteria, giving the freelancer crystal-clear parameters to fix and resubmit.

---

## 📄 Contract Interface Specifications

The contract is built using GenLayer's Python-centric development paradigm (`genlayer` SDK).

```python
# Core Entrypoint Functions Available to the Frontend Rail

def create_job(freelancer: Address, requirements: str, deposit_amount: int) -> int:
    """Instantiates an escrow agreement mapping an incremented job ID."""

def submit_work(job_id: int, submission_proof: str) -> None:
    """Invoked by verified freelancer to push milestone link indicators into state."""

def trigger_ai_review(job_id: int) -> str:
    """Spins up the decentralized AI validator quorum to parse, evaluate, and vote."""

```

### Expected Evaluation Response Schema

The GenVM engine enforces a clean structured JSON schema payload returned from consensus states:

```json
{
  "verdict": "REJECTED",
  "confidence_score": 0.98,
  "requirements_checklist": [
    {
      "requirement": "Functional Contact Form",
      "status": "FAILED",
      "evidence": "The contact call-to-action button paths directly to an unresolved 404 block page."
    }
  ],
  "detailed_reasoning": "A core functional element outlined inside the agreement specifications failed to respond correctly during endpoint inspection.",
  "suggested_remediation": "Restore routing to the contact component and ensure input forms validate properly before requesting another state evaluation."
}

```

---

## 💻 Tech Stack & Setup

* **Protocol Layer:** GenLayer (Python VM environment)
* **Frontend Layer:** React / Vite / TailwindCSS via Lovable sandbox
* **State Management:** JSON abstractions over `TreeMap` storage

### Running the Project Locally

1. **Clone the repository:**
```bash
git clone https://github.com/jimmyogb/genlayer-ai-escrow.git
cd genlayer-ai-escrow

```



```

2. **Interact with the Intelligent Contract:**
   * Open the [GenLayer Studio](https://studio.genlayer.com).
   * Connect your development wallet to the test network.
   * Open the contract simulator path or import directly via: `0x6d63c8eD36cca2e2E692E36e805BBbF9a4e4D7aa`.

3. **Modify the Frontend Engine:**
   * Access the frontend logic locally or via [Lovable](https://genaiescrow.lovable.app/) workspace connections to plug in custom API routes for your local node clusters.

---

## 🌟 Why GenLayer?

Traditional escrow options require multi-sig setups or centralized legal agencies that impose high platform premiums (often 5% to 20% in transaction friction fees) and take weeks to resolve disputes manually. 

GenLayer introduces **Natural Language Validation**, enabling near-zero-cost dispute handling, near-instant payment delivery cycles, and completely transparent, programmatic arbitration records kept entirely on-chain.

```
