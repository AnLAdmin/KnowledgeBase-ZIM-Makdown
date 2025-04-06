# Setup TLS for management web page (Webfig)
Created Sonntag 02 Februar 2025

Setup CA
========
Created Sonntag 02 Februar 2025

Webfig
------
### Create CA certificate
Go to System - Certificates.
Press ![](./Setup_TLS_for_management_web_page_(Webfig)/pasted_image.png).
In tab **General** set name **LocalCA** and Common Name to **LocalCA**.
In tab **Key Usage** set **key cert. sign** and **crl sign**.
Press **Apply**.
Press **Sign** to open signing dialog. 
Press **Start** to sign the CA certificate.
Close after **Progress** shows d**one**.
Close with OK.
### Create Webfig certificate
Press ![](./Setup_TLS_for_management_web_page_(Webfig)/pasted_image001.png).
In tab **General** set name **Webfig** and Common Name to **<Device FQDN>**.
In tab **Key Usage** leave default values.
Press **Apply**.
Press **Sign** to open signing dialog. 
Set **CA** to **LocalCA**.
Press **Start** to sign the CA certificate.
Close after **Progress** shows d**one**.
Close with OK.
### Set certificate to webfig services
Go to IP - Services.
Double click **www-ssl** service.
Change **Certificate** to above created certificate **Webfig**.
Press Enable.
Press OK.

Terminal
--------
Create the Webfig certificates with commands. 

Over SSH, Winbox: New Terminal or Webfig: Terminal open terminal.
Move to certificates
``[commander@ap] > /certificate``
### Create CA certificate
Create CA certificate.
``[commander@ap] > add name=LocalCA common-name=LocalCA key-usage=key-cert-sign,crl-sign``
Sign CA certificate.
``[commander@ap] > sign LocalCA``
### Create Webfig certificate
Create Webfig certificate.
``[commander@ap] > add name=Webfig common-name=<Device FQDN>``
Sign Webfig certificate.
``[commander@ap] > sign Webfig ca=LocalCA``
### Set certificate to webfig services
``[commander@ap] > ip service``
``[commander@ap] > set www-ssl certificate=Webfig disabled=no``

OPTIONALLY TLS for API access
-----------------------------
Also set the same certificate for the service api-ssl.
``[commander@ap] > ip service``
``[commander@ap] > set api-ssl certificate=Webfig``

