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

## Logs 

Datadog Log Management allows you to cost-effectively collect, process, *archive, explore, and monitor all your logs without limitations.

### Datadog Log Management:

- You can collect logs from various sources, such as hosts, containers, and cloud providers.
- Once the logs are ingested, you can enhance them using pipelines and processors, create metrics from the logs, and manage storage-optimized archives with Log Configuration options.
- You can connect logs to metrics and traces from other sources for greater insights.
- Finally, you can search, filter, and query the ingested logs in the Log Explorer.

### Log Explorer 

The Log Explorer is your central hub for investigating and exploring logs. You can browse logs, search for specific words, filter many log lines to show only the lines you’re interested in, group content, visualize patterns, and export logs.

A search query in Log Explorer is composed of terms (either a single word or a group of words surrounded by double quotes) and Boolean operators. You can also filter logs using log facets, which are user-defined tags and attributes from your indexed logs, which are logs that have been collected, processed, and retained for analysis, alerting, and troubleshooting.

Logs can be valuable as individual events, but sometimes valuable information lives in a subset of events. In order to get this information, you can group your logs into fields, patterns, and transactions.

To better visualize the results of the filtered and aggregated logs, you can choose different visualizations to surface crucial information. For example, you can arrange your log data into columns by viewing them as a list, or track changes in your log data over time by observing them in a timeseries. Other visualizations include top list, nested tables, pie charts, and a tree map.

#### Notas:

To see logs in real time: 
1. Logs
2. Explorer
3. Time field (ex.: Past 15 min.) change to Live Tail

Search bar:
Under the search bar, there are options to group the logs into fields, patterns, or transactions, and to visualize the logs as a list, timeseries, top list, table, tree map, or pie chart.

1. In the search bar, start typing service:store-frontend, and the search bar's autocomplete feature will provide values to complete your query.

2. When it appears, select store-frontend in the autocomplete list to view all the logs from the store-frontend service.

3. Next to Group into, click on Fields to group logs by fields.

4. When aggregating indexed logs by fields, all logs matching your query filter are aggregated into groups based on the value of one or more log facets.

5. Next to Show Count of, click on all logs if it is not already selected. Here you could alternatively filter results by selecting various available measures, such as the count of unique values for a particular facet (for example, Service), or statistical operations on numerical values of a facet (for example, Duration).

Search for all the logs originating from a file using that filename attribute:
- Filter by ``@filename:ads.py``

Filter using text strings from log messages:
- In the search bar, enter the following, making sure to include the double quotes " around the text string:
``"Total advertisements available"``

Facets:
Common tags and attributes automatically appear in the facet panel as Datadog parses logs. Facets are useful for qualitative or quantitative data analysis, so you can use them to search through logs, define log patterns, and perform log analytics. Although the automatically generated facets are helpful, you might also want to create your own custom facet that appears in the facet panel. You can accomplish this with the help of the log details in the log side panel.

1. In the list of store-discounts logs that have "influencer specific discounts" in the log message, click one of the log lines to open the log side panel.

2. Under Event Attributes, for the process attribute, click on name and select Create facet for @process.name from the popup menu.

3. The Add facet popup dialog will appear. You can expand Advanced if you want to view the additional fields.

4. Click Add.

5. You'll see a message confirming that the facet has been successfully added.

6. Close the logs side panel and clear the search bar at the top of the page.

7. Scroll to the bottom of the facet panel. Under the OTHERS facet group, expand the process.name facet.

Log Aggregation:
With field aggregation, all logs matching the query filter are split into groups (i.e., aggregated) based on the different values of a specified log facet. Aggregating or grouping logs this way can help you see trends more clearly and visualize relationships between different types of log facets.

It would likely be even more useful if you could see the logs grouped, for example, by Service.

Next to by, change Everything to Service (service) to group by service.

Export graphs
You can export any logs visualization to other areas of Datadog. You can even create a custom metric from logs or download aggregated data as a CSV.

1. Change the visualization back to Timeseries.

2. Click the Save to Dashboard button above the graph.

Note: If you click on the More button next to it, you can see the different ways to export the logs.

3. In the Export graph popup dialog, click the New Dashboard link.

4. Export graph dialog with New Dashboard highlighted.

5. A notice at the top of the page contains a link to the new dashboard.

6. Click the link if you want to see the dashboard.

## Metrics: 

Metrics are the smallest unit in the Datadog universe but they grant enormous insight into your infrastructure when they are visualized, measured, and monitored. Metrics are numerical measurements about any aspect of your system over a period of time, such as latency, error rates, or user registrations. In Datadog, metric data is received and retained as data points that include a value and timestamp.

Monitors send notifications when metrics fall outside of the tolerances that you define.

Service Level Objectives track metrics over long periods of time to help you define quality standards.

Sending metrics to Datadog
Metrics can be sent to Datadog from several sources:

The Datadog Agent automatically sends many standard metrics, such as avg:system.cpu.user: 18.63 or system.disk.read_time: 42.
Datadog integrations include metrics out of the box.
Metrics can be generated within the Datadog platform.
You can create custom metrics related to your business and submit them through the Agent, DogStatsD, or the HTTP API.
Metric types
Datadog offers metric types that apply to specific purposes: count, rate, gauge, histogram, and distribution. These metric types determine the available graphs and functions that can be utilized with the metric within Datadog.

Count: Adds up the values received within a specified time interval. For example, 2000 HTTP requests.

Rate: Divides the count by the duration of the time interval. Using the same example mentioned above, 0.566 HTTP requests per second.

Gauge: Reports the last value received during the specific time interval. This metric type would be appropriate for monitoring the usage of RAM or CPU, since the last value gives an accurate representation of the host’s behavior during the timeframe: 2097152 bytes of RAM.

Histogram: Summarizes the submitted values into five different values: the mean, count, median, 95th percentile, and maximum. This generates five distinct timeseries. For example, this metric type is useful for measuring latency, where it is inadequate to only know the average value. Histograms enable you to understand how the data is distributed without recording every single data point.

Distribution: Summarizes the values submitted within a time interval across all the hosts in your environment. Distributions provide enhanced query functionality and configuration options that aren’t offered with other metric types.

### Metrics Explorer
Once you have metrics in Datadog, you can examine them using the Metrics Explorer. You can customize the graph shown on the Metrics Explorer page by using the query editor. You can also search for tag values to define a filtering scope or select a space aggregation method (such as, average, max, min, sum) to combine metric values. Additionally, the function button can be used to add functions to your query.

### Monitors
It’s a Tuesday afternoon and global web hosting company ABC has a major outage in region jupiter-east-1. You happen to be staring at your Datadog dashboard at the exact moment when the outage begins. But what if you aren’t?

Monitors will continuously check metrics, integration availability, network endpoints, and other vital aspects for conditions that you define. When a threshold is exceeded, Datadog will notify you or your team on the Datadog mobile app, by email, or on your chat platform. This capability is essential for complete infrastructure visibility in one centralized location.

Datadog offers a variety of monitors to cater to different monitoring needs. Some of the most popular types of monitors include:

Metric monitors: Used to track and alert on specific metrics. This type of monitor is commonly used to track things like server CPU usage, memory utilization, or network bandwidth. For example, Send a notification to the DevOps team if average HTTP response time exceeds 1.50 seconds.

Service Checks: Used to verify the status and availability of various services, such as databases or APIs. Service Checks can be used to monitor both external and internal services. For example, is the redis service healthy?

APM monitors: Used to monitor application performance, track errors, and measure latency. This monitor provides insights into how applications are executing and helps to identify potential issues. For example, alert the development team with an application’s Errors per second is above 25.

Synthetics monitors: Used to monitor critical user flows and business transactions. Synthetic API tests and browser tests help you proactively identify issues in application endpoints and key business workflows before your end users encounter them. Synthetics monitors can simulate user actions, such as logging in or adding an item to a shopping cart, and alert you if there are any errors or delays.

Log monitors: Used to monitor specific keywords or patterns in log data. Log monitors can track security issues, application errors, or system events.

These monitors can be customized. You can create Service Level Objectives from them, too.

### Service Level Objective (SLO)
Service Level Indicators (SLIs) are metrics that are used to measure some aspect of the level of service that is being provided. For example, 10 errors per second on the storedog-payments service. SLIs that are vital to your organization’s success can be monitored over time as Service Level Objectives (SLO). Tracking these metrics as SLOs establishes clear targets for service quality, enabling you to measure progress and make improvements over time. For example, the service has an SLO of 99% of requests being successful over the past 7 days or less than 1 second latency 99% of the time over the past 30 days.

This approach enables site reliability engineers, frontend developers, and even product managers to maintain a consistent customer experience, balance feature development with platform stability, and enhance communication with both internal and external users. Your team will be focused on the metrics that matter most and you’ll be consistently delivering a high level of service to your customers. In essence, SLOs provide a roadmap for defining, measuring, and improving service quality, ultimately leading to a more robust and reliable system.

