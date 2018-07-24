Zybo Z7-20 DMA Audio Demo
==============

Introduction
--------------

This project demonstrates a way to use the Audio Codec, DDR memory, and 3.5mm Audio Jacks included on the Zybo Z7-20 in order to record and play audio. Three of the four user push buttons can be used to record a 5 second snippet of audio from the microphone input (MIC IN) and line input (LINE IN) jacks, or to play a recorded snippet back out over the headphone output (HPH OUT) jack. The USB-UART bridge attached to the microUSB port is used to display status messages. The table below shows the functions mapped to each of the push buttons.

| Button | Function            |
| ------ | ------------------- |
| BTN0   | N/A                 |
| BTN1   | Record from MIC IN  |
| BTN2   | Play on HPH OUT     |
| BTN3   | Record from LINE IN |

Using This Demo
--------------
Requirements:
* [Zybo Z7-20](https://store.digilentinc.com/zybo-z7-zynq-7000-arm-fpga-soc-development-board/)
* [Vivado+SDK 2018.2 Installation](https://reference.digilentinc.com/vivado/installing-vivado/start)
* [Tera Term Installation](https://ttssh2.osdn.jp/index.html.en) or other serial terminal application
* Audio Input Source (with 3.5mm plug)
* Audio Output Source (with 3.5mm plug)
* MicroUSB Cable
	
Release Usage:

1. Download and extract the most recent Zybo-Z7-20-DMA-<version>.zip archive from this repository's [releases page](https://github.com/artvvb/Zybo-Z7-20-DMA/releases).
2. Open project in Vivado 2018.2 (<archive extracted location>/vivado_proj/Zybo-Z7-20-DMA.xpr).
3. In the toolbar at the top of the Vivado window, select **File -> Export -> Export Hardware**.
4. Set "Export to" field to "<Local to Project>" and check "Include bitstream" box then click "OK".
5. In the toolbar at the top of the Vivado window, select **File -> Launch SDK**.
6. Set "Exported location" and "Workspace" fields to "<Local to Project>" then click "OK".

7. With SDK opened, wait for the hardware platform to be imported.
8. In the toolbar at the top of the SDK window, select **File -> New -> Application Project**.
9. Fill out fields as in the table below. Most of the listed values will be the defaults, but are placed in the table for completeness.
  
| Setting                                | Value                           |
| -------------------------------------- | ------------------------------- |
| Project name                           | Zybo-Z7-20-DMA                  |
| Use default location                   | checked box                     |
| OS Platform                            | standalone                      |
| Target Hardware: Hardware Platform     | system_wrapper_hw_platform_0    |
| Target Hardware: Processor             | ps7_cortexa9_0                  |
| Target Software: Language              | C                               |
| Target Software: Board Support Package | Create New (Zybo-Z7-20-DMA_bsp) |

10. Click "Next", then select "Empty Application" from the list of available templates. Then click "Finish".
11. Expand the new application project (named "Zybo-Z7-20-DMA") in the Project Explorer pane to the left of the SDK window.
12. Right click on the "src" subdirectory of the application project and select **Import**
13. In the "Select an import wizard" pane of the Import wizard, expand "General" and select "File System". Then click **Next**.
14. Fill out fields on the "File system" screen as in the table below. Most of the listed values will be the defaults, but are placed in the table for completeness.

| Setting                                               | Value                                   |
| ----------------------------------------------------- | --------------------------------------- |
| From directory                                        | <archive extracted location>/sdk_appsrc |
| Files to import pane: sdk_appsrc                      | checked box                             |
| Into folder                                           | Zybo-Z7-20-DMA/src                      |
| Options: Overwrite existing resources without warning | checked box                             |
| Options: Create top-level folder                      | unchecked box                           |

15. Click **Finish**.
<!--- Note for maintainers: This project does not require any additional application or bsp configuration. If this changes, please add the required steps to manually add them here. --->
16. Set the Zybo Z7-20's programming mode jumper (JP5) to "JTAG" and its power input select jumper (JP6) to "USB".
17. Plug the Zybo Z7-20 into the computer running SDK using a microUSB cable connected to the Zybo Z7's PROG/UART port (J12).
18. Plug in audio inputs and outputs to the 3.5mm headphone output (HPH OUT), line input (LINE IN), and microphone input (MIC IN) audio jacks.
19. Open a serial terminal application (such as TeraTerm FIXME LINK) and connect it to the Zybo Z7's serial port, using a baud rate of 115200. (FIXME more details here?)
20. In the toolbar at the top of the SDK window, select **Xilinx -> Program FPGA**. Leave all fields as their defaults and click "Program".
21. Right click on the "Zybo-Z7-20-DMA" application project in the Project Explorer pane, and select "Run As -> Launch on Hardware (System Debugger)".
22. Refer to the statements printed via the serial terminal application for instructions on how to use the demo.

<!--- FIXME Tera Term ... --->

For more information on how this project is version controlled refer to the [Digilent Vivado Scripts Repository](https://github.com/artvvb/digilent-vivado-scripts)
