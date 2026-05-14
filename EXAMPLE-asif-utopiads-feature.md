# Example Spec: AI-Assisted Ad Copy Variant Generation

Applies the pm-planning-system template to a real Utopiads feature.

## Problem
Account managers at Utopiads spend 3-6 hours per client per week hand-writing ad copy variants for Meta, Google, and TikTok placements. Output is inconsistent across managers, A/B coverage is shallow (usually 2 variants per ad set), and the bottleneck delays campaign launches by an average of 4 business days.

## Users
- Primary: Utopiads account managers running 3-12 active client accounts.
- Secondary: Client-side marketing leads who review and approve copy before launch.
- Tertiary: Utopiads ops lead tracking campaign throughput and margin per account.

## Hypothesis
If we give account managers an AI tool that drafts 8-12 platform-specific ad copy variants from a single brief, then time-to-launch will drop by 50% and A/B variant coverage will triple, without measurable degradation in client approval rate.

## Success Metrics
- Time from brief to launch: from 4 days to under 2 days (p50).
- Variants tested per ad set: from 2 to 6+.
- Client approval rate on first review: hold at or above 70% (baseline).
- Account manager NPS on the tool: 40+ within 60 days.

## Scope (In)
- Brief intake form (product, audience, offer, tone, banned phrases).
- Variant generation across Meta, Google Search, and TikTok formats.
- Brand voice guardrails per client.
- Export to CSV and direct push to Meta Ads Manager via API.

## Scope (Out)
- Image and video generation (v2).
- Auto-budget allocation across variants (v2).
- Non-English markets (v2).
- WSI Global-style white-label resale (not v1).

## Risks
- LLM hallucinations on regulated verticals (finance, health) could trigger platform policy strikes. Mitigation: vertical-specific banned-phrase lists and human approval gate before publish.
- Account managers may bypass the tool if outputs feel generic. Mitigation: per-client brand voice training from past winning ads.
- Meta API rate limits could throttle bulk pushes. Mitigation: batch queue with retry and exponential backoff.
