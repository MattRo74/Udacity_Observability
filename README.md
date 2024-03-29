**Note:** For the screenshots, you can store all of your answer images in the `answer-img` directory.

## Verify the monitoring installation

*TODO:* run `kubectl` command to show the running pods and services for all components. Take a screenshot of the output and include it here to verify the installation

*kubectl get pods,svc -n monitoring:*

<img src="https://github.com/MattRo74/Udacity_Observability/blob/main/answer-img/kubect_get_pods_svs_monitoring.png">

*kubectl get pods,svc -n observability:*

<img src="https://github.com/MattRo74/Udacity_Observability/blob/main/answer-img/kubect_get_pods_svs_observability.png">

*kubectl get pods -A:*

<img src="https://github.com/MattRo74/Udacity_Observability/blob/main/answer-img/kubectl_get_pods_A.png">

*kubectl get svc -A:*
<img src="https://github.com/MattRo74/Udacity_Observability/blob/main/answer-img/kubectl_get_svc_A.png">


## Setup the Jaeger and Prometheus source
*TODO:* Expose Grafana to the internet and then setup Prometheus as a data source. Provide a screenshot of the home page after logging into Grafana.

<img src="https://github.com/MattRo74/Udacity_Observability/blob/main/answer-img/grafana_homepage.png">
	
## Create a Basic Dashboard
*TODO:* Create a dashboard in Grafana that shows Prometheus as a source. Take a screenshot and include it here.

<img src="https://github.com/MattRo74/Udacity_Observability/blob/main/answer-img/basic_dashboard.png">

## Describe SLO/SLI
*TODO:* Describe, in your own words, what the SLIs are, based on an SLO of *monthly uptime* and *request response time*.

**Service Level Objectives (SLOs)** are measureable goals (set by your team). It is important, that this goals are defined from the customers perspective and also, a specific time period needs to be defined:

*monthly uptime*: The User expects an almonst 100 % reachability of the service.
-> The goal is set to a monthly uptime of 99.5 %.
*request response time*: The User expects a really short response time of the service. 
-> The goal is set to a request response time of 50 ms or less each month.

**Service Level Indicators (SLIs)** are metrics to measure the defined goals (SLOs). This measurements shows whether you achieved your set goals or not.

*monthly uptime*: The service has an uptime of 99.7 % last month.
*request response time*: The request response time was on average 10 ms last month.


## Creating SLI metrics.
*TODO:* It is important to know why we want to measure certain metrics for our customer. Describe in detail 5 metrics to measure these SLIs. 


  1. **Request Latency:** The lower the latency for a service, the better a customer will judge it. For example, low latency in streaming services can be a competitive advantage. Therefore, I assume that an SLI is very important in terms of latency.
  2. **Availability:** As a customer, I expect a high level of accessibility from a service. Especially if I have to pay a fee for this service. Let's take the streaming service again. Less Availabilty lead to customer dissatisfaction and ultimately to termination of the service. Therefore, this KPI will be very important.
  3. **Error Rate:** Error rates measures the incorrect API requests to a service. This information is important for the developer team, so that they can specifically fix problems. What is critical is when users accidentally receive data that they are not actually supposed to receive. This can lead to a data protection issue.
  4. **Throughput:** Throughput is a measure of how many units of information a system can process in a given period of time. This metric has a significant role in data transfer and storage throughput. For example the better the throughput of a data driven service is, the better the experience of the user.
  5. **Quality:** If a service is no longer available (because of an overload or a lost connection), it may still be possible to use it based on the previously downloaded data. For example, with a gaming app if the connection to the server has been lost. You can still continue with the app.


## Create a Dashboard to measure our SLIs
*TODO:* Create a dashboard to measure the uptime of the frontend and backend services We will also want to measure to measure 40x and 50x errors. Create a dashboard that show these values over a 24 hour period and take a screenshot.

## Tracing our Flask App
*TODO:*  We will create a Jaeger span to measure the processes on the backend. Once you fill in the span, provide a screenshot of it here. Also provide a (screenshot) sample Python file containing a trace and span code used to perform Jaeger traces on the backend service.

## Jaeger in Dashboards
*TODO:* Now that the trace is running, let's add the metric to our current Grafana dashboard. Once this is completed, provide a screenshot of it here.

## Report Error
*TODO:* Using the template below, write a trouble ticket for the developers, to explain the errors that you are seeing (400, 500, latency) and to let them know the file that is causing the issue also include a screenshot of the tracer span to demonstrate how we can user a tracer to locate errors easily.

TROUBLE TICKET

Name:

Date:

Subject:

Affected Area:

Severity:

Description:


## Creating SLIs and SLOs
*TODO:* We want to create an SLO guaranteeing that our application has a 99.95% uptime per month. Name four SLIs that you would use to measure the success of this SLO.

## Building KPIs for our plan
*TODO*: Now that we have our SLIs and SLOs, create a list of 2-3 KPIs to accurately measure these metrics as well as a description of why those KPIs were chosen. We will make a dashboard for this, but first write them down here.

## Final Dashboard
*TODO*: Create a Dashboard containing graphs that capture all the metrics of your KPIs and adequately representing your SLIs and SLOs. Include a screenshot of the dashboard here, and write a text description of what graphs are represented in the dashboard.  
