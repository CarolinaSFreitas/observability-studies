# 🐶 Datadog - Studies

[Docs.](https://docs.datadoghq.com/)

Datadog is an observability platform for cloud-scale apps, providing monitoring of servers, databases, tools, and services, through a SaaS-based data analytics platform. 

In the image below, it is possible to see the 3 pillars of observability in Datadog.

<div align="center">
  <img src="./images/datadog-overview.png">
   <p><em>Datadog Overview</em></p>
</div>

# Introduction to Observability

## 3 Pillars of Observability

1. Metrics:
These data points are numerical values that can track anything about your environment over time

2. Logs:
A computer generated file that contains time stamped information about the usage of that system

3. Traces:
Used to track the time spent by an application processing a request and the status of this request 

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

### Storing our Logs 

**What kind of services generate logs?**
- Servers
- Serverless Functions
- Web Browsers
- Mobile/IoT Devices
- Containers 
- Cloud Services

### How long do we store Logs? - Log Storage

Three guiding principles when determining how long we want to store our logs:

1. **Compliance:** Standards that the business is held to might dictate how long your logs need to be stored.
2. **Usefulness:** Some logs are more helpful than others. It's up to you to decide which logs need to be stored for whatever length of time is useful to you.
3. **Cost:** Storage costs money. Depending on the services you're using, you'll want to keep in mind your budget when deciding on storage length.

In Datadog from logs we can create metrics, alarms, archives, etc.

## Traces and Spans

- A trace is used to track the time spent by an app processing a request long with the execution path taken. 
A trace can also be defined as the entire journey including all of the stops along the way.

- A span is the individual unit of work that the code is doing.

![trace-span](./images/trace-span.png)

### Why do we collect traces?

1. **Microservices:** as business migrate away from Monolithic architecture, tracing is needed to figure out what all of the microservices are up to. 
2. **Optimization:** tracing allows you to optimize the performance of your apps by identifying bottlenecks in the calls being made.
3. **Troubleshooting:** when something goes wrong, we need insight into the actual app code. 

#### Topics overview of 'Datadog Foundation'
**Universal** Service Monitoring (USM) provides a comprehensive overview of service health metrics across your technology stack without requiring you to instrument your code.

**Logs** capture event streams from various components of your infrastructure. Datadog Log Management enables you to cost-effectively collect, process, archive, explore, and monitor all your logs.

**Metrics** can track a wide range of measurements—such as latencies, error rates, or even user signups—within your environment over time. Monitors actively check on these metrics and alert you when critical changes occur, for example, when a threshold indicating a problem is crossed. You can use either metrics or monitors as the basis for service level objectives (SLOs), which define targets for performance and provide a framework for establishing clear standards for service quality.

**Integrations** are plugins or add-ons that enable Datadog to monitor individual third-party software, services, or tools. With the help of integrations, Datadog can unify different metrics and logs generated by many technologies deployed across your infrastructure.

**Dashboards** allow you to view curated visualizations of key observability data on a single page. You can create custom dashboards from scratch, but there are also many out-of-the-box (OOTB) or pre-built dashboards available.

# Datadog Foundation

## Universal Service Monitoring - USM

USM offers a view of surface health metrics across your entire technology stack without the need to instrument your code. Instead, it relies on the presence of a configured Datadog agent and universal service tagging to collect data about your existing services, which can then be viewed through the service catalog. 

### Enabling USM requires the following: 

- If on Linux, your service must be running in a container.
- If on Windows and using IIS, your service must be running on a virtual marchine.
- The Datadog Agent needs to be installed alongside your service. 
- The env tag for Unified Service Tagging must be applied to your deployment. 

## Unified Service Tagging 

USM is capable of identifying services through commonly used container tags, such as app, short image and container name. And automatically generates corresponding entries in the service catalog. Once these services are covered, Datadog enables you to access request, access, error and duration metrics for both inbound and outbound traffic. 

These service health metrics are helpful in setting up alerts, tracking deployments, and establishing service level objectives (SLOs), providing you with a comprehensive view of all the services running on your infrastructure.

The Service Catalog in Datadog is a centralized place to view all services in your application. Service Catalog automatically includes services detected by USM. Developers and site reliability engineers can view all services, their structures, and links to more information. It improves the on-call experience for everyone by establishing correct ownership information and communication channels, alongside easy access to monitoring and troubleshooting details. In case of an incident, it can speed up recovery by increasing confidence and making it simpler to locate owners of upstream and downstream services and dependencies.

## LAB: USM and Service Catalog 

[docker-compose.yml](./docker-compose.yml) example of how the Agent was configured to enable USM

The first service listed, ``datadog``, is the Datadog Agent. The Agent monitors other containers and the Docker host to collect USM data.

On line 17, this environment variable enables USM in the Agent:

``DD_SYSTEM_PROBE_SERVICE_MONITORING_ENABLED=true``

Locate line 25. This is the start of a list of files on the Docker host that are mounted as volumes in the Agent container. The Agent will access these files to build a comprehensive picture of the services running on the Docker host.

Locate line 41, which defines the extra capabilities granted to the Agent container. These are required because the Agent uses eBPF for most of its data gathering, which operates at the kernel level.

Docker-compose is orchestrating Storedog in this lab, but USM can be enabled almost anywhere the Agent can run. See the USM documentation to learn about USM in other environments.

#### The Services
Services that you want to appear in Service Catalog should have unified service tags. These are three tags that the Agent will look for to help identify services:

``service``, the name of the services, such as ``store-ads``
``env``, the environment in which the services is running. For example, ``production``, ``internal``, ``foundation-lab``
``version``, a number such as ``1 or 1.2.3``
If services are running in containers, they are tagged using labels.

In docker-compose.yml, locate line 104, which defines the container labels for the ``store-frontend`` service:

````
labels:
   com.datadoghq.ad.logs: '[{"source": "nodejs", "service": "store-frontend"}]'
   com.datadoghq.tags.env: '${DD_ENV}'
   com.datadoghq.tags.service: 'store-frontend'
   com.datadoghq.tags.version: '1.0.10'
   my.custom.label.team: 'frontend'
```` 

You can see the ``com.datadoghq.tags.*`` labels that comprise the unified service tags for this service. ``env`` is set to ``${DD_ENV}``, an environment from the Docker host that is set to ``foundation-lab``.

Find other unified service tags in docker-compose.yml. Notice that the value for ``service`` is the name that Universal Service Monitoring uses to identify the service, and that's what is displayed in Service Catalog.

