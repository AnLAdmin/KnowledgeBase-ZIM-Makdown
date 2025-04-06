# Remote access
Created Sonntag 17 November 2024

Src, [Src](https://linuxcontainers.org/incus/docs/main/authentication/#adding-client-certificates-using-tokens)

Allow network access to Incus server
------------------------------------
Expose Incus servers API. This is also necessary for the [web client](../Installation/Stable/Clients/Web_management_interface.md).
``# incus config set core.https_address [<IP address>]:8443``
IP address	If you want to give access through a specific IP.

Configure port 8443 in firewall (Ubuntu: [UFW](../../UFW/Operation/Add_rule/for_local_access.md) or create an [UFW application profile](../../UFW/Operation/Add_new_app.md) ([Incus API](../../UFW/Configuration/Apllication_profiles.md#incus)) first).

Adding trusted certificates to the server for CLI
-------------------------------------------------
([Src](https://linuxcontainers.org/incus/docs/main/authentication/#authentication-add-certs))
This method already needs a client keypair. (See [here](#Software:Incus:Configuration:Remote access#adding-client-certificates-using-tokens-for-cli) as alternative)

[Enable](#Software:Incus:Configuration:Remote access#allow-network-access-to-incus-server) network access.

* ☐ Incus: Adding trusted certificates to the server from an existing keypair. ! @Todo

[Change](../Operation/Change_default_remote.md) the remote default to the newly added Incus server.

Adding client certificates using tokens for CLI
-----------------------------------------------
([Src,](https://linuxcontainers.org/incus/docs/main/howto/server_expose/#server-expose) [Src2](https://linuxcontainers.org/incus/docs/main/authentication/#adding-client-certificates-using-tokens))
This method creates a client keypair over the Incus client with a token as a setup passowrd. 

[Enable](#Software:Incus:Configuration:Remote access#allow-network-access-to-incus-server) network access.
First [register the client](../Operation/Add_trusted_client.md) on the Incus server as trusted. This will get you a **token** to use on the client to [add the Incus server](../Operation/Add_remote_server.md) as remote.
[Change](../Operation/Change_default_remote.md) the remote default to the newly added Incus server.

Configure ACME for TLS access to API and web interface
------------------------------------------------------

* ☐ Incus: Remote access - Configure ACME for TLS access to API and web interface @Todo !!


