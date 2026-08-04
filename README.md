# Pika (pika-art)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Pika (Pika Labs) is a generative AI video platform that turns text prompts and images into short, high-quality videos. It is primarily a **consumer and creator product** delivered through the web app at [pika.art](https://pika.art) (and historically a Discord bot), with features including text-to-video, image-to-video, Pikascenes, Pikaframes keyframe interpolation, lip sync, and AI sound effects.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/pika-art/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/pika-art/refs/heads/main/apis.yml)

## Access Model (read this first)

Pika does **not** publish a first-party developer API on its own domain. There is no `api.pika.art`, no Pika-issued API key, and no Pika-published OpenAPI document.

- **Consumer / app access** — Buy a credit-based monthly subscription (Free, Standard, Pro, Fancy) to use the pika.art web app. Each clip consumes credits based on resolution, duration, and mode. See [`plans/`](plans/pika-art-plans-pricing.yml).
- **Official programmatic access** — Delivered through a partnership with **fal.ai**, Pika's official inference partner. The [pika.art/api](https://pika.art/api) page is a landing page that hands developers off to fal, where Pika's 2.x models run as callable endpoints (for example `fal-ai/pika/v2.2/text-to-video` and `fal-ai/pika/v2.2/image-to-video`), authenticated with a fal API key and billed per generation. See fal's announcement: [Pika API is now powered by fal](https://blog.fal.ai/pika-api-is-now-powered-by-fal/).
- **Unofficial third parties** — Wrappers such as PiAPI, useapi.net, Pollo, and pikapikapika.io resell Pika access. They are **not** operated or endorsed by Pika and are not documented here as Pika's official API.

This entry is therefore an honest **gated stub**. The documented endpoint surface belongs to fal, and the endpoints listed in [`review.yml`](review.yml) are **modeled** from fal's public model pages, not confirmed against a Pika-operated specification.

## Tags

- Video Generation
- AI Video
- Generative AI
- Text-to-Video
- Image-to-Video
- Creative

## Timestamps

- **Created:** 2026-07-11
- **Modified:** 2026-07-11

## APIs

### Pika Video Generation API (via fal)

Pika's official developer access is served on fal's infrastructure, not by Pika. On fal, Pika models are exposed as asynchronous queue endpoints (submit / status / result) authenticated with a fal API key (`Authorization: Key FAL_KEY`). Documented model endpoint IDs include `fal-ai/pika/v2.2/text-to-video`, `fal-ai/pika/v2.2/image-to-video`, Pikascenes, and Pikaframes, plus v2.1 variants. Inputs include `prompt`, `resolution` (720p/1080p), `aspect_ratio`, `duration` (5 or 10 seconds), `seed`, and `negative_prompt`.

- **Human URL:** [https://pika.art/api](https://pika.art/api)
- **Base URL (fal-hosted):** `https://queue.fal.run`

#### Tags

- Video Generation
- AI Video
- Text-to-Video
- Image-to-Video

#### Properties

- [Documentation](https://pika.art/api)
- [Announcement](https://blog.fal.ai/pika-api-is-now-powered-by-fal/)
- [API Reference (fal)](https://fal.ai/models/fal-ai/pika/v2.2/text-to-video/api)

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/pika-labs)
- [Website](https://pika.art)
- [Documentation](https://pika.art/api)
- [Plans](plans/pika-art-plans-pricing.yml)
- [Fin Ops](finops/pika-art-finops.yml)

## Review

Does Pika expose a documented public WebSocket API? **No.** See [`review.yml`](review.yml). Pika publishes no first-party API at all; its official programmatic access runs behind fal's asynchronous HTTP queue (request/response REST with polling), and no WebSocket surface is documented by Pika or by fal for the Pika models.

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
