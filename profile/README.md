# SKALA

Real-time abuse detection for modern SaaS.

Stop fake signups, trial abuse, and automated attacks before they hit your backend.

---

## What SKALA Is

SKALA is an API that scores events like **signups, logins, and checkouts** and returns a risk score in real time.

```
ALLOW   → 0–39
STEP_UP → 40–69
BLOCK   → 70–100
```

Example response:

```json
{
  "risk_score": 87,
  "decision": "block",
  "reason_codes": ["SIG_IP_VELOCITY", "SIG_DEVICE_REUSE"]
}
```

---

## Example

```ts
import { createSkalaClient } from "skala"

const skala = createSkalaClient({
  apiKey: process.env.SKALA_API_KEY
})

const result = await skala.score({
  event: "signup",
  ip: req.ip,
  email: user.email
})
```

---

## Repositories

* **https://github.com/SKALA-sec/SKALA-TS-SDK** — official Node SDK
* **docs** — developer documentation

---

## Links

Website

[https://skala.dev](https://skala.dev)

Docs

[https://docs.skala.dev](https://docs.skala.dev)
