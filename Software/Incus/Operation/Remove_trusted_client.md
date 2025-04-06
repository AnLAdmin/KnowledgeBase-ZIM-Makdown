# Remove trusted client
Created Sonntag 24 November 2024

[List](./List_trusted_client.md) available trusted clients to get a fingerprint.
Remove the remote client.
``$ incus config trust remove <Fingerprint>``

To finish the removal you also need to [remove the remote server](./Remove_remote_server.md) on the client.

### Example
``$ incus config trust remove b81c27981236``

