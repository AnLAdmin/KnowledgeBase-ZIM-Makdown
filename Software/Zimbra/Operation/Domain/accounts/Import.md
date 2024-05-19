# Import
Created Mittwoch 02 September 2020

Command line
------------
[Src](https://wiki.zimbra.com/wiki/Zmmailbox#Export.2Fimport_an_entire_account)

zimbra$ /opt/zimbra/bin/zmmailbox -z -m <account> -t 0 postRestURL -u "https:*<mail service name>*" *"*?fmt=tgz&resolve=reset" <export data>.tgz
account:		in the form of **<short name>@<domain>** (e.g. [name@domain.tld](mailto:name@domain.tld)). [List](./List.md) available accounts
mail service name:	Mail service FQDN or server name (e.g. mail.domain.tld)
export data:		File with exported mail data in a tgz file

