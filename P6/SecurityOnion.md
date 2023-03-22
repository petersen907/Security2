# Project 6 - Security Onion

## Project Description

Configure a NIDS sensor, managed from your secure zone, that monitors DMZ
network traffic, and alerts when it notices potentially malicious traffic. Add
webservers and publish a website to monitor with the SEIM.

## Add webservers and publish a website to monitorwith SEIM



In our DMZ, we set up a containerized nginx web server. This is the publicly
exposed website that we will be able to monitor




We set up NAt rules to forward requests to one of our public IP's (157.201.22.43) to our DMZ nginx server.


We then configured Security Policy rules to make sure that the NAT'ed traffic
was allowed.


Now our NGINX server is publicly exposed.


## Configure a NIDS sensor, managed from your secure zone, that monitors DMZ network traffic, and alerts when it notices potentially malicious traffic.


We set up SecurityOnion using the setup wizard, configuring our Secure subnet
as home for our management interface, and our DMZ as the monitoring
interface in promiscuous mode.


We then were able to access the SecurityOnion GUI from our Secure network.


It picked up traffic from our .10.0/24 network (DMZ)



We then added a custom rule in /opt/so/rules/local.rules, following the suricata documentation found at https://suricata.readthedocs.io/en/suricata-6.0.0/rules/http-keywords.html



Then, we updated the rule table so that Security Onion can pick up the configured events.


Now to test our rule, we pinged within the DMZ.



The alert was successfully picked up, and we are able to now monitor our DMZ