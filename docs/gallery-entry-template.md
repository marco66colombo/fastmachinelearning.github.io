# Gallery Entry Template

Copy this structure into `_applications/example-name.md` or `_tools/example-name.md`.

Required fields for future form submissions:

- `title`
- `summary`
- `submitter`
- `domain`

All other fields may be left blank or omitted. Optional blank fields should not break the site.

```yaml
---
title: "Entry title"
layout: gallery-item
summary: "One or two sentences for the gallery card."
image: /images/example-thumbnail.png
image_alt: "Short description of the image"
submitter: "Name of submitter"
affiliation: "Institution or project"
domain: "Application domain or tool category"
tools_used:
  - hls4ml
  - Example tool
tags:
  - application
  - fpga
review_status: draft
links:
  - label: "Repository"
    url: "https://github.com/fastmachinelearning"
---

## Overview

Describe the application or tool and why it matters to the FastML community.

## FastML Tools Used

List the FastML tools, workflows, or methods used by this work.

## Implementation Notes

Describe relevant technical details, additions, constraints, or integration work.

## Results

Summarize key outcomes. Include latency, throughput, resource use, accuracy, deployment context, or other relevant metrics if available.

## Suggested Figures

- System diagram.
- Tool flow or architecture diagram.
- Performance table or plot.
- Deployment photo or screenshot.
```
