---
title: Mobile & Wearable Systems
slug: mobile-wearable
subtitle: Securing the smartphones, wearables, and personal mobile systems people use every day.
# hero_image: /assets/img/research/mobile-wearable.jpg   # uncomment + drop a real photo here
# hero_caption: ""
---

## What we work on

Personal mobile and wearable devices have become the trusted vault for
identity, health, location, and payments. Yet the same trends that make
these devices indispensable, short-lived connections, miniaturized form
factors, and minimal user interfaces, make traditional security
mechanisms like passwords and complex pairing flows impractical.

The lab designs **authentication, pairing, and secure-sensing primitives**
that work transparently on smartphones, smartwatches, earbuds, and
embedded camera modules. Our methods derive shared secrets from the
physical context the user is already in (vibration, ambient
electromagnetic radiation, image-sensor noise), instead of asking the
user to type a passkey or trust a remote service.

<div class="concept-flow" aria-hidden="true">
  <div class="concept-step"><span class="step-num">01</span><h3>Sense</h3><p>Each device samples a shared physical signal (motion, EM, light, or noise) using sensors it already has.</p></div>
  <div class="concept-step"><span class="step-num">02</span><h3>Distill</h3><p>Local randomness extractors turn the raw signal into a high-entropy bit string with known statistical guarantees.</p></div>
  <div class="concept-step"><span class="step-num">03</span><h3>Authenticate</h3><p>Co-located devices reach the same key. Devices outside the shared context don't, and are rejected.</p></div>
</div>

## Selected systems

- **AeroKey**, over-the-air authentication using ambient electromagnetic radiation. No extra hardware on the device.
- **SyncVibe**, pairing via short bursts of physical vibration between devices in direct contact.
- **PARAVIRT**, userland container isolation that lets untrusted apps coexist on a single mobile device.
