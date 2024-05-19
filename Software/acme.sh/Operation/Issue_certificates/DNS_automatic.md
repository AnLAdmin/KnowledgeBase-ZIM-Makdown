# DNS automatic
Created Freitag 06 November 2020

Cloudflare
----------
[Src](https://github.com/acmesh-official/acme.sh/wiki/dnsapi)

### Variables
Domain:		Domain to issue a host certificate for
CF token:	Cloudflare zone permission specific token
CF account ID:	Cloudflare account ID
CF zone ID:	Cloudflare zone ID
FQDN:		Full qualified DNS name of the host the certificate is for

### Configure DNS hoster access
This is only necessary for the first domain.

#### Get API key for single zone with token
First you need to login to your [Cloudflare](https://dash.cloudflare.com/login) account to get your *API key*.
Browse to <Domain>. Copy **Zone ID**. Copy **Account ID**.
Click Get **your API token ** on the *Overview* page. Switch to page **API Tokens**.
If you not already have a token for the <Domain> click **Create Token**.
Click **Use template** for **Edit zone DNS**.
Set permsissions: Zone DNS Edit
Set **Zone Resources** to *Include specific zone *to* <Domain>.*
*C*lick **Continue to summary**. If OK click **Create Token**.
Follow the instruction to test the token. If OK copy the token.

#### Set access to DNS hoster
As *acme.sh* user or root:
$ export CF_Token="<CF token>"
$ export CF_Account_ID="<CF account ID>"
$ export CF_Zone_ID="<CF zone ID>"

### Issue certificate

#### Issue
As *acme.sh* (prefered) user or root:
$ su - acme.sh
$ acme.sh --issue -k 4096 --dns dns_cf -d "<FQDN>"

