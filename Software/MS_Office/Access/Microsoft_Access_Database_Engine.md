# Microsoft Access Database Engine
Created Sonntag 10 November 2019

This contains a set of components that facilitate the transfer of data between existing Microsoft Office files such as Microsoft Office Access (*.mdb and *.accdb) files and Microsoft Office Excel (*.xls, *.xlsx, and *.xlsb) files to other data sources such as Microsoft SQL Server. Connectivity to existing text files is also supported. ODBC and OLEDB drivers are installed for application developers to use in developing their applications with connectivity to Office file formats.

The Access Database Engine 2016 Redistributable **is not intended**:

As a general replacement for Ace (If you need a general replacement for Ace you should use SQL Server Express Edition).
As a replacement for the Jet OLEDB Provider in server-side applications.
As a general word processing, spreadsheet or database management system -To be used as a way to create files. (You can use Microsoft Office or Office automation to create the files that Microsoft Office supports.)
To be used by a system service or server-side program where the code will run under a system account, or will deal with multiple users identities concurrently, or is highly reentrant and expects stateless behavior. Examples would include a program that is run from task scheduler when no user is logged in, or a program called from server-side web application such as ASP.NET, or a distributed component running under COM+ services.

Package
-------
Microsoft Access Database Engine 2010/16 Redistributable or Access Runtime 2013
Separate packages ar available for x86 and x64.

Installation
------------
Side by side installation of x64 and x86 is not possible, also not with the /passive switch anymore.

