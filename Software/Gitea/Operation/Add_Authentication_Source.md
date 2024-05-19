# Add Authentication Source
Created Samstag 17 Juli 2021

Login as administrator. Browse to Profile menu - Site Administration - Athentication Sources.
Click **Add Authentication Source**.

Settings for Nextcloud
----------------------
[Setup](file:///C:/Users/progy/Documents/ZIM/IT/Infrastructure/Software/Nextcloud/Configuration.txt) a OAuth2 client in Nextcloud.

Authentication Type:	OAuth2
Authentication Name:	Nextcloud_<Provider Name> -> E.g. Nextcloud_Hetzner
OAuth2 Provider:	Nextcloud
Client ID (Key):	Copy'n paste from Nextcloud **Settings -** **Administration - Sercurity - OAuth 2.0 clients ***Client Identifier *field
Client Secret:		Copy'n paste from Nextcloud **Settings -** **Administration - Sercurity - OAuth 2.0 clients ***Secret *field
Enable **Use Custom URLs instead of Default URLs**.
Replace <own-server> in the fields *Authorize URL*, *Token URL* and *Profile URL* with <Nextcloud URL> e.g. <Service name FQDN>

