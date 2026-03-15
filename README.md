# CS544 P7: Kafka, Weather Data

**Course:** CS544 — Big Data Systems, UW-Madison (Fall 2025)

## Overview

A **Kafka streaming pipeline** for daily weather data. A producer ingests weather station data into a Kafka topic; a consumer reads from the stream and produces **JSON summary statistics** for use in a web dashboard.

## Learning Objectives

- Implement Kafka producers and consumers in Python
- Design Kafka topics with appropriate partition strategies
- Process streaming data to compute rolling statistics
- Handle offset management and consumer group coordination

## Architecture

```
Weather Stations
      │
      ▼ produce
Kafka Topic (weather-data)
      │
      ▼ consume
Consumer → JSON summary files
```

## Tech Stack

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Kafka](https://img.shields.io/badge/Kafka-231F20?style=flat&logo=apachekafka&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)

## Project Structure

```
p7/
├── docker-compose.yml  # Kafka broker + Zookeeper
├── producer.py         # Reads weather data → Kafka topic
├── consumer.py         # Kafka topic → JSON summary stats
├── report.ipynb        # Analysis of streaming pipeline
└── README.md
```

## Key Features

- Single Kafka broker setup with configurable partitions
- Consumer groups for scalable parallel processing
- Rolling statistics: min, max, average temperature per station
- Exactly-once delivery semantics via offset management

## Author

**Rakshith Sriraman Krishnaraj** · MS CS @ UW-Madison · [LinkedIn](https://www.linkedin.com/in/rakshith-s-k-95b550151/)
