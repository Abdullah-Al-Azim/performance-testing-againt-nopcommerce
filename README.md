
# Summary

Dear, 

I’ve completed performance test on frequently used API for test App. 
Test executed for the below mentioned scenario in server 000.000.000.00. 

500 Concurrent Request with 1 Loop Count; Avg TPS for Total Samples is ~ 24.8 And Total Concurrent API requested: 2000.
1000 Concurrent Request with 1 Loop Count; Avg TPS for Total Samples is ~ 21 And Total Concurrent API requested: 4000.
1400 Concurrent Request with 1 Loop Count; Avg TPS for Total Samples is ~ 23 And Total Concurrent API requested: 5600.
1450 Concurrent Request with 1 Loop Count; Avg TPS for Total Samples is ~ 20 And Total Concurrent API requested: 5800.
1500 Concurrent Request with 1 Loop Count; Avg TPS for Total Samples is ~ 40 And Total Concurrent API requested: 12000.

While executed 1450 concurrent request, found  100 request got connection timeout and error rate is 1.72%. 

Summary: Server can handle concurrent 5800 API call with almost zero (0) error rate.

Please find the details report from the attachment and  let me know if you have any further queries.




## Introduction
This document explains how to run a performance test with JMeter against [nopcommerce.](https://demo.nopcommerce.com/)
## Install
Java
https://www.oracle.com/java/technologies/downloads/  
JMeter https://jmeter.apache.org/download_jmeter.cgi

Click =>Binaries  
=>apache-jmeter-5.5.zip

We use BlazeMeter to generate JMX files
https://chrome.google.com/webstore/detail/blazemeter-the-continuous/mbopgmdnpcbohhpnfglgohlbhfongabi?hl=en


## Prerequisites
As of JMeter 4.0, Java 8 and above are supported.
we suggest multicore cpus with 4 or more cores.
Memory 16GB RAM is a good value.
## Elements of a minimal test plan
* Thread Group
* The root element of every test plan. Simulates the (concurrent) users and then run all requests. Each thread simulates a single user.

* HTTP Request Default (Configuration Element)

* HTTP Request (Sampler)

* Summary Report (Listener)

## Collection of API
* Run JMeter

* Collect Frequently used API

* Save JMX file then paste => apache-jmeter-5.5\bin


### List of API
* https://demo.nopcommerce.com/
* https://demo.nopcommerce.com/digital-downloads
* https://demo.nopcommerce.com/books
* https://demo.nopcommerce.com/jewelry

### OR

* File > Open (CTRL + O)
* Locate the "OPENCART_T1.jmx" file contained on this repo
* Continue open OPENCART_T1 to OPENCART_T6
* Open those file
* The Test Plan will be loaded
![plot](https://i.ibb.co/QYPbk8r/jmeter.png)


## Test execution (from the Terminal)
* JMeter should be initialized in non-GUI mode.
* Make a report folder in the bin folder.
* Run Command in jmeter\bin folder.
## Make HTML File
```bash
 jmeter -g report\OPENCART_T1.jtl -o OPENCART_T1.html

```
* g: jtl results file

* o: path to output folder


## HTML Report
Number of Threads 1400 ; Ramp-Up Period 10s

Requests Summary  |Errors
------------- | -------------
  ![](https://i.ibb.co/wJdvrqc/500.png) | ![](https://i.ibb.co/Zm5fVvP/500eroor.png)
