# **A COMPLETE GUIDE TO INSTALL OPEN-SOURCE EDA TOOLS:** 

The contents of this training includes the following contents:
## Section 1: Introduction:
 * Introduction to IC design components
## Section 2: Steps to install open-source EDA tools on Ubuntu:
 * Download oracle virtual box and Ubuntu
 * Configure virtual box to add Ubuntu ISO
 * Generic steps to start Ubuntu installation
 * Setup Ubuntu, launch terminal and install GIT
 * Clone vsdflow, learn chmod and install vim
 * Understand basic Unix commands and execute vsdflow
 * Observing cmake installation and lock/unlock screen
 * Observing Yosys, graywolf, qrouter, netgen magic, qflow installation
 * Observing openSTA and Opentimerinstallation with fast-forward edit
 * Test opensource EDA tool installation using vsdflow and spi_slave design
 * Debug qflow gui error, implement solution and test
## Section 3: Steps to install open-source EDA tools on CentOS:
 * Download oracle virtual box and CentOS7
 * Configure virtual box to mount and install CentOS 
 * Setup CentOS, launch terminal and install GIT and clone vsdflow
 * Understand basic CentOS commands for installation and execute vsdflow
 * Observing Yosys, graywolf, qrouter, netgen magic, qflow installation
 * Strategy and steps to debug error, if any
 * Debug graywolf errors and test opensource tool installation using vsdflow
## Section 4: Back-up videos for learning indivudual packages installation
 * How to install virtual box?
 * How to install ngSpice?
 * How to install MAGIC layout editor?
 * How to install Optimeter STA tool?
 * How to install eSim schematic editor?
 * How to install Yosys Synthesis tool?

## Section 1: Introduction:

### Introduction to IC design components:
 * This course mainly focuses on the basic tools needed to IC design and simulations.
 * The components available to perform RTL to GDSII flow (IC Design components) includes,
   * **Qflow -** Tool chain (like Yosys, Gray wolf, Qrouter) for the complete RTL to GDSII flow.
     * **Yosys open synthesis suite** - RTL netlist is converted to synthezised netlist (a netlist which is converted to gates which operates in the same way as the RTL netlist operates).
     * **Gray wolf**:
       * This is the tool which performs **floorplan, placement and Clock tree synthesis (CTS)**
       * **Floorplan** is the stage after synthesis. We do a planning, place the pre-placed cells, plan the power distribution, etc
       * **Placement** is the stage after floorplaning. We place the logical cells that we have got after the synthesis stage.
       * **Clock tree synthesis (CTS)** is the stage after placement. Here we route the clock in such a fashion that the skew is zero or almost equal to the estimated value by the designer.  
     * **Qrouter** - The next step is Routing after CTS, which routes all the components that is being placed in the placement stage.
   * **Opentimer:**
     * After each step in the flow Static Timing Analysis need to be performed to analyse the design at each and every step. (Open source high performance timing analysis tool)
   * **Magic - Layout viewer:** After each stage in the flow, if the layout is to be viewed then this is used. (VLSI layout editor, extraction and DRC tool)
   * **ngSpice:** This tool is used to analyse the pre and post simulations after a specific stage, which will indicate the effect of parasites on the design. (General purpose circuit simulation for non-linear and linear analyses)
   * **eSim:** A complex circuit analysis can be performed, SPICE simulation, analysis and PCB design.
   * **Virtual box:** Only for windows user, who wish to install Linux OS.

## Section 2: Steps to install open-source EDA tools on Ubuntu:

### Download oracle virtual box and Ubuntu:
  * Open Google browser and type as **Oracle virtualbox and then click on Downloads**.
    
![Screenshot 2023-07-04 122924](https://github.com/shubhagore/a_complete_guide_to_install_OpenSource_EDA_tools_SG/assets/135098553/f89b92bf-3dc7-4944-bbbe-fef563440d7a)

  * Next click on **Windows host** and then **save the particular file** and then place the downloaded **exe** in the disk where you have got enough space to install the tool.

![windows_host](https://github.com/shubhagore/a_complete_guide_to_install_OpenSource_EDA_tools_SG/assets/135098553/1eeddb66-d2ff-44f5-b593-f1eae336577e)

![saved_in_disk_with_more_space](https://github.com/shubhagore/a_complete_guide_to_install_OpenSource_EDA_tools_SG/assets/135098553/52dc02df-7469-439a-8b31-02c4a8f3c631)

  * Start installing the oracle virtual box keeping everyting as default.

![oracle_VM_installation](https://github.com/shubhagore/a_complete_guide_to_install_OpenSource_EDA_tools_SG/assets/135098553/0bed507e-3be0-4a25-8a4b-372e8fe0fda6)

  * After installation the oracle VM looks as shown (will not contain vsdpdworkshop - this is my earlier saved session)

![oracle_VM](https://github.com/shubhagore/a_complete_guide_to_install_OpenSource_EDA_tools_SG/assets/135098553/7f01f28d-0a28-48d9-8ff6-63c6d0c48e70)

  * Next step is to download Ubuntu on the Virtual machine, type **Linux Ubuntu ISO** in chrome and the click on **Download Ubuntu desktop**.

![ubuntu_download](https://github.com/shubhagore/a_complete_guide_to_install_OpenSource_EDA_tools_SG/assets/135098553/5f25d338-c76b-44ca-aabd-830516cf31bb)

  * Download any ubuntu image place the downloaded file in the disk where you have got enough space to install the tool.

![ubuntu_download_img](https://github.com/shubhagore/a_complete_guide_to_install_OpenSource_EDA_tools_SG/assets/135098553/e2f234d6-b475-4241-9cb8-8d384a4b9a0c)

### Configure virtual box to add Ubuntu ISO:

* After the ubuntu file is been downloaded place it in a disk which has more space.
* Click on the properties of **This PC** and notice number of RAM your system have and the type of system, if it is 32 bit or 64 bit.
* Open VM and click on **new**.

![ubuntu_VM](https://github.com/shubhagore/a_complete_guide_to_install_OpenSource_EDA_tools_SG/assets/135098553/aa257461-f6dd-40bb-bd09-6e9c2d393ef9)

* Enter the name of the virtual machine, path of the folder (normally the disk with more space), select the type of OS to be **Linux** and finally select **Ubuntu 64-bit**.

![ubuntu_VM1](https://github.com/shubhagore/a_complete_guide_to_install_OpenSource_EDA_tools_SG/assets/135098553/4caf9f1f-b4cb-4c5f-a6b0-450469e8b214)

* **Base memory** must be atleast 3GB in size. If the RAM in your system is 4GB the keep the base memory to be 3GB, else the system will get slower. (In the course the RAM was 16GB, thus for the base memory it was choosen 8GB)

![ubuntu_VM2](https://github.com/shubhagore/a_complete_guide_to_install_OpenSource_EDA_tools_SG/assets/135098553/f85a1456-f678-4bc4-ac49-89118a5f9411)

![ubuntu_VM3](https://github.com/shubhagore/a_complete_guide_to_install_OpenSource_EDA_tools_SG/assets/135098553/65867414-4f2d-489d-b29e-99b9da8b7aa2)

* A step may appear which will ask for the size of virtual machine to be allocated. Allocate atleast 40GB of memory out of 2TB of memory of the drive of what we have.
* The virtual machine has been installed by the given name.
  
![ubuntu_VM4](https://github.com/shubhagore/a_complete_guide_to_install_OpenSource_EDA_tools_SG/assets/135098553/2cafca65-e0eb-4b0a-aae5-292919354b5a)

* Under storage we have a option as **Optical drive which is empty**. Here we will have to select the ubuntu version of what we have downloaded. So that that version of ubuntu will be present in the Virtual machine  

![ubuntu_VM5](https://github.com/shubhagore/a_complete_guide_to_install_OpenSource_EDA_tools_SG/assets/135098553/c322bd09-a2c2-4d9f-bfdf-6ec7e709d49f)

![ubuntu_VM6](https://github.com/shubhagore/a_complete_guide_to_install_OpenSource_EDA_tools_SG/assets/135098553/1710e3a3-d035-4a90-b1e3-296fe5e28ed1)

![ubuntu_VM7](https://github.com/shubhagore/a_complete_guide_to_install_OpenSource_EDA_tools_SG/assets/135098553/149ef6eb-5e77-44f2-9f7a-3ff1bb941c78)

* Click on **Start**









