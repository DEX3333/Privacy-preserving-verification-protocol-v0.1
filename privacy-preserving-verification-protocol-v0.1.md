# Privacy-Preserving Verification Protocol v0.1

## Purpose

This protocol is a practical review format for sensitive Task Node submissions where the contributor must prove meaningful work without exposing protected material.

It applies to sensitive technical artifacts where public evidence must be enough for review, but full disclosure would expose private code, raw datasets, wallet identifiers, proprietary trading logic, client information, or operational security details.

The reviewer should be able to answer:

1. What was produced?
2. What evidence proves the artifact exists?
3. What was withheld, and why?
4. Can the public proof be reviewed without exposing protected material?
5. Is a reviewer-local check needed?
6. Does the evidence support acceptance, clarification, or resubmission?

This page is reviewer-oriented. It is not a governance essay.

---

## 1. Accepted Proof Types

Sensitive submissions should include one or more of the following proof types. Hashes alone are only enough when the task explicitly requires proof of artifact existence. Most submissions should combine outcome proof with screenshots, redacted samples, reviewer-local checks, or minimum necessary metadata.

| Proof type | Accepted use | Minimum reviewer standard |
|---|---|---|
| Outcome proof | Shows the final dashboard, spreadsheet, report, chart, table, model summary, or research result without exposing sensitive internals. | The reviewer can understand what was produced, what changed, and why it matters. |
| Screenshots/logs | Shows the artifact running, a spreadsheet structure, a dashboard view, a backtest summary, terminal output, formula evidence, or safe run logs. | Screenshots/logs include relevant context, visible output, clear redactions, and an explanation of what is shown. |
| Hash proof | Proves a private file, notebook, dataset, code bundle, spreadsheet, or report existed at submission time. | Includes hash method, artifact label, creation date, description, and whether reviewer-local verification is available. |
| Redacted sample | Shows structure and quality while masking sensitive values. | Preserves enough shape for review, such as columns, safe sample rows, score categories, or shortened identifiers. |
| Reviewer-local check | Lets a trusted reviewer inspect private material without public release. | Provides exact steps the reviewer can follow and states what public claims the private artifact should confirm. |
| Minimum necessary metadata | Describes the task, proof, withheld material, review path, and downstream reuse without exposing private content. | The reviewer can evaluate the claim without needing unrelated sensitive details. |

Hash proof format:

```txt
Artifact:
Hash method: SHA-256
Hash:
Created:
Description:
Sensitive material withheld:
Reviewer access:
```

Reviewer-local check format:

```txt
Reviewer-local check:
1. Open the private artifact shared with reviewer only.
2. Confirm the artifact matches the public claim.
3. Compare the public redacted sample to the private artifact.
4. Confirm sensitive material is not exposed in public evidence.
5. Record the reviewer decision and any required clarification.
```

---

## 2. Redaction Checklist

Use this checklist before submitting public evidence.

```txt
[ ] No API keys, private keys, seed phrases, passwords, or environment variables are visible
[ ] No full private wallet addresses, validator operator addresses, client wallets, or exchange deposit addresses are exposed
[ ] No private repository URLs, admin panels, deployment endpoints, internal IPs, or monitoring links are visible
[ ] No raw private dataset, paid data feed, client dataset, or personally identifying information is exposed
[ ] No exact proprietary trading trigger, parameter set, signal weight, position-sizing formula, or live deployment logic is exposed
[ ] No client names, private communications, contracts, or confidential business metrics are exposed without permission
[ ] Screenshots were checked for hidden sensitive details in tabs, URLs, sidebars, tooltips, logs, filenames, and comments
[ ] Redactions preserve enough structure for review
[ ] Aggregates, shortened identifiers, schemas, pseudocode, or synthetic rows are used where raw details are unnecessary
[ ] Hash proof is included when proving a private file, dataset, notebook, spreadsheet, or code bundle
[ ] Reviewer-local check is included when public proof alone cannot establish the claim
[ ] The reason for withholding each sensitive material category is stated
```

Allowed public substitutes:

| Sensitive material | Safer substitute |
|---|---|
| Private code | Folder structure, selected signatures, pseudocode, dependency list, test output, screenshots, code bundle hash |
| Raw dataset | Schema, data dictionary, synthetic rows, aggregate statistics, row counts, dataset hash |
| Wallet identifiers | Shortened format, role labels, anonymized wallet groups, aggregate exposure |
| Proprietary trading logic | Research question, general methodology, aggregate results, risk metrics, sanitized chart, notebook hash |
| Client information | Anonymized client category, sanitized outcome, private reviewer-only proof |
| Operational security details | Sanitized architecture, non-sensitive logs, high-level controls, private report hash |

---

## 3. Reviewer Acceptance Criteria by Task Class

Only the following task classes are covered by this protocol.

### 3.1 Validator Dashboard

A validator dashboard submission may be accepted if it proves that the contributor built or improved a dashboard that helps review validator status, performance, risk, or delegation quality.

Required public evidence:

```txt
[ ] Dashboard objective stated clearly
[ ] Screenshot of dashboard overview
[ ] Screenshot or sample of validator detail view
[ ] Explanation of metrics used
[ ] Redacted sample data
[ ] Reproduction steps or reviewer-local check
[ ] Sensitive fields listed and justified
[ ] Downstream reuse potential explained
```

Acceptable proof types:

- Outcome proof
- Screenshots/logs
- Hash proof
- Redacted sample
- Reviewer-local check
- Minimum necessary metadata

Minimum acceptance standard:

```txt
[ ] Reviewer can identify what the dashboard tracks
[ ] Reviewer can understand how validators are evaluated
[ ] Reviewer can see the main risk or performance signals
[ ] Reviewer can identify what was withheld and why
[ ] Reviewer can determine whether the artifact is reusable for future review
```

Needs resubmission if:

```txt
[ ] Only a vague dashboard screenshot is provided
[ ] Metrics are not explained
[ ] Validator data cannot be interpreted
[ ] Redactions remove the structure needed for review
[ ] No reproduction path or reviewer-local check is provided
[ ] Private wallets, validator identifiers, infrastructure details, or admin URLs are exposed
```

### 3.2 DeFi Risk Spreadsheet

A DeFi risk spreadsheet submission may be accepted if it provides structured analysis of protocol, pool, asset, counterparty, liquidity, smart contract, or portfolio risk.

Required public evidence:

```txt
[ ] Spreadsheet objective stated clearly
[ ] Screenshot of sheet structure
[ ] Redacted sample rows
[ ] Explanation of scoring model or risk categories
[ ] Formula visibility on at least one safe sample row, if possible
[ ] Aggregate results or summary table
[ ] Source signals listed
[ ] Sensitive fields listed and justified
[ ] Reviewer-local check if formulas or private data cannot be public
```

Acceptable proof types:

- Outcome proof
- Screenshots/logs
- Hash proof
- Redacted sample
- Reviewer-local check
- Minimum necessary metadata

Minimum acceptance standard:

```txt
[ ] Reviewer can identify what risks were assessed
[ ] Reviewer can understand what inputs were used
[ ] Reviewer can understand how risk categories were generated
[ ] Reviewer can determine whether the spreadsheet is structured and reusable
[ ] Reviewer can connect the evidence to the claimed analytical value
```

Needs resubmission if:

```txt
[ ] Only final scores are shown with no method
[ ] Source signals are missing
[ ] Spreadsheet structure is hidden entirely
[ ] Formulas are claimed but not evidenced
[ ] Private wallets, client positions, or paid data rows are exposed
[ ] Reviewer cannot determine whether the analysis was actually performed
```

### 3.3 Trading-System Research Artifact

A trading-system research artifact may be accepted if it proves that the contributor conducted structured research into a market hypothesis, signal, strategy, risk model, execution model, or backtest without exposing proprietary trading logic.

Required public evidence:

```txt
[ ] Research question stated clearly
[ ] Market or asset universe described at a safe level
[ ] General methodology explained
[ ] Aggregate results shown
[ ] Risk metrics included
[ ] Drawdown or failure conditions included
[ ] Sensitive strategy logic redacted
[ ] Hash of research notebook or report included
[ ] Reviewer-local check available for private verification
```

Acceptable proof types:

- Outcome proof
- Screenshots/logs
- Hash proof
- Redacted sample
- Reviewer-local check
- Minimum necessary metadata

Minimum acceptance standard:

```txt
[ ] Reviewer can identify what hypothesis was tested
[ ] Reviewer can understand what kind of data was used
[ ] Reviewer can interpret what the result suggests
[ ] Reviewer can see risks, drawdowns, limitations, or failure conditions
[ ] Reviewer can identify what logic was withheld and why
[ ] Reviewer can privately verify that the research artifact exists
```

Needs resubmission if:

```txt
[ ] Submission only claims profitability
[ ] No risk metrics are included
[ ] No method is described
[ ] Exact trading logic is overexposed
[ ] Results cannot be connected to any artifact
[ ] Hash proof or reviewer-local verification is missing for private research
```

---

## 4. Three Mock Examples

### 4.1 Validator Dashboard

```txt
Task class: Validator dashboard
Contributor claim: Built a local dashboard that ranks validators by uptime, commission, slashing history, delegation concentration, and alert status.
Sensitive material withheld: Wallet identifiers, operational security details, private code
Proof types included: Outcome proof, screenshots/logs, hash proof, redacted sample, reviewer-local check

Public proof:
- Screenshot of dashboard overview with validator names shortened
- Screenshot of validator detail view with operator address masked
- Redacted sample row showing uptime_30d, commission, delegation_concentration_score, slashing_history, and risk_tier
- SHA-256 hash of private dashboard repo archive

Reviewer-local check:
1. Open reviewer-only dashboard build.
2. Confirm public screenshots match the private dashboard structure.
3. Confirm risk tier is generated from the stated metrics.
4. Confirm wallet identifiers and private endpoints are absent from public proof.

Reviewer decision: Accepted
Failure mode: None
```

### 4.2 DeFi Risk Spreadsheet

```txt
Task class: DeFi risk spreadsheet
Contributor claim: Produced a spreadsheet that scores DeFi pools by liquidity depth, smart contract maturity, counterparty exposure, volatility, and concentration risk.
Sensitive material withheld: Raw dataset, wallet identifiers, client information
Proof types included: Outcome proof, screenshots/logs, redacted sample, reviewer-local check, minimum necessary metadata

Public proof:
- Screenshot of workbook tabs: Inputs, Risk Scores, Pool Summary, Notes
- Redacted sample rows with pool labels anonymized
- One safe formula screenshot showing weighted scoring on synthetic values
- Aggregate summary table showing count of low, medium, and high risk pools

Reviewer-local check:
1. Open reviewer-only spreadsheet.
2. Confirm formulas exist in the private score columns.
3. Compare public synthetic row structure to private sheet structure.
4. Confirm client positions and raw wallet data are not public.

Reviewer decision: Accepted with clarification
Clarification needed: Contributor should add a short note explaining the source signal categories.
Failure mode: Ambiguous
```

### 4.3 Trading-System Research Artifact

```txt
Task class: Trading-system research artifact
Contributor claim: Completed research on whether a volatility-regime filter improves drawdown behavior for a market-neutral strategy.
Sensitive material withheld: Proprietary trading logic, raw dataset, operational security details
Proof types included: Outcome proof, screenshots/logs, hash proof, redacted sample, reviewer-local check

Public proof:
- Research summary with hypothesis, asset universe described at category level, and general methodology
- Aggregate backtest table showing annualized return, max drawdown, Sharpe ratio, win rate, and turnover
- Sanitized chart showing equity curve and drawdown without exact signal parameters
- SHA-256 hash of private research notebook
- Run log excerpt with dataset paths and parameters redacted

Reviewer-local check:
1. Open reviewer-only notebook.
2. Verify the notebook hash against the submitted hash.
3. Confirm aggregate results in the public summary match notebook outputs.
4. Confirm exact entry, exit, and parameter logic remain private.

Reviewer decision: Needs resubmission
Resubmission reason: Public evidence includes performance metrics but omits failure conditions and limitations.
Failure mode: Insufficient
```

---

## 5. Failure-Mode Table

| Failure mode | Reviewer signal | Common cause | Reviewer action |
|---|---|---|---|
| None | Evidence is specific, reviewable, properly redacted, and tied to the claimed artifact. | Submission includes outcome proof, safe samples, and a clear review path. | Accept or accept with minor clarification. |
| Insufficient | Evidence does not prove the artifact exists or does not support the claim. | Only claims, final scores, or vague screenshots are provided. | Mark `Needs resubmission` or `Insufficient evidence`. Request concrete proof. |
| Ambiguous | Evidence exists but the reviewer cannot connect it to the task, method, or claimed outcome. | Missing source signals, unclear metrics, unlabeled screenshots, or unexplained risk categories. | Mark `Accepted with clarification` or `Ambiguous evidence`. Request targeted explanation. |
| Overexposed | Evidence reveals sensitive material that should have been withheld. | Full wallets, raw datasets, client details, private endpoints, or exact trading logic are visible. | Mark `Overexposed evidence`. Require corrected public proof before acceptance. |
| Non-reproducible | The reviewer cannot inspect, reproduce, or privately verify the artifact. | No reviewer-local check, broken links, missing hash, missing files, or unverifiable screenshots. | Mark `Non-reproducible evidence`. Request a review path or private verification package. |

---

## 6. Copyable JSON Schema

```json
{
  "task_id": {
    "type": "string",
    "required": true
  },
  "task_class": {
    "type": "string",
    "required": true,
    "allowed_values": [
      "Validator dashboard",
      "DeFi risk spreadsheet",
      "Trading-system research artifact",
      "Other sensitive technical artifact"
    ]
  },
  "contributor_claim": {
    "type": "string",
    "required": true
  },
  "artifact_description": {
    "type": "string",
    "required": true
  },
  "sensitive_material_withheld": {
    "type": "array",
    "required": true,
    "items": {
      "type": "string",
      "allowed_values": [
        "Private code",
        "Raw dataset",
        "Wallet identifiers",
        "Proprietary trading logic",
        "Client information",
        "Operational security details",
        "Other"
      ]
    }
  },
  "withholding_reason": {
    "type": "string",
    "required": true
  },
  "proof_types_included": {
    "type": "array",
    "required": true,
    "items": {
      "type": "string",
      "allowed_values": [
        "Outcome proof",
        "Screenshots/logs",
        "Hash proof",
        "Redacted sample",
        "Reviewer-local check",
        "Minimum necessary metadata"
      ]
    }
  },
  "public_proof": {
    "type": "array",
    "required": true,
    "items": {
      "type": "object",
      "properties": {
        "proof_label": {
          "type": "string"
        },
        "proof_type": {
          "type": "string"
        },
        "url_or_reference": {
          "type": "string"
        },
        "what_it_shows": {
          "type": "string"
        },
        "redactions_applied": {
          "type": "string"
        }
      }
    }
  },
  "hash_proofs": {
    "type": "array",
    "required": false,
    "items": {
      "type": "object",
      "properties": {
        "artifact_label": {
          "type": "string"
        },
        "hash_method": {
          "type": "string",
          "example": "SHA-256"
        },
        "hash": {
          "type": "string"
        },
        "created": {
          "type": "string"
        },
        "description": {
          "type": "string"
        }
      }
    }
  },
  "reviewer_local_check": {
    "type": "array",
    "required": false,
    "items": {
      "type": "string"
    }
  },
  "reviewer_decision": {
    "type": "string",
    "required": true,
    "allowed_values": [
      "Accepted",
      "Accepted with clarification",
      "Needs resubmission",
      "Insufficient evidence",
      "Ambiguous evidence",
      "Overexposed evidence",
      "Non-reproducible evidence"
    ]
  },
  "failure_mode": {
    "type": "string",
    "required": true,
    "allowed_values": [
      "None",
      "Insufficient",
      "Ambiguous",
      "Overexposed",
      "Non-reproducible"
    ]
  },
  "reviewer_notes": {
    "type": "string",
    "required": false
  }
}
```

Copyable checklist format:

```txt
Task ID:
Task class:
Contributor claim:
Artifact description:

Sensitive material withheld:
[ ] Private code
[ ] Raw dataset
[ ] Wallet identifiers
[ ] Proprietary trading logic
[ ] Client information
[ ] Operational security details
[ ] Other:

Reason for withholding:

Proof types included:
[ ] Outcome proof
[ ] Screenshots/logs
[ ] Hash proof
[ ] Redacted sample
[ ] Reviewer-local check
[ ] Minimum necessary metadata

Public proof provided:
[ ] Outcome proof is specific
[ ] Screenshots/logs include context and clear redactions
[ ] Redacted sample preserves reviewable structure
[ ] Hash proof includes method, artifact label, date, and description
[ ] Reviewer-local check steps are clear if needed
[ ] Minimum necessary metadata is complete

Reviewer decision:
[ ] Accepted
[ ] Accepted with clarification
[ ] Needs resubmission
[ ] Insufficient evidence
[ ] Ambiguous evidence
[ ] Overexposed evidence
[ ] Non-reproducible evidence

Failure mode:
[ ] None
[ ] Insufficient
[ ] Ambiguous
[ ] Overexposed
[ ] Non-reproducible

Reviewer notes:
```

---

## 7. Dropdown/Form-Field Spec

Implementation-ready fields for a submission or reviewer form.

| Field key | Label | Type | Required | Options |
|---|---|---|---|---|
| `task_id` | Task ID | Text | Yes | Free text |
| `task_class` | Task class | Dropdown | Yes | Validator dashboard; DeFi risk spreadsheet; Trading-system research artifact; Other sensitive technical artifact |
| `contributor_claim` | Contributor claim | Long text | Yes | Free text |
| `artifact_description` | Artifact description | Long text | Yes | Free text |
| `sensitive_material_withheld` | Sensitive material withheld | Multi-select dropdown | Yes | Private code; Raw dataset; Wallet identifiers; Proprietary trading logic; Client information; Operational security details; Other |
| `withholding_reason` | Reason for withholding | Long text | Yes | Free text |
| `proof_types_included` | Proof types included | Multi-select dropdown | Yes | Outcome proof; Screenshots/logs; Hash proof; Redacted sample; Reviewer-local check; Minimum necessary metadata |
| `public_proof_links` | Public proof links or references | Repeating text fields | Yes | URL, file reference, or short description |
| `hash_proof` | Hash proof | Repeating group | Conditional | Artifact label; hash method; hash; created date; description |
| `reviewer_local_check` | Reviewer-local check | Ordered checklist | Conditional | Free-text steps |
| `reviewer_decision` | Reviewer decision | Dropdown | Yes | Accepted; Accepted with clarification; Needs resubmission; Insufficient evidence; Ambiguous evidence; Overexposed evidence; Non-reproducible evidence |
| `failure_mode` | Failure mode | Dropdown | Yes | None; Insufficient; Ambiguous; Overexposed; Non-reproducible |
| `reviewer_notes` | Reviewer notes | Long text | No | Free text |

Dropdown option sets:

```json
{
  "sensitive_material_withheld": [
    "Private code",
    "Raw dataset",
    "Wallet identifiers",
    "Proprietary trading logic",
    "Client information",
    "Operational security details",
    "Other"
  ],
  "proof_types_included": [
    "Outcome proof",
    "Screenshots/logs",
    "Hash proof",
    "Redacted sample",
    "Reviewer-local check",
    "Minimum necessary metadata"
  ],
  "task_class": [
    "Validator dashboard",
    "DeFi risk spreadsheet",
    "Trading-system research artifact",
    "Other sensitive technical artifact"
  ],
  "reviewer_decision": [
    "Accepted",
    "Accepted with clarification",
    "Needs resubmission",
    "Insufficient evidence",
    "Ambiguous evidence",
    "Overexposed evidence",
    "Non-reproducible evidence"
  ],
  "failure_mode": [
    "None",
    "Insufficient",
    "Ambiguous",
    "Overexposed",
    "Non-reproducible"
  ]
}
```
