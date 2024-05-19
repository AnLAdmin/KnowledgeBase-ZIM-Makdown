# Export
Created Mittwoch 02 September 2020

zimbra$ /opt/zimbra/bin/zmmailbox -z -t 0 -m "<account>" getRestURL -u "https:*<Mail service name>*" "//?fmt=tgz" > <export file>.tgz
account:		in the form of **<short name>@<domain>** (e.g. [name@domain.tld](mailto:name@domain.tld)). [List](./List.md) available accounts
mail service name:	Mail service FQDN or server name (e.g. mail.domain.tld)
export file:		File to export data to
Mail service name:	FQDN name to mail host

### Folder with spaces
([Orig](https://wiki.zimbra.com/wiki/Steps_to_export_a_folder_from_command_line_where_folder_name_contains_white_spaces))
zimbra$ zmmailbox -z -m [USERNAME@DOMAIN.COM](mailto:USERNAME@DOMAIN.COM) gru '//?fmt=tgz&query=in:"Communications Officer Recruitment"' > /tmp/test1.zip     
OR
zimbra$ zmmailbox -z -m [USERNAME@DOMAIN.COM](mailto:USERNAME@DOMAIN.COM) gru '//?fmt=tgz&query=under:"Communications Officer Recruitment"' > /tmp/test2.zip     

