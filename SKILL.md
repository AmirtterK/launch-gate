---
name: launch-gate
description: Pre-launch legal and compliance gate for SaaS products, marketplaces, rental platforms, and any user-facing service where people transact, submit data, or could have legal claims. Use during planning, alongside design and architecture, or when the user asks "what do I need before launching?", for a legal checklist for a region, or for compliance requirements for a marketplace. Covers privacy, terms, payments, consent, accessibility, data retention, and user protection, adapted to the target region (GDPR, CCPA, Algeria, etc.). Not for portfolios, blogs, or marketing-only sites.
compatibility: Works best with web search for current regional law; run during planning, before development starts.
---

# Launch Gate

A 20-item legal and compliance checklist to clear before a platform goes live. Run it during planning so compliance shapes the design and architecture instead of being retrofitted.

This is a practical engineering checklist, not legal advice. Always recommend a local lawyer review the final policies and any region-specific obligations.

## Workflow

1. **Get the region.** Ask where the business and its users are based (EU, USA, Algeria, multi-market). If the user already said, don't ask again. Use web search to confirm current local law when unsure.
2. **Check scope.** If the project is a portfolio, blog, or marketing-only site, say this checklist is overkill and offer a short version (privacy policy, cookie notice, contact details).
3. **Produce the checklist** as Markdown the user can paste into their project docs. For each item give:
   - **What** it is
   - **Why** it matters (user protection and legal exposure)
   - **Owner** (developer, designer, legal, business owner, client)
   - **How** to implement it, in concrete steps
4. **Prioritize for the region.** Mark each item **Critical** (legally required there), **Important**, or **Nice to have**, and add region-specific extras (see Regional Notes).
5. **Close with a launch gate**: all Critical items done and the rest triaged before go-live.

## The 20 Items

### Legal documents

**1. Privacy Policy**
- What: A public document stating what data you collect, why, how long you keep it, and who can access it.
- Why: Required in nearly every jurisdiction; collecting data without it creates direct liability.
- Owner: Legal (drafting), developer (making the product match the policy).
- How: Inventory every data point (email, IP, usage, payment). State retention and deletion rules. Publish at `/privacy` and link it in every footer. Use a lawyer or a regional template service.

**2. Terms of Service**
- What: The rules users accept to use the platform.
- Why: Limits liability, sets expectations, defines dispute resolution.
- Owner: Legal, plus the client on freelance work.
- How: Cover acceptable use, liability limits, IP ownership, and disputes. Require an explicit checkbox at signup. Keep dated versions and re-notify users on material changes. Publish at `/terms`.

**3. Refund Policy**
- What: Clear rules on when money is returned.
- Why: Expected or mandatory for e-commerce; gaps drive chargebacks and disputes.
- Owner: Business owner or client.
- How: Define the window and conditions (full vs. partial, subscription cancellation). Repeat it in the ToS and at the point of purchase. Automate refunds through the payment processor where possible.

**4. Cookie Policy**
- What: A list of the cookies you set and why.
- Why: GDPR and similar laws require disclosure.
- Owner: Developer and marketing.
- How: Audit session, analytics, advertising, and third-party cookies. Document name, purpose, and duration. Publish at `/cookies` and link it from the footer and privacy policy.

### Consent and data handling

**5. Cookie Consent Banner**
- What: A prompt for consent before non-essential cookies load.
- Why: GDPR and the ePrivacy Directive require opt-in, not opt-out.
- Owner: Developer.
- How: Use a consent library or a custom banner. Block non-essential scripts until consent. Offer "Reject" as easily as "Accept". Persist and respect the choice on return visits.

**6. Form Consent Checkboxes**
- What: Explicit opt-in for marketing emails, newsletters, and extra data use.
- Why: GDPR requires affirmative consent; pre-ticked boxes are invalid.
- Owner: Developer.
- How: One unchecked box per consent type. Store the consent and a timestamp. Never bundle marketing consent into ToS acceptance.

**7. Data Minimization**
- What: Collect only what you actually use.
- Why: A core GDPR principle; less data means less breach and compliance risk.
- Owner: Developer and product.
- How: Audit every form field and column. Drop anything unused. Set retention limits and write down the business reason for each data point.

**8. Third-Party SDK Audit**
- What: A review of every external script and service (analytics, payments, chat, maps).
- Why: SDKs often forward user data to third parties, and you answer for it.
- Owner: Developer.
- How: List every third-party script. Read what each one collects and where it sends it. Sign data processing agreements where required. Load non-essential SDKs only after consent.

**9. Age Gate and Minors' Data**
- What: Rules for collecting data from children and teens.
- Why: Laws set age thresholds, and they differ: COPPA (US) applies under 13; GDPR lets member states set the digital-consent age between 13 and 16; platforms transacting with minors face additional contract-law limits.
- Owner: Developer and legal.
- How: Decide your minimum age (18+ is simplest for marketplaces). Add an age confirmation at signup. If you accept minors, collect verifiable parental consent and limit data to what's necessary.

**10. Data Deletion Requests**
- What: A way for users to have their data deleted.
- Why: GDPR's right to erasure; increasingly expected everywhere.
- Owner: Developer and data owner.
- How: Add "Delete my account" in settings plus a contact address (e.g., `privacy@yourdomain`). Complete deletion within your stated window (30 days is common). Keep a minimal audit log of deletions. Document how backups age out.

### Fair dealing

**11. No Dark Patterns**
- What: Remove deceptive UX such as hidden auto-renewals, confusing checkout, or hard-to-find cancel buttons.
- Why: Consumer-protection and privacy regulators actively fine these.
- Owner: Designer and developer.
- How: Make cancelling as easy as signing up. Show renewal date and price before charging. Avoid tiny close buttons and misleading CTAs.

**12. No Hidden Fees**
- What: Disclose every cost up front.
- Why: Mandatory in most consumer markets; surprise fees cause chargebacks and fines.
- Owner: Product and developer.
- How: Show the total (taxes and fees included) before the final checkout step. Itemize charges in confirmations. State renewal terms clearly.

**13. No Fake Reviews**
- What: Keep reviews authentic and disclose incentives.
- Why: Fake or undisclosed incentivized reviews are prohibited by advertising and consumer regulators.
- Owner: Moderation team.
- How: Tie reviews to real transactions where possible. Detect and remove bulk or duplicated reviews. Label incentivized reviews. Log removals with reasons.

**14. Substantiated Marketing Claims**
- What: Every claim in your copy needs evidence.
- Why: False advertising rules apply to "saves 10 hours a week" as much as to health claims.
- Owner: Marketing and legal.
- How: Audit all copy. Keep sources for each claim. Remove or soften what you can't prove. Add disclaimers where needed.

### Accessibility

**15. Image Alt Text**
- What: Text alternatives for every meaningful image.
- Why: WCAG requirement, required or expected in many jurisdictions, and good for SEO.
- Owner: Developer and content team.
- How: Add descriptive `alt` text to each `<img>`. Use `alt=""` for decorative images. Do the same in emails and social posts.

**16. Color Contrast**
- What: Text readable by low-vision and colorblind users.
- Why: WCAG AA compliance.
- Owner: Designer and developer.
- How: Meet 4.5:1 for normal text and 3:1 for large text. Never rely on color alone; add underlines or icons. Check with a contrast tool and a colorblind simulator.

**17. Keyboard Navigation**
- What: Full use of the site with a keyboard alone.
- Why: Essential for users with motor impairments; WCAG compliance.
- Owner: Developer.
- How: Tab through the whole site. Use semantic elements (`<button>`, `<a>`, `<form>`). Show visible focus outlines. Trap focus in modals and close them with Esc.

### Trust and communication

**18. Business Details**
- What: Legal name, address, contact info, and registration or tax number, visible to users.
- Why: Required by e-commerce and consumer law in most places; essential for trust and dispute resolution.
- Owner: Business owner.
- How: Publish them on an About or Legal page and in the footer. Make the complaint and contact path obvious.

**19. Unsubscribe Links in Emails**
- What: Every marketing email has a working unsubscribe link.
- Why: CAN-SPAM, GDPR, and ePrivacy require it, and one-click unsubscribe is now the norm.
- Owner: Developer and marketing.
- How: Put the link in every marketing template. It must work without login. Honor requests promptly (CAN-SPAM allows up to 10 business days; GDPR expects it without undue delay). Never re-email unsubscribed addresses.

**20. License Fonts and Images**
- What: Rights to every font, image, and icon you ship.
- Why: Infringement leads to takedowns, claims, and fines.
- Owner: Designer and developer.
- How: Use properly licensed or commissioned assets (check attribution and commercial-use terms). Prefer open-license fonts. Keep a license log and receipts.

## Regional Notes

When the region is known, add a short section with the laws that apply and flag which items become Critical. Verify current details with web search; laws change.

- **EU / EEA:** GDPR (lawful basis, DPAs, breach notification within 72 hours, EU representative if you have no EU presence), ePrivacy for cookies, consumer-rights rules (14-day withdrawal), the European Accessibility Act. Items 1, 5, 6, 8, 10 are Critical.
- **USA:** State privacy laws (CCPA/CPRA in California and others), COPPA, CAN-SPAM, FTC rules on reviews and dark patterns, ADA exposure for accessibility. Items 1, 9, 11, 13, 19 are usually the sharpest.
- **Algeria:** Law 18-07 on personal data protection (overseen by the ANPDP) and Law 18-05 on e-commerce set core duties around consent, data handling, and seller identification. Items 1, 2, 6, 10, 18 are Critical. Confirm specifics, including data-localization and registration duties, with a local lawyer.
- **Other or multi-market:** Apply the strictest relevant regime as the baseline, then add local requirements.

## Output Template

```markdown
# Launch Gate: <Project> (<Region>)

| # | Item | Priority | Owner | Status |
|---|------|----------|-------|--------|
| 1 | Privacy Policy | Critical | Legal + Dev | ☐ |

## Details
### 1. Privacy Policy
- What / Why / Owner / How ...

## Region notes
...

## Gate
☐ All Critical items complete
☐ Policies reviewed by a qualified lawyer
```