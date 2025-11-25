---
title: "Initial Adventures Using N8N"
slug: initial-n8n-adventures
date: 2025-11-24
categories:
  - Development
  - AgenticAI
  - N8N
---

## Introduction

I've spent a lot of time over the last two weeks working on a project using N8N and I've been quite pleased.

## Main Content

After my initial foray into agentic AI workflows using CrewAI, I realized the complexity of the primary task I was interested in exceeded what was easily achievable on that platform. I then pivoted and, based on colleague input, began exploring N8N.

N8N is a MUCH more sophisticated resource compared to CrewAI, which makes sense, given it is rooted in LangChain. However, with that sophistication comes a steeper learning curve. That said, their documentation is well integrated with their platform, which made it easy to overcome (most) hurdles. I really appreciated the variety of nodes (i.e. operations) available in N8N. The tools were highly adaptable and easily met my needs. Additionally, they have a `Code` node that can operate in JavaScript or Python, so there's practically no limit to what can be done on the platform. They don't host models themselves, so you'll need an API key to call any LLMs, but you can do A LOT without relying on that. Additionally, they offer the option to provide your own LLM endpoint (ala Ollama), which is a great feature if you have an LLM-heavy task and don't want to burn cash.

I also opted to try out the new Gemini 3 as a co-assistant for this effort. This was my first in depth usage of that tool, and I was quite impressed with the results and low-latency. I did find it seemed to 'forget' a bit more than ChatGPT / Sonnet, but nothing that couldn't easily be resolved. I'll continue working with Gemini to finish off my POC task in N8N and then revisit if that's still the best co-development tool to use.

## Takeaways

Tried out N8N and Gemini 3, and was thoroughly impressed with both. Comfort level is increasing with both and the progress being made is encouraging.