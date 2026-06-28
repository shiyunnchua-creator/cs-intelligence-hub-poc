# Customer Success Intelligence Hub: a working POC

A proof of concept exploring how generative AI can augment Customer Success workflows in B2B SaaS, with two distinct deployment modes for SMB and Enterprise segments.

**Live demo:** https://shiyunnchua-creator.github.io/cs-intelligence-hub-poc/

## What this project is

In B2B SaaS, 60 to 80 percent of revenue comes from existing accounts, which makes the renewal process one of the most commercially important and effort heavy parts of the Customer Success role. Three months before renewal, a CSM is pulling data across multiple systems, mapping stakeholders, scoring churn risk, and identifying expansion opportunities. One month out, they are assembling the commercial proposal by combining structured data (contracts, MRR, client economics) with unstructured signals (call transcripts, industry news, stakeholder movement).

This prototype explores what happens when AI takes over the assembly and synthesis work, while keeping human judgment at the centre of every commercial decision.

## The main use case: AI-powered renewal centre

The hub does three things:

1. **A single dashboard** surfacing client economics, engagement data, and churn risk from an internal scoring model.
2. **Upsell signals pulled from external sources** like office expansion, new country entry, headcount growth, or downsizing news.
3. **Stakeholder movement tracking**, flagging when a champion moves to a prospect (opportunity to follow), or when someone joins an existing client as a future champion (relationship to build early).

The renewal workflow demo shows the full journey end to end: pick an account, see the data the AI pulled, review the drafted commercial deck, edit before sending, and approve.

## What the dashboard shows

The prototype is structured around a four-step CSM workflow. The toggle at the top right switches between **ENT** and **SMB** modes, which is the central design idea.

**ENT mode (human in the loop).** Each CSM manages 20 to 30 strategic accounts. The agent drafts the deck, surfaces churn signals, maps stakeholders, and stops. The CSM reviews, edits, and decides. The agent never sends client-facing communication autonomously. Every output is labelled "for your review only".

**SMB mode (autonomous agent).** Each CSM manages 150 to 1,000 accounts. Manual review of every renewal is structurally impossible, so the agent acts autonomously within hard guardrails. It drafts and sends routine renewals, scores accounts, and surfaces only exceptions (contract amendments, disputed pricing, upsells above a value threshold) for human review.

Key things to look for in the demo:

- The **"context the agent used"** block shows exactly which data sources fed each draft (Salesforce, Looker, Gong, LinkedIn Sales Nav, Clay). This is what makes the output auditable rather than a black box.
- On the edit screen, **commercial terms are locked**. The CSM can rewrite narrative but cannot silently change pricing. AI handles words. Deterministic code handles numbers.
- The **"AI also recommends"** panel surfaces context the CSM needs to walk into the conversation prepared, not ambushed.

## This is a proof of concept

This prototype was built to demonstrate the workflow and the SMB versus ENT autonomy distinction. The mock data, account names, and AI outputs are illustrative only.

**Next steps for productionisation:**

1. **Data integration.** Connecting to live Salesforce, Looker, Gong, Clay, and LinkedIn Sales Navigator instances with proper authentication, refresh schedules, and data quality monitoring.
2. **System linkage.** Wiring the agent's actions into the existing CRM workflow so drafts route into Salesforce templates, audit logs land in the right place, and CSM approvals push back into the system of record.
3. **Deterministic scoring layer.** Building the churn and health scoring models in partnership with the data science team, with formulas owned by code rather than the LLM.
4. **Guardrail enforcement.** Tool permissions, escalation thresholds, and never-do lists enforced structurally (via API scopes and rate limits) rather than only in prompts.
5. **Pilot launch.** A small cohort of ENT and SMB CSMs to validate launch criteria, gather feedback, and measure time-saved and accuracy lift against baseline.

## About

Built by Shi Yunn Chua, Director of Customer Success (Enterprise) at Wellhub, as part of the Executive Diploma in AI for Business at Oxford Saïd Business School.
