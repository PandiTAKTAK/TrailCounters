# Trail Counter

The trails make use of trail counters in order to track visitor numbers.

## Issues

The current trail counter setup has a few high-level issues ->

- exposure to significant risk of data loss
  - water ingress
  - malicious actors
  - equipment degradation
  - power loss (batteries)
- data extraction is mandraulic
  - data is currently extracted 1..2 times per year
    - this limits identification of any sudden behavioural changes

## High-Level Options

There are a couple of high-level options ->

### Hardware

- LTE
  - Power consumption may be an issue
  - Signal may be an issue
  - On-going cost
- LoRA-WAN
  - Requires a base-station
    - Assume PP *wouldn't mind* hosting the equipment
  - ~3..10mi range

### Software

Not a huge amount to implement - It's a simple sensing application with some form of radio interfacing.

Likely to be rudimentary MQTT client and broker for the backlink, then dump into S3 for consumption.

Data is low integrity with zero PII. Security impact and risk is negligible.
