---
title: /fraud
excerpt: >-
  Retrieve probability of fraud for a specific IP, Device, or Agent.

  The Fraud Blocking API returns a probability (risk score) 0.01 to 1.0
  representing

  the likelihood a given value is related to malicious or compromised devices.

  This risk scoring is calculated by Pixalate's proprietary machine-learning
  algorithm and

  allows clients to set their own blocking thresholds based on the quality and
  scale of their supply inventory.

  The following is a general guideline for setting fraud blocking thresholds:

  - Probability equal to 1.0, for filtering out only the worst offender for
  blocking (deterministic).

  - Probability is greater than or equal to 0.90 for filtering out users that
  are fraudulent beyond a reasonable doubt.

  - Probability between 0.75 (inclusive) and 0.90 (exclusive) to filter out
  users associated with clear and convincing evidence that they are fraudulent.

  - Probability between 0.5 (inclusive) and 0.75 (exclusive) to filter out users
  that it is more likely than not that they are fraudulent (also known as
  preponderance of the evidence standard).


  Pixalate does not recommend blocking any probabilities less than 0.5.

  When making adjustments to the probability threshold, Pixalate highly
  recommends regular checks and balances against

  impression delivery as lowering the probabilistic threshold can potentially
  impact the impression count.


  Zero or more of the following parameters may be provided. If more than one
  parameter is specified,

  the probability returned is determined by assessing risk based on the
  combination of each parameter's individual risk probability.


  **Not specifying an IP, Device, or Agent will return the metadata for fraud,
  including the user's current quota.  See alternate response schema below.**
api:
  file: ad-fraud-api.json
  operationId: Get Fraud
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---