# Pika (pika-art)

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
