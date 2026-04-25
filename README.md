# Senitnel Labs

Behavioural fraud intelligence for Indian fintech firms.

## What it does

Senitnel detects coordinated financial fraud across multiple 
accounts that individually look completely normal.

Every existing tool monitors one account at a time.
Fraud happens across accounts.
Sentinel watches the behaviour across them.

## The problem

Fintech fraud teams take days to weeks to detect coordinated 
attacks ,because each individual signal never crosses a 
threshold. Five accounts sending ₹49,000 each to the same 
merchant UPI looks like five normal transactions. Together 
it is ₹2.4 lakh in coordinated structuring to evade RBI 
reporting obligations.

Senitnel caught this in 3 seconds.


## How it works

Sentinel runs as a Docker container inside the customer's 
own infrastructure. Nothing leaves their environment.

The agent uses a ReAct loop — Reason, Act, Observe — to:

1. Watch live transaction streams continuously
2. Filter 99% of noise before LLM reasoning begins
3. Correlate events across accounts using 6-month memory
4. Trace hidden common origins autonomously
5. Reason about group behaviour using a local LLM
6. Fire structured alerts with RBI consequence analysis

## What it catches

- UPI structuring across multiple accounts below ₹50,000 threshold
- Mule networks with hidden common funding origin
- Insider data theft via legitimate access misuse  
- Vendor API access drift outside normal scope
- Weekly slip detection — slow fraud across 4-week windows
- Cross-team signal gaps — risk, operations, legal

## Architecture

- Built in Go — handles high concurrency natively
- Local LLM inference — Llama 3.1 fine-tuned on fintech patterns
- Zero external API calls in production
- Three-layer memory: hot (2h), warm (30d), cold baseline (6m)
- PCI-DSS and RBI compliant by design
- One command deployment: docker pull + docker run

## Stack

- Go — agent core, ReAct loop, tools, memory
- Llama 3.1 via Ollama — local LLM inference
- SQLite → PostgreSQL — memory persistence
- Slack webhooks — alert delivery

## Status

R&D stage. Actively talking to fintech security engineers.
Seeking pilot partners.

## Contact

hello@sentinellabs.com
