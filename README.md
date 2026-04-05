# NYC Housing Navigation Suite

**From Shelter to Home**

A comprehensive web platform guiding New Yorkers experiencing homelessness through every step of the journey to permanent housing — with parallel tools for housing specialists and case workers.

No existing tool in the NYC housing ecosystem provides end-to-end coverage. Government portals like ACCESS NYC and Housing Connect address individual pieces. Case management software like WellSky and CaseWorthy serves agencies but not clients. Consumer apps like Propel focus on benefits but not housing navigation. This product fills the gap between all of them.

## The problem

A person experiencing homelessness in NYC must navigate a fragmented system of disconnected agencies, websites, and physical offices. The process involves visiting intake centers with no guide on what to bring, gathering the same documents repeatedly for multiple agencies, understanding complex CityFHEPS voucher eligibility rules, apartment hunting under a 120-day shopping letter deadline, and assembling application packages that are frequently incomplete — causing delays that extend the process by months.

The result: an average of **10 months** to find an apartment and secure a CityFHEPS voucher, with many people losing their shopping letters to expiration and having to restart.

## What this app does

### For clients
- **Shelter intake orientation** — intake center locations, what to bring, what to expect, interactive checklist
- **CityFHEPS eligibility calculator** — enter 4 paystubs, see transparent math comparing your annualized income against 200% of the Federal Poverty Level for your household size
- **Document vault** — secure encrypted cloud storage for birth certificates, IDs, paystubs, shopping letters — never lose a document again
- **Voucher application tracker** — milestone-based progress bar from eligibility through lease signing, with shopping letter expiration countdown
- **Workforce connector** — curated directory of NYC employment programs (Urban Upbound, Jobs-Plus, WorkForce1, HRA Career Services, Urban Pathways ACE) for people who need paystub history to qualify
- **Apartment search & package builder** — pre-filtered StreetEasy and Housing Connect links based on your voucher specs, plus a document assembly tool that checks your package for completeness before you bring it to a landlord
- **Know your rights** — DHS client rights, source of income discrimination protections, CityFHEPS late fee protections, fair hearing rights, right to counsel in housing court

### For case workers
- **Client dashboard** — all assigned clients with status indicators, sortable by stage, days in current stage, shopping letter expiration
- **Eligibility queue** — clients flagged as eligible by the calculator, ready for case worker review
- **Document review** — view client documents remotely, mark as reviewed, request missing items
- **Tracker management** — update milestones that push notifications to the client side

## Architecture

| Layer | Technology |
|-------|-----------|
| Frontend | Next.js (React) |
| Backend / Auth / DB / Storage | Supabase (PostgreSQL + Auth + Storage + Realtime) |
| Hosting | Vercel |
| Maps | Google Maps JavaScript API |
| Notifications | Firebase Cloud Messaging |

Designed to run on free tiers during pilot. See the PRD for full cost analysis at each growth stage.

## Key design decisions

- **Web-first, not native mobile** — many clients access the internet through library computers and shared devices
- **Row-level security at the database level** — clients can only see their own data, case workers can only see assigned clients
- **No hardcoded policy values** — FPL thresholds, voucher amounts, and program details stored in configuration tables and updated annually
- **Manual paystub entry for v1** — PDF auto-parsing is a future enhancement to avoid blocking launch on OCR complexity
- **Eligibility calculator shows all math transparently** — users see every step of the calculation so they can trust and understand the result
- **Educational content is contextual, not buried** — rights information appears at the moment it's relevant in the user's journey


## Contributing

This project is built to serve people experiencing homelessness in NYC. If you have experience with the shelter system, CityFHEPS vouchers, housing navigation, or case management and want to contribute — whether code, content review, or domain expertise — please open an issue or reach out.

If you are a housing attorney or legal aid professional willing to review the rights content for accuracy, that would be especially valuable.

## License

MIT

## Disclaimer

This application provides informational tools and educational content only. The eligibility calculator provides estimates — only DSS can make official CityFHEPS eligibility determinations. Rights information is for guidance purposes and does not constitute legal advice. Consult a housing attorney or legal aid organization for specific legal questions.