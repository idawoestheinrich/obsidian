---
tags:
aliases:
  - LDOs
  - LDO
---
https://www.analog.com/en/resources/technical-articles/supply-clean-power-with-ultralow-noise-ldo-regulators.html?utm_source=chatgpt.com
### What an LDO is

- A **linear voltage regulator** that can regulate the output voltage even when the input is only slightly higher than the desired output (the “dropout voltage” can be as low as a few hundred millivolts).
- Example: with a 12 V supply, an LDO can still provide a clean, regulated 11.8 V, whereas older linear regulators might need 2–3 V of “headroom.”
 ### Why LDOs are used in preamplifiers
Preamps handle very small, sensitive signals (microvolts to millivolts), so the **power supply quality** directly affects noise and distortion. LDOs help by:

- **Low noise regulation:** Many LDOs are designed for audio/RF applications with very low output noise and high power supply rejection ratio (PSRR).
- **Filtering:** They “clean up” ripple and switching noise from upstream supplies (e.g., a switch-mode supply or rectifier).
- **Compact and efficient:** Because of the low dropout, you can run the regulator closer to the desired voltage, generating less heat than with a standard regulator.