---
title: "Further Impressions of CrewAI"
slug: crewai-further-impressions
date: 2025-11-11
categories:
  - Development
  - AgenticAI
  - CrewAI
---

## Introduction

I've spent more time tinkering with CrewAI, and have a better understanding of how to leverage this tool

## Main Content

On the plane ride back from the conference, I decided to be a good boy and do some work instead of watching a show. This was actually a good opportunity, as I was captive for a few hours and the mediocre airline internet was more than sufficient to continue exploring CrewAI.

I had a reasonably well defined task in mind, related to parsing various web content and collating a report from it. From a bit of initial testing, I could already see that the tools and capabilities in CrewAI were well adapted to the task overall. I initially felt I was gaining momentum and would soon be sipping wine from my yacht, while my agents toiled away. Alas, that was not to be.

The crux of the issue I encountered relates to the scope of my task. While the tools performed adequately, collating information and building a basic report, I needed to do this many, many times. That's fine, because computers and AI are really good at doing tedious, serial work. Unfortunately, I soon encountered timeout errors. It appears, at least during the free trial, that CrewAI terminates an execution once it has run for 10 minutes. I can appreciate the need to enforce limits, but knowing that in advance would have saved me time.

A 10 minute limit isn't a deal-breaker, but it does require reconsidering the workflow and introducing persistent storage of some kind, so that reports can be built in batches. Additionally, it looks like CrewAI supports this, but those changes to the workflow aren't trivial. It's also possible that a paid tier may change this limit, but that's uncertain. Their pricing model seems to be tied to workflow executions, rather than tokens, which suggests to me that a 10 minute timeout may be universal.

Armed with that information, I think now that CrewAI may not be the best platform for this particular project. That said, I do think I'll continue exploring CrewAI for other work. I found their UI to be approachable (needs a dark mode though!), and their AI assistant does a solid job of creating a workflow and also assisting with debugging and improvements. While I'll continue exploring other tools for this project, I have no concerns about using CrewAI for lighter tasks that require daily exectution.

## Takeaways

CrewAI seems like a solid product for light agentic workflows, but isn't optimized for the scope of my project of interest.