# CST8917-Assignment 2
# Serverless Services Comparison – Azure vs AWS vs GCP

This document compares key Microsoft Azure serverless services used in our course with their closest equivalents in Amazon Web Services (AWS) and Google Cloud Platform (GCP).  
It covers overviews, triggers/bindings, integration options, monitoring tools, pricing, and strengths/weaknesses for each.

---

## **Quick Reference Comparison Table**

| Azure Service                               | AWS Equivalent                              | GCP Equivalent                             |
|---------------------------------------------|---------------------------------------------|---------------------------------------------|
| Azure Functions                             | AWS Lambda                                  | Google Cloud Functions                      |
| Durable Functions                           | Step Functions + Lambda                     | Workflows + Cloud Functions                 |
| Azure Logic Apps                            | AWS Step Functions + Amazon EventBridge     | Google Cloud Workflows + Eventarc           |
| Azure Service Bus (Queues & Topics)         | Amazon Simple Queue Service (SQS) + SNS     | Pub/Sub                                     |
| Azure Event Grid                            | Amazon EventBridge                          | Eventarc                                    |
| Azure Event Hubs                            | Amazon Kinesis Data Streams                 | Pub/Sub Lite                                |

---

## **1. Azure Functions**

**AWS Equivalent:** AWS Lambda  
**GCP Equivalent:** Google Cloud Functions

### Overview
- **Azure Functions:** Event-driven serverless compute supporting triggers/bindings for multiple Azure services.
- **AWS Lambda:** Executes code in response to events without provisioning servers.
- **GCP Cloud Functions:** Lightweight compute responding to HTTP, Pub/Sub, or other events.

### Core Features
- Triggers for storage, queues, HTTP, timers, and more.
- Bindings for input/output to services (e.g., Cosmos DB, Blob Storage).
- Multiple language runtimes (C#, Python, Node.js, Java).

### Integration Options
- CI/CD via Azure DevOps, GitHub Actions, Terraform.
- Deep integration with Azure services.

### Monitoring & Observability
- Azure Application Insights for logs, metrics, distributed tracing.

### Pricing Model
- Consumption plan: pay per execution time and memory usage.
- Premium plan for predictable performance.

### Strengths & Weaknesses
- **Strength:** Rich bindings ecosystem.
- **Weakness:** Cold start latency in consumption plan.

---

## **2. Durable Functions**

**AWS Equivalent:** AWS Step Functions + Lambda  
**GCP Equivalent:** Workflows + Cloud Functions

### Overview
- **Durable Functions:** Extension of Azure Functions for stateful workflows.
- **Step Functions:** Orchestration service for Lambda and AWS services.
- **GCP Workflows:** Orchestrates Cloud Functions and services.

### Core Features
- Function chaining, fan-out/fan-in, human interaction patterns.
- Long-running state management.

### Integration Options
- Works with storage, queues, and APIs.
- CI/CD integration similar to Azure Functions.

### Monitoring & Observability
- Visualizations in Azure Portal, Application Insights tracing.

### Pricing Model
- Charged per function execution and orchestration state storage.

### Strengths & Weaknesses
- **Strength:** Built directly into Azure Functions model.
- **Weakness:** Limited to Azure runtime environment.

---

## **3. Azure Logic Apps**

**AWS Equivalent:** AWS Step Functions + EventBridge  
**GCP Equivalent:** Workflows + Eventarc

### Overview
- **Logic Apps:** Low-code workflow automation connecting services and APIs.
- **AWS Step Functions/EventBridge:** Workflow + event routing in AWS.
- **GCP Workflows/Eventarc:** Workflow automation and event routing.

### Core Features
- 300+ connectors to SaaS and on-prem systems.
- Visual designer for workflow creation.

### Integration Options
- Connects to APIs, databases, messaging platforms.

### Monitoring & Observability
- Azure Monitor, run history, error diagnostics.

### Pricing Model
- Pay per execution and connector usage.

### Strengths & Weaknesses
- **Strength:** Large connector library.
- **Weakness:** Complex pricing for high-volume integrations.

---

## **4. Azure Service Bus (Queues & Topics)**

**AWS Equivalent:** Amazon SQS (queues) + SNS (pub/sub)  
**GCP Equivalent:** Google Pub/Sub

### Overview
- **Service Bus:** Enterprise-grade messaging with queues (point-to-point) and topics (pub/sub).
- **SQS/SNS:** Managed message queuing and notification services.
- **Pub/Sub:** Asynchronous messaging for event-driven architectures.

### Core Features
- Message sessions, dead-letter queues, FIFO.
- Scheduled delivery.

### Integration Options
- Works with Functions, Logic Apps, and Event Grid.

### Monitoring & Observability
- Azure Monitor metrics, message tracking.

### Pricing Model
- Based on operations and message size.

### Strengths & Weaknesses
- **Strength:** Advanced features like sessions.
- **Weakness:** Slightly higher latency than lightweight queues.

---

## **5. Azure Event Grid**

**AWS Equivalent:** Amazon EventBridge  
**GCP Equivalent:** Eventarc

### Overview
- **Event Grid:** Event routing service with publish/subscribe model.
- **EventBridge:** Event bus for AWS services and custom apps.
- **Eventarc:** Routes events from GCP services or SaaS.

### Core Features
- High throughput, low latency.
- Filters and routing rules.

### Integration Options
- Triggers Functions, Logic Apps, automation workflows.

### Monitoring & Observability
- Azure Monitor event metrics.

### Pricing Model
- Pay per million operations.

### Strengths & Weaknesses
- **Strength:** Deep Azure integration.
- **Weakness:** Vendor lock-in for certain event sources.

---

## **6. Azure Event Hubs**

**AWS Equivalent:** Amazon Kinesis Data Streams  
**GCP Equivalent:** Pub/Sub Lite

### Overview
- **Event Hubs:** Big data streaming platform for telemetry/event ingestion.
- **Kinesis:** Real-time data streaming at scale.
- **Pub/Sub Lite:** Lower-cost streaming alternative to GCP Pub/Sub.

### Core Features
- Partitioned consumer model.
- Capture to storage for batch processing.

### Integration Options
- Feeds into analytics, Functions, or Databricks.

### Monitoring & Observability
- Azure Monitor metrics, lag tracking.

### Pricing Model
- Based on throughput units and data retention.

### Strengths & Weaknesses
- **Strength:** High ingestion rates.
- **Weakness:** Requires throughput planning.

---

## **Summary**

Azure, AWS, and GCP all offer strong serverless capabilities, but:
- Azure shines in **tight integration and bindings**.
- AWS has **broad ecosystem reach** and mature orchestration with Step Functions.
- GCP offers **simple pricing** and strong integration with Google’s data tools.

When choosing, consider **event source compatibility**, **latency needs**, **pricing**, and **developer experience**.
