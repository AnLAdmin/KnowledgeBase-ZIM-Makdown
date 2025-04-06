# Search application - sorted
Created Mittwoch 26 Februar 2025

``PS> $nameVar = winget search <Search text/App name> ; $namevar[4..($namevar.length)] | Sort-Object | Format-Table``

### Example
``PS> $nameVar = winget search git ; $namevar[4..($namevar.length)] | Sort-Object | Format-Table``

