+++
title = "Manage files on my machine"
date = 2025-09-09

[taxonomies]
categories = ["organizer", "project"]
tags = ["mermaid", "example", "high-level", "architecture"]
+++

{% blockquote(class="info", author="Lao Tzu") %}
"A journey of a thousand miles begins with a single step"
{% end %}

I’m struck by a familiar feeling: my computer is a mess. Scattered files, half-finished projects, and random "temp" folders clogging up my drive—it’s chaos. Sound familiar? Just like Lao Tzu said, “A journey of a thousand miles begins with a single step,” and for me, that first step is cleaning up my machine. It’s not just about freeing up disk space; it’s about clearing the mental clutter to make room for creativity, focus, and a bold new project.

Like all small step, we will begin with a simple idea to jumpstart the intention. Monitoring these directories are a good start and it will nag me constantly until an action is taken.

## What is the idea?
At its core, this project is about creating a service that monitors one or more designated directories for changes—such as file creations, modifications, deletions, or renames. When a change is detected, the system generates a stream of structured event data that can be consumed by a notification service. This could trigger alerts via email, push notifications, webhooks, or other channels, depending on your needs.

{% mermaid() %}
flowchart LR
    B[Monitoring]
    G[Aggregator]
    H[Notifier]

    A@{ shape: lin-cyl, label: "Directory 1"} -->|New Event| B
    C@{ shape: lin-cyl, label: "Directory 2"} -->|Modify Event| B
    B -->|publishes| G
    G -->|subscribed by| H
    H -->I[Email]
    H -->J[Push]
{% end %}

## How It Works (High-Level)
The system will leverage file system APIs to detect changes in real time. Once a change is detected, the event is processed and formatted into a standardized structure, then pushed to a configurable output stream. This stream can be consumed by a notification service, which could range from a simple logging mechanism to a sophisticated messaging queue.

## What's next?
In the planning and prototyping phase, I will be focusing on:
* Selecting the right tools and libraries for cross-platform compatibility and performance.
* Designing a flexible `event` format that balances detail and simplicity.
* Exploring how to make the event stream plug-and-play with popular notification services.

This is just getting started so expect more technical deep dives, progress updates, and eventually, a working prototype in the days to follow.
