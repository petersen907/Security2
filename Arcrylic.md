# Setting up Arcrylic on Windows Server

## Find Source

Arcrylic is available to install through:

https://mayakron.altervista.org/support/acrylic/Home.htm

## Download Arcrylic

Click "Download Setup for Windows" under "How do I download Arcrylic?"

![image](https://user-images.githubusercontent.com/55543355/223294928-166262c3-30c6-4ea0-bf1d-cb8340a31ebe.png)

## Setup

Once you have Arcrylic downloaded, click "File" and then "Open Arcrylic Configuration" or press Ctrl+F1 to open the Configuraion File.

![image](https://user-images.githubusercontent.com/55543355/223299409-f1459512-1807-4ea6-a93d-973054b15d37.png)


At the bottom, under "[AllowedAddressesSection]" enter your custom IP addresses as shown by the examples highlighted in blue.

![image](https://user-images.githubusercontent.com/55543355/223296946-22c978ba-2d7f-4885-b53c-a0c4acccd828.png)

## NAT Policy

# Login to PA-440 machine. Under Policies => NAT at the bottom left, click "+ Add" to begin a new NAT Policy.

![image](https://user-images.githubusercontent.com/55543355/223483093-a36a2d99-080e-4c1a-8b49-7016d3452e28.png)

# Name the Policy

![image](https://user-images.githubusercontent.com/55543355/223483355-3a34a6da-c8f2-46dc-8774-b116711e07b4.png)

# Under "Original Packet", add the DMZ to "Source Zone" and Outside to "Destination Zone"

![image](https://user-images.githubusercontent.com/55543355/223483673-b1d52c5a-377b-4d04-a22e-47748a8d0860.png)

# Make sure your Interface is set to your Outside IP or Internet source Interface.

![image](https://user-images.githubusercontent.com/55543355/223484504-a8526ec5-d9e4-4a69-aa9a-c3c413c7c316.png)


