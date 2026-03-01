---
layout: post
title: "Streaming Data Just Got Interesting Again"
date: 2026-02-24
categories: [databricks, kafka, streaming]
description: "Why Zerobus looks compelling for teams that want streaming ingestion without Kafka's operational complexity, and where its current Databricks-only scope limits flexibility."
hero_image: assets/images/posts/streaming-data-just-got-interesting-again/kafka_vs_zerobus.png
image: https://kcdatasherpa.com/assets/images/posts/streaming-data-just-got-interesting-again/kafka_vs_zerobus.png
hero_alt: "A comparison graphic contrasting Kafka and Zerobus for streaming data architecture."
hero_caption: "Kafka offers flexibility and fan-out. Zerobus reduces operational overhead inside Databricks."
---

We implemented **Apache Kafka** over two years ago and I've been extremely pleased with the speed and performance. It works. It scales. It's powerful.

But let's be honest: it's not simple.

To run Kafka well, you need:

- Data engineers with **specialized streaming experience**
- Infrastructure knowledge, especially around **AWS ECS**
- Familiarity with streaming protocols like **TCP, HTTP/HTTPS, WebSockets, gRPC, AMQP**, and Kafka's own binary protocol
- Operational maturity around brokers, partitions, replication, offsets, and consumer groups
- Often a different programming language mindset depending on the ecosystem

It's not just development. It's **ongoing management and support**.

If you don't already have that muscle on your team, standing up a Kafka-based architecture is not trivial.

That's why **Zerobus** caught my attention.

Based on conversations with Databricks and the GA announcement of Zerobus Ingest as part of Lakeflow Connect, it appears you could take a solid data engineer who already knows the Databricks ecosystem and have them implementing streaming ingestion almost immediately.

- No Kafka clusters.
- No broker management.
- No ECS orchestration.
- No consumer group balancing.

That's compelling.

## Now the limitation

Today, the only destination is inside Databricks.

One of the biggest advantages we've leveraged with Kafka is its **publish-subscribe model**. Multiple downstream consumers can subscribe to a topic, enabling a true **one-to-many architecture**. That flexibility has allowed us to support real-time use cases beyond Databricks when needed.

Zerobus currently narrows that scope. That doesn't make it bad. It just makes it opinionated.

And opinionated tools are powerful when they align with your architecture. Risky when they don't.

Even with our Kafka investment, we're going to evaluate where Zerobus fits. There may be workloads where eliminating the operational burden is absolutely worth the trade-off.

I'm very interested to see how Databricks evolves this. If they expand destinations or introduce broader fan-out capabilities, this could become a serious contender in the streaming space.

Streaming is not going away. The question is whether we want to keep managing the plumbing.

Here is the GA announcement for Zerobus:

[Zerobus GA announcement](https://www.databricks.com/blog/announcing-general-availability-zerobus-ingest-part-lakeflow-connect)
