## PCIE Endpoint
1. Apply steps from Videorecorder SDK customization

2. Configure SDK according to your needs (i.e. IP, rootfs, sd card, etc.)

3. Configure PCIE Endpoint mode in Video Recorder & Multiplexer submenu

Exemplary Endpoint config file available at bsp/mach/bspconfig.pcie_endpoint

4. Disable PCI support in kernel.
Kernel configuration ->
    Bus support -> 
	[ ] PCI support

5. Enable TI81XX PCIe Endpoint Driver as a module <M> in kernel
Kernel configuration -> 
    Device Drivers ->
	Character devices ->
	    <M> TI81XX PCIe Endpoint Driver6. Build SDK

6. Build SDK
make

7. Run bootloader and kernel

8. Type lsmod command on the console (UART or ssh) in order to check if modules: 
ti81xx_edma and ti81xx_pcie_epdrv are successfully loaded.

/ # lsmod
Module                  Size  Used by
cmemk                  20323  0 
syslink              1132471  0 
vpss                   75481  4 ti81xxvin,ti81xxvo,ti81xxhdmi,ti81xxfb
ti81xxfb               21979  1 
ti81xxhdmi             16985  0 
ti81xxvo               21310  0 
ti81xxvin              20908  0 
gs2971                 13289  4 
ti81xx_edma             3453  0 
ti81xx_pcie_epdrv       5359  0 
ipv6                  209855 10

9.

## PCIE Root Complex
1. Apply steps from Videorecorder SDK customization

2. Configure SDK according to your needs (i.e. IP, rootfs, sd card, etc.)

3. Configure PCIE Root Complex mode in Video Recorder & Multiplexer submenu

Exemplary Endpoint config file available at bsp/mach/bspconfig.pcie_rootcomplex

4. Enable PCI support in kernel.
Kernel configuration ->
    Bus support -> 
	[*] PCI support
	[*] Message Signaled Interrupts (MSI and MSI-X) 

5. TI81XX PCIe Root Complex Driver is enabled automatically when Message Signaled Interrupt is enabled

6. Build SDK
make

7. Run bootloader and kernel

8. Type lsmod command on the console (UART or ssh) in order to check if modules: 
ti81xx_edma and ti81xx_pcie_rcdrv are successfully loaded.

~ # lsmod
Module                  Size  Used by
cmemk                  20319  0 
syslink              1132055  0 
vpss                   75481  4 ti81xxvin,ti81xxvo,ti81xxhdmi,ti81xxfb
ti81xxfb               21979  1 
ti81xxhdmi             16985  0 
ti81xxvo               21310  0 
ti81xxvin              20908  0 
gs2971                 13289  4 
ti81xx_edma             3453  0 
ti81xx_pcie_rcdrv       2421  0 
ipv6                  209855 12 

9.
