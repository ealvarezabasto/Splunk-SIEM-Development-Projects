# Introduction

Below are personal notes from reading and understanding Splunk Capacity Planning Manuagl
Link: https://docs.splunk.com/Documentation/Splunk/9.4.2/Capacity/IntroductiontocapacityplanningforSplunkEnterprise

* Splunk Enterprise can accomodate nearly any capacity need. However, effectively taking advantage of the scaling capability requires planning.

# When to consider a Standalone Deployment (single reference machine) vs. a distributed deployment (multiple machines to increase performance)
* * **Amount of Incoming data** How much data is expected to be ingested from data sources to the indexers on a daily basis? The more data is sent to Splunk Enterprise, the more time it needs to convert/process ingested data into events that can be later searched, reported, and generate alert on.
* * **Amount of indexed data** What is the amount of data that will be retained in Splunk index and for how long?
* * **Number of concurrent users** How many users will be using an instance of Splunk Enterprise? The more users, the more resources required to perform searches and create visuals
* * **Number of saved searches** Splunk Enterprise needs capacity to perform saved searches promptly and efficiently. The higher the count of saved searches, the higher the resources required.
  * Definition "Saved Search": A saved search in Splunk is a predefined search query that you can save for future use. It allows users to run complex searches without having to re-enter the search parameters each time. Saved searches can be scheduled to run at specific intervals, and the results can be stored for later analysis or used to trigger alerts. This feature enhances efficiency by enabling users to quickly access frequently used searches and automate repetitive tasks. Additionally, saved searches can be shared with other users or teams within the Splunk environment.
* * **Type of search you use** Type of search that will be run. The more complex the search, the more resources required as it affects how the indexer respons to search requests.
* * **Splunk Apps** By running Splunk apps, consider the resource requirements.

# Index
## Key Metrics
* An indexer can index over 20 megabytes of data per second or over 1.7 terabytes per day.
  * As data volume increase (size of each event in GB), the indexer uses more system memory to process and index.
* If a single indexer cannot meet your indexing capacity needs, you can add more indexers to the deployment to accommodate the higher demand.

## Indexes Performance Impacted

* After Splunk Enterprise consumes data and places it into indexes, those indexes grow and take up disk space. As the indexes grow and available disk space decreases, Splunk Enterprise takes more time to index incoming data because the indexer's disk subsystem takes more time to find space to store the data.
* This growth has an impact on search, as well. On a single indexer, disk throughput splits between indexing, which is ongoing, and search requests, which are interrupts based on requests scheduled by users. As indexes grow, search slows down because the disk subsystem needs to account for search requests, and it also needs to handle increasingly longer requests to store incoming data. Depending on the type of search, those kinds of requests can be I/O-intensive.
* 


