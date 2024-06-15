# SentimentStorageSymphony

# Beyond the Headlines: My Journey with Cassandra, Neo4j, and MongoDB for Advanced Machine Learning and NLP Analysis

![Project Overview Image](https://raw.githubusercontent.com/TruthQuest/SentimentStorageSymphony/main/database_artwork.jpeg)

## Project Overview

This project explores how Cassandra, MongoDB, and Neo4j handle the complexities of machine learning and NLP tasks. It evaluates their pros and cons in sentiment analysis to find the best fit for performance, scalability, and integration.

## Goals

- Evaluate the performance, scalability, and integration capabilities of Cassandra, MongoDB, and Neo4j.
- Perform sentiment analysis using VADER and BERT models.
- Measure execution time, resource utilization, and scalability for each database.
- Integrate each database with existing project architecture, including Spark.

## Methodology

### 1. Data Ingestion

- **Cassandra**: Used Spark to read JSON files containing news articles and loaded them into a Cassandra table for further processing.
- **MongoDB**: Converted processed JSON files to CSV format and loaded them into a MongoDB collection using the Spark-MongoDB connector.
- **Neo4j**: Transformed processed JSON files to CSV format and imported them into Neo4j, creating relationships between articles, authors, publishers, themes, and emotions.

### 2. Sentiment Analysis

Performed sentiment analysis on the article content using VADER and BERT models concurrently to ensure consistency in sentiment scores.

### 3. Data Retrieval and Aggregation

- **Cassandra**: Queried the Cassandra table directly to retrieve article data and sentiment scores.
- **MongoDB**: Used the Spark-MongoDB connector to read data from the MongoDB collection and performed aggregations.
- **Neo4j**: Utilized Cypher queries for data retrieval and aggregation.

### 4. Performance Evaluation

Measured execution time and resource utilization for data ingestion, sentiment analysis, and data retrieval tasks. Tested scalability with varying data sizes and concurrent user requests.

### 5. Integration and Ease of Use

Evaluated the ease of integrating each database with the existing project architecture, including Spark. Considered the learning curve and impact on developer productivity.

## Initial Insights

### Cassandra

- Wide-column store design posed challenges in mapping JSON data to its table-based structure.
- Handling semi-structured or unstructured data was tough.
- Lack of native support for complex queries and aggregations required external tools for NLP tasks.

### MongoDB

- Native JSON support made it easy to store and retrieve JSON-like documents.
- Flexible schema and robust querying capabilities simplified work.
- Integration with NLP tools and frameworks like BERT and VADER was straightforward.
- Integration with Spark required extra configuration.

### Neo4j

- Powerful graph capabilities with complex and verbose Cypher queries.
- Converting JSON data into nodes and relationships in a graph was unique.
- Graph traversal for analyzing entity relationships in sentiment analysis showed potential.
- Seamless integration with NLP libraries and frameworks.

## Actual Findings

- Cassandra was easier to work with compared to both MongoDB and Neo4j.
- Cassandra presented fewer integration challenges and was easier to manage than expected.
- Neo4j required verbose code and complex syntax, making it less consistent.

## Conclusion

Initially, MongoDB seemed the best choice for storing JSON data and performing NLP tasks using BERT and VADER, due to its native support for JSON-like documents, flexible schema, and powerful querying capabilities. However, practical implementation revealed that Cassandra was easier to manage and presented fewer integration challenges. While Neo4j offers significant advantages for analyzing entity relationships, it requires additional transformation steps for JSON data compatibility.

This analysis suggests that while MongoDB remains a robust option for sentiment analysis projects, Cassandra's unexpected ease of use makes it a viable and potentially more straightforward solution, depending on the project's specific requirements and constraints.

## Getting Started

To get started with this project, follow these steps:

1. Clone the repository:
   ```bash
   git clone https://github.com/TruthQuest/SentimentStorageSymphony.git
   cd SentimentStorageSymphony
