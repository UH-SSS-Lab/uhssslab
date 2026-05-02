---
title: Internet-of-Things
slug: iot
subtitle: Zero-involvement pairing and authentication for the Internet of Things.
# hero_image: /assets/img/research/iot.jpg   # uncomment + drop a real photo here
# hero_caption: ""
---

## What we work on

A typical home, office, or factory floor now has dozens of small
networked devices, speakers, sensors, locks, lights, gateways. Most
have no keyboard, no screen, no good way to ask the user for a password.
Traditional pairing flows (type the PIN on both devices, scan a QR
code, log in to an app) don't scale and erode security in practice.

The lab develops **zero-involvement pairing and authentication (ZIPA)**:
co-located devices independently observe the same physical environment,
extract a shared key from it, and authenticate one another without any
human action. We design new entropy sources, study the
information-theoretic limits of context-based key extraction, and build
threat models that capture real-world attacks against these systems.

<div class="concept-flow" aria-hidden="true">
  <div class="concept-step"><span class="step-num">01</span><h3>Harvest</h3><p>Devices passively sample a co-located physical signal, power-line noise, audio, EM, motion.</p></div>
  <div class="concept-step"><span class="step-num">02</span><h3>Distill</h3><p>An online randomness distiller converts the noisy signal into a high-quality cryptographic key.</p></div>
  <div class="concept-step"><span class="step-num">03</span><h3>Reconcile</h3><p>Lightweight reconciliation handles small disagreements without leaking the key over a public channel.</p></div>
</div>

## Selected systems

- **VoltKey**, continuous shared-key generation from local power-line noise. Deployable as a USB-power add-on.
- **Moonshine**, online randomness distiller that nearly doubles NIST-test key quality from environmental sources.
- **SyncBleed → TREVOR**, first realistic attack on ZIPA's synchronization channel, plus a sync-free defense.
- **DESTION'24 attack**, first successful signal-injection attack on a popular ZIPA algorithm.
