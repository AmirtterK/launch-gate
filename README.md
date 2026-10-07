# Launch Gate

A pre-launch legal and compliance gate for SaaS products, marketplaces, and rental platforms, packaged as a [Claude skill](https://docs.claude.com).

Run it during planning, next to design and architecture, so compliance is built in from day one instead of bolted on before launch. Tell it your target region and it returns a prioritized, region-aware checklist you can paste straight into your project docs.

## What it covers

20 items across five areas:

| Area | Items |
|------|-------|
| Legal documents | Privacy policy, terms of service, refund policy, cookie policy |
| Consent and data | Cookie banner, form consent, data minimization, third-party SDK audit, age gate, deletion requests |
| Fair dealing | Dark patterns, hidden fees, fake reviews, substantiated marketing claims |
| Accessibility | Alt text, color contrast, keyboard navigation |
| Trust and comms | Business details, email unsubscribe, font and image licensing |

Each item states what it is, why it matters, who owns it, and how to implement it. Regional notes cover the EU (GDPR), the USA (CCPA, COPPA, CAN-SPAM), and Algeria (Laws 18-07 and 18-05).

## Install

1. Download this repo as a ZIP.
2. In Claude, go to **Settings > Capabilities > Skills** and upload it.

For Claude Code, copy the folder into `~/.claude/skills/launch-gate/`.

## Use

Ask something like:

- "Run the launch gate for my rental marketplace in Algeria"
- "What legal items do I need before launching a SaaS in the EU?"

## Not for

Portfolios, blogs, and marketing-only sites. Launch Gate will point you to a short version instead.

## Disclaimer

This is a practical engineering checklist, not legal advice. Have a qualified local lawyer review your final policies.

## License

MIT