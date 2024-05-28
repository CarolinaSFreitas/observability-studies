# 🐶 Datadog - Studies

[Docs.](https://docs.datadoghq.com/)

Datadog is an observability platform for cloud-scale apps, providing monitoring of servers, databases, tools, and services, through a SaaS-based data analytics platform. 

In the image below, it is possible to see the 3 pillars of observability in Datadog.

<div align="center">
  <img src="./images/datadog-overview.png">
   <p><em>Datadog Overview</em></p>
</div>

## Metrics

Metrics are numerical values that can track anything about your environment over time, from latency to error rates to user signups. 

<div align="center">
  <img src="./images/ex-metrics.png">
     <p><em>Metrics</em></p>

  <img src="./images/ex2-metrics.png">
   <p><em>Datadog Metrics</em></p>
</div>

Metrics make more sense when we graph them over time. This allows us to clearly identify patterns in our data. In this way, we can distinguish between what is normal and what is abnormal.

### Reasons to Collect Metrics: 

- Baseline for Operations: 
Metrics can tell us what normal looks like for our apps. Without metrics, we're stuck guessing what's going on.

- Reactive Responses:
Using metrics we don't have to wait until a customer reports an outage. We can react to issues in our environment before they snowball. 

- Proactive Responses: 
Why wait for something to go wrong? By looking at metrics we can get ahead of problems before they happen. 

### Why does this matter?

- Wake up less for on call
- Less fire drills
- Reduced costs
- Happier customers 
- Less tickets
- Happier boss

## Monitoring 

Monitoring is the act of paying attention to the patterns that your metrics are telling you. It's about analyzing your data and acting on it. 

### What do we Monitor?

1. Performance
- By watching performance we can watch how our architecture and apps are using the resources that are available
- CPU, disk, memory...

2. Security
- Is something going wrong in our environment? Creating monitors around security metrics can stop incidents in their tracks  
- Anomalies, sign-ins from unauthorized locations, and ensure data is securely stored.

3. Usage 
- What are our users doing in our environment? Are they interacting with our products? 

## Alerting

Alerts are simply setting a threshold in a monitor. When that threshold is breached, a notification is sent to the designated recipient. 

### Alert Fatigue 

Alert fatigue arises from over alerting. It's important to only alert team member when something actionable needs to be done. 
**If everything is an emergency, nothing is an emergency.**

## Logs 

A log is a computer generated file that contains information regarding the usage of a system. This gives you insight into the behavior of the resource. 

### Why do we collect logs? 

1. Compliance
- Standards that the business is held to might dictate which logs you'll need to store and for how long you need to store them. 

2. Insight 
- Logs can give you insight into apps and system performance that metrics by themselves might not be able to provide.

3. Security
- This is a priority for businesses. Logs are needed to demonstrate that only authorized activities are going on inside of a system. 

### Practical uses for Logs

- Troubleshooting
- Auditing 
- Monitoring 
- Alerting
- Personal History 
- Not getting in trouble 
