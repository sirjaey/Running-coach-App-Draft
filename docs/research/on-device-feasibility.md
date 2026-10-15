# On-device speech feasibility

This is the Week 3 spike named in [the Week 2 action points](../../reports/week-02/meeting-report.md#action-points): whether on-device text-to-speech and a small model, starting from Gemma, fit the ten weeks.

## Text-to-speech

Android's platform text-to-speech speaks a string on the phone. It does not need a model in this repository, and it does not need a server. That is enough for the spoken confirmations, the stat cues, and the effort words in [US-01](https://github.com/Running-Coach-App/running-coach-app/issues/37), [US-02](https://github.com/Running-Coach-App/running-coach-app/issues/38), and [US-03](https://github.com/Running-Coach-App/running-coach-app/issues/39).

It fits the minimum usable product.

## Gemma

[DEC-008](../decisions.md#dec-008) names Gemma as the candidate engine for simple verbal stat queries. [Gemma 3n](https://ai.google.dev/gemma/docs/gemma-3n) is the variant Google describes as built for phones, laptops, and tablets. The same page says the E2B model loads over 5 billion parameters in a standard run, and that with parameter skipping and PLE caching the effective load can be just under 2 billion parameters (1.91B). It also takes audio input.

That is a phone-class model. It is not a Week 3 binary:

- The course rules keep model weights out of git history.
- A clean checkout that followed [the setup page](../setup.md) would still have to fetch weights and a runtime before it could answer from Gemma.
- This spike did not run Gemma on a phone. [ASM-09](../assumptions.md#asm-09) stays open until that run exists.

## What the Week 3 slice does instead

[US-04](https://github.com/Running-Coach-App/running-coach-app/issues/40) asks for an answer to time, pace, or distance, and for no invented stat on any other question. A phrase matcher on the phone does that without a model. [DEC-009](../decisions.md#dec-009) records that choice for the minimum usable product. Gemma stays the candidate for a later engine, which is [RISK-01](../risks.md#risk-01).

## Wearable

The same action point's open question asks what a wearable adds and whether one is reachable in ten weeks. [CON-04](../product-vision.md#con-04) already allows a wearable only when one is connected, and [CON-08](../product-vision.md#con-08) records that the team has no sports watch to test against. Heart rate is not an input in the Week 3 slice. Whether a wearable is reachable later is still a question for the customer, and it is in [the Week 3 script](../../reports/week-03/meeting-script.md).
