---
title: Advanced Vehicular Systems
slug: vehicles
subtitle: Securing vehicle-to-vehicle, vehicle-to-pedestrian, and intra-vehicle communication.
# hero_image: /assets/img/research/vehicles.jpg   # uncomment + drop a real photo here
# hero_caption: ""
---

## What we work on

Modern vehicles are computers on wheels. They talk to phones, to each
other, to pedestrian devices, and to roadside infrastructure. Every one
of those channels needs a way to establish trust, and the existing
methods (cellular PKI, manual Bluetooth pairing, pre-shared certificates)
either don't scale to shared mobility or fail when the network drops.

The lab builds **lightweight, sensor-grounded trust for V2X**. We exploit
signals that are physically bound to the vehicle (tire-pressure-monitor
RF, cabin vibration, GPS + visual fusion) so that legitimate co-located
parties can authenticate each other in seconds, with no infrastructure
or user effort, while remote attackers cannot.

<div class="concept-flow" aria-hidden="true">
  <div class="concept-step"><span class="step-num">01</span><h3>Bind</h3><p>Trust is rooted in a physical signal that only co-located devices can observe, TPMS bursts, cabin vibration, sensor co-witness.</p></div>
  <div class="concept-step"><span class="step-num">02</span><h3>Verify</h3><p>Devices independently extract identifying features and compare them in a way that resists replay and injection.</p></div>
  <div class="concept-step"><span class="step-num">03</span><h3>Connect</h3><p>Successful match unlocks a secure channel; mismatch means the peer is remote, malicious, or in a different vehicle.</p></div>
</div>

## Selected systems

- **TPKEY**, zero-involvement intra-vehicle authentication using TPMS RF transmissions.
- **ivPair**, pin-equivalent pairing extracted from a vehicle's vibration response under real driving.
- **PEDRO**, V2P pedestrian-mobility verification that admits real, moving pedestrians and rejects stationary remote attackers.
- **V2V trust via sensor fusion**, combining GPS and visual data so two AVs can verify physical co-location without infrastructure.
