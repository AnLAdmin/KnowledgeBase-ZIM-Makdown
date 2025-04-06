# WSL 2
Created Sonntag 08 Dezember 2024

Install Virt-Viewer on WSL Ubuntu.
``$ sudo apt update && apt install virt-viewer -y``

Install an X server on windows like [MobaXterm](https://mobaxterm.mobatek.net/) (which contains Xming).

Configure the dispalay server to use. (Add to .bashrc)
``$ export DISPLAY="localhost:10.0"``

* ☐ [MobaXterm:](https://mobaxterm.mobatek.net/) Need to figure out how this works. Sometimes it does sometimes not.  @Todo

Start **MobaXterm** and wait until X server is started. Se symbol in the left corner ![](./WSL_2/pasted_image.png).

Start Virt-Viewer.
``$ virt-viewer <VM name>``

