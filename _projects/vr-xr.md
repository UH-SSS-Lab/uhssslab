---
title: VR/XR & Immersive Computing
slug: vr-xr
subtitle: Trustworthy sensing for immersive environments and digital twins.
# hero_image: /assets/img/research/vr-xr.jpg   # uncomment + drop a real photo here
# hero_caption: ""
---

## What we work on

VR and XR are moving from entertainment into training, health, and
collaborative work. The minute an immersive system becomes safety- or
business-critical, the fidelity of its sensing, pose, motion, scene
geometry, turns into a security property. A digital twin that drifts a
few centimeters off the ground is not just an animation glitch; it's a
trust problem.

The lab works on **3D pose estimation and ground-relative positioning**
that produces faithful, authenticatable digital twins of human motion.
Our methods plug into off-the-shelf pose frameworks and recalibrate the
character's position against the real-world floor plane, so virtual
characters interact with their environment realistically.

<div class="concept-flow" aria-hidden="true">
  <div class="concept-step"><span class="step-num">01</span><h3>Capture</h3><p>3D pose landmarks are extracted from RGB / depth input using off-the-shelf pose frameworks.</p></div>
  <div class="concept-step"><span class="step-num">02</span><h3>Align</h3><p>Dynamic Ground Alignment pins the body-centered coordinate system to the real-world floor plane.</p></div>
  <div class="concept-step"><span class="step-num">03</span><h3>Render</h3><p>The digital avatar moves with realistic grounding and contact, in animation, VR, or training environments.</p></div>
</div>

## Where this is going

Beyond visualization fidelity, we're interested in trustworthy XR sensing
more broadly: sensor authentication for VR controllers, attack-resistant
SLAM, and verifiable provenance for digital-twin recordings.
