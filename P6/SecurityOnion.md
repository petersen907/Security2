# Project 6 - Security Onion

## Project Description

Configure a NIDS sensor, managed from your secure zone, that monitors DMZ
network traffic, and alerts when it notices potentially malicious traffic. Add
webservers and publish a website to monitor with the SEIM.

## Add webservers and publish a website to monitorwith SEIM

![Onion1](https://user-images.githubusercontent.com/55543355/227064989-258e8c60-dec8-4616-917a-3806d4c97076.png)

In our DMZ, we set up a containerized nginx web server. This is the publicly
exposed website that we will be able to monitor

![Onion2](https://user-images.githubusercontent.com/55543355/227065084-010125bb-7d61-4d4c-903f-f045700ebc7d.png)

![Onion4](https://user-images.githubusercontent.com/55543355/227065223-d18779b7-ddf4-4458-bc8b-991e7b9ccc20.png)

We set up NAT rules to forward requests to one of our public IP's (157.201.22.43) to our DMZ nginx server.

![Onion3](https://user-images.githubusercontent.com/55543355/227065104-7b752b9c-e5b7-4f11-a13f-88e431a0a270.png)

We then configured Security Policy rules to make sure that the NAT'ed traffic
was allowed.

![Onion5](https://user-images.githubusercontent.com/55543355/227065252-7c452aec-4c16-4cef-a425-0a155ec0bf8d.png)
  
Now our NGINX server is publicly exposed.

## Configure a NIDS sensor, managed from your secure zone, that monitors DMZ network traffic, and alerts when it notices potentially malicious traffic.

We set up SecurityOnion using the setup wizard, configuring our Secure subnet
as home for our management interface, and our DMZ as the monitoring
interface in promiscuous mode.

![Onion6](https://user-images.githubusercontent.com/55543355/227065337-0cfecca8-7e62-47aa-a319-fd181e24bbb2.png)

We then were able to access the SecurityOnion GUI from our Secure network.

![Onion7](https://user-images.githubusercontent.com/55543355/227065372-1c4b5bb1-f86d-4309-8c34-5b3e14c12e0a.png)

It picked up traffic from our .10.0/24 network (DMZ)

![Onion8](https://user-images.githubusercontent.com/55543355/227065406-a37780af-f354-48a9-b4dd-1ae9677ffcf6.png)

We then added a custom rule in /opt/so/rules/local.rules, following the suricata documentation found at https://suricata.readthedocs.io/en/suricata-6.0.0/rules/http-keywords.html

![Onion9](https://user-images.githubusercontent.com/55543355/227065484-131a2e5b-36a7-44c7-819d-e50fd93b92b6.png)

Then, we updated the rule table so that Security Onion can pick up the configured events.

![Onion10](https://user-images.githubusercontent.com/55543355/227068566-5ff1c524-83ff-4e1f-9599-017d3c4f0ed5.png)

Now to test our rule, we pinged within the DMZ.

![Onion11](https://user-images.githubusercontent.com/55543355/227068585-5ace0250-105e-4dab-b14c-e7854d743420.png)

The alert was successfully picked up, and we are able to now monitor our DMZ
