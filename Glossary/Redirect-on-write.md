# Redirect-on-write
Created Freitag 10 Januar 2020

In the redirect-on-write method, whenever the original volume receives a change (write I/O request), the change is not applied to the original volume. Instead, the change is written to ([VSS](../Software/Windows/Services/Volume_Shadow_Copy.md): another volume's shadow copy storage area) free blocks.

