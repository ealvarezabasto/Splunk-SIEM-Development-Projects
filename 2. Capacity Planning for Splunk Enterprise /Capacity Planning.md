# Introduction

Below are personal notes from reading and understanding Splunk Capacity Planning Manual
Link: https://docs.splunk.com/Documentation/Splunk/9.4.2/Capacity/IntroductiontocapacityplanningforSplunkEnterprise
***Disclaimer: All text within "" is a word by word copy paste from the Splunk Capacity Planning Manual***

* Splunk Enterprise can accomodate nearly any capacity need. However, effectively taking advantage of the scaling capability requires planning.

# When to consider a Standalone Deployment vs. a distributed deployment

*Note: Standalone Deployment: single reference machine); Distributed deployment: multiple machines to increase performance*

Ask the below questions with regards to your organization:

* **Amount of Incoming data** How much data is expected to be ingested from data sources to the indexers on a daily basis? The more data is sent to Splunk Enterprise, the more time it needs to convert/process ingested data into events that can be later searched, reported, and generate alert on.
* **Amount of indexed data** What is the amount of data that will be retained in Splunk index and for how long?
* **Number of concurrent users** How many users will be using an instance of Splunk Enterprise? The more users, the more resources required to perform searches and create visuals
* **Number of saved searches** Splunk Enterprise needs capacity to perform saved searches promptly and efficiently. The higher the count of saved searches, the higher the resources required.
  * Definition "Saved Search": A saved search in Splunk is a predefined search query that you can save for future use. It allows users to run complex searches without having to re-enter the search parameters each time. Saved searches can be scheduled to run at specific intervals, and the results can be stored for later analysis or used to trigger alerts. This feature enhances efficiency by enabling users to quickly access frequently used searches and automate repetitive tasks. Additionally, saved searches can be shared with other users or teams within the Splunk environment.
* **Type of search you use** Type of search that will be run. The more complex the search, the more resources required as it affects how the indexer respons to search requests.
* **Splunk Apps** By running Splunk apps, consider the resource requirements.

# Index
## Key Metrics

* An indexer can index over 20 megabytes of data per second or over 1.7 terabytes per day.
  * As data volume increase (size of each event in GB), the indexer uses more system memory to process and index.
* If a single indexer cannot meet your indexing capacity needs, you can add more indexers to the deployment to accommodate the higher demand.

## Indexes Performance Impacted

![image](https://github.com/user-attachments/assets/7a322496-2c7c-4d49-b00a-3d9d31d1f412)

* "After Splunk Enterprise consumes data and places it into indexes, those indexes grow and take up disk space. As the indexes grow and available disk space decreases, Splunk Enterprise takes more time to index incoming data because the indexer's disk subsystem takes more time to find space to store the data."
* "As indexes grow, search slows down because the disk subsystem needs to account for search requests, and it also needs to handle increasingly longer requests to store incoming data."

## Understanding I/O Bandwidth

**Overview**

* "As the amount of data stored in a Splunk Enterprise index increases, so does the I/O bandwidth needed to store data and provide results for searches."

**Defining I/O Bandwidth**

* Measurement: I/O bandwidth is typically measured in units such as megabytes per second (MB/s) or gigabytes per second (GB/s). This indicates how much data can be transferred to or from the storage medium within one second.

* Components: I/O bandwidth is influenced by several factors, including:
   * Storage Type: Different storage technologies (HDDs, SSDs, NVMe) have varying bandwidth capabilities. SSDs, for example, generally offer much higher bandwidth than traditional hard drives.
   * Interface: The connection between the storage device and the computer (e.g., SATA, SAS, PCIe) can affect bandwidth. Faster interfaces allow for higher data transfer rates.
   * System Architecture: The overall design of the system, including CPU, memory, and how they interact with storage, can impact I/O performance.
* Importance: High I/O bandwidth is essential for applications that process large volumes of data or require quick access to data. For example, in data analytics platforms like Splunk, sufficient I/O bandwidth ensures that search queries return results quickly, even when dealing with large datasets.

# Searching
* An indexer dedicates one of its available CPU cores for every search that a user runs for as long as the search is active. Multiple users running searches can eat up the available CPU cores. CPU cores are split between indexing, search, and handling on-line users. The solution is to increase the number of indexers that will increase capacity.
* "This growth has an impact on search, as well. On a single indexer, disk throughput splits between indexing, which is ongoing, and search requests, which are interrupts based on requests scheduled by users. As indexes grow, search slows down because the disk subsystem needs to account for search requests, and it also needs to handle increasingly longer requests to store incoming data. Depending on the type of search, those kinds of requests can be I/O-intensive."

## Saved Searches
* A saved search (report) consumes ~1 CPU core and a specified amount of memory white it executes.
* A saved search increases the amount of disk I/O temporarily as the disk subsystme looks through the indexes to retrieved the requested data.

## Search Heads
Definition
* Components in a Splunk architecture that handle user search requests and distribute them to indexers.

Key Metrics
* By adding more search heads, you increase the number of CPU cores available for processing search queries. This allows the system to handle more concurrent searches (multiple users or processes searching at the same time) efficiently.

* "Adding search heads provides additional CPU cores to run more concurrent searches. Adding indexers helps scale with the increased search load and concurrency that comes from adding search heads. Adding RAM to your existing machines helps with concurrent searches but does not give you additional search capacity."
