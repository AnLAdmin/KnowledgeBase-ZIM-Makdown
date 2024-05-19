# Powershell
Created Donnerstag 26 Dezember 2019

Lists features on a desktop:
C:\> get-windowsoptionalfeature -online

List enabled features:
C:\> get-windowsoptionalfeature -online | ? State -eq Enabled | ft

Get detailed information about a feature:
C:\> get-windowsoptionalfeature -online -featurename <Name>

