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
    











