# for local access
Created Freitag 04 Dezember 2020

Open a port to a local service:
# ufw allow <Port>/<Protocol>

Example
-------
Open http to a local proxy or web server.
# ufw allow 80/tcp

Open ntp port to local time server.
# ufw allow 123/udp

