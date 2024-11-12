## Objective
This is my first cybersecurity project, inspired by a video walkthrough from the MYDFIR YouTube channel. While this is a guided walkthrough, my goal is to not only follow along but to rebuild the ELK stack entirely from scratch, speaking to each part as I go. I aim to fully understand and explain every component, documenting this hands-on journey to establish a strong foundation in cybersecurity skills.  

There are many similarities to Splunk, and the benefits are centralized logging, customized ingestions, visualizations, scalability,  many intergrations and rich community.

## Day 1  
- Created a logical diagram where I utlize cloud infrastructure from VULTR. Within this infrastructure I have a virtual private cloud that houses 5 servers.

- Of these 5, we have a Windows10 server and a Ubuntu server, both with remote connection capabilities. These 2 servers will forward logs via agents to the Elastic/Kibana server.

- The osTicket server will receive alerts create corresponding tickets within the the osTicketing service. The Windows and Ubuntu server, as well as the agents will be centrally managed by the Fleet server.

- We have configured a private network of 172.31.0.0/24 with a subnet of 255.255.255.0.There 254 hosts available within this IP range

- We have a gateway that leads out to the external network, where there will be a SOC analyst laptop connected to Elastic/Kibana via GUI. On the other end lies an attack laptop (Kali) and a C2 server.
  <img src="https://github.com/user-attachments/assets/fea64ba9-a8c2-47d5-b43a-1a680bf06e3e" height="70%" width="70%" alt="logical-diagram"/>

## Day 2
- Today was a introduction into the ELK stack, which I had no prior knowledge of before I started.  It consists of Elasticsearch, Logstash, and Kiabana

### Elasticsearch
- At it's core elasticsearch is a database that is used to store logs such windows event logs, firewall logs, sys logs, etc. Allows you to query data using it's own query language ESQL or elasticsearch query language.  
  - Uses Restful APIs and json.
    
### Logstash
- Server side data processing pipeline ingests data, processes, cleans, transforms data and then sends it to your stash of choice (storage or database) to be searched, and analyzed (in this case elasticsearch).
- Collects telemetry (automated process of collecting, transmitting, and analyzing data) utilizing two popular ways: Elastic agents, and beats.
- Highly customizable filters that allow you to parse through data creating a structured format.

### Kibana
- Kibana is a analytics and visualization tool. Adds an UI experience allows drag and drop to build out custom dashboards.
- Through data exploration/discover tab it allows you to query logs using ESQL (elasticsearch query language), maps for geospacial locations, ML anomaly detection etc.

## Day 3


  
  <!--
  - https://www.notion.so/justinmoore/30-Day-DFIR-Challenge-13778832b68e804e9dd2cd2d9399331c
