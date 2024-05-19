# Information
Created Donnerstag 18 März 2021

How does nging reload work without downtime
-------------------------------------------
How dos **nginx -s reload **garantie smallest downtime if any garantie?
The master process first checks the syntax validity, then tries to apply new configuration. If this succeeds, it starts new worker processes, and sends messages to old worker processes requesting them to shut down gracefully.
([Src](http://nginx.org/en/docs/control.html))

