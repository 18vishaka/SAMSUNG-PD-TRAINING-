# SAMSUNG-PD-TRAINING-
This github repository summarizes the progress made throughout the training duration.

Quick links:
- [Day-0-Installation](#day-0-Installation)

- [Day-1-Introduction to Verilog RTL design and Synthesis](#Day-1--Introduction-to-Verilog-RTL-design-and-Synthesis)

- [Day-2-Timing libs, Hierarchical vs flat synthesis and efficient flop coding styles](#Day-2--Timing-libs,-Hierarchical-vs-flat-synthesis-and-efficient-flop-coding-styles)
  
- [Day-3-Combinational and Sequential optimisations](#Day-3--Combinational-and-Sequential-optimisations)
  
- [Day-4-GLS, Blocking vs Non Blocking Assignments and Synthesis-Simulation Mismatch](#Day-4--GLS,-Blocking-vs-Non-Blocking-Assignments-and-Synthesis--Simulation-Mismatch)
  
- [Day-5-Design For Testability (DFT)](#Day-5--Design-For-Testability-(DFT))
  
- [Day-6-Introduction to logic synthesis](#Day-6--Introduction-to-logic-synthesis)
  
- [Day-7-Basic SDC Constarints](#Day-7--Basic-SDC-Constarints)

- [Day-8-Advanced SDC Constraints](#Day-8--Advanced-SDC-Constraints)

- [Day-9-Optimizations in Synthesis](#Day-9--Optimizations-in-Synthesis)

- [Day-10-Quality Checks](#Day-10--Quality-Checks)

- [Day-11-Introduction to BabySoC](#Day-11--Introduction-to-BabySoc)

- [Day-12-BabySoC Modelling](#Day-12--BabySoC-Modelling)

- [Day-13-Post Synthesis Simulation](#Day-13--Post-Synthesis-Simulation)

- [Day-14-Synopsys DC and Timing Analysis](#Day-14--Synopsys-DC-and-Timing-Analysis)

- [Day-15-Inception of open-source EDA, openLANE and sky130PDK](#Day-15--Inception-of-open-source-EDA,-openLANE-and-sky130PDK)

- [Day-16-Good floorplan vs bad floorplan and introduction to library cells](#Day-16-Good-floorplan-vs-bad-floorplan-and-introduction-to-library-cells)

- [Day-17-Design library cell using Magic Layout and ngspice characterization](#Day-17-Design-library-cell-using-Magic-Layout-and-ngspice-characterization)

- [Day-18-Pre-layout timing analysis and importance of good clock tree](#Day-18-Pre-layout-timing-analysis-and-importance-of-good-clock-tree)

- [Day-19-Final steps for RTL2GDS using tritonRoute and openSTA](#Day-19-Final-steps-for-RTL2GDS-using-tritonRoute-and-openSTA)

- [Day-20-Floorplanning and Powerplanning Labs](#Day-20-Floorplanning-and-Powerplanning-Labs)

- [Day-21-Placement and CTS Labs](Placement-and-CTS-Labs)

- [Day-22-CTS analysis Labs](CTS-analysis-Labs)

- [Day-23-Clock Gating techniques](Clock-Gating-techniques)

- [Day-24-Timing violations and ECO](Timing-violations-and-ECO)

- [Day-26-Introduction to mixed signal flow](Introduction-to-mixed-signal-flow)

- [Day-27-Introduction to crosstalk - glitch and delta delay](Introduction-to-crosstalk---glitch-and-delta-delay)

- [Day-28-Introduction to DRC/LVS](Introduction-to-DRC/LVS)

- [Day-29- Low power design using opensource sky130](Low-power-design-using-opensource-sky130)

- [Day-30- TCL Programming](TCL-Programming)



## Day-0-Installation

	
<details>
<summary>dc_shell </summary>
<ul>
	<li>dc_shell (Design Compiler Shell) is a command-line-based EDA tool used for logic synthesis provided by Synopsys, Inc.</li>		
	<li>It is typically used through scripts written in languages like TCL (Tool Command Language). Designers create scripts to specify the synthesis process and provide input files, and then dc_shell executes these scripts to perform the synthesis.</li>
	<li>The tool can be invoked by using the command "dc_shell" in a UNIX shell.</li>
</ul>	
Here is the snapshot of successful launch of dc_shell:<br><br>
<img width="1085" alt="dc_shell" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day0/dc_shell.png">
</details>

<details>
<summary>icc2_shell</summary>
<ul>	
	<li>icc2_shell (Integrated Circuit Compiler 2 Shell) is a command-line-based EDA tool primarily used for the physical design stages of integrated circuits, which includes tasks like placement, routing, and physical verification; provided by Synopsys, Inc.</li>
	<li>It is typically used through scripts written in languages like TCL (Tool Command Language). Designers create scripts to specify the physical design flow, provide input files, and set various design constraints. The tool then executes these scripts to perform the physical design tasks.</li>  
	<li>The tool can be invoked by using the command "icc2_shell" in a UNIX shell.</li>
</ul>
Here is the snapshot of successful launch of icc2_shell:<br><br>    
<img width="1085" alt="icc2_shell" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day0/icc2_shell.png">
</details>

<details>
<summary>lc_shell</summary>
<ul>
	<li>lc_shell (Library Compiler Shell) is a command-line based EDA tool provided by Synopsys, Inc.</li>
	<li>The core of any ASIC design is the technology library containing a set oflogic cells. The library may contain functional description, timing, area andother pertinent information of each cell. Library Compiler (LC) parses thistextual information for completeness and correctness, before converting it toa format, used globally by all Synopsys applications.</li>
<li>The tool can be invoked by using the command "lc_shell" in a UNIX shell.</li>
</ul>
Here is the snapshot of successful launch of lc_shell:<br><br>   
<img width="1085" alt="lc_shell" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day0/lc_shell.png">
</details>

<details>
<summary>pt_shell</summary>
<ul>
	<li>pt_shell (Prime Time Shell) is a command-line based EDA tool provided by Synopsys, Inc.</li>
	<li>It is primarily used for static timing analysis.</li>	
	<li>It verifies the timing of a design by considering factors such as gate delays, interconnect delays, clock constraints, and setup/hold times and also calculates the best-case and worst-case timing paths in the design to ensure that all signals meet their timing requirements under various conditions.</li>
	<li>The tool can be invoked by using the command "pt_shell" in a UNIX shell.</li>	
</ul>
Here is the snapshot of successful launch of pt_shell:<br><br>  
<img width="1085" alt="pt_shell" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day0/pt_shell.png">
</details>

<details>
<summary>iverilog</summary>
<ul>
	<li>iverilog (Icarus verilog) is an open-source Verilog simulation and synthesis tool used for the development of digital circuits and systems.</li> 
	<li>One of the primary purposes of Icarus Verilog is to simulate digital designs. Designers can write Verilog code to describe the behavior of digital circuits, and Icarus Verilog can simulate the operation of these circuits over time, helping to verify their functionality.</li>
<li>The tool can be invoked by using the command "iverilog [options] [input_files]" in a UNIX shell.</li>
</ul>
Here is the snapshot of successful launch of iverilog:<br><br>
<img width="1085" alt="iverilog" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day0/iverilog.png">
</details>

<details>
<summary>gtkwave</summary>
<ul>
	<li>gtkwave is an open-source waveform viewer tool used primarily for analyzing and displaying simulation results from digital circuit simulations. It is a popular choice for visualizing and debugging digital designs described in hardware description languages (HDLs) such as Verilog or VHDL.</li>
	<li>It is primarily used as a waveform viewer. It allows you to load and display simulation waveforms, which represent signals' behavior over time during a digital simulation.</li>
<li>The tool can be invoked by using the command "gtkwave" in a UNIX shell.</li>
</ul>
Here is the snapshot of successful launch of gtkwave:<br><br>
<img width="1085" alt="gtkwave" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day0/gtkwave.png">
</details>

<details>
<summary>yosys</summary>
<ul>
	<li>yosys is an open-source framework for RTL (Register-Transfer Level) synthesis and formal verification of digital circuits. RTL synthesis is a crucial step in the design flow of digital integrated circuits, where high-level descriptions of a circuit (usually written in a hardware description language like Verilog or VHDL) are converted into gate-level representations that can be used for physical design and manufacturing. It provides a suite of tools and algorithms to perform this transformation efficiently.</li>
	<li>The tool can be invoked by using the command "yosys" in a UNIX shell.</li>
</ul>	
Here is the snapshot of successful launch of yosys:<br><br>
<img width="1085" alt="yosys" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day0/yosys.png">
</details>

<details>
<summary> Summary </summary>
	
Day 0 concludes with understanding of various essential tools and their invocation within a UNIX shell environment. 

</details>	

# Day-1-Introduction to Verilog RTL Design and Synthesis

 <details>
 <summary>Introduction to RTL-Design, Test-bench, Simulators</summary>
	 
 **RTL**: In digital circuit design, it is a design abstraction which models the flow of digital signals between hardware registers, and the logical operations performed on those signals. It is a critical step in the process of designing digital hardware. It bridges the gap between high-level functionality and the low-level gate-level implementation, allowing designers to express the desired behavior of a digital circuit in a human-readable and verifiable form.


Here is an example considering a 1 bit adder with carry:
(RTL code snippet and Gate level code snippet respectively)
<img width="1085" alt="Snippets" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day0/Snippets.png"><br><br>


 **Design** :  A design in Verilog is a digital circuit description that defines how various digital components are connected to achieve a specific functionality. It serves as a blueprint for creating digital systems, which can be tested and synthesized for hardware implementation.
<img width="1085" alt="design_concept" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day0/design_concept.png"><br><br>


**Testbench**: A setup to apply stimulus (test_vector) to the design to check its functionality. It is a separate piece of code written to simulate the behavior of the digital circuit or component you are designing or testing. It provides the necessary inputs and monitors the outputs of the design under test.
<img width="1085" alt="Testbench_1" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day0/Testbench_1.jpeg"><br><br>

**Simulator**: RTL design is checked for adherence to its design specification using simulation by giving simple inputs. The tool used for this purpose is called Simulator. The simulator looks at the input changes and then evaluates the output. It produces an output in the form of a .vcd file.  


NOTE:
<ul>
	<li>Design may have one or more primary inputs, one or more primary outputs.</li>
	<li>Testbench does'nt have primary inputs nor primary outputs.</li>
</ul>
</details>	

<details>
<summary>Lab-1: Introduction to using iverilog and gtkwave (Part-1)</summary>
(All the lab examples will be performed on the Linux operating system.)<br><br>

 **Iverilog**: Icarus Verilog (Iverilog) is a versatile tool for digital design engineers, enabling them to both simulate and, to some extent, synthesize digital circuits described in Verilog. It aids in the development and testing of digital hardware designs, ensuring their correctness and functionality before they are physically implemented.

 **Gtkwave**: GTKWave is a versatile waveform viewer used in digital design and simulation for visualizing and analyzing simulation results. It plays a crucial role in the debugging and verification of digital hardware designs by providing an intuitive and interactive representation of the signals' behavior over time.

**iverilog based simulation flow** :
<img width="1085" alt="iverilog_sim_flow" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day0/iverilog_sim_flow.png"><br><br>


**Steps involved**:

Step-1: Initially a directory named VLSI is created, inside this directory we cloned sky130RTLDesignAndSynthesisWorkshop repository; this repository consists of the required .lib files and verilog codes for practice.<br><br>
<img width="1085" alt="Intro_iverilog_gtk" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day0/Intro_iverilog_gtk.png"><br>
Here "my_lib" contains all the library files needed and it contains a folder "verilog_model" that contains all the standard cell verilog model which are present in the .lib. "verilog_files" is the folder which contains all the lab experiments, and also all verilog source files and testbench files are present here.


Step-2: Loading the design in iverilog (loading multiplexer into the simulator), we see that 'a.out' gets created. Then execute 'a.out', on execution it's going to dump a vcd file.<br><br>
<img width="1085" alt="iverilog_lab" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day0/iverilog_lab.png"><br>


Step-3: Loading this VCD file into gtkwave simulator.<br><br>
<img width="1085" alt="gtkwave_lab" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day0/gtkwave_lab.png"><br><br>
<img width="1085" alt="gtkwave_lab_1" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day0/gtkwave_lab_1.png"><br><br>

From the above waveforms it is clear that when the select line is 0 (sel=0) the output "y" follows input "i0" and when the select line is 1 (sel=1) the output "y" follows input "i1" which is the functionality of a mux.


This is how we load the design and check for its functionality.
</details>

<details>
<summary>Lab-2: Introduction to using iverilog and gtkwave (Part-2)</summary>
A look into what exactly is written inside a verilog design file and a testbench file.<br><br>
RTL design code of the 2:1 MUX:<br><br>
<img width="1085" alt="design" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day0/design.png"><br><br>
Testbench for 2:1 MUX:<br><br>
<img width="1085" alt="TestBench" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day0/TestBench.png"><br><br>
</details>

<details>
<summary>Introduction to Yosys</summary>

 **Synthesis**: Synthesis in VLSI is the process of converting your code (program) into a circuit. In terms of logic gates, synthesis is the process of translating an abstract design into a properly implemented chip. It is a process of converting a RTL code into a gate level netlist. The tool used for this purpose is called synthesizer.
<img width="1085" alt="Synthesizer_1" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day0/Synthesizer_1.png">
<img width="1085" alt="Synthesizer" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day0/Synthesizer.png"><br><br>
 

 **Yosys** : Yosys is a framework for RTL synthesis and more. It currently has extensive Verilog-2005 support and provides a basic set of synthesis algorithms for various application domains. Yosys is the core component of most our implementation and verification flows.

 Here is the yosys setup:
 <img width="1085" alt="yosys_setup" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day0/yosys_setup.png"><br><br>
 

**Verification of synthesized design** : In order to make sure that there are no errors in netlist we need to verify the netlist generated by synthesizer. This can be done by giving netlist and testbench to a simulator which in turn produces a .vcd file , then verifying the vcd file gtkwave. The output produced by this vcd file should be same as the one generated by the RTL design code.
<img width="1085" alt="synth_verification" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day0/synth_verification.png"><br><br>

**.lib** : It is a collection of logical modules, includes basic logic gates like and, or, not, etc.... and also includes different flavors of same gate.

**Faster Cells Vs Slower Cells** :
<ul>
	<li>Load in digital circuit is of Capacitence.</li>
	<li>Faster the charging or dicharging of capacitance, lesser is the celll delay. However, for a quick charge/ discharge of capacitor, we need transistors capable of sourcing more current i.e, we need WIDE TRANSISTORS.</li>
	<li>Wider transistors have lesser delay but consume more area and power. Narrow transistors are other way around. Faster cells come with a cost of area and power.</li>
</ul>

**Selection of the Cells** : We'll need to guide the Synthesizer to choose the flavour of cells that is optimum for implementation of logic circuit. Keeping in view of previous observations of faster vs slower cells,to avoid hold time violations, larger circuits, sluggish circuits, we offer guidance to synthesizer in the form of Constraints.
</details>

<details>
<summary>Lab-3: Introduction to using Yosys and sky 130 PDks (Part-1)</summary>
(An overview of this tool and the basic files required to perform the experiment on 2:1 MUX were explained.)<br><br>
 
 **Procedure** : 
 First we need to read the liberty file using the code
 **read_liberty -lib <path of the .lib>**
 
 Then we need read the RTL Design code
 **read_verilog <RTL_Design_file>**


 <img width="1085" alt="yosys_lab" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day0/yosys_lab.png"><br><br>



 After this we need to perform synthesis 
 **synth -top <instance_name>**

 <img width="1085" alt="yosys_lab_1" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day0/yosys_lab_1.png"><br><br>

 
 Then Generating netlist
 **abc -liberty <.lib path>**

 
<img width="1085" alt="yosys_lab_2" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day0/yosys_lab_2.png"><br><br>
 
This Netlist can be viewed in the synthesized circuit form using the **show** command    


<img width="1085" alt="yosys_lab_3" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day0/yosys_lab_3.png"><br><br>


The Nestlist code:
<img width="1085" alt="yosys_lab_4" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day0/yosys_lab_4.png">
<img width="1085" alt="yosys_lab_5" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day0/yosys_lab_5.png">

</details>
 
<details>
<summary> Summary </summary>
	
Day 1 concludes with understanding of iverilog, gtkwave and yosys tools and their working with an example of mux. 

</details>


## Day-2-Timing libs, Hierarchical vs flat synthesis and efficient flop coding styles

	
<details>
<summary>Introduction to timing .libs </summary><br>
 A look at how exactly a .lib file looks like and what it consists of:
 <img width="1085" alt="lib_intro" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day2/lib_intro.png">


 library ("sky130_fd_sc_hd__tt_025C_1v80") gives the name of the liberty file being used. "sky130_fd_sc_hd__tt_025C_1v80" is a  130nm technology library file where 'tt' stands for typical library; '025C' is the temperature value and '1v80' is the voltage value  of this libarary file.
<ul>		
	<li>Typically a library file consists of cell timing information, library variations, operating conditions, timing models, constraints and timing arcs.</li>
	<li>These liberty files are crucial in the design flow to ensure that the designed integrated circuits meet their timing requirements and can operate reliably under various conditions.</li>
	
</ul>

**Operating Conditions:**
.lib files often include data for different operating conditions, such as variations in voltage and temperature (PVT corners). This data helps designers assess how the library cells will perform under different conditions, considering the Process Voltage Temperature (PVT) variations 


**Proccess Voltage Temperature (PVT):**
<ul>
	<li>Process Variation: This aspect of PVT deals with the inherent variability that exists in the manufacturing process of semiconductor devices. In semiconductor fabrication, tiny variations can occur in things like the thickness of oxide layers, the doping levels of transistors, and other factors. These variations can lead to differences in the electrical characteristics of individual transistors and other components on a chip. Process variations can result in some transistors being faster or slower than others, consuming more or less power, and so on.</li>
	<li>Voltage Variation: Voltage variation refers to changes in the supply voltage that powers the IC. Variations in supply voltage can occur due to factors like power supply noise, voltage droops, or fluctuations. These voltage variations can impact the performance and power consumption of the IC. Chips are typically designed to operate within a specified voltage range, and deviations from this range can lead to functional errors or reduced performance.</li>
	<li>Temperature Variation: Temperature variation refers to changes in the operating temperature of the IC. Integrated circuits are sensitive to temperature, and their performance can vary with temperature changes. Higher temperatures can lead to increased leakage current and power consumption. Additionally, the speed of transistors can be affected by temperature; they may operate faster at lower temperatures and slower at higher temperatures.</li>
	<li>In summary, Process Voltage Temperature (PVT) variations are an essential aspect of VLSI design and manufacturing, encompassing the inherent variability in the manufacturing process, voltage supply fluctuations, and temperature changes that can affect the performance and reliability of integrated circuits.</li>
</ul>

**Know .lib well:**
<ul>
	<li>The technology("cmos") line is typically a command or directive that specifies the technology or process to be used for characterizing the library cells. 
	<img width="1085" alt="intro_lib_1" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day2/into_lib_1.png"></li><br><br>
 	<li>Specifying units of time and other physical parameters is crucial for accurately characterizing and describing the behavior of library cells. These units help ensure consistency and compatibility when designing integrated circuits.
	<img width="1085" alt="intro_lib_2" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day2/intro_lib_2.png"></li><br><br>
 	<li>There are going to be many cells in the library file, "cell" is the keyword that marks the beginning of cell definition, they contain different features of the particular cell; the cells that are described and characterized represent the fundamental building blocks used in designing digital integrated circuits. These cells serve various logical and sequential functions and are essential for constructing complex digital circuits.</li>
  	<li>let us consider a AND gate with two inputs:
	<img width="1085" alt="intro_lib_3" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day2/intro_lib_3.png"><br><br>
		For each gate cell based on the number of inputs(N), there will be 2^N combinations, and for each combination leakage power, area, delay, and all related parameters will be mentioned. For example, here the above AND gate is having two inputs, each of these two inputs potentially can take low or high any of the two values; that is 2 to the power 2 which is 4 possible input combinations that exists. For each of these 4 possible input combinations we need to know what is the delay, power and other related parameters; all of those information are present in each cell definitions.</li>
  	<li>The "area" parameter in a .lib file specifies the physical size or footprint of a library cell on the silicon wafer. It plays a crucial role in various stages of VLSI chip design. Accurate and well-characterized area values are essential for designing efficient and cost-effective integrated circuits.</li>


   Understanding many different variations of the same gate cells:
   <img width="1085" alt="lib_area" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day2/lib_area.png"><br>
   <ul>
	<li>"and2_0", "and2_2", "and2_4" are different flavors of the same AND cell.</li>
	<li>As we go from cell "and2_0" to "and2_4" the area increases from 6.256 to 8.7584, what we infer from this is that "and2_4" is larger cell than "and2_2" and from "and2_0". Larger cell meaning it is employing wider transistor.</li>
 	<li>Wider cells will be faster, area is more therefore power is more.</li>
  	<li>Smaller cells delay will be more, area is less hence the power.</li>
   	<li>Intermediate cells which are not wider nor small have intermediate characteristic.</li>
   </ul>
</details>

<details>
<summary>Hierarchical vs flat synthesis</summary>

	
 **Hierarchical Synthesis:**
Hierarchical synthesis in Verilog is a design practice that involves breaking down complex digital designs into modular blocks or modules and organizing them in a hierarchical structure. This approach offers advantages such as modularity, reusability, easier debugging, parallel development, and efficient synthesis. It is a common and recommended practice for designing large and complex digital systems.

**Flat Synthesis:**
Flat synthesis in Verilog involves describing an entire digital design within a single module, without any hierarchical organization or modular separation. While it may be suitable for simple designs, it is not recommended for complex projects, as it can lead to challenges in readability, reusability, and efficient resource utilization. Hierarchical synthesis is the more common and recommended approach for managing complex digital designs.

Consider a 1 bit full adder it can either be described using gates or by considering a half adder as a module too.
<img width="1085" alt="hier_vs_flat" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day2/hier_vs_flat.jpeg"><br><br>
<img width="1085" alt="hier_vs_flat_1" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day2/hier_vs_flat_1.jpeg"><br><br>


Consider a multimodule combinational circuit which consists of two sub_modules one that of a AND gate and other of a OR gate:
<img width="1085" alt="mul_module" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day2/mul_module.png"><br><br>

After performing synthesis using yosys it generates the following schematic:
<img width="1085" alt="mul_module_1" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day2/mul_module_1.png"><br><br>

The netlist code for hierarchical implementation of the multiple_modules

```ruby
module multiple_modules(a, b, c, y);
  input a;
  input b;
  input c;
  wire net1;
  output y;
  sub_module1 u1 (
    .a(a),
    .b(b),
    .y(net1)
  );
  sub_module2 u2 (
    .a(net1),
    .b(c), 
    .y(y)
  );
endmodule

module sub_module1(a, b, y);
  wire _0_;
  wire _1_;
  wire _2_;
  input a;
  input b;
  output y;
  sky130_fd_sc_hd__and2_0 _3_ (
    .A(_1_),
    .B(_0_),
    .X(_2_)
  );
  assign _1_ = b;
  assign _0_ = a;
  assign y = _2_;
endmodule

module sub_module2(a, b, y);
  wire _0_;
  wire _1_;
  wire _2_;
  input a;
  input b;
  output y;
  sky130_fd_sc_hd__or2_0 _3_ (
    .A(_1_),
    .B(_0_),
    .X(_2_)
  );
  assign _1_ = b;
  assign _0_ = a;
  assign y = _2_;
endmodule
```
In the netlist we can observe that separate modules namely sub_module1 sub_module2 are getting instanstiated not the gate cells.

**Flat synthesis** : In Flat synthesis the hierarchies the flattened  out and there is a single module in the netlist i.e the gates are instantiated directly instead of submodules. We apply flat synthesis on the same  design mentioned above. The command used to perform Flat synthesis from yosys are as follows

**read_liberty -lib <path of the .lib>**
 
 **read_verilog <RTL_Design_file>**

 **synth -top <instance_name>**

 **abc -liberty <.lib path>**
 
 **flatten**

**write_verilog -noattr <File_name>**

The synthesized circuit for a flattened netlist: (submodules u1 and u2 are flattened)
<img  width="1085" alt="flat" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day2/flat.png">

The netlist code of the flattened synthesis is as follows
```ruby
module multiple_modules(a, b, c, y);
  wire _0_;
  wire _1_;
  wire _2_;
  wire _3_;
  wire _4_;
  wire _5_;
  input a;
  input b;
  input c;
  wire net1;
  wire \u1.a ;
  wire \u1.b ;
  wire \u1.y ;
  wire \u2.a ;
  wire \u2.b ;
  wire \u2.y ;
  output y;
  sky130_fd_sc_hd__and2_0 _6_ (
    .A(_1_),
    .B(_0_),
    .X(_2_)
  );
  sky130_fd_sc_hd__or2_0 _7_ (
    .A(_4_),
    .B(_3_),
    .X(_5_)
  );
  assign _4_ = \u2.b ;
  assign _3_ = \u2.a ;
  assign \u2.y  = _5_;
  assign \u2.a  = net1;
  assign \u2.b  = c;
  assign y = \u2.y ;
  assign _1_ = \u1.b ;
  assign _0_ = \u1.a ;
  assign \u1.y  = _2_;
  assign \u1.a  = a;
  assign \u1.b  = b;
  assign net1 = \u1.y ;
endmodule
```
There is only a single module seen which consist of the gate level instantion of the two submodules .


Performing synthesis at the sub-module level is considered a best practice, especially for large and complex designs, as it simplifies the debugging process and enhances efficiency. This approach becomes particularly beneficial when dealing with multiple instances of the same module. Instead of synthesizing each instance separately, we can synthesize one and replicate it for others, effectively stitching them together. 


The synthesized circuit and netlist image of sub_module1 as an example of this approach:
<img  width="1085" alt="sub_module" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day2/sub_module.png">

</details>

<details>
	<summary>Flop coding styles</summary>
(Will be looking into how to code a flop, what are the different types of flops available, how to use them and what are the different coding styles possible.)<br><br>
	
 **Flip Flop:**
 A flip-flop is a fundamental building block in digital circuits and is used to store a single binary digit (either a 0 or a 1) of data. Flip-flops are used extensively in sequential logic circuits and play a critical role in the storage and transfer of data within a digital system.

 **D Flip Flop:**
A D flip-flop, also known as a Data or Delay flip-flop, is a fundamental building block in digital electronics and sequential logic circuits. It's a type of flip-flop that has a single data input (D), a clock input (CLK), and two outputs: Q and Q-bar (the complement of Q). The primary function of a D flip-flop is to store the value of its data input (D) and then transfer that stored value to its Q output on the rising or falling edge of the clock signal, depending on the specific type of D flip-flop used.

**Setup and Hold time:**
<ul>
	<li>Setup time: refers to the minimum amount of time that the data input (D) must be stable and valid before the active edge of the clock signal (usually the rising edge or falling edge) arrives for the flip-flop to reliably capture and store the data.
	<img  width="1085" alt="setup" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day2/setup.jpeg"></li>
	<li>Hold time: refers to the minimum amount of time that the data input (D) must be held stable and unchanged after the active edge of the clock signal (usually the rising edge or falling edge) has occurred for the flip-flop to reliably capture and store the data.
	<img  width="1085" alt="hold" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day2/hold.jpeg"></li>
</ul>

**What is an efficient coding style?**
Considering a scenario say, efficient coding style between using two adders and a 2:1 multiplexer (mux) or two 2:1 muxes and an adder depends on your specific requirements of th design, the target hardware platform, and optimization goals such as area, speed, or power consumption.
<img  width="1085" alt="eff_coding" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day2/eff_coding.jpeg">

It is wise to choose the circuit with two 2:1 mux and an adder as adde consumes more area. This provides us a basic insight towards efficient coding style.

**Why flip flops?**
<ul>
	<li>Flip-flops are fundamental components in digital circuit design because they enable the storage of information, sequential operation, synchronization, and control necessary for a wide range of digital applications. They are building blocks that form the basis of complex digital systems, from simple registers to advanced microprocessors.</li>
	<li>In the realm of combinational circuits, outputs respond to input changes with a delay known as propagation delay. When data propagates through various paths within a circuit, each characterized by distinct propagation delays, the possibility of generating undesirable signal anomalies known as "glitches", becomes a concern. A glitch is an abrupt, short-lived alteration in a signal's value, typically occurring when a logic level experiences multiple transitions in a brief timeframe. In scenarios involving multiple combinational circuits within a design, the likelihood of glitches occurring multiplies, jeopardizing the overall stability of the circuit's output. To address this challenge, flip-flops are introduced.</li>
</ul>

 **Asynchronous Reset D Flip Flop:**
Input is affected by an immediate reset signal, without waiting for the clock edge. When the asynchronous reset is active (usually low), the flip-flop's output is forced to a predefined state, often logic low, regardless of the clock signal. 

RTL Design code of positive edge trigerred asynchronous reset D Flop:
```ruby
 module dff_asyncres ( input clk ,  input async_reset , input d , output reg q );
	always @ (posedge clk , posedge async_reset)
	begin
		if(async_reset)
			q <= 1'b0;
		else	
			q <= d;
	end
endmodule
```

Simulation:

<img  width="1085" alt="async_re" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day2/async_re.png">

Synthesized circuit:

<img  width="1085" alt="asyn_re_sy" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day2/asyn_re_sy.png">

**Asynchronous Set D Flip Flop**

The D (data) input is affected by an immediate set signal, without waiting for the clock edge. When the asynchronous set is active (usually low), the flip-flop's output is forced to a predefined state, often logic high, regardless of the clock signal. 

RTL Design code of positive edge trigerred asynchronous set D Flop:
```ruby
module dff_async_set ( input clk ,  input async_set , input d , output reg q );
	always @ (posedge clk , posedge async_set)
	begin
		if(async_set)
			q <= 1'b1;
		else
			q <= d;
	end
endmodule
```
Simulation:

<img  width="1085" alt="asyn_set" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day2/asyn_set.png">

Synthesized circuit:

<img  width="1085" alt="asyn_set_sy" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day2/asyn_set_sy.png">

**Synchronous Reset D Flip Flop**

The D (data) input is affected by the reset signal, but the reset action only occurs at the clock edge (either rising or falling edge), ensuring synchronized and predictable behavior.

RTL Design code of positive edge trigerred synchronous reset D Flop:
```ruby
module dff_syncres ( input clk , input async_reset , input sync_reset , input d , output reg q );
	always @ (posedge clk )
	begin
		if (sync_reset)
			q <= 1'b0;
		else	
			q <= d;
	end
endmodule

```
Simulation:

<img  width="1085" alt="syn_re" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day2/syn_re.png">

Synthesized circuit:

<img  width="1085" alt="syn_re_sy" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day2/syn_re_sy.png">

</details>

<details>
	<summary>Interesting optimisations</summary>
	In various scenarios, additional hardware components are unnecessary for circuit implementation. For instance, when multiplying a 3-bit number by 2, there's no need for extra hardware; we can achieve this simply by connecting certain bits to the output and grounding the least significant bit (LSB). This practical approach has been successfully implemented using tools like Yosys:

```ruby
module mul2 (input [2:0] a, output [3:0] y);
	assign y = a * 2;
endmodule
```
When dealing with multiplication by powers of 2, the operation essentially involves shifting, as illustrated in the image below:
<img  width="1085" alt="mul_2" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day2/mul_2.jpeg">
<img  width="1085" alt="mul_2_" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day2/mul_2_.jpeg"><br><br>
Synthesized circuit:
<img  width="1085" alt="mul_2_sy" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day2/mul_2_sy.png"><br><br>
Netlist:
<img  width="1085" alt="mul_2_net" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day2/mul_2_net.png"><br><br>

The next special case involves multiplying a 3-bit number by 9, resulting in the pattern shown in the image below:
<img  width="1085" alt="mul_9" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day2/mul_9.jpeg"><br><br>
<img  width="1085" alt="mul_9_" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day2/mul_9_.jpeg"><br><br>
The  RTL  Design code:

```ruby
module mul8 (input [2:0] a, output [5:0] y);
	assign y = a * 9;
endmodule
```

The synthesized circuit:

<img  width="1085" alt="mul_9_sy" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day2/mul_9_sy.png"><br><br>

Netlist:

<img  width="1085" alt="mul_9_net" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day2/mul_9_net.png">
  
</details>

<details>
<summary> Summary </summary>
	
Day 2 concludes with understanding of timing libs, hierarchical vs flat synthesis and efficient coding styles.
</details>

# Day-3-Combinational and sequential optimisations
<details>
	<summary>Introduction</summary>
	
	
 **Optimisation Methodology:**
 <ul>
	<li>The synthesis tool performs optimisation by minimizing cost functions- one for design rule costs and the other for optimisation costs.</li> 
	 <li>The cost functions come in various flavors depending on the EDA tool vendor.</li>
  	<li>Since synthesis results are dependent to a large extent on several factors such as constraints, libraries and coding styles, optimisation of a design is an iterative process.</li>
   <li>The optimisation cost function consists of your parts in the following order of importance:
   <ul><li>Max delay cost</li>
 <li>Min delay cost</li>
 <li>Max power cost</li>
 <li>max area cost</li></ul></li>
		 
 </ul>


**Basic Identities of boolean algebra:**<br>
Here's a table of basic identities of Boolean algebra-

| Identity Name              | AND Form                 | OR Form                |
| -------------------------- | ------------------------ | ----------------------- |
| Identity Law            | A · 1 = A                | A + 0 = A               |
| Domination Law          | A · 1 = A                | A + 1 = 1               |
| Idempotent Law          | A · A = A                | A + A = A               |
| Complement Law          | A + A' = 1               | A · A' = 0              |
| Double Negation Law     | A = A''                  | A = A''                 |
| Commutative Law         | A · B = B · A            | A + B = B + A           |
| Associative Law         | (A · B) · C = A · (B · C) | (A + B) + C = A + (B + C)|
| Distributive Law        | A + (B · C) = (A + B) · (A + C) | A · (B + C) = (A · B) + (A · C) |
| Absorption Law          | A . (A + B) = A          | A + (A . B) = A         |
| De Morgan's Law         | (A . B)' = A' + B'       | (A + B)' = A' . B'      |
| Consensus Theorem       | (A + B) · (A' + C) · (B + C) = (A + B) · (A' + C) | (A · B) + (A' · C) + (B · C) = (A · B) + (A' · C) |

These identities are fundamental in Boolean algebra and are used for simplifying and manipulating logical expressions. The "AND Form" represents how the identity looks in terms of multiplication (logical AND), and the "OR Form" represents how it looks in terms of addition (logical OR).


**Combinational Optimisation:**
Combinational optimization deals with optimizing the combinational logic portion of a digital circuit. Combinational logic is a type of logic where the output depends only on the current input values, without any consideration for past input values or internal state.
Techniques used for combinational logic optimisation:
<ul>
	<li>Constant Propagation
	<ul>
		<li>Direct optimisation
		<img  width="1085" alt="combi_1" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day3/combi_1.jpeg"><br><br></li>
	</ul></li>
	<li>Boolean Logic Optimisation
	<ul>
		<li>K-map</li>
		<li>Quine Mckluskey
		<img  width="1085" alt="combi_2" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day3/combi_2.jpeg"><br><br>
		<img  width="1085" alt="combi_3" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day3/combi_3.jpeg"><br><br>
		<img  width="1085" alt="combi_4" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day3/combi_4.jpeg"><br><br></li>
	</ul></li>
</ul>

**Sequential Optimization:**
Sequential optimization focuses on optimizing the sequential logic portion of a digital circuit. Sequential logic includes elements like flip-flops, registers, and state machines, where the output depends not only on the current inputs but also on the previous state of the circuit.
Techniques used for sequential logic optimisation:
<ul>
	<li>Sequential constant propagation</li>
	<li>State optimisation</li>
	<li>Retiming</li>
	<li>Sequential Logic Cloning (Floor Plan aware synthesis)</li>
</ul>
</details>

<details>
<summary>Combinational Logic Optimisation Lab</summary>

 
The command to do optimizations is opt_clean -purge, which is executed after synth -top command.

**Example-1:**

The behavioral code: 
```ruby
module opt_check (input a , input b , output y);
	assign y = a?b:0;
endmodule
```

The synthesized circuit:
<img  width="1085" alt="const_prop" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day3/const_prop.png"><br><br>

**Example-2:**

The behavioral code:
```ruby
module opt_check2 (input a , input b , output y);
	assign y = a?1:b;
endmodule
```

The synthesized circuit:
<img  width="1085" alt="const_prop_1" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day3/const_prop_1.png"><br><br>

**Example-3:**

The behavioral code:
```ruby
module opt_check3 (input a , input b, input c , output y);
	assign y = a?(c?b:0):0;
endmodule
```

The synthesized circuit:
<img  width="1085" alt="lab_1" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day3/lab_1.png"><br><br>


**Example-4:**

The behavioral code:
```ruby
module opt_check4 (input a , input b , input c , output y);
	assign y = a?(b?(a & c ):c):(!c);
endmodule
```

The synthesized circuit:
<img  width="1085" alt="lab_2" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day3/lab_2.png"><br><br>

**Example-5:**

The behavioral code:
```ruby
module sub_module1(input a , input b , output y);
	assign y = a & b;
endmodule


module sub_module2(input a , input b , output y);
	assign y = a^b;
endmodule


module multiple_module_opt(input a , input b , input c , input d , output y);
wire n1,n2,n3;

sub_module1 U1 (.a(a) , .b(1'b1) , .y(n1));
sub_module2 U2 (.a(n1), .b(1'b0) , .y(n2));
sub_module2 U3 (.a(b), .b(d) , .y(n3));

assign y = c | (b & n1); 


endmodule
```

The synthesized circuit:
<img  width="1085" alt="lab_3" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day3/lab_3.png"><br><br>

The netlist code:
```ruby
module multiple_module_opt(a, b, c, d, y);
  wire _0_;
  wire _1_;
  wire _2_;
  wire _3_;
  wire _4_;
  wire _5_;
  wire _6_;
  wire _7_;
  wire \U1.a ;
  wire \U1.b ;
  wire \U1.y ;
  input a;
  input b;
  input c;
  input d;
  wire n1;
  output y;
  sky130_fd_sc_hd__a21o_1 _8_ (
    .A1(_3_),
    .A2(_1_),
    .B1(_2_),
    .X(_4_)
  );
  sky130_fd_sc_hd__and2_0 _9_ (
    .A(_6_),
    .B(_5_),
    .X(_7_)
  );
  assign _3_ = n1;
  assign _1_ = b;
  assign _2_ = c;
  assign y = _4_;
  assign _6_ = \U1.b ;
  assign _5_ = \U1.a ;
  assign \U1.y  = _7_;
  assign \U1.a  = a;
  assign \U1.b  = 1'h1;
  assign n1 = \U1.y ;
endmodule
```

**Example-6:**

The behavioral code:
```ruby
module sub_module(input a , input b , output y);
 assign y = a & b;
endmodule



module multiple_module_opt2(input a , input b , input c , input d , output y);
wire n1,n2,n3;

sub_module U1 (.a(a) , .b(1'b0) , .y(n1));
sub_module U2 (.a(b), .b(c) , .y(n2));
sub_module U3 (.a(n2), .b(d) , .y(n3));
sub_module U4 (.a(n3), .b(n1) , .y(y));


endmodule
```

The synthesized circuit:
<img  width="1085" alt="lab_4" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day3/lab_4.png"><br><br>

The netlist code:
```ruby
module multiple_module_opt2(a, b, c, d, y);
  wire _00_;
  wire _01_;
  wire _02_;
  wire _03_;
  wire _04_;
  wire _05_;
  wire _06_;
  wire _07_;
  wire _08_;
  wire _09_;
  wire _10_;
  wire _11_;
  wire \U1.a ;
  wire \U1.b ;
  wire \U1.y ;
  wire \U2.a ;
  wire \U2.b ;
  wire \U2.y ;
  wire \U3.a ;
  wire \U3.b ;
  wire \U3.y ;
  wire \U4.a ;
  wire \U4.b ;
  wire \U4.y ;
  input a;
  input b;
  input c;
  input d;
  wire n1;
  wire n2;
  wire n3;
  output y;
  sky130_fd_sc_hd__and2_0 _12_ (
    .A(_01_),
    .B(_00_),
    .X(_02_)
  );
  sky130_fd_sc_hd__and2_0 _13_ (
    .A(_04_),
    .B(_03_),
    .X(_05_)
  );
  sky130_fd_sc_hd__and2_0 _14_ (
    .A(_07_),
    .B(_06_),
    .X(_08_)
  );
  sky130_fd_sc_hd__and2_0 _15_ (
    .A(_10_),
    .B(_09_),
    .X(_11_)
  );
  assign _10_ = \U4.b ;
  assign _09_ = \U4.a ;
  assign \U4.y  = _11_;
  assign \U4.a  = n3;
  assign \U4.b  = n1;
  assign y = \U4.y ;
  assign _07_ = \U3.b ;
  assign _06_ = \U3.a ;
  assign \U3.y  = _08_;
  assign \U3.a  = n2;
  assign \U3.b  = d;
  assign n3 = \U3.y ;
  assign _04_ = \U2.b ;
  assign _03_ = \U2.a ;
  assign \U2.y  = _05_;
  assign \U2.a  = b;
  assign \U2.b  = c;
  assign n2 = \U2.y ;
  assign _01_ = \U1.b ;
  assign _00_ = \U1.a ;
  assign \U1.y  = _02_;
  assign \U1.a  = a;
  assign \U1.b  = 1'h0;
  assign n1 = \U1.y ;
endmodule
```
</details>

<details>
	<summary>Sequential Logic Optimisation Lab</summary>

**Example-1:**

The behavioral code:
```ruby
module dff_const1(input clk, input reset, output reg q);
always @(posedge clk, posedge reset)
begin
	if(reset)
		q <= 1'b0;
	else
		q <= 1'b1;
end

endmodule
```
Simulation:
<img  width="1085" alt="lab_5" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day3/lab_5.png"><br><br>

The Synthesized Circuit:
<img  width="1085" alt="lab_6" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day3/lab_6.png"><br><br>


 **Example-2:**
 
The behavioral code:

```ruby
module dff_const2(input clk, input reset, output reg q);
always @(posedge clk, posedge reset)
begin
	if(reset)
		q <= 1'b1;
	else
		q <= 1'b1;
end

endmodule
```
Simulation:

<img  width="1085" alt="lab_7" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day3/lab_7.png"><br><br>

The Synthesized Circuit:

<img  width="1085" alt="lab_8" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day3/lab_8.png"><br><br>

**Example-3:**
 
The behavioral code:

```ruby
module dff_const3(input clk, input reset, output reg q);
reg q1;

always @(posedge clk, posedge reset)
begin
	if(reset)
	begin
		q <= 1'b1;
		q1 <= 1'b0;
	end
	else
	begin
		q1 <= 1'b1;
		q <= q1;
	end
end

endmodule
```
Simulation:

<img  width="1085" alt="lab_9" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day3/lab_9.png"><br><br>
This circuit employs two flip-flops with reset-set functionality. In this configuration, q1 outputs a low signal when the reset input is high. However, when the reset input transitions from high to low, q1's output goes high, but there is a slight delay due to the clock-to-q propagation. Therefore, there's a brief moment during this transition when q1 is low, and afterward, it consistently holds a high signal until the next clock edge. This behavior occurs because q1's state momentarily goes low during the transition but quickly returns to a high state after the delay, resulting in a one-clock-cycle dip in its output.

The Synthesized Circuit:

<img  width="1085" alt="lab_10" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day3/lab_10.png"><br><br>

 **Example-4:**
 
The behavioral code:

```ruby
module dff_const4(input clk, input reset, output reg q);
reg q1;

always @(posedge clk, posedge reset)
begin
	if(reset)
	begin
		q <= 1'b1;
		q1 <= 1'b1;
	end
	else
	begin
		q1 <= 1'b1;
		q <= q1;
	end
end

endmodule
```
Simulation:

<img  width="1085" alt="lab_11" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day3/lab_11.png"><br><br>
In this circuit, flip-flops are not necessary because the outputs q1 and q remain high regardless of the clock edge or the state of the reset condition.

The Synthesized Circuit:

<img  width="1085" alt="lab_12" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day3/lab_12.png"><br><br>

**Example-5:**
 
The behavioral code:

```ruby
module dff_const5(input clk, input reset, output reg q);
reg q1;

always @(posedge clk, posedge reset)
begin
	if(reset)
	begin
		q <= 1'b0;
		q1 <= 1'b0;
	end
	else
	begin
		q1 <= 1'b1;
		q <= q1;
	end
end

endmodule
```
Simulation:

<img  width="1085" alt="lab_13" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day3/lab_13.png"><br><br>
In this context, q serves as the primary output, while q1 acts as an intermediate output. This configuration resembles a synchronous reset condition. However, it's important to note that the output changes occur after an additional clock cycle due to the presence of two flip-flops in the circuit.

The Synthesized Circuit:

<img  width="1085" alt="lab_14" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day3/lab_14.png"><br><br>
</details>

<details>
	<summary>Sequential Optimisation for Unused Outputs</summary>
	Sequential circuits with unutilized outputs can be streamlined for better efficiency and resource utilization.
 

 **An example of 3-bit up counter:**
 
The Behavioral code:
```ruby
module counter_opt (input clk , input reset , output q);
reg [2:0] count;
assign q = count[0];

always @(posedge clk ,posedge reset)
begin
	if(reset)
		count <= 3'b000;
	else
		count <= count + 1;
end

endmodule
```

In the provided code, the output q is influenced by count[0], count[1], and count[2], but these inputs aren't utilized. The counter resets to 0 when the reset signal is high; otherwise, it increments. It's worth noting that the least significant bit (LSB) incrementation causes the output to toggle with each clock cycle, independently of other output states. To optimize this, we can replace the three flip-flops with a single toggle flip-flop, resulting in an output change on every clock cycle.
<img  width="1085" alt="seq_un" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day3/seq_un.jpeg"><br><br>

The synthesized circuit:
<img  width="1085" alt="seq_un1" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day3/seq_un1.png"><br><br>

**Another example:**

The behavioral code:
```ruby
module counter_opt (input clk , input reset , output q);
reg [2:0] count;
assign q = (count[2:0] == 3'b100);

always @(posedge clk ,posedge reset)
begin
	if(reset)
		count <= 3'b000;
	else
		count <= count + 1;
end

endmodule
```

Here, the q is being assigned to a 3 bit value 100, which can be obtained using NOR gate as follows:
<img  width="1085" alt="seq_un2" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day3/seq_un2.jpeg"><br><br>

In this scenario, all three flip-flops are necessary because the output consists of a 3-bit data, and each flip-flop retains a significant part of this data. The combinational logic defines the adder's behavior, ensuring that the counter increments with each clock cycle as required.

The synthesized circuit:
<img  width="1085" alt="seq_un3" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day3/seq_un3.png"><br><br>
</details>

<details>
	<summary>Summary</summary>
	Day 3 involves discussions of topics related to digital circuit optimization, Boolean algebra identities, and the difference between combinational and sequential logic, emphasizing efficient design and resource utilization.
</details>

## Day-4-GLS, Blocking vs Non Blocking Assignments and Synthesis-Simulation Mismatch

<details>
	<summary>Introduction</summary><br><br>

**Gate Level Simulation (GLS):**
 <ul>
	 <li>Mapping the appropriate technology parameters like delays and functionality from the library models, at hand to our synthesized netlist, we can simulate the netlist, just like our RTL code.</li>
	 <li>We  are just conducting zero delay simulations, as we are focusing on synthesis and simulation mismatch at pre-layout level.</li>
	 <li>Used in dynamic timing analysis as it is able to take in account various clocks and resets at the same time, and thus  give insight about the asynchronous performance which STA is not meant for.</li>
 </ul><br><br>

**Blocking Assignment:**
 
 Execution of blocking assignments can be viewed as a one-step process:
 	<ul>
	 	<li>Evaluate the RHS (Right Hand Side equation) and update the LHS (Left Hand Side Equation) of the blocking assignment without interruption from any other verilog statement.</li>
	 	<li>A blocking assignment "blocks" trailing assignments in the same always block from occuring until after the current assignment has been completed.</li>
   	</ul>
Example of Blocking assignment:
			
		 a=b+c;
The value of 'a' is set to the sum of 'b' and 'c', and the next line of code will not execute until this assignment is complete.<br><br>
 

**Non Blocking Assignment:**
 <ul>
	 <li>The non blocking operator is the same as the less than or equal to operator ("<=").</li>
		 <li>Non blocking assignments are only made to register data types and are therefore only permitted inside of procedural blocks, such as initial blocks and always blocks. Non blocking assignments are not permitted in continuous assignments.</li>
		 <li>The non blocking assignment does not block other verilog statements from being evaluated.</li>
		 <li>Execution of non blocking assignmnet can be viewed as a two step process:</li>
		 <ul>
			 <li>Evaluate the RHS of non blocking  statements at the beginning of the time step.</li>
			 <li>Update the LHS of non blocking statements at the end of the time step.</li>
 </ul><br><br>


**A simple Example to differentiate Blocking Assignments and Non Blocking Assignmnets:**

```ruby
always @ (posedge clock)
	begin
	   temp= b;
	   b= a;
	   a= temp;
	end
```

```ruby
always @ (posedge clock)
	begin
	   a<= b;
	   b<= a;
	end
```

**Stratified Event Queue:**
<img  width="1085" alt="stratified" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day4/stratified.jpeg">


**RTL Coding Guidelines:**
<ul>
	<li>Never mix blocking and non blocking assignments in the same always block.</li>
	<li>Never make assignments to the same variable from more than one always block.</li>
	<li>Assignment (always blocks)
	<ul>
		<li>Combinational (always @ *) --> blocking (=) assignment.</li>
		<li>Sequential (always @ posedge) --> non blocking (<=) assignment.</li>
		<li>Always separate sequential and combinational logic.</li>
	</ul></li>
</ul><br><br>

**Simulation Synthesis Mismatch:**

<ul>
<li>Incomplete sensitivity lists
	<ul>
		<li>The synthesis may ignore this, but the simulators will adhere to it.</li>
	</ul>
</li>
<li>Complete sensitivity list with mis-ordered assignments.</li>
<li>Timing delay; Placing delays on the left side of always block assignments does'nt accurately model either RTL or behavioral models.</li>
	
```ruby
always @ (in) begin
	#25 out 1= ~in;
	#40 out 2= ~in;
end
```
		
<li>The outputs will not be updated on every input change if changes happen more frequently than every 65 time units.</li>
<li>The port synthesis gate level model will simulate two inverters while the pre synthesis RTL code will miss multiple input transitions.</li>

</ul>
</details>

<details>
	<summary>Lab experiments</summary><br><br>

	
 **What is GLS?:**<br>
 Running the test bench with netlist as Design Under Test.

 **Why GLS?:**
 <ul>
	 <li>Verify the logic correctness of the design after synthesis</li>
	 <li>Ensuring the timing of the design is met; For this GLS needs to be run with delay annotation.</li>
	
 </ul>

 **GLS using iverilog:**
 <img  width="1085" alt="GLS_iverilog" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day4/GLS_iveriog.jpeg"><br><br>
Before performing GLS, we typically start with RTL simulation to verify the functionality of our design at an abstract level using tool like iverilog, then we compile our verilog code into an executable form for simulation. GLS mainly involves  with replacing the abstract RTL description of digital circuit with gate level description. We need Gate level netlist for our design, which contains information about the gates, flip flops and their interconnections. Then there is Testbench which is a separate verilog code that applies inputs to our gate level netlist and checks the outputs,and simulates how our design responds to different inputs.


**Synthesis Simulation Mismatch:**<br>
Synthesis  Simulation Mismatch also known as syn-sim mismatch refers to the differences between the behavior of a digital circuit as simulated during the RTL simulation and how it actually operates after it has been synthesized and implemented in  hardware. 

This mismatch can arise due to:
<ul>
	<li>Missing sensitivity list.</li>
	<li>Blocking vs Non blocking assignments.</li>
	<li>Non standard verilog coding.</li>
</ul><br>

  
**Missing sensitivity list:**

A simulator operates in response to evolving activity patterns. It generates updated outputs only when there are changes in the input. Let's take the example of a 2x1 multiplexer. In the first behavioral code, the primary focus is on the 'sel' input. When 'sel' undergoes a change, the simulator promptly recalculates the output, preserving either 'io' or 'i1' at that specific moment. This computed output remains constant until the next 'sel' change, regardless of any alterations in 'io' or 'i1.' Conversely, in the second behavioral code, the simulator continually monitors changes in all signals, including 'sel,' 'i0,' and 'i1.' It maintains a high degree of responsiveness by evaluating these signals for any modifications.

```ruby
module mux(input i0, input i1, input sel, output reg y);
always @ (sel)
begin
    if (Sel)
          y= i1;
    else
          y= i0;
end
endmodule
```


```ruby
module mux(input i0, input i1, input sel, output reg y);
always @ (*)
begin
   if (Sel)
         y= i1;
   else
         y= i0;
end
endmodule
```

**Caveats with blocking statements:**


In the following case below, the number of flip-flops simulated in the circuit varies due to flip-flop assignments. To address this issue, one can employ Non-Blocking Statements as a more effective alternative.

```ruby
module code (input clk, input reset, input d, output d, output reg q);
always @ (posedge clk, posedge reset)
begin
    if (reset)
    begin
         q0= 1'b0;
         q= 1'b0;
    end
    else
    begin
         q0= q0;
         q0= d;
    end
endmodule
```
Here our aim was to get shift registers i.e. two Flip flops and after synthesis we can see two Flip flops.

```ruby
module code (input clk, input reset, input d, output d, output reg q);
always @ (posedge clk, posedge reset)
begin
    if (reset)
    begin
         q0= 1'b0;
         q= 1'b0;
    end
    else
    begin
         q0= d;
         q0= q0;
    end
endmodule
```
After synthesis we see only one Flip flop. 

In the following cases below, the synthesis yields the same circuit as shown below, but the simulation gives different behaviour, which causes Synthesis-Simulation mismatch.
<img  width="1085" alt="syn_sim" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day4/syn_sim.png">

Case- 1:
```ruby
module code (input a, input b, input c, output reg y);
reg q0;
always @ (*)
begin
    y= q0&c;
    q0= a|b;
end
endmodule
```

Case- 2:
```ruby
module code (input a, input b, input c, output reg y);
reg q0;
always @ (*)
begin
    q0= a|b;
    y= q0&c;
end
endmodule
```

In the above two cases, case 1 and case 2 namely we see syn-sim mismatch issues. Because of these type of issues it becomes very importance to run the GLS on the netlist and match the expectations. It is very important to check the behavior of the circuit obtained and then match it with the respected outputs or the expectations which were seen in the simulations and see that there are no synthesis and simulation mismatches.

**Example- 1:**

A ternary operator, also known as the conditional operator, is a shorthand way to write simple conditional statements, it is called "ternary" because it takes three operands: a condition followed by two expressions. 

The syntax for the ternary operator is typically as follows:

		condition ? expression_if_true : expression_if_false

Behavioral code:

```ruby
module ternary_operator_mux (input i0 , input i1 , input sel , output y);
	assign y = sel?i1:i0;
endmodule
```

RTL simulated output:
<img  width="1085" alt="ter_op" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day4/ter_op.png"><br><br>

RTL synthesized circuit:
<img  width="1085" alt="syn_ter_op" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day4/syn_ter_op.png"><br><br>

GLS simulated output:<br>
The process of Gate-Level Simulation (GLS) involves the utilization of the RTL netlist, a testbench, and Verilog models, which are fed into the Icarus Verilog (iverilog) simulator. Subsequently, the simulator generates a VCD (Value Change Dump) file, which can be visualized and analyzed using a tool such as GTKWave.
<img  width="1085" alt="GLS_ter_op" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day4/GLS_ter_op.png"><br><br>

**Example-2:**

Behavioral code:

```ruby
module bad_mux (input i0 , input i1 , input sel , output reg y);
always @ (sel)
begin
    if(sel)
         y <= i1;
    else 
         y <= i0;
end
endmodule
```

RTL Simulated output:
<img  width="1085" alt="bad_mux" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day4/bad_mux.png"><br><br>

RTL Synthesized circuit:<br>
The circuit exhibits the characteristics of a dual-edge triggered flip-flop, despite its core functionality being that of a 2x1 multiplexer.
<img  width="1085" alt="syn_bad_mux" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day4/syn_bad_mux.png"><br><br>

GLS Simulated output:
<img  width="1085" alt="GLS_bad_mux" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day4/GLS_bad_mux.png"><br><br>

Synthesis Simulation Mismatch:<br>
In the RTL simulation we see it fails to capture the alterations in the input-output relationship following a select line edge, whereas the GLS simulation accurately portrays these changes in input-output correlation driven by the select line. We see the GLS varies from the RTL simulation from the arrow marks drawn. This situation signifies synthesis simulation mismatch, as evidenced by the discrepancies in the generated output between RTL and GLS.
<img  width="1085" alt="bad_mux_syn_sim" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day4/bad_mux_syn_sim.png"><br><br>

**Example- 3:**

Behavioral code:
```ruby
module blocking_caveat (input a , input b , input  c, output reg d); 
reg x;
always @ (*)
begin
	d = x & c;
	x = a | b;
end
endmodule
```

RTL Simulated output:<br>
<img  width="1085" alt="caveat" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day4/caveat.png"><br><br>


RTL Synthesized circuit:<br>
This circuit emulates the behavior of a flip-flop, although the synthesized circuit doesn't contain an actual flip-flop component.
<img  width="1085" alt="syn_caveat" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day4/syn_caveat.png"><br><br>


GLS Simulated output:<br>
<img  width="1085" alt="GLS_caveat" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day4/GLS_caveat.png"><br><br>


Synthesis Simulated Mismatch:<br>
In the output of the RTL simulation, even when 'a' or 'b' is low, the output turns high when 'c' is high. This behavior arises from the utilization of blocking statements. The previous value of 'a|b' is used in conjunction with 'c,' resulting in 'x' emulating the characteristics of a flip-flop. However, in the output of the GLS simulation, it's evident that the output relies solely on the current inputs, with no dependence on past values.
<img  width="1085" alt="caveat_syn_sim" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day4/caveat_syn_sim.png"><br><br>


</details>

<details>
	<summary>Summary</summary>
	Day 4, we explored various concepts related to digital circuit simulation, GLS, Blocking vs Non Blocking Assignments and synthesis-simulation mismatches.
</details>


## Day-5-Design for Testability (DFT)

<details>
	<summary>Summary</summary>
	Day 5 gives us a brief dive into the world of DFT (Design For Test). 
</details>

## Day-6-Introduction to logic synthesis

<details>
	<summary>Getting started with DC (Design Compiler)</summary>


 **Design Compiler (DC):**
 <ul>
	 <li>A synthesis EDA tool by Synopsys Inc.</li>
	 <li>Command to invoke textual interface "dc_shell"</li>
	 <li>Command to invoke GUI "design_vision"</li>
	 <li>Understands .db format.</li>
	 <li>Design information can be stored in .ddc format.</li>
	 <li>It is primarily used in the field of digital integrated circuit (IC) design for creating, optimizing, and verifying RTL (Register-Transfer Level) descriptions of digital designs.</li>
	 <li>Design Compiler provides scripting capabilities through languages like Tcl, allowing users to automate and customize various aspects of the synthesis flow.</li>
	 <li>Has interoperability with various backend tools from Synopsys.</li>
	 <li>Has the ability to perform DFT scan stitch.</li>
	 
 </ul><br><br>

**Common Terminologies Associated with DC:** <br><br>

<ul>
	<li>SDC (Synopsys Design Constraints):
   	<ul>
	   	<li>These are the design constraints which are supplied to DC to enable appropriate optimization suitable for achieving the best implementation.</li>
	   	<li>It is more like industrial standard and it is used across EDA (Electronic Design Automation) implementation tools.</li>
	   	<li>SDC is based on TCL.</li>
   	</ul></li>
<li>.lib:
   	Design library which contains the standard cells.
</li>
<li>.db:
   	Same as .lib but in a different format. DC understands libraries in .db format.
</li>
  <li>DDC(Design Data Center):
   	Synopsys proprietary format for storing the design information. DC can write out and read in DDC.
</li>
<li>Design:
   	RTL files which has the behavioral model of the design.</li>
  </ul>
<br><br>

 **DC Setup:**
 <img  width="1085" alt="dc_setup" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day6_1/dc_setup.jpeg">
A DC (Design Compiler) setup involves using Synopsys Design Compiler, a popular tool in the digital design and synthesis flow, to convert RTL (Register-Transfer Level) descriptions of a digital circuit into a gate-level netlist. This process includes specifying library files and SDC (Synopsys Design Constraints) constraints as inputs and obtaining outputs such as a Verilog netlist, DDC (Design Data Container), and synthesis reports.
The DC setup process typically involves the following steps:
<ul>
	<li>RTL Compilation: The RTL files are read and compiled by the DC tool, which performs logic synthesis to map the design to the target technology using the library files.</li>
	<li>Constraint Application: The SDC constraints are applied to guide the synthesis tool in optimizing the design for timing, power, and area.</li>
	<li>Synthesis: The synthesis tool generates the Verilog netlist and optimization reports based on the provided RTL, library, and constraint files.</li>
	<li>Output Generation: The Verilog netlist, DDC, and synthesis reports are the final outputs of the synthesis process and can be used for further stages in the design flow, such as place-and-route and verification.</li>
</ul>
<br><br>

 **Implementation flow of ASIC:**
 <img  width="1085" alt="ASIC" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day6_1/ASIC.jpeg">
 Below is an overview of the ASIC implementation flow, including the key stages:
<ul>
	<li>RTL (Register Transfer Level) Design:
		The design process begins with the creation of an RTL description of the digital circuit. This description defines the logical behavior and functionality of the ASIC.</li>
	<li>Synthesis:
		The RTL code is synthesized using tools like Synopsys Design Compiler or Cadence Genus. Synthesis maps the RTL description to the target technology library, converting it into a gate-level representation. The output is a gate-level netlist.</li>
	<li>Design for Test (DFT):
		DFT engineers introduce testability features into the design to ensure that the ASIC can be effectively tested during manufacturing and throughout its operational life. DFT techniques may include scan chains, built-in self-test (BIST) structures, and test access mechanisms (TAMs).</li>
	<li>Floorplanning:
		The floorplanning stage involves defining the physical layout of the ASIC on the silicon die. It includes decisions on where functional blocks, memory, and I/O pads will be placed. Floorplanning also considers power grid and clock distribution network planning.</li>
	<li>Clock Tree Synthesis (CTS):
		CTS is a critical step for ensuring proper clock distribution. Clock signals are balanced and distributed to all flip-flops, ensuring that setup and hold time constraints are met. Clock skew is minimized to maintain synchronous operation.</li>
	<li>Place and Route:
		During this stage, the physical locations of individual gates are determined and routing resources are allocated. Algorithms in place-and-route tools, like Cadence Innovus or Synopsys ICC, perform this task. The goal is to optimize for performance, power, and area while adhering to design constraints.</li>
	<li>Physical Verification:
		Physical verification checks are run to ensure that the design meets manufacturing rules and constraints. This includes checks for design rule compliance (DRC), electrical rule compliance (ERC), and other physical design checks.</li>
	<li>Timing Closure:
		Timing analysis is performed to ensure that the design meets its required performance targets, such as maximum clock frequency. This may involve iterative optimizations, including gate resizing and buffer insertion.</li>
	<li>Final Physical Design Database:
		Once the design has passed all verification and timing closure checks, the final physical design database is generated. This database contains all the layout information necessary for mask generation and fabrication.</li>
	<li>Mask Generation and Tapeout:
		The final physical design database is used to create the masks required for semiconductor fabrication. These masks define the exact patterns of transistors and interconnects on the silicon wafer.</li>
	<li>Fabrication (Foundry Process):
		The semiconductor foundry manufactures the ASIC based on the masks provided during tapeout. The fabricated wafers undergo various processing steps, including lithography, etching, and doping, to create the physical semiconductor devices.</li>
	<li>Packaging and Testing:
		After fabrication, the individual ASIC chips are packaged and tested. This includes functional testing to ensure the chips meet their specifications and are free of defects.</li>
	<li>Final Product Integration:
		The tested ASIC chips are integrated into the final product, whether it's a consumer electronic device, a network router, or any other application-specific product.</li>
</ul>
The ASIC implementation flow is a complex and iterative process that requires close collaboration among RTL designers, synthesis engineers, physical design teams, and foundry partners.
<br><br>

 **DC Synthesis Flow:**
 <img  width="1085" alt="synth_flow" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day6_1/synth_flow.jpeg"><br><br>
Here's a step-by-step explanation of the DC synthesis flow:
<ul>
	<li>Read Standard Cell or Technology Library (.lib):
		The first step is to read the technology library, often referred to as the ".lib" file. This library contains information about the standard cells available for use in the ASIC design, including their logical functions, timing characteristics, and power consumption. It serves as a foundation for the synthesis process, allowing DC to select the best cells to implement the design based on performance and area constraints.</li>
	<li>Read Design Files (Verilog, Design .lib):
		The RTL design description, usually written in a hardware description language like Verilog, is read into the DC tool. Additionally, the design library (sometimes called the "design .lib") is also provided. This library may contain user-specific cells or specialized components that are not part of the standard cell library.</li>
	<li>Read Design Constraints (SDC - Synopsys Design Constraints):
		SDC constraints are used to guide the synthesis process. Constraints include timing requirements, clock definitions, input/output specifications, and other design guidelines. These constraints are typically provided in an SDC file and ensure that the synthesized design meets the desired timing and functional goals.</li>
	<li>Link the Design:
		In this step, the design and library files are linked together. The tool matches the cells used in the design with the cells available in the library, considering the specified constraints. This process creates a design database that includes both the RTL and the library components.</li>
	<li>Synthesize the Design:
		The core of the synthesis flow is the actual synthesis step. The DC tool analyzes the RTL description, applies optimization techniques, and maps the logic to the standard cells in the library. It aims to optimize the design for area, speed, and power while adhering to the specified constraints. The output of this stage is a gate-level netlist that represents the synthesized design.</li>
	<li>Generate Reports and Analyze QOR (Quality of Results):
		After synthesis, various reports are generated to assess the quality of the synthesized design. These reports include information on area utilization, power consumption, and timing analysis results. The Quality of Results (QOR) is evaluated to ensure that the design meets its performance and area targets as specified in the constraints.</li>
	<li>Write Out Netlist:
		The final step involves writing out the gate-level netlist in a format that can be used for subsequent stages of the design flow, such as place-and-route or simulation. Common formats for the output netlist include Verilog or EDIF (Electronic Design Interchange Format).</li>
</ul>
Throughout the synthesis flow, design engineers may iterate and fine-tune the constraints and optimization settings to achieve the desired results.
    <br><br>
    
 **TCL (Tool Command Language):**
 <ul>
	 <li>A scripting language that was originally designed as a simple and embeddable scripting language for use in various software applications and tools.</li>
	 <li>A strongly typed language.</li>
	 <li>In the context of Synopsys Design Compiler (DC) and its shell environment, Tcl (Tool Command Language) is used as the scripting language for interacting with and controlling the DC tool.</li>
	 <li>Tcl scripts can be used to automate the entire synthesis flow within DC. This includes loading RTL designs, specifying constraints, running synthesis, performing optimizations, and generating reports.</li>
	 <li>Overall, Tcl plays a crucial role in scripting and automating tasks within the DC shell, making it a powerful tool for managing complex RTL synthesis and optimization processes.</li>
	 <li>Can handle huge designs with extreme complexity and provide very good QOR.</li>
 </ul> 
</details>

<details>
	<summary>Lab 1- Invoking DC basic setup</summary>

 DC_WORKSHOP directory contains two files lib and verilog_files; lib file contains the .db file and .lib file; verilog_files contain all the neccessary verilog files to conduct the lab experiments.
  <img  width="1085" alt="dc_shell_1" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day6_1/dc_shell_1.png"><br><br>
   <img  width="1085" alt="dc_shell_3" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day6_1/dc_shell_3.png"><br><br>

 .lib file we will be using "sky130_fd_sc_hd__tt_025C_1v80"
  <img  width="1085" alt="dc_shell_2" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day6_1/dc_shell_2.png"><br><br>

  Invoke dc shell as a textual interface by "dc_shell" command
  <img  width="1085" alt="dc_shell_4" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day6_1/dc_shell_4.png"><br><br>

  In DC the technology library is present in terms of target library and link library.
  These two libraries namely target library and link library are very important which will be used by the DC tool to run.
  <img  width="1085" alt="dc_shell_6" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day6_1/dc_shell_6.png">
  The verilog file used here "lab1_flop_with_en.v"
  <img  width="1085" alt="dc_shell_5" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day6_1/dc_shell_5.png"><br><br>
  Internally from DC memory it is loading some db's to infer the design they are "gtech.db" and "standard.sldb".
  We see a warning message saying **can't read link_library 'your_library_db'** the reason is that we have not yet linked the design or the proper technology lib.
 
 <img  width="1085" alt="dc_shell_7" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day6_1/dc_shell_7.png">
 <img  width="1085" alt="dc_shell_8" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day6_1/dc_shell_8.png">
  We see it is in gtech format while we need it in the sky130 library format.<br><br>

 <img  width="1085" alt="dc_shell_9" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day6_1/dc_shell_9.png">
  <img  width="1085" alt="dc_shell_10" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day6_1/dc_shell_10.png">
 We still see it is in gtech format, because the target library and link library are still pointing to 'your_library.db' which needs to be corrected:
 <img  width="1085" alt="dc_shell_11" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day6_1/dc_shell_11.png">
  <img  width="1085" alt="dc_shell_12" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day6_1/dc_shell_12.png">
  <img  width="1085" alt="dc_shell_13" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day6_1/dc_shell_13.png">
  We see that it is in sky130 lib format, which was the expected outcome.<br><br>

  In order to invoke Design vision, we need to write out ddc:
  <img  width="1085" alt="dc_shell_14" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day6_1/dc_shell_14.png"><br><br>
</details>

  <details>
	  <summary>Lab-2: Introduction to DDC gui with design vision</summary><br><br>
	  
  Launching Design vision:
  <img  width="1085" alt="dc_shell_15" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day6_1/dc_shell_15.png"><br><br>

The DDC (Design Database Container) seamlessly loads both the technology file and the current design without the need for explicit specifications. It stores all the relevant information in the tool's memory for the duration of the session. However, it's important to note that DDC is a proprietary format exclusive to Synopsys tools. One of its key advantages is the ability to consolidate all the loaded information within one tool and easily transfer it to another tool using a single command.
For instance, the 'read_ddc' command comprehensively imports data, including the '.db' file, without the need for explicit file references. Conversely, the 'read_verilog' command focuses solely on reading the Verilog file, as illustrated in the accompanying image. This clear distinction showcases the versatility and efficiency of utilizing DDC for managing design and technology data.
The schematic view of the scan flipflop:
<img  width="1085" alt="dc_shell_16" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day6_1/dc_shell_16.png"><br><br>

Clicking on this flip-flop allows for a closer examination of its detailed behavior. The ultimate behavior of the circuit is presented below, as depicted through the DDC GUI:
<img  width="1085" alt="dc_shell_17" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day6_1/dc_shell_17.png"><br><br>
  
</details>

<details>
	<summary>Lab-3: Synopsys dc setup</summary>
	
**.synopsys dc setup:**
To initiate the dc shell using csh and issue dc_shell commands, setting the 'target_library' and 'link_library' variables with each session load is essential. However, in a practical scenario, managing multiple .db files for a design can become cumbersome and error-prone if these variables are manually configured each time.

This challenge can be effectively addressed through the use of the '.synopsys_dc.setup' file. DC reads '.synopsys_dc.setup' files in the following order of priority:
1. Synopsys installation directory (applies to all user projects).
2. User home directory (applies to all projects for the specific user).
3. Current project directory.

The order of priority dictates that if the file exists in the user's home directory, it will be chosen, and the installed (default) file will be ignored. If not found in the user's home directory, the installed one will be selected. This setup file is an excellent tool for automating repetitive tasks, especially those related to tool configuration, such as 'target_library' and 'link_library' settings.

By creating a file with the name '.synopsys_dc.setup' and specifying the desired tasks within it, the tool will automatically retrieve and load these values into its memory. Achieving this can be done by following these steps:

```ruby
$ gvim .synopsys_dc.setup
$dc_shell
dc_shell> echo $target_library
```
<img  width="1085" alt="dc_shell_18" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day6_1/dc_shell_18.png">
</details>

<details>
	<summary>Lab-4: TCL (Tool Command Language)</summary>
	
**Basic commands in TCL:**

- Tcl is a typed language, meaning that correct spacing and proper parentheses usage are crucial.
- The wildcard symbol (*), on the other hand, is employed for handling larger datasets.
- The dollar sign ($) is employed to reference variables, not for assignment purposes.
  
**set:**
<ul>
	<li>It is used both for declaring and assigning variables.</li>
   <li>Example:
	   <ul>
		   
**set a 8** --> a=8


**set a \[expr $x+$y\]** --> x=x+y
     </ul>
   </li>
     
<li>Square brackets in TCL are employed for command nesting.</li>
     </ul><br><br>

     
  ```ruby
  if {condition} {
  statements if true
  } else {
  statements if false
  }
   ```
Conditions must always be enclosed within curly braces. The '$' sign is employed when referencing a variable's value, not when assigning it (use 'set' for assignment).
Example:
```ruby
if {$a < 1} {
echo "$a is less than 1"
}else {
echo "$a is greater than 1"
}
```
**echo:**
In Tcl, the 'echo' command is used for displaying output, similar to its use in Linux.<br><br>
     
 ```ruby
  while {condition} {
  statements
  }
 ```

Example:
```ruby
set i 0
while {$i < 10} {
  echo $i;
 incr i;
}
```
<br><br>

  ```ruby
  for {looping var} {condition} {looping var modification} {
  statements
  }
```

Example:	  
```ruby
  for {set i 0} {$i < 10} {incr i} {
  echo $i;
  }
```
<br><br>



foreach is a general tcl statement.
```ruby
  foreach var list {
  statements
  }
```
<br><br>	  

The following image illustrates the usage of the DC-specific command 'get_lib_cells.' In this image, 'cellnames' is enclosed within curly braces. It's important to note that in Tcl, a collection, such as 'cellnames,' is typically enclosed with curly braces, while a list is enclosed with square brackets.
<img  width="1085" alt="dc_shell_24" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day6_1/dc_shell_24.png"><br><br>


```tcl
foreach_in_collection var collection {
   statements
 }
```
foreach_in_collection is a dc specific command used for collections.

The provided image demonstrates the usage of the DC-specific command 'get_object_name.' When 'get_object_name' is not used, the shell typically produces a pointer-like output, such as '_sel3.' By using 'get_object_name,' you can obtain the actual names of library cells, which are then printed as follows:
<img  width="1085" alt="dc_shell_25" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day6_1/dc_shell_25.png"><br><br>


</details>

## Day-7-Basic SDC Constraints

<details>
	<summary>Introduction</summary>

 **Recap: Setup Time:**
 <img  width="1085" alt="re_su" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/prtactice_1%23day7/re_su.jpeg"><br><br>

 **Recap: Hold Time:**
 <img  width="1085" alt="re_ho" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/prtactice_1%23day7/re_ho.jpeg"><br><br>

**Basics of STA:**
<ul>
	<li>Static Timing Analysis, is a fundamental aspect of digital design, plays a crucial role in ensuring that digital circuits operate correctly and meet their timing requirements.</li>
	<li>It helps ensure that signals in a digital design meet setup time, hold time, and other timing constraints.</li>
	<li>STA does a complete and exhaustive point to point analysis of the design.</li>
	<li>It does'nt verify the functionalityof the design.</li>
</ul>
<img  width="1085" alt="sta_1" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/prtactice_1%23day7/sta_1.jpeg"><br><br>
<img  width="1085" alt="sta_2" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/prtactice_1%23day7/sta_2.jpeg"><br><br>

**Delays:**
<ul>
<li>Transition Delay:
Transition delay is the time taken for a signal to change from one logic state to another.
It is specific to a single gate or cell and depends on factors like load capacitance and driving signal strength.</li>
<li>Propagation Delay:
Propagation delay is the time for a signal change at the input of a gate or cell to propagate through it and appear at the output.
It includes intrinsic gate delay and net delays due to interconnections.</li>
<li>Cell/Gate Delay:
Cell or gate delay represents the delay introduced by a single logic gate or cell when processing input to produce an output.
It's provided in library files as part of technology characterization.</li>
<li>Net Delay:
Net delay accounts for the time taken for a signal to traverse interconnects, wires, and routing resources between gates or cells.
Net delay varies with interconnect length, topology, and electrical properties.</li>
<li>Process and Temperature Variation:
STA considers process variations that affect transistor characteristics and temperature variations impacting circuit behavior.
This ensures the design functions correctly under different conditions.</li>
 </ul>

**Timing Arcs:**
Timing arcs describe the timing characteristics of signal paths within a digital circuit.
They are critical for determining the arrival time, required time, and clock-to-q delays for signals as they propagate through gates and nets.
<ul>
	<li>Cell Arcs (or Gate Arcs):
Cell arcs describe the timing behavior of individual logic gates or cells.
Each cell in a technology library has associated cell arcs that specify how input transitions affect the output transition time and other timing parameters.</li>
	<li>Combinational Arcs:
		Combinational arcs describe the timing behavior of combinational logic paths.
These arcs focus on signal paths that involve only combinational logic gates, where the output depends solely on the current input values without any feedback.</li>
	<li>Sequential Arcs:
	Sequential arcs describe the timing behavior of sequential logic paths.
They consider signal paths that involve sequential elements like flip-flops, latches, and registers. These paths have clock-to-q delays, setup times, and hold times associated with them.</li>
	<li>Net Arcs:
		Net arcs describe the timing behavior of interconnects and nets.
They take into account the delay introduced as signals propagate through wires, routing resources, and the parasitic capacitance of the interconnects.</li>
</ul>

**Timing Paths:**
<ul>
	<li>Timing paths are a collection of paths each having a start point and end point.</li>
	<li>Valid timing paths based on valid start and end point are categorized intp four types
	<ul>
		<li>Input port to Output port (Not recommmended)</li>
		<li>Input port to Input of flop (IO timing path)</li>
		<li>Clock pin of a flop to Output port (IO timing path)</li>
		<li>Clock pin of launch flop to Input pin of capture flop (Reg 2 Reg)</li>
	</li>
	<li>Timing paths are sorted into groups based on clocks associated with endpoint of path.</li>
</ul>

  **More about Static Timing Analysis:**
  <ul>
	  <li>Each signal path in a digital circuit is subject to delay constraints, which encompass both a maximum delay (setup condition) and a minimum delay (hold condition).</li>
	  <li>The setup condition establishes the maximum permissible delay for the combinational circuit, while the hold condition defines the minimum combinational delay required for reliable operation.</li>
	  <li>The clock period is typically predetermined based on design requirements, and the clock-to-q delay as well as setup and hold times are specific to flip-flops. Therefore, the parameter that can be adjusted to meet timing requirements is the combinational delay.</li>
  </ul>

**Setup Time Equation (Tsu):**

The setup time (Tsu) represents the minimum amount of time before the active edge of the clock signal during which the input data must be stable to guarantee correct capture by a flip-flop.

Setup Time Equation: Tsu = Tck - Tcq - Tcomb

Tsu: Setup time.
Tck: Clock period (time between successive clock edges).
Tcq: Clock-to-Q delay of the flip-flop (time taken for the output to respond to a clock edge).
Tcomb: Combinational delay along the data path (time taken for the signal to propagate from input to flip-flop input).

**Hold Time Equation (Th):**

The hold time (Thold) represents the minimum amount of time after the active edge of the clock signal during which the input data must remain stable to guarantee correct capture by a flip-flop.

Hold Time Equation: Thold = Tcq + Th - Tcomb

Thold: Hold time.
Tcq: Clock-to-Q delay of the flip-flop (time taken for the output to respond to a clock edge).
Th: Hold time of the flip-flop (time data must remain stable after the clock edge).
Tcomb: Combinational delay along the data path (time taken for the signal to propagate from input to flip-flop input).

**Water Bucket Analogy:**

Consider two water taps with different flow rates. The tap with faster inflow fills a bucket more quickly than the one with slower inflow. In this analogy, the slower inflow results in greater delay, while the faster inflow leads to less delay. Therefore, delay is a function of inflow rate. In our context, the inflow of water corresponds to the inflow of current (input transition). Faster current sourcing (faster rise times) results in less delay, and vice versa.

Now, if we keep the inflow rates of the taps the same but vary the sizes of the buckets (e.g., 5 gallons and 25 gallons), the larger bucket takes more time to fill compared to the smaller one. This illustrates that delay is also influenced by the size of the container, which is analogous to load capacitance.

Hence, the delay of a logic gate is a function of both the input transition (inflow) and the output load (bucket size).

Let's consider two gates in a design that are physically far apart, resulting in a long net length between them. This extended net adds more capacitance, causing an increase in the delay of the first gate due to the load capacitance. High output load can occur not only due to long nets but also because of a large number of connected loads (high fanout). The cumulative capacitance of all these load pins adds up, resulting in high output capacitance at the gate and, consequently, increased delay.

**Input and Output external delay:**
The input ports of a digital design can also serve as the outputs of external registers, which may be clocked by the same or a different clock compared to the internal registers within the design. Likewise, the output ports of the design may be connected as the D inputs of other external registers. These external registers are subject to their own timing constraints and must meet their respective timing conditions.

To ensure that the entire design operates correctly, it's essential to consider these external registers as boundary components of the design. Meeting the timing requirements for these external registers is crucial. To achieve this, both the input logic (feeding into the design) and the output logic (driven by the design's outputs) must be optimized effectively to prevent any timing violations from occurring.

The input external delay and output external delay serve as two critical constraints that define the maximum allowable combinational design delay. These external delays are typically specified to restrict the combinational logic's operation within a specific time frame before signals enter or exit the external environment and use the clock period.

A common guideline for setting these constraints is the '30-70 rule,' which means that the internal delay (comprising combinational logic and setup time) is constrained to be no more than 30% of the clock period, while the external delay (related to signals entering or exiting the design) is constrained to be at least 70% of the clock period. Adhering to these constraints helps ensure that the design operates reliably and within the required timing boundaries.
 <img  width="1085" alt="sta_3" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/prtactice_1%23day7/sta_3.png"><br><br>

 **Input Transition and Output Capacitance:**
When specifying external delays, it's essential to allocate the clock period among external delay, combinational logic delay, and setup time. This allocation assumes ideal conditions, where input signals have zero transition time, and there is no load at the output. 

However, in practice, cell delay is influenced by both the input transition time and the output capacitance. Any non-ideal conditions, such as a non-zero transition time at the input or significant load capacitance at the output, can lead to delays exceeding the allocated budget. This can result in a violation of the setup time requirement.

To prevent such violations, it's crucial to constrain both the input transition time and the output load capacitance. These constraints guide the optimization performed by the tool, ensuring that it optimizes the combinational delay to meet the setup time requirement more effectively.

</details>


<details>
	<summary>Labs</summary>
	
**Timing .lib file:**
The Timing File (.lib) contains ASCII representations of timing, area, and power information associated with standard cells. These files follow a naming convention known as PVT (Process, Voltage, Temperature). 

For instance, consider the standard library name 'sky130_fd_sc_hd_tt_025C_1v8.' This naming convention provides the following information:
- 'sky130': Indicates the technology node, in this case, 130 nm.
- 'fd': Stands for 'foundry,' representing the manufacturing process.
- 'sc': Denotes 'standard cell,' indicating that it's a library of standard logic cells.
- 'hd': May refer to the cell height or variant.
- 'tt_025C_1v8': Specifies the operating conditions, where 'tt' signifies the typical temperature (25°C), and '1v8' represents the supply voltage (1.8 V).

This naming convention helps users identify the specific library and its characteristics, such as the process technology, operating conditions, and voltage levels associated with the standard cells.
 <img  width="1085" alt="lab_7" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/prtactice_1%23day7/lab_7.png"><br><br>

 The Timing File (.lib) also includes information about the technology used for standard cells, which in the example mentioned earlier is CMOS. It specifies the delay model, units of time, voltage, resistance, and other relevant units of measurement. Additionally, within the .lib file, you can find different flavors or variants of the same logic gates. These flavors may have varying characteristics to suit different design requirements.

Furthermore, the .lib file provides data on leakage power, area, and timing sense for each of these different flavors of gate cells. This comprehensive information is crucial for accurately modeling and optimizing the performance of digital circuits during the design and synthesis process.
<img  width="1085" alt="lab_7_3" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/prtactice_1%23day7/lab_7_3.png"><br><br>

A Look-Up Table (LUT) within a Liberty file is a fundamental component that defines the logical behavior and timing characteristics of a combinational logic cell found in a digital library. These Liberty files are essential in the field of electronic design automation (EDA) and are used to represent collections of standard cells for use in Very Large Scale Integration (VLSI) design projects.

In a Liberty file, the LUT typically comprises a table with two indices:
- 'index1': This index represents the input transition characteristics.
- 'index2': This index represents the output load capacitance.

For instance, consider an example of a 'and2_1' gate index table, which provides specific data on the behavior and timing of a two-input AND gate for different input transition times and output load capacitances. This information is invaluable for EDA tools and designers when performing accurate timing analysis and optimization for their digital designs.
<img  width="1085" alt="lab_7_2" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/prtactice_1%23day7/lab_7_2.png">
<img  width="1085" alt="lab_7_22" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/prtactice_1%23day7/lab_7_22.png"><br><br>

A Boolean function is termed 'unate' when it exhibits the unateness property, which characterizes its behavior concerning input variables. Unate functions play a pivotal role in logic optimization and simplification techniques, particularly in processes like logic synthesis and minimization.

There are two primary types of unateness:

1. **Positive Unate Function:** A Boolean function is deemed positive unate with respect to a specific input variable when, for any assignment of values to the other input variables, the function either remains constant or increases as the designated input variable transitions from 0 to 1. In essence, the function relies solely on the positive (1) values of that input variable.

2. **Negative Unate Function:** A Boolean function is considered negative unate with respect to a particular input variable when, for any assignment of values to the other input variables, the function either remains constant or decreases as the specified input variable transitions from 0 to 1. In this scenario, the function hinges exclusively on the negative (0) values of that input variable.

As an illustrative example, an AND gate exhibits positive unateness, as its output depends solely on the presence of positive (1) values in its input variables, regardless of the negative (0) values.

This explanation provides a clearer understanding of unate functions and their significance in logic design and optimization.
<img  width="1085" alt="unnate_lab" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/prtactice_1%23day7/unnate_lab.png"><br><br>

Sequential flip-flops are characterized by their clock pin set to 'true'
```ruby
area : 38.787200000;
        cell_footprint : "sky130_fd_sc_hd__sdfbbn";
        cell_leakage_power : 0.0153947700;
        driver_waveform_fall : "ramp";
        driver_waveform_rise : "ramp";
        ff ("IQ","IQ_N") {
            clear : "!RESET_B";
            clear_preset_var1 : "H";
            clear_preset_var2 : "L";
            clocked_on : "!CLK_N";
            next_state : "(D&!SCE) | (SCD&SCE)";
            preset : "!SET_B";
        }
        pg_pin ("VGND") {
            pg_type : "primary_ground";
            related_bias_pin : "VPB";
            voltage_name : "VGND";
        }
        pg_pin ("VNB") {
            pg_type : "nwell";
            physical_connection : "device_layer";
            voltage_name : "VNB";
        }
        pg_pin ("VPB") {
            pg_type : "pwell";
            physical_connection : "device_layer";
            voltage_name : "VPB";
        }
        pg_pin ("VPWR") {
            pg_type : "primary_power";
            related_bias_pin : "VNB";
            voltage_name : "VPWR";
        }
        pin ("CLK_N") {
            capacitance : 0.0017800000;
            clock : "true";                           ( Clock is true )
            direction : "input";
            fall_capacitance : 0.0016980000;
```

**The unateness property of a D flip-flop that is negative-edge-triggered.**
<img  width="1085" alt="unnate_lab2" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/prtactice_1%23day7/unnate_lab2.png"><br><br>

**The unateness property of a positive-edge-triggered D latch.**
<img  width="1085" alt="unnate_lab3" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/prtactice_1%23day7/unnate_lab3.png"><br><br>

**The library linked:**
<img  width="1085" alt="lab_7_5" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/prtactice_1%23day7/lab_7_5.png"><br><br>

**To print all the sequential gates:**
<img  width="1085" alt="lab_7_6" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/prtactice_1%23day7/lab_7_6.png"><br><br>

**To print the list of cells from the collection:**
<img  width="1085" alt="lab_7_7" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/prtactice_1%23day7/lab_7_7.png"><br><br>

**To print the pins associated with the gate cell and functionality of a particular gate:**
<img  width="1085" alt="lab_7_8" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/prtactice_1%23day7/lab_7_8.png"><br><br>

**To print the pins along with the direction of nand2_4 gate:**
<img  width="1085" alt="lab_7_9" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/prtactice_1%23day7/lab_7_9.png"><br><br>

**To print the attributes of the cell/pin:**
<img  width="1085" alt="lab_7_10" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/prtactice_1%23day7/lab_7_10.png"><br><br>

**A TCL program that accepts a list of cells as input and prints the output pins along with their corresponding functionalities:**
<img  width="1085" alt="lab_7_11" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/prtactice_1%23day7/lab_7_11.png">
<img  width="1085" alt="lab_7_12" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/prtactice_1%23day7/lab_7_12.png"><br><br>

**To print list of all attributes:**
<img  width="1085" alt="lab_7_13" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/prtactice_1%23day7/lab_7_13.png"><br><br>
<img  width="1085" alt="lab_7_14" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/prtactice_1%23day7/lab_7_14.png"><br><br>

</details>


## Day-8-Advanced SDC Constraints

<details>
	<summary>Introduction</summary><br><br>

 **Clock:** <br>
 Is a fundamental timing signal that provides synchronization and coordination for various components and operations within a digital system.

 **Clock Terminologies:**
1. **Clock Signal (CLK)**: The primary signal that synchronizes and controls the operation of various components in a digital circuit.

2. **Clock Edge**: Refers to either the rising edge (transition from low to high voltage) or falling edge (transition from high to low voltage) of the clock signal. Many operations in digital circuits are triggered on specific clock edges.

3. **Clock Frequency (fCLK)**: The rate at which the clock signal oscillates, typically measured in Hertz (Hz). It determines how quickly a circuit processes data.

4. **Clock Period (TCLK)**: The time interval between two consecutive rising (or falling) edges of the clock signal. It's the inverse of clock frequency (TCLK = 1 / fCLK).

5. **Clock Domain**: A specific region of a digital circuit that operates based on a common clock signal. Complex digital systems may have multiple clock domains.

6. **Clock Skew**: The variation in arrival times of the clock signal at different points in a clock domain. Excessive clock skew can lead to timing violations.

7. **Clock Gating**: A power-saving technique where the clock signal is used to enable or disable specific circuit elements, reducing power consumption when they are not needed.

8. **Clock Distribution Network**: The infrastructure that carries the clock signal to different parts of a chip. It includes clock trees and buffers to maintain signal integrity.

9. **Clock Jitter**: The variation in the timing of clock edges from their ideal positions. It can affect the reliability and performance of a circuit.

10. **Clock Synchronization**: Ensuring that different clock domains within a chip or system are aligned and operate together correctly.

11. **Clock Tree Synthesis (CTS)**: The process of designing and optimizing the clock distribution network to ensure a balanced and efficient clock signal distribution.

12. **Clock-to-Q Delay**: The time it takes for a flip-flop or latch to capture data after a clock edge. It's a critical parameter in ensuring proper circuit operation.

**Clock Latency:** <br>

Clock latency in digital circuits refers to the delay or time it takes for a clock signal to propagate from its source to various components or registers within the circuit. Understanding and managing clock latency is crucial for ensuring that a digital design meets its timing requirements and functions correctly.

Two types of Clock latency:
<ul>
	<li>Source Latency (Insertion delay)- from clock source to clock definition pin, could be on chip or off chip.</li>
	<li>Network Latency- from clock definition point to clock pin of the flop.</li>
</ul>

```ruby
Total latency= Source Latency + Network Latency
```

**Generated Clocks:**
<ul>
	<li>Such clocks are derived from master clock and are in phase with master clock.</li>
	<li>Major advantage- Clock origin is still that of master clock --> Source latency specifications are automatically included.</li>
</ul>

**Virtual Clocks:**
<ul>
	<li>Is not associated with any pin or port, not a real clock but mimics the functionality of a real clock.</li>
 	<li>Used as reference to constrain the interface pins by relating the arrivals at input or output port with respect to it with help of input and output delays.</li>

</ul>

**False Paths:**
<ul>
	<li>Certain timing paths are not real/possible and need to be executed from STA as they don't occur during the functional operation of the design.</li>
	<li>Such paths are turned off in STA as false paths</li>
	<li>Reduced analysis to nfocus only on real paths is its advantage.</li>
</ul>

**Half-cycle Paths:**
<ul>
	<li>If the design has both the positive and negative edge triggered flops, such paths might exist.</li>
	<li>It could be from rising edge of a flop to the falling edge of another flop.</li>
	<li>Data path gets only half a cycle for setup check (more stringent condition)</li>
	<li>The hold check gets relaxed by half a cycle --> resulting in slack met with a large value.</li>
</ul>

**Multicycle Paths- 1/2:**
<ul>
	<li>In some cases, the combinational path between two flops may take longer than one cycle to propagate through the logic.</li>
	<li>We direct the STA tool that the relevant capture edge occurs after some specified number of clocks.</li>
</ul>

**Asynchronous timing checks- Removal time:**
<ul>
	<li>Related to asynchronous control signals like asynchronous reset.</li>
	<li>Ensures there is adequate time between an active edge of clock and release of the asynchronous signal.</li>
	<li>This is done in order to ensure the clock edge has no effect and does not cause any change in the values.</li>
	<li>It is a min path check like hold check.</li>
</ul>

**Asynchronous timing checks- Recovery time:**
<ul>
	<li>Ensures that there is minimum amount of time between asynchronous signal becoming inactive and arrival of next active edge of clock.</li>
	<li>Ensure that once the asynchronous signal inactivates, the design has enough time to recover and respond back to the clocks</li>
	<li>Defined in the cell library of the asynchronous pin of the flop as the 'library recovery time.'</li>
	<li>Max path check like the setup check.</li>
</ul>

**Clock Tree Modelling- Uncertainty:**

<ul>
	<li>All Reg 2 Reg paths are constrained by Clocks.</li>
	<li>All In 2 Reg paths are constrained by Clock, Input delay and Input transition.</li>
	<li>All Reg 2 Out paths are constrained by Clock, Output delay, Load.</li>
</ul><br><br>

*Clock Generation:*
<ul>
	<li>Oscillator</li>
	<li>PLL</li>
	<li>External Clock Source</li>
All the above clcok sources have inherent variations in the clock period due to Stochastic effects called as a jitter.
	Tclk - Tjitter >= Tcq + Tcombi + Tsu
</ul>

*Clock Distribution:*
<ul>
	<li>In ideal clock network all flops see the edge at same time.</li>
	<img  width="1085" alt="PHOTO-2023-09-13-12-07-50.jpg" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/PHOTO-2023-09-13-12-07-50.jpg"><br><br>
 	<li>In a practical clock network after CTS, all flops may not see the clock edge at same instance this is called Clock skew.</li>
  	<img  width="1085" alt="PHOTO-2023-09-13-12-07-51.jpg" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/PHOTO-2023-09-13-12-07-51.jpg"><br><br>

</ul>

The command to create clock is create_clock:

```ruby
create_clock -name <clock_name> -per <PERIOD> [clock_definition point]
```

<ul>
	<li>Clocks must be created on the clock generator (PLL, Oscillators) or primary IO pins (for external clocks), clocks should not be created on hierarchical pins which are not clock generators.</li>
</ul>
 
*Jitter:* <br>

Refers to the short-term variations or fluctuations in the timing of a signal's edges or transitions from their ideal or expected positions. Jitter can manifest as small, rapid deviations in the timing of a clock or data signal. It is typically characterized by its amplitude (magnitude of variation) and frequency (rate of variation).

*Clock Skew:* <br>

Refers to the variation in the arrival times of a clock signal at different elements or points within a digital circuit or system. It is a timing irregularity that occurs when the clock signal, which is supposed to arrive simultaneously at all parts of the circuit, arrives at different times due to differences in routing delays.

*Effect of Clock skew:* <br>

<img  width="1085" alt="PHOTO-2023-09-13-12-07-52.jpg" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/PHOTO-2023-09-13-12-07-52.jpg">
<img  width="1085" alt="PHOTO-2023-09-13-12-07-52%202.jpg" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/PHOTO-2023-09-13-12-07-52%202.jpg">
<img  width="1085" alt="PHOTO-2023-09-13-12-07-53.jpg" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/PHOTO-2023-09-13-12-07-53.jpg"><br><br>

*Clock Modelling:* <br>

Model the clock for following:
<ul>
	<li>Period</li>
	<li>Source Latency (Time taken by the clock source to generate clock.)</li>
	<li>Clock Network Latency (Time taken by clock distribution network.</li>
	<li>Clock Skew (Clock path delay mismatches which causes difference in the arrival of clock.</li>
</ul>

*Clock Uncertainty:* <br>

Collectively clock skew, jitter is called clock uncertainty.

<img  width="1085" alt="PHOTO-2023-09-13-12-07-54.jpg" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/PHOTO-2023-09-13-12-07-54.jpg"><br><br>

**IO Dealy:** <br><br>

*Getting ports in DC:*

```ruby
get_ports clk   

get_ports *clk*					#returns a collection of ports whose name contains clk in it

get_ports *					#gives all the ports of the design

get_ports * -filter "direction == in"		#lists all input ports

get_ports * -filter "direction == out"		#lists all output ports
```

*Getting the clocks in DC:*

```ruby
get_clocks *					#will get all the clocks in the design

get_clocks *clk*				#all clocks which has the name clk

get_clocks * -filter "period > 10"

get_attribute [get_clocks my_clk] period

get_attribute [get_clocks my_clk] is_generated

report_clocks my_clk				#reports all the details about clock
```

*Command used to query the cells in the design:*

Physical cells, also known as standard cells, are pre-designed building blocks that incorporate the essential logic gates and other components required for the implementation of diverse digital functions. These standard cells serve as the foundational elements used in the layout and construction of the digital logic within an integrated circuit.

```ruby
get_cells * -hier				#lists all the cells in the design both physical and hierarchical cells.
```

Hierarchical cells represent a methodology employed in VLSI (Very Large Scale Integration) design to effectively manage and organize the intricacies of large-scale circuits.
<img  width="1085" alt="PHOTO-2023-09-13-12-07-55.jpg" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/PHOTO-2023-09-13-12-07-55.jpg"><br><br>

```ruby
dc_shell> get_attribute [get_cells u_combo_logic] is_hierarchical
true
dc_shell> get_attribute [get_cells u_combo_logic/U1] is_hierarchical
false
```

*Clock Waveform:*

```ruby
create_clock -name <clock name> -period <clock period value> [clock definition point] -wave { first rising edge, next falling edge }
```
The clock definition command specifies a 50% duty cycle with a period of 10ns. By default, the rising edge occurs at 0ns and 10ns, while the falling edge occurs at 5ns.

```ruby
create_clock -name MYCLK -per 10 [get_ports clk] -wave {0 5}
```

*Constraining IO paths:* <br>

A clearer and more concise version of your sentence could be: "The input and output ports are constrained with respect to the MY_CLK generated on the 'clk' port. These constraints specify a permissible range for the clock period, which is set using the '-min' and '-max' switches.

Input ports: <br>

Input ports in a design are subject to constraints such as clock period, input transition, and input delay. The following commands are employed to define these constraints for the input ports

```ruby
set_input_delay -max 3 -clock[get_clocks MY_CLK] [get_ports IN_*]
set_input_delay -min 0.5 -clock[get_clocks MY_CLK] [get_ports IN_*]
set_input_transition -max 1.5 [get_ports IN_*]
set_input_transition -min 0.75 [get_ports IN_*]
```

Output ports: <br>

The output ports are subject to constraints related to clock period, output delay, and output load. The following commands are employed to specify constraints for the output ports of a design:

```ruby
set_output_delay -max 3 -clock[get_clocks MY_CLK] [get_ports OUT_Y]
set_output_delay -min 0.5 -clock[get_clocks MY_CLK] [get_ports OUT_Y]
set_output_load -max 80 [get_ports OUT_Y]
set_output_load -min 20 [get_ports OUT_Y]
```

</details>

<details>
	<summary>Labs</summary> <br>
 
**Load design, get_cells, get_ports, get_nets, get_pins, get_clocks, querying clocks:** <br>

The verilog file and design used for this lab is as follows:
<img  width="1085" alt="lab8_1" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/a6f401f64cc2bea2717cdc99eca0946ff888bf24/day8_1/lab8_1.png">
<img  width="1085" alt="" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/"><br><br>

get_ports: <br>

<img  width="1085" alt="lab8_2" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_2.png">

To print them one by one: <br>

<img  width="1085" alt="lab8_3" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_3.png"><br><br>

To print direction of the ports: <br>

<img  width="1085" alt="lab8_4" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_4.png"><br><br>

get_cells: <br>

<img  width="1085" alt="lab8_5" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_5.png"><br><br>

To know if the cell is hierarchical or not: <br>

<img  width="1085" alt="lab8_6" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_6.png"><br>
<img  width="1085" alt="lab8_7" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_7.png"><br><br>

To get the reference name of all the cells in the design: <br>

<img  width="1085" alt="lab8_9" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_9.png"><br><br>

To see what the DC has done in gui form using design vision: <br>

<img  width="1085" alt="lab8_10" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_10.png">
<img  width="1085" alt="lab8_11" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_11.png">
<img  width="1085" alt="lab8_12" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_12.png"><br><br>

To print all the nets in the design: <br>

<img  width="1085" alt="lab8_13" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_13.png"><br><br>

To know what a particular net is connecting: <br>

<img  width="1085" alt="lab8_14" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_14.png">
<img  width="1085" alt="lab8_15" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_15.png"><br><br>

To know who is getting driven and who is the driver on a particular net: <br>

<img  width="1085" alt="lab8_16" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_16.png"><br><br>

get_pins: <br>
Prints all the pins in the design <br>
<img  width="1085" alt="lab8_17" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_17.png"><br><br>

To know the clock pins in our design: <br>

<img  width="1085" alt="lab8_18" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_18.png">
Here we see there is some error with respect to Q pin, so lets debug this-
<img  width="1085" alt="lab8_19" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_19.png">
From here we understand that the attribute 'clock' must be queried only on input pins. So let us first check if the pin is input pin or output pin; by listing all the attributes for cells and particularly checking for the 'clock' attribute-
<img  width="1085" alt="lab8_20" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_20.png"><br><br>
The script:
<img  width="1085" alt="lab8_21" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_21.png">
<img  width="1085" alt="lab8_22" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_22.png"><br><br>

The difference between the attribute 'clocks' and 'clock':
<img  width="1085" alt="lab8_23" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_23.png">

The attribute 'clock' tells us if the pin is meant to be a clock pin or not. While the attribute 'clocks' tells what are the clocks reaching the pin. <br><br>

get_clocks: <br>

<img  width="1085" alt="lab8_24" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_24.png">
No clock is seen because we have not created a clock usinh the 'create_clock' command, 'get_clock' is meant to get the clocks of the design.

Lets create clock: <br> 

To know which design we are currently working on-
<img  width="1085" alt="lab8_25" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_25.png">
<img  width="1085" alt="lab8_26" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_26.png"><br><br>

To know if the clock is generated clock or not:
<img  width="1085" alt="lab8_27" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_27.png">
We see that it is not a generated clock, it is a master clock.

To see all the clocks in the design the command used:
```ruby
report_clocks *
```

To see the clocks:
script-
<img  width="1085" alt="lab8_29" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_29.png">
<img  width="1085" alt="lab8_30" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_30.png"><br><br>

Note: <br>

Clock should be created only on the clock port, external port meaant to receive clock or clock generators and not on some pin: <br>

<img  width="1085" alt="lab8_32" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_32.png">
In case there is a wrong clock created then the command used to remove it:
```ruby
remove_clock <clock name>
```
<img  width="1085" alt="lab8_33" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_33.png"><br><br>


**Clock waveforms:** <br>

To create a clock by name 'MYCLK' with clock period of 10ns with first rise edge at 5ns and the next fall edge at 10ns-
<img  width="1085" alt="lab8_34" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_34.png"><br><br>

To create a clock by name 'MYCLK' with clock period of 10ns with first rise edge at 15ns and the next fall edge at 20ns-
<img  width="1085" alt="lab8_36" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_36.png"><br><br>

To create 25% duty cycle clock:
<img  width="1085" alt="lab8_35" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_35.png"><br><br>

**Clock network modelling- Uncertainty, report_timing:**
Few terminologies:
<ul>
	<li>Clock skew: Comes because of clock network, due to delay imbalance between flops.</li>
	<li>Clock jitter: Random variation in the clock edge (coming from source.)</li>
	<li>CTS: Clock Tree Synthesis, tool used for CTS will minimize the imbalance but it cannot make it zero.</li>
	<li>Clock Uncertainty: During pre CTS phase uncertainty includes skew and jitter. During post CTS phase uncertainty includes jitter alone as clock network is actually built.</li>
	<li>Source latency: refers to the delay or time it takes for a signal to propagate from the source of that signal, such as a digital input, to its destination within the circuit. This delay can occur due to various factors, including the time it takes for the signal to travel through wires, pass through logic gates, or encounter other components like buffers and flip-flops.</li>
	<li>Network latency: refers to the delay or time it takes for data to travel from one point in a network to another.</li>
</ul>

Clock network modelling:
Step-1: Modelling source latency
step-2: Modelling network latency
Step-3: Modelling clock uncertainty for max delay (for setup)
Step-4: Modelling clock uncertainty for min delay (for hold)
Step-5: Report timing
Lets compare the two reports:
<img  width="1085" alt="lab8_38" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_38.png"><br><br>
<img  width="1085" alt="lab8_37" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_37.png"><br><br>
Observations-
<ul>
	<li>Slack has reduced.</li>
</ul>

<img  width="1085" alt="lab8_39" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_39.png"><br><br>
Reg2Reg path that ends at REGC_reg, since here clock is not defined we see the message 'Path is unconstrained.'

<img  width="1085" alt="lab8_40" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_40.png"><br><br>
When clock is defined now, we see the timing path shows timing being met with a positive slack of 9.55s.

The following command gives information about all the constraints of ports:
```ruby
report_port -verbose
```
<img  width="1085" alt="lab8_42" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_42.png"><br><br>
Example of one instance where input delay is being constrained to 5ns:
<img  width="1085" alt="lab8_43" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_43.png"><br><br>
<img  width="1085" alt="lab8_44" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_44.png"><br><br>

Timing report after defining input transition:
<img  width="1085" alt="lab8_45" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_45.png"><br><br>
<img  width="1085" alt="lab8_46" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_46.png"><br><br>

The timing report after defining output  delay and output constraints:
<img  width="1085" alt="lab8_47" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_47.png"><br><br>

The timing report after defining the load/capacitance:
<img  width="1085" alt="lab8_48" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_48.png">
<img  width="1085" alt="lab8_49" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_49.png"><br><br>

The timing report after defining the minimum load capacitance (hold report):
<img  width="1085" alt="lab8_50" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_50.png"><br><br>

A script that 
Note:
What should be the load, input transition, output transition that depends upon what is the design we are trying to constraint and how it should be modeled.


**Generated clock:**
The necessity for the clock of the external world and the input module to match physically is hindered by the lengthy routing paths, which incorporate buffers and result in increased clock network delays. To address this challenge, we opt to define the generated clock at a separate location, ensuring both logical and physical alignment of the clocks. However, opting to create a new master clock in lieu of generated clocks introduces the following disadvantages:

1. Managing additional clock domains becomes essential.
2. The need for specifying supplementary constraints arises.
3. Source latency specifications must be redefined for the new master clocks.

Generated clocks are consistently defined with respect to the master clock, which functions as the primary clock source or is linked to the primary I/O pins. The relevant command for this procedure is as follows:
```ruby
create_generated_clock -name MYGEN_CLK -master [get_clocks MY_CLK] -source [get_ports clk] -div 1 [get_ports out_clk]
```
The command demonstrates that the generated clock, MYGEN_CLK, is derived from the master clock, MY_CLK, defined at the clk port with a divide factor of 1. MYGEN_CLK is defined at the output port, out_clk. Implementation tools automatically propagate the clock downstream using timing arcs from the definition point as the default behavior.

Verilog file used for this experiment:
<img  width="1085" alt="lab8_53" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_53.png"><br><br>

A script with all the constraints:
<img  width="1085" alt="lab8_54" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_54.png"><br><br>
After sourcing the script and the report generated:
<img  width="1085" alt="lab8_55" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_55.png"><br><br>
<img  width="1085" alt="lab8_56" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_56.png"><br><br>
<img  width="1085" alt="lab8_57" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_57.png"><br><br>
<img  width="1085" alt="lab8_58" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_58.png"><br><br>


**vclk, max_latency, rise_fall IO Delays:**
*set_input_delay:*
The command specifies that data arrives at the input port IN_A 3ns after the arrival of a clock edge. This means that 3ns of the total period (10ns) are reserved for input delay. Consequently, the available time for combinational delay is reduced when considering the setup constraint.
```ruby
create_clock -name myclk -per 10 [get_ports clk]
set_input_delay -max 3 - clock myclk [get_ports IN_A]
set_input_delay -min 1 - clock myclk [get_ports IN_A]
```
When the defined input delay is negative, it results in additional time for the combinational process. This scenario can be elucidated as follows: during routing, the clock experiences a delay, while the data arrives on schedule. Typically, a positive delay implies that data arrives after the clock edge, whereas a negative delay implies data arrives before the clock edge. In essence, a negative delay signifies that the clock is relatively delayed in relation to the data.
In the context of hold constraints, when the input delay is positive, it means the data arrives after 1ns of the clock period, aiding in meeting the hold time requirement since the data aligns within the hold window. However, when the input delay is negative, the data arrives before the hold window, resulting in a failure. To rectify this situation, adjustments must be made to delay the data arrival appropriately.
In scenarios where an input port connects to multiple external registers, leading to multiple timing paths towards a single endpoint with different starting points, the input delay can be constrained more than once using the '-add' switch. If one of these paths involves negative edge triggering while the capture is positive edge-triggered, you can specify this using the '-clock_fall' switch. This concept can be illustrated as follows:
```ruby
set_input_delay -max 2 -clock MY_CLK [get_ports IN_A]
set_input_delay -max 3 -clock MY_CLK -clock_fall -add [get_ports IN_A]
```
Positive delay narrows the path for the maximum constraint and widens it for the minimum constraint, while negative delay widens the path for the maximum constraint and narrows it for the minimum constraint

*set_output_delay:*
The command specifies a 3ns delay for data to reach the external flop. As a result, 3ns of the total period (10ns) are allocated for output delay. This allocation reduces the available time for combinational delay.
```ruby
create_clock -name myclk -per 10 [get_ports clk]
set_output_delay -max 3 - clock myclk [get_ports OUT_Y]
set_output_delay -min 1 - clock myclk [get_ports OUT_Y]
```
Similarly, positive delay narrows the path for the maximum constraint and widens it for the minimum constraint, while negative delay widens the path for the maximum constraint and narrows it for the minimum constraint. Hold constraints remain independent of the clock period as launch and capture flops are evaluated simultaneously. Furthermore, the 'add' switch and 'clock' switch are also the same for output delay, as demonstrated below
```ruby
set_output_delay -max 2 -clock MY_CLK [get_ports OUT_Y]
set_output_delay -max 3 -clock MY_CLK -clock_fall -add [get_ports OUT_Y]
```
The 'clock_fall' switch is used to indicate that the annotated delay is in reference to the negative edge of the clock. Conversely, the 'add' switch is employed to append the constraint to existing constraints without overwriting them.

**constraining IO path:**
To constrain pure combinational logic without any flops, you can utilize the 'set_max_latency' command or define a virtual clock. The command is defined as follows:
```ruby
set_max_latency 1.0 -from [get_ports IN_C] -to [get_ports OUT_Z]
```
This implies that data transfer from port IN_C to OUT_Z must occur within a 1ns timeframe. A virtual clock, unlike a physical clock, lacks latency and does not have a specific definition point. It serves as an abstract time reference for budgeting purposes and can be defined as follows:
```ruby
create_clock -name my_vclk -period 5
set_input_delay -max 1.5 -clock my_vclk [get_ports IN_C]
set_output_delay -max 2.5 -clock my_vclk [get_ports OUT_Z]
```
*set_driving_cell:*
The 'set_driving_cell' command is employed for module-level IOs, where the same technology can be utilized. On the other hand, the 'set_input_transition' command is suitable for top-level primary IOs, where two different chips may be connected, and the transition is specified by the interface. These two commands can be used interchangeably, but 'set_driving_cell' is more accurate and recommended for all internal timing paths.

The driving cell is defined to model input transitions based on the load and fanout of the input port or pin. The 'set_driving_cell' command is illustrated as follows: 'set_driving_cell -lib_cell <lib_cell_name> [ports]
```ruby
set_driving_cell -lib_cell sky130_fd_sc_hd _buf_1 [all inputs]
```

Now, let's examine the same design with an additional 'in2out' path included (lab14_circuit.v). Here's the corresponding behavioral code:
<img  width="1085" alt="lab8_59" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_59.png"><br><br>

The following indicates that there are now 4 flip-flops after modifying the design. Consequently, all constraints are derived from the lab8_cons.tcl file. When reporting clocks, all clocks in the design are inferred as follows:
<img  width="1085" alt="lab8_60" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_60.png"><br><br>
<img  width="1085" alt="lab8_61" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_61.png"><br><br>

<img  width="1085" alt="lab8_62" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_62.png">
<img  width="1085" alt="lab8_63" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_63.png">
Here:
<ul>
	<li>all_inputs : returns all the inputs in design.</li>
	<li>all_outputs : returns all the outputs in design.</li>
	<li>all_clocks : returns all clock in design.</li>
	<li>all_fanout : returns all pins connected as load to given port/pin.</li>
	<li>all registers -clock <clock_name> : returns the registers clocked with the given clock.</li>
	<li>all_fanin : returns all the driving cells to a port/pin.</li>
	<li>all_fanin -flat -startpoints_only : returns only startpoints of a timing path connected as driver.</li>
	<li>all_fanout -flat -endpoints only : returns only endpoints of a timing path connected as load.</li>
</ul>

Here when max delay is constrained it violates the path, when compiled again the path is met as tool optimises the logic choosing appropriate cells:
<img  width="1085" alt="lab8_64" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_64.png"><br><br>

Schematic view of the design after writing out the ddc file:
<img  width="1085" alt="lab8_65" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_65.png">
<img  width="1085" alt="lab8_66" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_66.png">

Clock report:
<img  width="1085" alt="lab8_67" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day8_1/lab8_67.png">


</details>

## Day-9-Optimizations in Synthesis

<details>
	<summary>Introduction</summary>

 **Optimisation:**
 
Optimization in digital circuits involves improving various aspects of a digital design to meet specific goals, such as minimizing power consumption, maximizing performance, reducing area (size), or enhancing reliability.

**Combinational logic optimisation:**

Combinational logic optimization is the process of improving the performance, area efficiency, and other characteristics of combinational logic circuits. Combinational logic circuits consist of logic gates that perform specific Boolean functions without any feedback loops or memory elements. These circuits are used to perform various tasks such as data processing, arithmetic operations, and data routing.

<ul>
	<li>Constant Propagation:

In constant propagation, simplifications are made by fixing one input as a constant value, which allows for the simplification of the remaining circuit. For instance, as previously mentioned, the expression (AB+C)' can be reduced to C', resulting in optimized area and power efficiency.
</li>
	<Li>Boolean Logic Optimization:

<ul>
	<li>K-Map (Karnaugh Map):
	Utilizing K-Maps, Boolean logic expressions can be visually simplified, leading to more efficient logic designs. K-Maps help identify patterns and groupings of terms for simplification.</li>

<li>Quine-McCluskey Algorithm:
The Quine-McCluskey algorithm is a systematic method for minimizing Boolean functions. It efficiently finds prime implicants and essential prime implicants to optimize logic expressions.</li>

<li>Nested Ternary Operator Optimization:
Consider a circuit containing nested ternary (conditional) operators that include multiple multiplexers. Through optimization, this complex circuit can often be simplified to a more compact form, such as an exclusive-NOR (exnor) gate. This simplification process enhances both the area efficiency and the overall performance of the circuit.
<li></ul></Li>
</ul>

**Resource Sharing:**

Let's consider a ternary operator represented as y = sel ? ab : cd. This operator performs multiplication based on the value of 'sel,' but multiplication circuits tend to be large and resource-intensive.
To optimize both area and power efficiency, we can implement this operation using two multiplexers as follows: y = (sel ? a : c) * (sel ? b : d). By doing this, we share the 'sel' input between both multiplexers, allowing us to obtain the same result with a significantly smaller area footprint. This resource sharing not only optimizes area utilization but also leads to power savings in the circuit.

**Logic Sharing:**

Efficient logic design involves sharing common logic elements when multiple gates can use the same intermediate results. For example, let's consider a design with two expressions: y = a & b & c and z = (a & b) | c. In the traditional approach, this would require one 3-input AND gate (which consumes more area and power), one 2-input AND gate, and one 2-input OR gate.
However, both of these expressions share a common 2-input AND gate. By leveraging this shared logic element, we can optimize the design by using two 2-input AND gates and one OR gate. This approach results in a more area and power-efficient circuit compared to the previous configuration.

**Balanced Implementation vs. Preferential Implementation:**

In a balanced implementation, equal time is allocated to all timing arcs, ensuring that the delay from input to output pins is consistent across all paths. Conversely, preferential implementation prioritizes certain signals by giving them less delay time, while others receive more time based on their margin.
Let's illustrate this with an example. Imagine a design that doesn't include any 5-input AND gates. This design can be implemented in two ways, as shown below:
In the left image, there is an equal delay between signals a → y and e → y.
In the right image, there's more delay for signal a → y and less delay for signal e → y.
When e represents a signal with a very tight delay requirement, meaning it arrives late due to external factors (e.g., long routing delays), and it cannot tolerate a 2-gate delay, the preferential implementation shown on the right is preferred. This approach ensures that the critical signal e meets its timing requirements while still accommodating other signals within their respective timing constraints.
<img  width="1085" alt="lab9" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9.png">

**Sequential Logic Optimizations::**

Sequential logic optimizations encompass various techniques to improve the efficiency and performance of sequential logic circuits. These optimizations can be categorized as basic and advanced methods:

A. Basic Sequential Optimizations:<br>
	<br>1. Sequential Constant Propagation: Involves simplifying sequential circuits by propagating constant values through flip-flops and logic elements.<br>
	<br>2. Sequential Constant Propagation: Involves simplifying sequential circuits by propagating constant values through flip-flops and logic elements.<br>
	<br>3. Retiming: Reorders the placement of flip-flops within a design to optimize critical paths and meet timing requirements.<br>
	<br>4. Unused Flop Removal: Identifies and eliminates flip-flops that are no longer necessary for correct circuit operation, reducing area and power consumption.<br>
	<br>5. Clock Gating: Introduces clock gating logic to disable clock signals to specific flip-flops during idle or non-active periods, reducing power consumption.<br><br>

 
B. Advanced Sequential Optimizations:<br>
	<br>1. State Optimization: Analyzes and optimizes the state transition logic of finite state machines (FSMs) to reduce the number of states or transitions, leading to a more efficient design.<br>
	<br>2. Sequential Logic Cloning: Involves replicating portions of sequential logic with specific conditions, often used for optimization when dealing with asynchronous set or reset signals.<br>
For example, if a flip-flop has an asynchronous set input and its D pin is connected to Vss (ground), it can be optimized by connecting the D pin to Vss directly. Similarly, if a flip-flop has an asynchronous reset input and its D pin is connected to Vdd (supply voltage), it can be optimized by connecting the D pin to Vdd directly. However, if the flip-flop has an asynchronous set input with D connected to Vss or an asynchronous reset input with D connected to Vdd, it cannot be optimized and remains in the circuit.

**Optimization of Unused Outputs:**

Unused outputs in a design do not need to be generated, which can lead to more efficient implementations. For instance, consider a 4-bit up counter where only q is assigned to cnt[0], while the remaining outputs (cnt[1], cnt[2], cnt[3]) are unused. In this case, the design can be simplified to a single flip-flop that toggles when enabled. This optimization can be achieved using just one flip-flop and a multiplexer with an inverter, rather than employing four registers for counting.

However, it's important to note that if there's a future need for cnt[1], the design tool can make suboptimal changes during the design process to ensure no violations occur. This can be controlled using specific boolean variables:

compile_seqmap_propagate_constants: When this variable is set to true, the tool will propagate constants sequentially, optimizing circuits by removing unnecessary sequential constant-propagating circuits. <br>
compile_delete_unloaded_sequential_cells: If this variable is set to true, it allows the tool to remove unused counter cells as discussed earlier, helping optimize the design by eliminating unnecessary components. <br>
compile_register_replication: When set to true, this variable enables register replication in cloning optimization, ensuring that timing constraints are met while maintaining the design's efficiency. <br>
These variables provide control and flexibility in optimizing designs with unused outputs while allowing for potential future adjustments if needed.

**"Register Retiming:**

Also known as Pipelining, is a technique that involves breaking down long combinational paths by inserting registers. This concept can be illustrated through an example. Consider the following design with a significant combinational delay of 48ns, and the setup time of flops is 1ns each. This lengthy combinational path represents the critical path of the design, limiting the circuit's operating frequency to 20MHz.
To overcome this limitation, more flip-flops can be introduced into the design. These additional flip-flops create new 'reg2reg' paths, which have ample positive slack, up to 48ns. The combinational logic can then be divided and shared among these flip-flops. This pipelining technique effectively improves the performance of the design.
The tool does not necessarily distribute the logic equally; it optimizes the design to a certain extent. In the shared configuration shown, the delay of the design on the critical path is reduced to 20ns, effectively improving the performance to 50 MHz. However, when the design is heavily optimized, it may become challenging to define intermediate values, making it difficult to calculate the exact impact of the optimization. Consequently, any bugs that arise in subsequent design stages can make debugging more complex.
Choosing not to use optimization may result in a sub-optimal design, while using it introduces complex behaviors at intermediate stages of the design process.

**Boundary Optimization:**

Boundary Optimization can be illustrated through an example. Suppose you have a top module that includes an internal submodule. By optimizing the combinational logic at the output port of the submodule and the external logic, you can reduce area or power consumption. This process involves dissolving the boundary of the submodule, merging the logic to obtain the optimal design, and then implementing the design. Essentially, this optimization is performed without considering the boundaries, resulting in a remodeled design.
However, it's important to note that this optimization doesn't preserve the hierarchical structure of the design. As a result, the tool may remove intermediate signals in the netlist during optimization. This can make debugging complex, as some hierarchical modules and intermediate signals may be absent in the optimized design.

Boundary optimizations can be controlled using the following switches:

- `set_boundary_optimization true|false`: This switch enables or disables boundary optimization.
- `set_boundary_optimization u_im false`: This switch controls boundary optimization for specific cases or scenarios."

These switches provide control over whether boundary optimization is applied and under what conditions.


**Multi-cycle paths (MCPs):**
Are a concept in digital VLSI (Very Large Scale Integration) design that allows specific paths within a digital circuit to have different clock cycles or timing constraints than the primary clock signal. MCPs are essential for accommodating various functional requirements and ensuring that different parts of a circuit can operate at their own, often slower, clock rates.

**How Multi-Cycle Paths (MCPs) are Timed:**

In the context of timing analysis, Multi-Cycle Paths (MCPs) are timed differently compared to single-cycle paths. Here's how the timing checks for MCPs are typically performed:

1. Single-Cycle Paths:

For single-cycle paths, setup and hold checks are done at the same consecutive clock edge of the flip-flop.
The setup check ensures that data is stable before the next clock edge, and the hold check verifies that the data remains stable until the next clock edge.
Hold check is always performed one clock edge before the setup check to ensure data stability.

2. Half-Cycle Paths:

In half-cycle paths, the setup check is performed at the subsequent falling edge of the flip-flop.
The hold check is done at the previous falling edge of the flip-flop.
Half-cycle paths have stringent setup requirements and relaxed hold requirements.

3. Multi-Cycle Paths:

Multi-cycle paths are more flexible and allow for setup and hold checks to be delayed by multiple clock cycles.
The '-setup' switch specifies the number of cycles after the launch edge that need to be checked for setup.
The '-hold' switch specifies the number of cycles the launch edge can move for hold checks with respect to capture.

Example of Multi-Cycle Path Definitions:
```ruby
set_multicycle_path -setup 2 -to prod_reg[*]/D -through [all_inputs]
set_multicycle_path -hold 1 -to prod_reg[*]/D -through [all_inputs]
```

**False Paths:**

False paths are paths in a design that are considered invalid for Static Timing Analysis (STA). These paths are typically paths where the launch and capture flops have no temporal correlation between their clock edges. Not all paths between different clocks are necessarily asynchronous; clocks generated from the same master clock may have a known relationship, which would not classify them as false paths. Additionally, paths from constant selection lines of multiplexers to registers are not considered timing paths and are therefore designated as false paths.

To specify a false path in a design, you can use the following command:
```ruby
set_false_path -through <>
```
This command marks the specified path as a false path in STA analysis, indicating that it should not be considered when performing timing checks. False paths are important to exclude from analysis to prevent unnecessary violations and to accurately represent the timing relationships in the design.



</details>

<details>
	<summary>Labs</summary>

**Combinational Optimisation:**
The following image illustrates the behavioral code of various designs being synthesized as follows:
<img  width="1085" alt="lab9_1" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_1.png"><br><br>

The following image illustrates the synthesis steps for synthesizing 'opt_check.v', which includes a multiplexer (ternary operator) in the design. After linking and compilation, the unconstrained path utilizes library cells as follows:
<img  width="1085" alt="lab9_2" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_2.png">
<img  width="1085" alt="lab9_3" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_3.png">
<img  width="1085" alt="lab9_4" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_4.png"><br><br>

The following image depicts the synthesized design of 'opt_check'. Initially, the design includes a multiplexer, but after optimization, it has been reduced to an AND gate and an inverter.
<img  width="1085" alt="lab9_5" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_5.png">
<img  width="1085" alt="lab9_6" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_6.png"><br><br>


Likewise, in the following image, you can observe that the ternary operator in 'opt_check2.v' has been reduced to an OR gate after the synthesis process, as depicted:
<img  width="1085" alt="lab9_7" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_7.png"><br><br>


Opt_check3.v has been optimized to a 3-input AND gate, as demonstrated below:
<img  width="1085" alt="lab9_8" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_8.png"><br><br>

The nested ternary operator in 'opt_check4,' which originally contained three multiplexers, has been optimized and reduced to an EX-NOR gate, as shown below:
<img  width="1085" alt="lab9_9" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_9.png"><br><br>

Let's examine the timing path of this circuit. When constrained with a maximum delay of 60ps, the initial timing report shows an unconstrained condition. However, if a slower gate is employed, the tool automatically selects a faster gate to rectify the timing violation, as illustrated below:
<img  width="1085" alt="lab9_10" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_10.png">
<img  width="1085" alt="lab9_11" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_11.png"><br><br>


**Sequential Optimization:**

In the image below, you can see the behavioral code of the designs as follows:
<img  width="1085" alt="lab9_12" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_12.png">
<img  width="1085" alt="lab9_13" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_13.png"><br><br>

The following image illustrates the design, which includes a single flip-flop with an asynchronous reset. It also outlines the synthesis steps for 'dff_const1.v':
<img  width="1085" alt="lab9_14" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_14.png"><br><br>

The synthesized design of 'dff_const1.v' is depicted in the following image. It demonstrates a flip-flop input connected to logic high via a tie cell, along with an asynchronous reset condition as defined in the code.
<img  width="1085" alt="lab9_15" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_15.png">
Tie Cell: <br>
In CMOS designs, it's crucial to avoid surges at the gate terminal because the gate oxide is sensitive. Therefore, VDD (logic high) is not directly connected to the input pin. Tie cells are employed to drive values of 1'b1 or 1'b0.
The image below displays the synthesized circuit of 'dff_const2.v.' This circuit has been fully optimized, with the 'compile_seqmap_propagate_constants' variable set to true.
<img  width="1085" alt="lab9_16" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_16.png"><br><br>

If the boolean variable is set to false, the design appears as follows:
<img  width="1085" alt="lab9_15" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_15.png"><br><br>

The following image presents the output of 'dff_const3.v.' This design has been retained, as it demonstrates a set-reset relationship between flip-flops.
<img  width="1085" alt="lab9_19" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_19.png"><br><br>


The output of 'dff_const4.v' is displayed in the following image. The design appears to be sub-optimized since the variable is set to false.
<img  width="1085" alt="lab9_19" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_19.png"><br><br>


When optimized with the variable set to true, the following output is achieved as shown:
<img  width="1085" alt="lab9_18" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_18.png"><br><br>

The output of 'dff_const5.v' is presented in the following image. In this design, the two flip-flops have been retained due to their set and reset behavior.
<img  width="1085" alt="lab9_19" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_19.png"><br><br>

The following code represents a 4-bit multiplier that multiplies two 4-bit numbers and utilizes three 8-bit registers to propagate data to the output.
<img  width="1085" alt="lab9_20" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_20.png"><br><br>

The following image indicates the presence of three 8-bit registers, each equipped with asynchronous reset functionality.
<img  width="1085" alt="lab9_21" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_21.png"><br><br>

The following images showcase the synthesized design with the graphical user interface (GUI) of the multiplier sub-module and the complete design.
<img  width="1085" alt="lab9_23" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_23.png">
<img  width="1085" alt="lab9_24" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_24.png"><br><br>

The following image illustrates the timing path where the worst delay violation occurs at the input port in the design.
<img  width="1085" alt="lab9_26" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_26.png">
<img  width="1085" alt="lab9_27" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_27.png"><br><br>

After using the command: 'compile_ultra -retime'
<img  width="1085" alt="lab9_28" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_28.png"><br><br>

Now, the previously violated slack has been reduced, and the violation now occurs at the output delay.
<img  width="1085" alt="lab9_29" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_29.png"><br><br>


The following image displays the behavioral code of 'boundary_check.v'.
<img  width="1085" alt="lab9_30" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_30.png"><br><br>

In the provided code, 'im' represents the internal module, which is a 3-bit counter. When the counter reaches the value '111', it triggers 'cnt_roll,' enabling a 4-bit register. The following image illustrates the design, which includes a 3-bit counter and a 4-bit register, both equipped with asynchronous reset functionality.
<img  width="1085" alt="lab9_31" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_31.png"><br><br>

The following image depicts the design, including the hierarchical module 'u_im.' In this design, Boundary Optimization has not been applied.
<img  width="1085" alt="lab9_32" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_32.png"><br><br>

In the DC-Shell, Boundary Optimization is performed, which results in the absence of hierarchies. However, Design Vision retains the ability to display the hierarchical pins of the sub-module as shown above.
<img  width="1085" alt="lab9_34" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_34.png"><br><br>

The Boundary optimized design is as follows:
<img  width="1085" alt="lab9_35" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_35.png">
During functional Engineering Change Orders (ECOs), if bugs are identified, making direct changes in the netlist is possible when hierarchies are preserved. However, if hierarchies are not preserved, re-synthesizing the entire design may consume a significant amount of time.
It's important to note that there's no fixed rule for setting `set_boundary_optimization` to either true or false. The decision depends entirely on the specific requirements and constraints of the design.

The following image displays the behavioral code of 'mcp_check.v'.
<img  width="1085" alt="lab9_36" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_36.png"><br><br>

The following image indicates that the design contains a 16-bit register for the multiplier output and a flip-flop for enable.
<img  width="1085" alt="lab9_38" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_38.png"><br><br>

The following image shows the constraints defined in a tcl file for mcp_check:
<img  width="1085" alt="lab9_37" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_37.png"><br><br>


The following image shows the initial violation before compilation and the violation after compilation:
<img  width="1085" alt="lab9_39" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_39.png">
<img  width="1085" alt="lab9_40" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_40.png">
<img  width="1085" alt="lab9_41" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_41.png"><br><br>

Now, with the multi-cycle path set, the previously violated slack has been reduced, as shown below:
<img  width="1085" alt="lab9_42" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_42.png"><br><br>

The command should infer the startpoint as well because single-cycle paths should not be affected or relaxed due to multi-cycle paths. In the following image, it is evident that all timing paths have met the setup requirements without violations.
<img  width="1085" alt="lab9_43" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_43.png">
<img  width="1085" alt="lab9_44" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_44.png"><br><br>


But the hold is violated as it is not constrained as follows:
<img  width="1085" alt="lab9_45" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_45.png"><br><br>

After defining hold, the timing is met as follows:
<img  width="1085" alt="lab9_46" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_46.png"><br><br>


Here the flop is overloaded with 0.4 fF, so by adding buffers to isolate output ports, all the timing violations are met as follows: 
<img  width="1085" alt="lab9_47" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_47.png">
<img  width="1085" alt="lab9_48" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_48.png">
<img  width="1085" alt="lab9_49" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day9_1/lab9_49.png"><br><br>

</details>


## Day-10-Quality Checks

<details>
	<summary>Introduction</summary><br>

**Generating Timing Reports:** 
<ul>
	<li>Our process for generating timing reports is grounded in the fundamental principles of semiconductor device physics.</li>
	<li>These reports delve into the intricacies of transistor configuration, type selection, and interconnections, each of which contributes to the unique characteristics of different cells, ultimately influencing cell delays.</li>
	<li>Furthermore, our analysis extends to the modeling of wires, accounting for factors such as resistance and capacitance. These wire properties, in turn, play a pivotal role in determining path delays.</li>
	<li>It's important to note that the path with the most significant delay is referred to as the critical path.</li>
	<li>To generate these informative reports, we utilize the 'report_timing' tool, employing various parameters such as:</li>
	<ul>
		<li>'-to {list of signals}': Analyzing inputs and flip-flop outputs relevant to these specified signals.</li>
		<li>'-from {list of signals}': Investigating flip-flop outputs and inputs that are connected to these designated signals.</li>
		<li>'-through {list of pins}': Exploring paths that traverse through these specific pins.</li>
		<li>'-max_paths N': Customizing the report to include information on the top N paths of interest.</li></ul>
</ul>

*Understanding Timing Slack and Checks:*
<ul>
	<li>Timing slack, a crucial concept in our reports, represents the time difference between the arrival of the clock signal (referred to as data required time) and the arrival of the data signal (data arrival time). This difference is expressed as:
   Slack = data required time - data arrival time.</li>
	<li>Setup Check: To ensure the proper functioning of your circuit within the specified cycle time, it is imperative that the rising edge of the clock signal arrives either later or simultaneously with your data signal. In other words, your slack should always be non-negative.
</li>
	<li>Hold Check: For your data to change (data arrival time) at a specific time after the rising edge of the clock signal (data required time), we employ hold checks. In this context, we aim for the following condition to hold true: the slack should be non-negative, calculated as:

	
	Slack = data arrival time - data required time.
	
  </li>

These checks are essential for guaranteeing the reliable operation of your circuit within defined timing constraints.</ul>

*Efficient Path Analysis in DC:*
<ul>
	<li>Within the DC tool, a comprehensive inventory of all available paths, encompassing various transitions (fall to rise, rise to fall, and more), is meticulously compiled. This exhaustive path database serves as a foundation for precise timing path calculations, which complement the constraints provided.
</li>
	<li>To tailor the analysis to your specific needs, DC offers the following options:</li>
	<ul>
		<li>'-max_paths N': Enables you to define the maximum number of paths to be included in each path group's report.</li>
		<li>'-n_worst paths_per_endpoint': Allows you to specify the number of paths to be reported for each individual endpoint within a given path group.
</li></ul>
	</ul>
These features empower you to fine-tune your analysis and obtain targeted insights into your design's timing characteristics.

**check_design, check_timing and report_constraints:**
<ul>
	<li>check_design: This function diligently examines your design for consistency, offering insights into potential issues. For instance, it can identify anomalies like feedthrough, where we directly source 'out_clk' from the defined clock in some of our examples.
</li>
	<li>check_timing: This function specializes in evaluating the adequacy and correctness of your timing constraints. It not only verifies the presence of constraints but also assesses whether they encompass the necessary end-points. Any discrepancies in constraint specifications are flagged for further review.
</li>
	<li>report_constraints: This function provides a valuable overview of your design's feasibility from an electrical perspective. It offers critical insights into parameters such as power consumption and capacitance, helping you gauge the design's electrical characteristics and make informed decisions.</li>
</ul>

 **High Fan-out Nets:**
 <ul>
	 <li>In the realm of digital electronics, fan-out represents the count of gate inputs that are being driven by the output of a single logic gate.
</li>
	 <li>Typically, clock nets, reset signals, scan lines, and enable networks fall into the category of High Fanout Nets, meaning they connect to a significant number of gate inputs.
</li>
	 <li>A high fan-out scenario entails a substantial capacitance load, which can lead to timing violations. This occurs because the increased capacitance results in extended transition times, ultimately contributing to delays.
</li>
	 <li>To address this issue effectively, the 'set_max_capacitance' function becomes a valuable tool. It assists in either breaking down the high fanout net into smaller segments or buffering it, mitigating the adverse effects on timing performance.
<img  width="1085" alt="lab10" src=""><br><br></li>
</ul>

**Constraints:**
1. **Clock**: The fundamental timing reference for your system.
2. **Generated Clocks (genclk)**: Any additional clocks generated within the design.
3. **Virtual Clocks (vclk)**: If applicable, these represent virtual clock domains.
4. **Clock Practicalities**: Factors like clock uncertainty and latency that affect clock performance.
5. **Input and Output Delays**: Delays introduced at the input and output interfaces.
6. **Signal Transitions**: Considerations related to signal transitions, which impact timing.
7. **Load**: The load imposed on various components.
8. **set_max_capacitance**: A function used to manage high-capacitance loads.
9. **Transition Analysis**: Studying signal transitions for timing optimization.

These elements collectively shape the design and timing behavior of digital systems, warranting careful consideration during the design process.

 **Synthesis Optimization Parameters:**
1. **Boundary Optimization**: Focusing on optimizing the system's interface or boundary to improve its interaction with external components or systems.
2. **Retiming**: A method used to reorganize the placement of flip-flops within a design to achieve better timing and performance characteristics.
3. **Constant Propagation**: Identifying and eliminating unnecessary constants or values in the design to simplify logic and improve efficiency.
4. **Unused Flop Removal**: Identifying and removing flip-flops that are not actively contributing to the functionality of the design, reducing resource consumption.
5. **Isolating Ports**: Managing and isolating ports, ensuring efficient and controlled access to the design's inputs and outputs.

These optimization techniques play a vital role in refining digital designs, streamlining their operation, and enhancing their overall performance.

**Flow:**
1. **read_verilog**: Ingesting and processing the Verilog code that describes the digital design.
2. **provide dbs**: Supplying the necessary design databases or data structures for subsequent analysis and synthesis steps.
3. **source constraints**: Specifying and inputting timing and design constraints to guide the design process.
4. **check_design**: Conducting an initial assessment to ensure design consistency and identify any potential issues.
5. **check_timing**: Evaluating the correctness and sufficiency of the specified timing constraints.
6. **compile or compile_ultra**: Initiating the compilation process to synthesize and optimize the design, with 'compile_ultra' often used for advanced optimization.
7. **report_constraints**: Generating reports that detail the design's adherence to specified constraints, including aspects like power and capacitance.
8. **report_area and report_timing**: Providing insights into the design's physical area utilization and timing characteristics.
9. **write**: Saving or outputting the synthesized design to relevant file formats for further use or integration into the broader system.

This structured workflow ensures a systematic and efficient approach to digital design, from code input to optimization and reporting.

**QOR:**

When evaluating the performance of a design, the Quality of Results (QOR) emerges as a pivotal metric. A high-quality result is achieved when your design not only meets but also surpasses all specified design constraints, leaving comfortable margins for error and variability. In essence, a strong QOR signifies that your design is not just compliant but excels in its performance, offering robustness and reliability.

**report_timig:**
The 'report_timing' command is a vital tool for analyzing timing paths in your design, offering valuable insights into critical parameters such as cell delays, signal transitions, capacitance, and timing slack. By default, this command provides the setup delay of a timing path with two significant digits. Here are various ways to utilize the 'report_timing' command:

report_timing -from DFF_A/clk: Analyzes timing paths starting from the DFF_A/clk signal.
report_timing -from DFF_A/clk -to DFF_C/D: Evaluates timing paths from DFF_A/clk to DFF_C/D.
report_timing -fall_from DFF_A/clk: Focuses on falling-edge transitions from DFF_A/clk.
report_timing -rise_from DFF_B/clk: Concentrates on rising-edge transitions from DFF_B/clk.
report_timing -delay_type min -to DFF_C/D: Specifies the minimum delay and analyzes paths to DFF_C/D.
report_timing -delay_type min -through INV/a: Considers minimum delays and examines paths passing through the INV/a gate.
report_timing -delay_type max -through AND/b: Utilizes maximum delays and investigates paths traversing the AND/b gate.
report_timing -rise_from DFF_B/clk -delay_type max -nets -cap -trans -sig 4: Fine-tunes the analysis by focusing on rising-edge transitions from DFF_B/clk, using maximum delays, and providing detailed information on nets, capacitance, transitions, and signals with a precision of 4 significant digits.

**Example:**

Behavioral code:
<img  width="1085" alt="lab10_1" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day10/lab10_1.png"><br><br>

Constraints to be defined for the design:
<img  width="1085" alt="lab10_2" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day10/lab10_2.png"><br><br>

The image below illustrates the sequential steps involved in synthesizing a netlist from behavioral code. Within this design, there are a total of four flip-flops, each featuring an asynchronous reset.
<img  width="1085" alt="lab10_3" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day10/lab10_3.png"><br><br>

Timing report of setup:
<img  width="1085" alt="lab10_5" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day10/lab10_5.png">
This implies:
- The selected delay type is 'max,' focusing on maximum delays.
- There's a disparity in timing between the launch edge and capture edge.
- The design incorporates a specified library setup time.
- Slack is calculated as the difference between the required time and arrival time.

In the provided image, two separate timing reports are displayed: one considering the 'fall_from' transition in IN_A, and the other focusing on the 'rise_from' transition in IN_A. In this context:
The letter 'r' indicates the rise delay, while 'f' denotes the fall delay for the specified timing path.
Notably, the U14 cell exhibits a shorter delay for the 'rise to fall' arc (113ps) compared to the 'fall to rise' arc (248ps). This discrepancy is attributed to the U14 gate's nature as an inverter, characterized by negative unateness.
The library setup time differs for rise and fall transitions, reflecting the intrinsic characteristics of the library elements.
Within the timing path, there is variation in delay between the 'rise_from' and 'fall_from' transitions.
The slack, a key metric, exhibits a variation of 200ps, signifying the difference between required time and arrival time, thus highlighting timing disparities in the design.
<img  width="1085" alt="lab10_8" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day10/lab10_8.png">
<img  width="1085" alt="lab10_6" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day10/lab10_6.png"><br><br>



<img  width="1085" alt="lab10_6" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day10/lab10_6.png">
<ul>
	<li>This depiction illustrates the 'hold' condition, specifically considering the minimum hold time requirement for a timing path.</li>
	<li>The concept of library hold time is introduced, reflecting a crucial parameter in ensuring proper timing in the design.</li>
	<li>Both the launch edge and capture edge are synchronized, occurring at the same moment in time.</li>
	<li>The slack is calculated as the difference between the arrival time and the required time, helping assess whether the hold condition is met or not for the specified timing path.</li>
</ul>

<img  width="1085" alt="lab10_10" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day10/lab10_10.png">
<img  width="1085" alt="lab10_11" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day10/lab10_11.png">
<ul>
	<li>The timing report highlights variations in cell delay when assessing setup and hold conditions. Specifically, it focuses on the U14 cell.</li>
	<li>For the setup condition at the rising transition, the U14 cell exhibits a delay of 25 ps.</li>
	<li>Conversely, for the hold condition at the falling transition, the cell demonstrates a delay of 60 ps.</li>
	<li>It's worth noting that the cell delay can fluctuate, potentially being either high or low.</li>
	<li>Despite these variations in cell delay, the overall arrival time is evaluated by the path and considered as the worst-violating timing path, emphasizing the significance of addressing timing violations comprehensively.</li>
</ul>
</details>


<details>
	<summary>Labs</summary>

In the image provided, it outlines the sequential steps involved in the process of synthesizing a netlist from a behavioral design. Within this context:
1. The 'check_design' step indicates the presence of a feedthrough path within the design.
2. Notably, there's a direct connection between the input clock and output clock signals, implying a direct linkage between them.
<img  width="1085" alt="lab10_12" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day10/lab10_12.png">
<img  width="1085" alt="lab10_13" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day10/lab10_13.png"><br><br>


In the image provided, the combined output of 'check_timing' and 'report_constraints' is depicted. 'check_timing' serves as a crucial diagnostic tool to determine if the design adheres to its constraints. Within this context, the output highlights whether the design is properly constrained or not, with 'MET' indicating constraints that are met, and unconstrained endpoints listed as such, signifying that constraints for those endpoints have not been defined yet.
Simultaneously, the 'report_constraints' output sheds light on the default constraints that are preloaded into the tool's memory, providing insight into the baseline conditions against which the design is being evaluated.
<img  width="1085" alt="lab10_14" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day10/lab10_14.png">
<img  width="1085" alt="lab10_15" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day10/lab10_15.png"><br><br>

Following the definition of constraints, a subsequent 'check_timing' analysis reveals that several endpoints have been successfully defined. However, it's worth noting that, at this point, only the clock ports remain undefined. This condition is illustrated as follows:
<img  width="1085" alt="lab10_16" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day10/lab10_16.png"><br><br>

The following report shows that the timing paths met the violation:
<img  width="1085" alt="lab10_18" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day10/lab10_18.png">
<img  width="1085" alt="lab10_17" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day10/lab10_17.png"><br><br>

The image below, displaying the 'report_constraints' output, confirms that there is no negative slack detected. This unequivocally indicates that the design satisfies all constraints, categorizing it as 'MET' in terms of its compliance with the specified timing requirements.
<img  width="1085" alt="lab10_19" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day10/lab10_19.png">
<img  width="1085" alt="lab10_20" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day10/lab10_20.png"><br><br>


Now, let's delve into another design, a 128-bit multiplexer. While the code snippet below represents a 4:1 multiplexer, the one above it is a 128:1 multiplexer. Here's the corresponding behavioral code for the design:
<img  width="1085" alt="lab10_22" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day10/lab10_22.png"><br><br>

Let's proceed with reading the design and initiating the netlist synthesis process as outlined below. Although the original design infers the presence of a latch, it's important to note that after synthesis, the resulting netlist will comprise only gates, with any latch elements transformed accordingly.
<img  width="1085" alt="lab10_23" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day10/lab10_23.png"><br><br>

Generated list is a pure combinational logic design:
<img  width="1085" alt="lab10_24" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day10/lab10_24.png"><br><br>

In the provided image, it's evident that there are no sequential cells present in the design. The inference of a latch occurs due to the utilization of an 'always' statement and the assignment of 'y' within a 'for' loop. The 'report_timing' analysis reveals the presence of multiple fanouts, with counts of 16 and 17, among others. It's important to note that a higher fanout count can result in increased capacitance, exemplified by the net with a fanout of 17, which carries a capacitance of 40fF.
<img  width="1085" alt="lab10_25" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day10/lab10_25.png"><br><br>

Check_timing report; The report shows y is unconstrained so the set_max_delay constraints all feedthrough paths so it gets constrained. Now, the timing gets violated.
<img  width="1085" alt="lab10_26" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day10/lab10_26.png"><br><br>

Now, to adhere to a stricter capacitance constraint of 0.025pF, it's essential to address violations on specific nets. These violations become apparent when using the 'report_constraints' command, providing a clear picture of which nets require adjustment to meet the desired capacitance target.
compile_ultra, there is no unconstrained endpoint due to set_max_delay command. 
<img  width="1085" alt="lab10_26" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day10/lab10_26.png"><br><br>

The 'report_constraints' command confirms that all constraints are met, thanks to the defined 'set_max_capacitance' parameter. This feature plays a crucial role in managing high fanout nets, ensuring they are appropriately broken down or buffered. Failing to address poorly loaded nets can potentially lead to critical timing issues within the design.
<img  width="1085" alt="lab10_27" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day10/lab10_27.png"><br><br>

Now, with a capacitance constraint set to be below 25fF for each cell, as depicted in the constraints, a meticulous optimization process takes place. This optimization effort focuses on splitting and optimizing the fanout, thus reducing both transition times and capacitance. The ultimate goal is to significantly reduce cell delays and enhance overall design efficiency.
<img  width="1085" alt="lab10_28" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day10/lab10_28.png">
<img  width="1085" alt="lab10_29" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day10/lab10_29.png"><br><br>

As the number of inputs increases, the fanout of the select line also rises. When this fanout reaches significant levels, it results in what we call a High Fanout Net (HFN). Fanout represents the count of gate inputs that are being driven by the output of a single logic gate. Typically, clock nets, reset signals, scan lines, and enable networks are prime examples of High Fanout Nets.
A high fanout configuration translates to an exceptionally high capacitance load on the net. This heavy loading can lead to timing violations due to the prolonged signal transition times, which subsequently contribute to delay calculation issues. To illustrate this concept, let's consider the following design where the enable pin is combined with the input through an AND operation. Consequently, the load on the enable pin becomes exceedingly high. Below is the corresponding behavioral code:
<img  width="1085" alt="lab10_37" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day10/lab10_37.png"><br><br>

The steps to synthesize the netlist as follows:
<img  width="1085" alt="lab10_38" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day10/lab10_38.png"><br><br>



The report_timing shows the unconstrained path as follows. It has a fanout of 128 which results a high capacitance of 0.2pF.
<img  width="1085" alt="lab10_39" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day10/lab10_39.png"><br><br>



Let us constraint the capacitance to 30fF on current design. So, the capacitance is violated by huge amount as follows: 
<img  width="1085" alt="lab10_40" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day10/lab10_40.png"><br><br>


After compiling the design, the capacitance is now limited to 0.03 pF and fanout is reduced to 17
<img  width="1085" alt="lab10_42" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day10/lab10_42.png"><br><br>



 Design in ddc can be viewed as follows:
 <img  width="1085" alt="lab10_43" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day10/lab10_43.png">
 <img  width="1085" alt="lab10_44" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day10/lab10_44.png"><br><br>


In the current design, the enable signal is no longer directly driving all the cells. Instead, it is selectively driving a specific group of cells through the intermediary of a buffer, as depicted below:
  <img  width="1085" alt="lab10_45" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day10/lab10_45.png"><br><br>


In the provided image, it's evident that the transition hasn't been optimized to its desired level. To address this, we utilize the 'set_max_transition' constraint, aimed at constraining the transition time. Specifically, if the transition time exceeds 0.36 (indicating high transition time), it is constrained to a more favorable value of 0.15.
However, the 'report_constraints' output reveals that the transition constraint is currently violated. The 'cost' value associated with this constraint represents the optimization target that the tool aims to achieve. It's important to note that, in this context, capacitance does not have a cost associated with it, signifying that only the transition time will undergo further optimization efforts to meet the specified constraint.
 <img  width="1085" alt="lab10_46" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day10/lab10_46.png">
 <img  width="1085" alt="lab10_47" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day10/lab10_47.png"><br><br>


The report_constraint shows all the pins violating the transition:
 <img  width="1085" alt="lab10_48" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day10/lab10_48.png"><br><br>


 After compiling the design:
  <img  width="1085" alt="lab10_49" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day10/lab10_49.png"><br><br>


Check_timing shows only the unconstrained endpoints:
  <img  width="1085" alt="lab10_50" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day10/lab10_50.png"><br><br>


  The transition is limited to 150ps in the timing report. 
    <img  width="1085" alt="lab10_52" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day10/lab10_52.png"><br><br>



</details>

## Day-11-Introduction to BabySoc

<details>
	<summary>Introduction</summary>

 **Introduction to System-on-Chip (SoC):** <br>
A System-on-Chip (SoC) is a cutting-edge integrated circuit that encompasses multiple electronic components required for the operation of a computing or electronic device. These components include central processing units (CPUs), graphics processing units (GPUs), memory, input/output interfaces, and more, all consolidated onto a single chip. SoCs have become a cornerstone in modern electronics, powering a wide range of devices, from smartphones and tablets to smart appliances and IoT devices.

**Why Soc:** <br>
System-on-Chip (SoC) technology has gained widespread adoption due to its numerous advantages in the realm of electronic device design and development. Here are some key reasons why SoCs are favored:

1. **Integration of Components**: SoCs consolidate a variety of electronic components onto a single chip. These components can include CPUs, GPUs, memory, input/output interfaces, and more. This integration not only reduces the physical space required but also lowers power consumption and simplifies overall device design.
2. **Space Efficiency**: SoCs are especially valuable in compact devices like smartphones, wearables, IoT devices, and tablets. By combining multiple functions into a single chip, SoCs enable smaller, more streamlined designs.
3. **Power Efficiency**: Integrated components within SoCs can be optimized for energy efficiency. This is crucial for battery-powered devices, as reduced power consumption extends battery life, enhancing the user experience.
4. **Cost Savings**: Employing SoCs can lead to cost-effective solutions. Instead of sourcing and integrating individual components, manufacturers can utilize a single SoC, which often proves more cost-efficient in terms of production and assembly.
5. **Performance**: SoCs are designed to provide high performance for specific tasks. CPUs, GPUs, and other elements can be tailored to meet the performance requirements of the device, resulting in efficient and responsive operation.
6. **Customization**: Manufacturers have the flexibility to customize SoCs to suit their unique requirements. This allows for the optimization of chip architecture and features, leading to improved performance and efficiency.
7. **Reduced Interconnects**: Devices based on SoCs require fewer interconnections, reducing signal propagation delays and potential interference. This can enhance device reliability and performance.
8. **Ease of Development**: Developers benefit from a unified platform when working with SoCs, streamlining both software and hardware development. This simplifies the development process and accelerates time-to-market.
9. **Scalability**: SoC designs can be scaled to accommodate various device configurations. This scalability makes them suitable for a wide range of applications, from low-power IoT devices to high-performance computing systems.
10. **Security**: Many SoCs include built-in security features like hardware encryption and secure boot mechanisms. These features enhance data and device security, safeguarding against security threats.

In summary, SoCs offer a versatile and efficient solution for electronic device design. Their ability to integrate components, optimize power usage, and allow customization makes them a preferred choice for various applications, ranging from consumer electronics to industrial and automotive systems.


**Different Categories of SoCs:** <br>
System-on-Chip (SoCs) come in various forms and cater to diverse applications. Here are three primary types of SoCs: <br>
1. **SoCs with Microcontrollers**: These SoCs revolve around a microcontroller, which is a compact computing device featuring a processor core, memory, and input/output peripherals. Microcontroller-based SoCs are commonly employed in embedded systems and IoT devices for their efficiency in handling simple and specific tasks.
2. **SoCs with Microprocessors**: SoCs that incorporate microprocessors are frequently encountered in smartphones and other computing devices. These microprocessors provide the computing power needed for running complex operating systems and applications, making them suitable for a wide range of consumer electronics.
3. **Specialized Application-Specific Integrated Circuit (ASIC) SoCs**: These SoCs are meticulously designed for particular applications that don't neatly fall into the microcontroller or microprocessor categories. ASIC SoCs are tailored to meet specific performance, power, and functionality requirements, often in fields like automotive, aerospace, and industrial applications.

These distinct categories of SoCs reflect the versatility and adaptability of this technology, accommodating a broad spectrum of applications and devices.

**An Insight into SoC Structure:** <br>
System-on-Chip (SoC) architecture is defined by its hardware functional units, which encompass microprocessors responsible for executing software code. These functional units are seamlessly integrated with a communications subsystem designed to establish connections, exert control, facilitate direction, and manage interfaces between these individual modules.

*Key Components of an SoC Structure::* <br>
1. **Processor Cores**: These are the computing engines at the heart of an SoC. Processor cores execute instructions and perform tasks as dictated by the software running on the device.
2. **Memory**: SoCs feature various types of memory, including RAM and non-volatile storage, to store data, instructions, and application code.
3. **Interfaces**: Interfaces provide the means for the SoC to interact with external components, peripherals, and sensors. They are essential for data exchange and communication.
4. **Digital Signal Processor (DSP)**: DSP units are specialized processing elements optimized for tasks involving signal processing, such as audio and image processing in smartphones and multimedia devices.
5. **Others**: Depending on the specific application, SoCs may include various additional functional components, such as graphics processors (GPUs), hardware accelerators, or security modules.

*Intermodule Communication::* <br>
1. **Bus-Based Communication**: SoCs employ internal buses to facilitate data transfer and communication between various functional units. Buses serve as data highways, allowing components to exchange information.
2. **Network on a Chip (NoC)**: In more complex SoCs, Network on a Chip architectures may be used. NoCs offer a structured and efficient way to manage intermodule communication, particularly in multi-core and high-performance SoC designs.

This SoC structure underscores the intricate integration of hardware components and the importance of seamless communication between these components to ensure the efficient operation of the device across a wide array of applications and functionalities.

**Exploring BabySoC Components:** <br>
The BabySoC comprises several integral components, each contributing to its functionality and capabilities:

1. **RVMYTH**: The RVMYTH core stands as the cornerstone of the BabySoC. It is a simplified RISC-V-based CPU (Central Processing Unit) that executes instructions and performs computational tasks. RVMYTH forms the central processing unit, the "brain" of the SoC.
2. **PLL (Phase-Locked Loop)**: The PLL, or Phase-Locked Loop, is a vital control system within the BabySoC. It operates by generating an output signal whose phase is intricately synchronized with the phase of an input signal. PLLs find extensive utility in synchronization applications, including clock generation and distribution. In the context of SoCs, PLLs play a pivotal role in ensuring precise and synchronized timing across various components.
3. **DAC (Digital-to-Analog Converter)**: The DAC, or Digital-to-Analog Converter, is another indispensable component of the BabySoC. It is responsible for transforming digital signals into analog signals. DACs hold significant importance in modern communication systems, enabling the generation of analog signals from digitally-defined transmission data. This capability is fundamental in processes such as audio playback and signal modulation.

These three core components - RVMYTH, PLL, and DAC - collectively form the foundation of the BabySoC, endowing it with the computational power, synchronization capabilities, and signal conversion prowess needed to execute a wide array of tasks and functions.

**Samsung Exynos 9611 Processor:**

*Overview:*
The Samsung Exynos 9611 is a prominent example of a System-on-Chip (SoC) designed and manufactured by Samsung Electronics. Launched in 2019, the Exynos 9611 is part of the Exynos 7 Series, which targets mid-range smartphones and other mobile devices. This SoC packs a host of advanced features and capabilities, making it a notable player in the mobile computing landscape.
*Architecture:*

CPU <br>
The Exynos 9611 boasts an octa-core CPU architecture, divided into two clusters:
1. High-Performance Cluster (Cortex-A73): Four cores clocked at up to 2.3 GHz. These cores handle resource-intensive tasks such as gaming and multimedia playback, delivering a responsive user experience.
2. Power-Efficient Cluster (Cortex-A53): Four additional cores running at up to 1.7 GHz. These cores handle less demanding tasks to optimize power efficiency and extend battery life.

GPU <br>
For graphics processing, the Exynos 9611 features the Mali-G72 MP3 GPU. This tri-core GPU offers a balance between performance and power efficiency, enabling smooth gaming and multimedia experiences.

AI Capabilities <br>
The SoC incorporates a dedicated neural processing unit (NPU) for AI and machine learning tasks. This enhances various aspects of the device, including camera capabilities, voice recognition, and user experience personalization.

Connectivity <br>
The Exynos 9611 includes an integrated LTE modem, supporting fast data speeds and reliable network connectivity. It also provides support for Wi-Fi, Bluetooth, and NFC, ensuring comprehensive connectivity options for diverse applications.

Camera Support <br>
With support for up to 64-megapixel camera sensors, the Exynos 9611 enables high-quality photography and video recording. It also supports various camera features, including multi-camera setups and advanced image processing.

Display <br>
The SoC is equipped to handle Full HD+ displays with ease, offering vibrant visuals and an immersive viewing experience.

Performance and Efficiency <br>
The Exynos 9611 strikes a balance between performance and power efficiency, making it an ideal choice for mid-range smartphones and mobile devices. Its octa-core CPU architecture, coupled with the Mali-G72 GPU, provides solid performance for everyday tasks, gaming, and multimedia consumption while optimizing power consumption for prolonged battery life.

**Conclusion:** <br>
The Samsung Exynos 9611 processor exemplifies the capabilities of modern SoCs designed for mid-range mobile devices. Its architecture, featuring a robust CPU cluster, efficient GPU, AI capabilities, and comprehensive connectivity options, underscores its suitability for a wide range of applications, offering a compelling user experience.

 
</details>

## Day-12-BabySoC Modelling

<details>
	<summary>Introduction</summary> <br><br>

 **SoC (System on Chip):** <br>
 Soc is a single-die chip that has some different IP cores on it. These IP could vary from microprocessor (completely digital) to 5G broadband modems (completely analog). <br>

 **Modelling:** <br>
 <ul>
	 <li>Modelling and simulation is the use of a physical or logical representation of a given system to generate data and help determine decisions or make predictions about the system.</li>
	 <li>Models are representations that can aid in defining, analyzing and communicating a set of concepts.</li>
 
 </ul> <br>

**Purpose of Modelling:** <br>
System models are specifically developed to:
a. support analysis, specification,
b. design,
c. verification,
d. and validation of a system,
e. as well as to communicate certain information

**What are we modelling?** <br>
Modelling of VSDBabySoC, a System-on-Chip (SoC). In this process, we aim to create a comprehensive model and conduct simulations for VSDBabySoC.
<ul>
	<li>To kick things off, we'll introduce some initial input signals into the VSDBabySoC module. These signals will trigger the phase-locked loop (PLL) to start generating the necessary clock signals for the entire circuit.</li>
	<li>The clock signal, now in action, serves a critical role. It drives the RVMyth processor to execute instructions, resulting in the generation of various values. These generated values play a pivotal role as inputs for the Digital-to-Analog Converter (DAC) core, which is responsible for producing the ultimate output signal aptly named 'OUT.'
</li>
	<li>In essence, our SoC comprises three main elements, each represented as Intellectual Property (IP) cores. These cores, along with a wrapper, come together to form the SoC. Additionally, it's important to mention that there is also a testbench module integrated into the overall design for testing and verification purposes.
</li>
</ul>
We will get to see more structured and coherent explanation of the VSDBabySoC modeling process. <br>

**This week's task is centered around modeling the three primary IP cores::** <br>
1. RVMYTH Modelling
2. PLL Modelling
3. DAC Modelling

Before we dive into the modeling process, let's first gain a comprehensive understanding of how each of these components operates. <br>

**1. RVMYTH - Risc-V based MYTH (Microprocessor for You in Thirty Hours):** <br>
<ul>
	<li>RVMYTH, which stands for RISC-V based Microprocessor for You in Thirty Hours, is built upon the principles of Reduced Instruction Set Computer (RISC). 
</li>
	<li>The RISC-V ISA, pronounced as 'risk-five,' is defined as a fundamental integer ISA (Instruction Set Architecture) that must be present in any RISC-V implementation. This base ISA can be extended with optional add-ons to enhance its capabilities.</li>
	<li>Key characteristics of each base integer instruction set include the width of the integer registers, the size of the address space, and the number of integer registers. There are two primary base integer variants within the RISC-V architecture, namely RV32I and RV64I.</li>
	<li>Within the RISC-V ISA, there are two primary base integer variants, namely RV32I and RV64I:</li>
	<ul>
		<li>RV32I: This variant is characterized by a 32-bit wide integer register file. It offers a 32-bit address space, meaning it can address 2^32 unique memory locations. RV32I provides a balance between performance and code size, making it suitable for a wide range of embedded systems and applications.
</li>
		<li>RV64I: In contrast, RV64I features a 64-bit wide integer register file. It boasts a more extensive 64-bit address space, allowing it to access a much larger memory range. This variant is well-suited for more demanding computational tasks and applications that require larger data sets.
</li>
		The 'I' in both RV32I and RV64I signifies that these are base integer instruction sets, forming the core of the RISC-V architecture. While they share common features, their differences in register width and address space size cater to varying performance and memory requirements.
	</ul>
</ul>
This provides a clearer and more organized explanation of RVMYTH and the RISC-V ISA. <br>

**A simple one cycle CPU for Risc-V:** <br>
<img  width="1085" alt="lab12.1" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day12/lab12.1.jpeg">
A simple one-cycle CPU for RISC-V is a minimalistic central processing unit (CPU) design that executes instructions in a single clock cycle. Here's a basic explanation of how it works:
Fetch:<br>
The CPU begins by fetching the next instruction from memory. In the case of RISC-V, each instruction is a fixed length, typically 32 bits. The CPU reads this instruction from memory into an instruction register.

Decode:<br>
Once the instruction is fetched, the CPU decodes it to determine the operation to be performed and the operands involved. RISC-V instructions have a straightforward encoding, which makes decoding relatively simple.

Execute:<br>
In the one-cycle CPU, the execution of the instruction takes place in the same clock cycle as the fetch and decode stages. This means that the actual operation (e.g., arithmetic, logical, or data transfer) is carried out immediately.

Writeback:<br>
After execution, the result is written back to the appropriate destination, such as a register file or memory location. This ensures that the CPU can store the output or update registers as needed.

Next Instruction:<br>
Finally, the CPU increments the program counter to point to the next instruction in memory, and the process repeats. This allows the CPU to continue fetching, decoding, and executing instructions in a seamless loop.

A one-cycle CPU design is straightforward and efficient but often lacks the performance optimizations found in more complex CPUs. It's typically used in educational settings to teach the fundamentals of CPU architecture. In real-world applications, modern CPUs use pipelining and multiple stages to achieve higher performance. <br>

**2. PLL (Phase Locked Loop):**
**Explanation:** <br>
A Phase-Locked Loop (PLL) is an electronic circuit commonly used in digital systems to generate and control clock signals. It operates by constantly adjusting the frequency and phase of its output signal to match that of an input signal. PLLs have a wide range of applications, including frequency synthesis, clock recovery, modulation, and demodulation. They play a crucial role in many electronic devices, including System-on-Chip (SoC) designs. <br>

**Let's answer few of the questions in detail to get better understand the importance of PLL:**

**A. Why do we need a PLL for our SoC?** <br>
   - *Clock Synchronization:* <br>
In a SoC, various components and subsystems often need to work together at specific time intervals, requiring a synchronized clock signal. A PLL ensures that the clock signal generated for the SoC is stable, precise, and aligned with the desired frequency, enabling reliable operation of the entire system.

   - *Frequency Scaling:* <br>
PLLs can generate clock signals at different frequencies, allowing the SoC to adapt to varying performance requirements. This is essential for power management and optimizing performance in different operational modes.

   - *Clock Domain Crossing:* <br>
In complex SoCs, there can be multiple clock domains with different clock frequencies. PLLs help in synchronizing data between these domains, preventing data corruption and ensuring correct operation.

   - *Reducing Jitter and Noise:* <br>
PLLs are designed to reduce phase noise and jitter in the clock signal, which is critical for high-speed data transfer and signal integrity in digital circuits.

   - *Clock Recovery:* <br>
In communication systems, PLLs are used to recover clock signals from incoming data streams, ensuring accurate data reception. <br>

**B. How is a clock generated?** <br>
Clock signals are generated by electronic circuits known as oscillators. There are various types of oscillators, and one commonly used method is the **Quartz Crystal Oscillator**. Here's how it works:
   - A quartz crystal oscillator relies on the piezoelectric effect in quartz crystals. When a voltage is applied to a quartz crystal, it vibrates at a specific frequency determined by its physical dimensions. <br>

   - The crystal's vibration frequency is highly stable and precise, making it suitable for generating accurate clock signals. <br>

   - The oscillator circuit typically includes amplifiers and feedback mechanisms to sustain the oscillations and maintain a constant frequency. <br>

   - The output of the quartz crystal oscillator is a clean and stable clock signal that can be used as a reference or input to a PLL for frequency synthesis and control. <br>

**C. Why is an off-chip oscillator not good enough for frequencies above 100MHz?** <br>
Off-chip oscillators, such as those in the form of discrete components, are suitable for generating clock signals up to a certain frequency, but they may not be sufficient for higher frequencies (e.g., above 100MHz) due to several reasons:

   - *Signal Integrity:* <br>
At higher frequencies, the transmission of clock signals through external wires and connectors can introduce signal integrity issues, including noise, interference, and attenuation, which can degrade the quality of the clock signal. 

   - *Phase Noise:* <br>
Off-chip oscillators may have higher phase noise, which can affect the precision and stability of the clock signal. PLLs can be used to reduce phase noise.

   - *Jitter:* <br>
Jitter, or variations in the timing of clock edges, becomes more critical at higher frequencies. PLLs can mitigate jitter effects.

   - *Frequency Accuracy:* <br>
Off-chip oscillators may have limitations in achieving precise frequency control and synchronization, which can be essential in SoC designs. <br>

To overcome these challenges and meet the stringent requirements of high-speed digital systems, on-chip PLLs are often used to generate and stabilize clock signals at frequencies above 100MHz within the SoC itself, ensuring reliable and accurate operation. <br>

**D. Why Off-Chip Clocks Can't Be Used All the Time in SoCs:** <br>
Off-chip clocks, generated by external sources, cannot always be relied upon for all aspects of an integrated circuit, especially in the case of System-on-Chip (SoC) designs. Several critical factors necessitate the use of on-chip clock generation and distribution:

1. *Propagation Delays and Signal Quality:* <br>
Clock signals originating from off-chip sources can experience substantial propagation delays when distributed across the chip. Long interconnects and routing can introduce timing uncertainties, leading to synchronization issues and compromised signal quality. This can result in unreliable operation and data corruption in a complex SoC.

2. *Clock Jitter:* <br>
Off-chip clocks are susceptible to clock jitter, which refers to small, unpredictable variations in the clock signal's timing. Jitter can negatively impact the synchronization and stability of various on-chip components, particularly when stringent timing requirements must be met.

3. *Variable Clock Frequencies:* <br>
In SoCs, different blocks and subsystems often operate at varying clock frequencies based on their specific performance requirements. For example, some components may require a 200MHz clock, while others may function optimally at 100MHz. Using a single off-chip clock source for all these diverse requirements is impractical.

4. *Precision and Accuracy:* <br>
Clock accuracy is a critical consideration. When external quartz crystals are used as clock sources, they inherently come with a certain degree of error, typically measured in parts per million (ppm). This error can accumulate when distributed across a large SoC, leading to timing discrepancies that affect system performance.

To address these challenges, SoC designers often implement on-chip Phase-Locked Loops (PLLs) and clock distribution networks. These on-chip PLLs allow for the generation of stable, synchronized, and precise clock signals tailored to the specific needs of different blocks within the SoC. By doing so, designers can minimize the impact of propagation delays, mitigate clock jitter, and ensure that each component operates at its required frequency with high accuracy, thereby maintaining the overall reliability and performance of the integrated circuit. <br>

**What is ppm Error (Parts Per Million)?** <br>
PPM, which stands for parts per million, is a measurement of relative error or variation. It expresses the magnitude of a discrepancy in parts per million between an expected value and an actual value. In the context of electronic devices, including integrated circuits, ppm error is used to quantify how accurate a clock signal generated by a component, such as a quartz crystal oscillator, is when compared to an ideal or reference frequency. <br>
*Example:*
Let's take the example of a 20 ppm quartz crystal oscillator used in watches:

- 20 ppm translates to 20 parts in a million, or 20/1,000,000, which is equivalent to 2e-5 or 0.000002 (0.000002 times the ideal frequency).

- Over the course of one day, which has 86,400 seconds, this 20 ppm error leads to a time discrepancy of 86400 seconds * 2e-5, which equals 1.73 seconds per day.

- Over a month (30 days), this error accumulates to 30 days * 1.73 seconds per day, which results in a loss of approximately 51 seconds, equivalent to 1 minute per month.

Now, consider the impact of ppm error in the context of an integrated circuit (chip):

- In a chip where precision and timing are critical, even very small errors in clock signals can have significant consequences.

- Electronic components within a chip often operate at incredibly high speeds, with processors executing instructions in nanoseconds or even picoseconds (billionths or trillionths of a second).

- A ppm error in the clock signal can cause components to operate slightly out of sync, leading to data corruption, timing failures, and, in some cases, system crashes or malfunctions.

- As a result, chip designers use on-chip Phase-Locked Loops (PLLs) and other clock management techniques to generate and distribute clock signals with minimal ppm error, ensuring precise synchronization and accurate timing throughout the chip's operation.

In summary, ppm error, although seemingly small in absolute terms, can have a significant impact on the performance and reliability of electronic devices, particularly in high-speed systems like microprocessors and integrated circuits. It underscores the importance of precise clock signal generation and management in modern electronic design.

**A PLL Used in SoCs - Main Components:** <br>
<img  width="1085" alt="lab12.2" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day12/lab12.2.jpeg">
1. *Phase Detector (PD):* <br>
   - The Phase Detector is a crucial component of a PLL. Its primary function is to compare the phase of the incoming reference clock (often denoted as "REF") with the phase of the feedback clock (usually labeled "FB").
   
   - It produces an error signal (or phase difference) based on the comparison, which indicates whether the frequencies of the REF and FB clocks are in sync or not.

2. *Loop Filter:* <br>
   - The Loop Filter receives the error signal generated by the Phase Detector. It is responsible for filtering and processing this signal to produce a control voltage.
   
   - The control voltage is used to adjust the frequency and phase of the Voltage-Controlled Oscillator (VCO) to minimize the phase difference between the REF and FB clocks.

3. *Voltage-Controlled Oscillator (VCO):* <br>
   - The Voltage-Controlled Oscillator is a key element of the PLL. It generates the output clock signal (often referred to as "OUT").
   
   - The VCO's frequency can be adjusted by applying a control voltage from the Loop Filter. When the error signal from the Phase Detector is nonzero, it changes the control voltage, causing the VCO to modify its frequency.

4. *Frequency Divider:* <br>
   - The Frequency Divider (or counter) is used to divide the frequency of the VCO's output signal. This division results in a divided output, which can be used as feedback (FB) to the Phase Detector.
   
   - By controlling the division factor, the PLL can achieve frequency multiplication, division, or fractional-N synthesis to generate the desired output frequency. <br>

In summary, a PLL in an SoC is a feedback control system that aims to synchronize and stabilize the output clock signal with respect to an input reference clock. The Phase Detector compares the phases, the Loop Filter processes the error signal, the VCO generates the output clock, and the Frequency Divider controls feedback. These components work together to ensure that the output clock maintains a desired frequency and phase relationship with the reference clock, making PLLs indispensable in modern integrated circuits.

**3. Digital-to-Analog Converter (DAC):** <br>
A Digital-to-Analog Converter (DAC) is an essential electronic component that plays a fundamental role in converting digital signals into analog signals. It takes a digital input, which is typically represented using binary code (combinations of 0s and 1s), and transforms it into a continuous analog output signal. DACs are employed in various applications, from audio reproduction to communication systems, where converting digital data into analog waveforms is necessary.

**Key Features of a DAC:**
- *Binary Inputs:* <br>
A DAC typically consists of multiple binary inputs, each corresponding to a bit in the digital input code. These binary inputs determine the magnitude of the analog output.

- *Power of Two Inputs:* <br>
In most cases, the number of binary inputs in a DAC is a power of two. This choice simplifies the conversion process and allows for precise control of analog output levels.

**Types of DACs:** <br>
There are two primary types of DACs commonly used in electronic systems:
1. *Weighted Resistor DAC:* <br>
   - In a Weighted Resistor DAC, each binary input corresponds to a resistor in the circuit with a specific weight. The resistors are connected in parallel.
   
   - The more significant bits (higher-order bits) control resistors with higher values, while the less significant bits (lower-order bits) control resistors with lower values.
   
   - By adjusting the binary inputs, the combination of resistors contributing to the analog output changes, effectively creating a weighted sum that represents the digital input value.

2. *R-2R Ladder DAC:* <br>
   - An R-2R Ladder DAC employs a unique ladder-like resistor network composed of two resistor values: R and 2R.
   
   - The digital input bits are connected to the ladder's rungs, where switches determine whether to include the resistor (R) or bypass it (2R) in the path.
   
   - By toggling these switches according to the binary code, the DAC calculates the analog output as a weighted sum of the resistor values.

In both types of DACs, the key principle is to use binary codes to control resistor networks and generate an analog voltage output proportional to the digital input. The choice between the two types depends on factors such as precision requirements, cost considerations, and specific application needs. <br>

In summary, DACs are vital components that bridge the digital and analog worlds by converting discrete digital data into continuous analog signals, making them indispensable in various electronic systems and communication devices. The choice of DAC type depends on the specific requirements and constraints of the application at hand. <br>

**Weighted Resistor Digital-to-Analog Converter (DAC):** <br>
<img  width="1085" alt="lab12.3" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day12/lab12.3.jpeg">
A Weighted Resistor DAC is a type of Digital-to-Analog Converter (DAC) that generates an analog output signal proportional to a digital input. It achieves this by employing a specific configuration of binary-weighted resistors within an inverting adder circuit. <br>
*Key Features of a Weighted Resistor DAC:*
- Binary Weighting: <br>
In this DAC, each binary input bit is associated with a resistor whose value is binary-weighted. This means that the resistors have a specific hierarchy, with each resistor representing a different power of 2 (e.g., 2^0, 2^1, 2^2, and so on).

- Inverting Adder Circuit: <br>
The binary-weighted resistors are connected to an inverting adder circuit. This circuit sums the currents or voltages generated by the resistors based on the binary input values. <br>
*How It Works:* <br>
- When a digital input code is applied to the Weighted Resistor DAC, each bit in the code corresponds to a specific binary-weighted resistor.

- The higher-order bits control resistors with higher values, while the lower-order bits control resistors with lower values.

- As the digital input code changes, different combinations of resistors contribute to the overall output voltage.

- The inverting adder circuit takes these currents (or voltages) and combines them in such a way that the output voltage is an analog representation of the digital input code.

In summary, a Weighted Resistor DAC operates by using binary-weighted resistors and an inverting adder circuit to produce an analog output that closely matches the digital input. The choice of binary-weighted resistors allows for precise control over the analog output levels based on the binary code applied to the DAC. This type of DAC is widely used in various applications where accurate digital-to-analog conversion is required. <br>

**R-2R Ladder Digital-to-Analog Converter (DAC):** <br>
<img  width="1085" alt="lab12.4" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day12/lab12.4.jpeg">
The R-2R Ladder DAC is a type of Digital-to-Analog Converter (DAC) that offers advantages over the binary-weighted resistor DAC. It achieves this by utilizing an R-2R ladder network within the inverting adder circuit to generate an analog output signal that closely corresponds to the digital (binary) input. <br>
*Key Features of an R-2R Ladder DAC:*
- R-2R Ladder Network: <br>
This DAC is named after the unique resistor network it employs. In this network, two distinct resistor values are used: R and 2R.

- Inverting Adder Circuit: <br>
Similar to the weighted resistor DAC, the R-2R ladder network is connected to an inverting adder circuit. This circuit is responsible for summing the currents or voltages produced by the resistors based on the binary input values. <br>
*How It Works:* <br>
- When a digital input code is applied to the R-2R Ladder DAC, each bit in the code corresponds to a specific rung on the R-2R ladder network.

- The ladder network is designed such that each rung has two resistors: one with a resistance value of R and the other with 2R. The choice of R and 2R is significant and determines the ladder's unique behavior.

- Depending on the binary input bit (0 or 1), either the R resistor or the 2R resistor on each rung is included in the circuit.

- As the digital input code varies, different combinations of resistors are engaged, altering the current or voltage flowing through the ladder network.

- The inverting adder circuit then combines these currents (or voltages) to produce an analog output voltage that accurately represents the digital input. <br>
*Advantages over Binary-Weighted DAC:* <br>

- The R-2R Ladder DAC offers advantages over the binary-weighted resistor DAC in terms of simplicity and linearity. The use of only two resistor values simplifies manufacturing and calibration.

- It provides excellent linearity and precision, making it suitable for applications demanding high accuracy in digital-to-analog conversion.

In summary, the R-2R Ladder DAC is an innovative approach to digital-to-analog conversion that leverages an R-2R ladder network within an inverting adder circuit. This configuration allows for precise control over the analog output based on the binary input, with the added benefits of simplicity and linearity compared to other DAC designs. <br>





  </details>

<details>
	<summary>Labs</summary>

 **Lab-1:** <br>
 *Consider a 8:1 multiplexer:* <br>
An 8-to-1 multiplexer (often abbreviated as 8:1 MUX) is a digital circuit that has eight data inputs (D0 to D7), one output (Y), three control inputs (A, B, and C), and a single select input (S). Its primary function is to select one of the eight data inputs and route it to the output based on the binary value of the control inputs (A, B, C) provided by the select input (S).

Here's a detailed explanation of how an 8:1 multiplexer works:
1. **Data Inputs (D0 to D7):** An 8:1 MUX has eight data input lines labeled D0 through D7. These are the potential data sources that can be selected and directed to the output.
2. **Output (Y):** The output Y is where the selected data input is sent to. When the multiplexer is configured to choose a specific data input, that input's value appears on the Y output.
3. **Select Input (S):** The select input (S) determines which of the eight data inputs will be selected. It's a 3-bit input, meaning it can take one of eight possible binary values (000, 001, 010, 011, 100, 101, 110, 111), corresponding to the eight data inputs.
4. **Control Inputs (A, B, and C):** These control inputs (A, B, and C) are directly connected to the select input lines. They help specify which of the eight data inputs will be routed to the output based on the binary value of these inputs.
   - If A, B, and C are set to 000, the multiplexer selects D0 as the output.
   - If A, B, and C are set to 001, the multiplexer selects D1 as the output.
   - And so on, up to A=1, B=1, C=1, which selects D7 as the output.
5. **Functionality:** The 8:1 MUX functions as a data selector. Depending on the values of the control inputs (A, B, and C), it routes the data input from one of the eight lines (D0 to D7) to the output Y. The select input (S) specifies which control inputs (A, B, C) should be used to make the selection.

In summary, an 8-to-1 multiplexer is a versatile digital circuit used in various applications, including data routing and selection in digital systems. It can choose from eight data inputs and send the selected data to the output based on the binary value of the control inputs, making it a fundamental building block in digital electronics and computer architecture.

 Verilog code- <br>
 <img  width="1085" alt="lab12_1" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day12/lab12_1.png"><br><br>
The Verilog code provided defines a module named "mux_81," which represents a simple multiplexer (mux). This multiplexer takes an 8-bit input vector `in`, a 3-bit selection vector `sel`, and produces a single output `y`.  <br>
Breaking down the code step by step:

```verilog
module mux_81 (input [7:0] in, input [2:0] sel, output y);
```

- `module mux_81`: This line declares the beginning of a Verilog module named "mux_81." Modules are used to encapsulate and define reusable logic components in a Verilog design.

- `(input [7:0] in, input [2:0] sel, output y)`: This line defines the module's ports. Here's what each part means:
  - `input [7:0] in`: This declares an 8-bit input vector named "in." The `[7:0]` notation specifies that the input vector consists of eight bits, labeled from bit 7 (the most significant bit) to bit 0 (the least significant bit). This is where the data to be selected by the multiplexer is provided.
  - `input [2:0] sel`: This declares a 3-bit input vector named "sel." The `[2:0]` notation specifies that the input vector consists of three bits, labeled from bit 2 to bit 0. This vector is used to select one of the eight data inputs.
  - `output y`: This declares a single output wire named "y." The output "y" will carry the selected data value based on the input vector "sel."

```verilog
assign y = in[sel];
```

- `assign y = in[sel];`: This line defines the behavior of the mux_81 module. It uses an "assign" statement to specify that the output wire "y" is equal to the value of one of the bits in the input vector "in," determined by the value of the selection vector "sel."


   - `in[sel]`: This expression selects a specific bit from the "in" vector based on the binary value represented by the "sel" vector. For example, if `sel` is 3'b001 (binary value 1), it selects the second bit (bit 1) from the "in" vector, and that value is assigned to "y."


In summary, the "mux_81" module represents a multiplexer that selects one of the eight inputs (from "in") based on the 3-bit control input "sel" and routes the selected value to the output wire "y." This code is a concise representation of a multiplexer's functionality in Verilog. <br><br>

 Testbench code- <br>
 <img  width="1085" alt="lab12_2" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day12/lab12_2.png"><br><br>
Signal Declarations: <br>
In the testbench module tb_mux81, signals are declared to mimic the inputs and outputs of the mux_81 module. These include in (the 8-bit data input), sel (the 3-bit selection input), and y (the output wire).

Module Instantiation: <br>
The mux_generate module (uut) is instantiated within the testbench. It connects the testbench signals to the module's ports.


Test Input Values: <br>
Inside the initial block, test cases are defined to verify the behavior of the mux_generate module. Two test cases are provided as examples: <br>

Case 1: It selects input 0 (sel = 3'b000) and applies an 8-bit data input of 8'b10101010. <br>
Case 2: It selects input 3 (sel = 3'b011) and applies an 8-bit data input of 8'b11001100. <br>

Simulation Termination: <br>
The simulation is finished using $finish to conclude the testbench after all test cases are executed.

This testbench checks the functionality of the mux_81 module by applying different input combinations and verifying that the output y corresponds to the selected input according to the values of sel. You can extend the test cases as needed to thoroughly test the module's behavior. <br><br>

Explanation of VCD Dumping Code: <br>
$dumpfile("tb_mux81.vcd"): This line specifies the name of the VCD file where the simulation results will be saved. We can choose any suitable file name, here it is 'tb_mux81.vcd".

$dumpvars(0, tb_mux81): This line instructs the simulator to dump the values of all signals within the tb_mux81 module (including signals inside the mux_81 module if they are instantiated within the testbench). The 0 argument indicates that dumping starts at time 0. <br>


Simulation using gtkwave- <br>
<img  width="1085" alt="lab12_3" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day12/lab12_3.png"><br><br>

**Lab-2:** <br>
*Modelling of BabySoc:* <br>

 Step-1: Modelling rvmyth <br>
 commands involved- <br>
 ```ruby
iverilog mythcore_test.v tb_mythcore_test.v 
./a.out
gtkwave tb_mythcore_test.vcd
```

Simulation output using gtkwave- <br>
<img  width="1085" alt="lab12_8" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day12/lab12_8.png">
*10-bit Digital Output (D) in RVMyth:*
The 10-bit digital output 'D' in RVMyth is a dynamic representation of the cumulative sum of natural numbers computed by the processor. This processor operates in a continuous loop, adding natural numbers until the sum surpasses 999, at which point it reverses its operation and subtracts the natural numbers in reverse order. 'D' provides insight into the current state of this computational process, serving as an indicator of the ongoing operations within the RVMyth RISC-V processor. <br>

Step-2: Modelling DAC <br>
commands involved- <br>
 ```ruby
iverilog avsddac.v avsddac_tb_test.v
./a.out
gtkwave avsddac_tb_test.vcd
```

Simulation output using gtkwave- <br>
<img  width="1085" alt="lab12_9" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day12/lab12_9.png">
*10-Bit Digital-to-Analog Converter (DAC):*
This 10-bit DAC takes digital input D[9:0] and converts it into an analog voltage signal. It operates with a voltage range of Vhigh (3.3V) and Vlow (0V). For example, if the input D[9:0] is 111111011, which is equivalent to 1019, the output is calculated as: <br>
```ruby
Out = Vref * (1019/1024) = 3.2878986 volts.
```
This calculated output voltage aligns accurately with the expected values, as verified using gtkwave. <br>


Step-3: Modelling PLL <br>
commands involved- <br>
 ```ruby
iverilog avsd_pll_1v8.v pll_tb.v
./a.out
gtkwave test.vcd
```

Simulation output using gtkwave- <br>
<img  width="1085" alt="lab12_15" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day12/lab12_15.png"><br><br>

Step-4: Modelling rvmyth and DAC interface <br>
commands involved- <br>
 ```ruby
verilog rvmyth_avsddac.v rvmyth_avsddac_TB.v
./a.out
gtkwave rvmyth_avsddac.vcd
```

Simulation output using gtkwave- <br>
<img  width="1085" alt="lab12_13" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day12/lab12_13.png"><br><br>

Step-5: Modelling rvmyth and PLL interface <br>
commands involved- <br>
 ```ruby
iverilog rvmyth_pll.v rvmyth_pll_tb.v
./a.out
gtkwave test1.vcd
```

Simulation output using gtkwave- <br>
<img  width="1085" alt="lab12_16" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day12/lab12_16.png"><br><br>

Step-6: Interfacing all the modules <br>
commands involved- <br>
 ```ruby
iverilog vsdbabysoc.v testbench.v mythcore_test.v avsddac.v avsdpll.v 
./a.out
gtkwave dump.vcd
```

Simulation output using gtkwave- <br>
<img  width="1085" alt="lab12_17" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day12/lab12_17.png"><br><br>




</details>

## Day-13-Post Synthesis Simulation

<details>
	<summary>Introduction</summary>

**Synthesis:** <br>
Synthesis, within the realm of digital integrated circuit design, is the pivotal process of transforming a high-level description of a hardware design into a lower-level representation that comprises logic gates and flip-flops. 

**Pre-Synthesis:** <br>
The pre-synthesis phase in digital circuit design is a critical step that occurs before the actual synthesis process. It involves several technical tasks and activities aimed at preparing the design for synthesis, which ultimately leads to the creation of the physical hardware. 

**Post-Synthesis:** <br>
The post-synthesis phase in digital circuit design occurs after the synthesis process has translated the high-level RTL (Register-Transfer Level) design into a gate-level representation. This phase involves a set of technical tasks and activities aimed at further refining and optimizing the design, ensuring that it meets performance, area, and power constraints.

**Why do pre-synthesis? Why not just do post-synthesis?** <br>
Pre-synthesis and post-synthesis simulations serve different purposes in the design and verification of digital circuits. Both have their own advantages and are essential at different stages of the design process. Let's explore why both are important:

1. **Pre-Synthesis Simulation**: <br>
   - **Functionality Focus**: Pre-synthesis simulation is primarily focused on verifying the logical functionality of the design. It checks whether the design operates as intended based on the high-level RTL (Register Transfer Level) description.
   - **Early Validation**: It allows designers to catch and correct logical errors and functional issues before the design is synthesized. This is crucial for identifying and fixing design flaws early in the development cycle, which can save a lot of time and resources.
   - **Fast Execution**: Pre-synthesis simulations are usually faster than post-synthesis simulations because they don't consider gate-level delays and are closer to the original RTL code.

2. **Post-Synthesis Simulation**: <br>
   - **Timing Analysis**: Post-synthesis simulation considers gate-level delays, which means it takes into account the actual propagation delays of logic gates, interconnects, and other physical components. This helps in analyzing the timing behavior of the design.
   - **Accurate Timing Violation Detection**: It can detect and report timing violations such as setup and hold time violations, clock-to-q delays, and other timing-related issues. This is essential for ensuring that the design meets the required performance criteria.
   - **Power Analysis**: Post-synthesis simulations can also provide insights into power consumption, which is important for battery-powered or low-power designs.
   - **Realistic Behavior**: It provides a more realistic view of how the design will behave once implemented in hardware.

3. **Mismatch Detection**: <br>
   - Both pre-synthesis and post-synthesis simulations are used to detect mismatches, but they focus on different aspects. Pre-synthesis simulation can identify logical mismatches early in the design phase, while post-synthesis simulation helps identify timing-related mismatches and issues caused by incorrect usage of operators and inference of latches.

In summary, pre-synthesis simulation is essential for early design validation and catching logical errors, while post-synthesis simulation is crucial for ensuring that the design meets timing requirements and for obtaining a realistic view of how the design will perform in hardware. Both types of simulation are complementary and necessary for a comprehensive design verification process.

**GLS: a brief introduction:** <br>
  - **Gate Level Perspective**: The term "gate level" refers to the netlist representation of a circuit, typically generated through logic synthesis.
  - **Timing in the Design Flow**: While RTL simulation takes place prior to synthesis, GLS is conducted after synthesis has transformed the design. 
  - **Comprehensive Netlist**: The netlist view encompasses a detailed connection list that includes gates and IP models, complete with their functional and timing characteristics.
  - **Simulation Environments**: RTL simulation operates within a zero-delay environment, where events primarily occur on the active clock edge. On the other hand, GLS can be configured for zero delay but is often utilized in unit delay or full timing modes.
  - **Confidence in Implementation**: Gate level simulation serves as a critical step in the verification process, enhancing confidence in the design's practical implementation. It excels in verifying dynamic circuit behavior, a task that static methods like RTL simulation cannot accurately accomplish.


</details>

<details>
	<summary>Post-Synthesis of 8:1 Multiplexer</summary> <br>

 **Gate level Simulation:** <br>

 The 8:1 multiplexer output discussed in the pre-synthesis simulation matches the post-synthesis simulation output. 
 The following are the sequence of steps for simulating the output:
 
 ```ruby
iverilog <netlist_file_name> <testbench>
./a.out
gtkwave <vcd_file_name>
```

The 'iverilog' command utilizes the simulated gate-level netlist and the same testbench for post-synthesis simulation. Running './a.out' generates a VCD format file corresponding to the netlist, which can be viewed using 'gtkwave'.
The post-simulaation output is as follows: <br>
<img  width="1085" alt="lab13_21" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day13/lab13_21.png"><br>
Thus the exact match between the post-synthesis and pre-synthesis outputs verifies the logical correctness of the design. 




**Synthesis of 8:1 Multiplexer using DC shell:** <br>
The following are the sequence of steps:
```ruby
set target_library <path_of_the_target_library>
set linl_library {* <path_of_the_target_library>}
read_verilog <file_name.v>
link
compile_ultra
write -f verilog -out mux81_net.v
write -f ddc -out mux81.vcd
```
The schematic of 8:1 Multiplexer in design vision: <br>
<img  width="1085" alt="lab13_22" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day13/lab13_22.png"><br>


</details>

<details>
	<summary>Post Synthesis of BabySoC</summary>

BabySoc consists of three IP's-
1. RVMYTH
2. DAC
3. PLL <br>
Here only RVMYTH is synthesizable and not DAC nor PLL.

So here is the post-synthesis output of RISC-V processor RVMYTH is as follows: <br>
<img  width="1085" alt="lab13_14" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day13/lab13_14.png">
We observe that the functionality remains consistent with the one compared to the pre-synthesis stage, where it calculates the sum of the first n natural numbers up to 1000 and then decrements in the same manner.
The following are the sequence of steps:
```ruby
set target_library <path_of_the_target_library>
set linl_library {* <path_of_the_target_library>}
read_verilog mythcore_test.v
link
compile_ultra
write -f verilog -out rvmyth_net.v
```
The netlist written here as 'out' represents the default output 'clk_gate' in the code. Hence, the 'current_design' is switched to 'core' and the resulting netlist is written out as follows: <br>
```ruby
current_design core
write -f verilog -out rvmyth_net.v
```
The processor's output increments in the same manner as it did at the pre-synthesis stage, confirming the proper definition of logic. 
The following commands are used to simulate the output waveform: <br>
```ruby
iverilog -DFUNCTIONAL -DUNIT_DELAY=#1 rvmyth_net.v tb_mythcore_test.v primitives.v sky130_fd_sc_hdd.v
./a.out
gtkwave tb_mythcore_test.vcd
```

**BabySoC post-synthesis:** <br>
Since only RVMYTH is synthesizable, we proceed to synthesis 'rvmyth' and subsequently verify its functionality with 'DAC' and 'PLL'.
The following are the sequence of steps:
```ruby
set target_library <path_of_the_target_library>
set linl_library {* <path_of_the_target_library>}
read_verilog mythcore_test.v
link
compile_ultra
write -f verilog -out rvmyth_net.v
```
```ruby
iverilog -DFUNCTIONAL -DUNIT_DELAY=#1 rvmyth_net.v vsdbabysoc.v testbench.v avsddac.v avsdpll.v primitives.v sky130_fd_sc_hdd.v
./a.out
gtkwave dump.vcd
```
<img  width="1085" alt="lab13_16" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day13/lab13_16.png">
We observe that the outputs of both pre-synthesis and post-synthesis simulations match, confirming the logical correctness of the design.
</details>


## Day-14-Synopsys DC and Timing Analysis

<details>
	<summary>Introduction</summary> <br>

 **What is PVT?:** <br>
 PVT stands for Process, Voltage and Temperature. We can think of these factors as the 'environment' in which electronic chips or circuits operate.
 <ul>
	 <li>Process: <br>
	 This refers to how a chip is manufactured and the tiny details in it's design. It's like the recipe and ingredients used to bake a cake. Different manufacturing processes can create chips with varying performace and power characteristics.</li>
	 <li>Voltage: <br>
	 It is like the electrical pressure that powers the chip. Just like our electronic devices need the right voltage from batteries or power outlets to work properly, chips need a specific voltage level to function correctly.</li>
	 <li>Temperature: <br>
	 Temperature is how hot or cold the chip becomes during operation. Like how a car engine can overheat if it gets too hot, chips can malfunction if they get too hot or too cold.</li>

"PVT testing" or "PVT conditions," they are essentially referring to the specific combination of the manufacturing process, the electrical voltage supplied, and the temperature at which a device is tested or operates. Ensuring that a device can perform well under different PVT conditions is important for making sure it works reliably in various real-world situations.
 </ul>

 **Corners of PVT:** <br>
*Designing Robust Integrated Circuits*:
  - Integrated circuits (ICs) are meticulously designed to operate effectively across a broad spectrum of temperatures and voltages, rather than being optimized for just one specific set of conditions.

*Testing Under Diverse Conditions*:
  - To ensure that our ICs perform reliably under a wide range of real-world scenarios, we subject them to various combinations of process, voltage, and temperature conditions during simulation.

*Defining Corners*:
  - These specific combinations of process, voltage, and temperature conditions are referred to as "corners." Each corner represents a distinct set of conditions that the IC may encounter in its operational environment.

*Impact on Delay*:
  - It's important to note that all three parameters—process, voltage, and temperature—directly influence the signal propagation delay of the individual circuit cells within the IC. Understanding these effects is crucial for optimizing performance and reliability.
 
  
In semiconductor design and testing, "corners" refer to different combinations of Process, Voltage, and Temperature (PVT) conditions. These corners are used to evaluate how a chip or integrated circuit (IC) performs under a range of real-world operating conditions. Let's delve into greater detail about PVT corners:

1. **Process Corner**: 
   - *Definition*: The process corner represents variations in the manufacturing process itself. It accounts for differences in factors like doping levels, oxide thickness, and other fabrication parameters.
   - *Types*: There are typically three main process corners:
     - *Nominal (Typical)*: This represents the expected or ideal process conditions. It assumes that the manufacturing process is performing as intended.
     - *Slow Process (SS)*: This corner simulates the worst-case scenario, where the manufacturing process results in slower transistors and circuits. It accounts for variations that can lead to reduced performance.
     - *Fast Process (FF)*: This corner represents a best-case scenario, where the manufacturing process produces faster-than-expected transistors and circuits. It accounts for variations that can lead to improved performance.

2. **Voltage Corner**:
   - *Definition*: The voltage corner deals with variations in the supply voltage (Vdd) supplied to the chip. Different voltage corners help evaluate how the chip behaves when the voltage is not at its nominal level.
   - *Types*: Voltage corners include:
     - *Nominal Voltage*: This represents the normal operating voltage for the chip.
     - *Lower Voltage (LV)*: This corner tests the chip's performance when the supply voltage is lower than normal. It helps assess power efficiency and how the chip handles reduced power.
     - *Higher Voltage (HV)*: This corner evaluates the chip's performance when the supply voltage is higher than normal. It helps assess how the chip handles over-voltage conditions but may lead to increased power consumption.

3. **Temperature Corner**:
   - *Definition*: The temperature corner considers variations in the operating temperature of the chip. Temperature can significantly impact a chip's performance and reliability.
   - *Types*: Temperature corners include:
     - *Nominal Temperature*: This represents the expected operating temperature for the chip.
     - *Low Temperature (LT)*: This corner tests the chip's behavior in cold conditions, which can affect its speed and power consumption.
     - *High Temperature (HT)*: This corner assesses the chip's performance and reliability in hot conditions, which can lead to overheating and potential reliability issues.

PVT corners are crucial for ensuring that a semiconductor device or IC works reliably across a range of conditions. By testing chips under different PVT corners, designers and engineers can identify potential issues, optimize performance, and ensure that the final product meets its specifications and can withstand real-world variations in process, voltage, and temperature. This comprehensive testing is essential for producing high-quality electronic devices that perform consistently in various environments and use cases.

 **Understanding PVT:** <br>
*Process Variation*:
- In modern integrated circuits (ICs), which can contain millions or even billions of transistors, uniformity is a significant challenge. Not all transistors on a chip will have identical characteristics due to variations in the manufacturing process. This is referred to as "process variation."
- During the fabrication of the chip, variations can occur in parameters such as transistor size, threshold voltage, and other electrical properties. These variations are often caused by slight imperfections or fluctuations in the manufacturing equipment.
- Process variation is a fundamental concern, especially as semiconductor technology advances to smaller nodes (finer manufacturing processes). These smaller nodes are more sensitive to process variations, making it critical to account for them in chip design.

*Voltage Variation*:
- The supply voltage (Vdd) to a chip is a crucial factor in its operation. However, as semiconductor technology advances to smaller nodes, the supply voltage tends to decrease to improve power efficiency and reduce heat generation.
- For example, if a chip is designed to operate at 1.2 volts (V), there is a possibility that the actual voltage supplied to the chip may fluctuate at certain times. These voltage variations can be caused by factors like power management techniques, power delivery network quality, or external conditions.

*Temperature Variation*:
- The temperature of a chip is not constant during its operation; it can vary across the chip's surface. This variation in temperature is primarily a result of the power dissipation in the MOS (Metal-Oxide-Semiconductor) transistors within the chip.
- When transistors are active and processing data, they consume electrical power, and this consumption generates heat. The heat generated can cause localized temperature variations.
- Temperature variations can impact the speed and reliability of a chip. Some regions may become hotter than others, affecting the performance of circuits in those areas.

Understanding these PVT factors is critical for semiconductor designers and engineers because they directly influence how a chip performs under real-world conditions. To ensure the reliability and functionality of a chip across a range of scenarios, designers conduct extensive testing and simulation under different PVT conditions, known as PVT corners. This testing helps identify potential issues, optimize performance, and ensure that the chip can operate successfully in diverse environments, despite the inherent variations in process, voltage, and temperature.

 **PVT Graphs:** <br>
<img  width="1085" alt="pvt_graphs" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day14/pvt_graphs.jpeg">

</details>

<details>
	<summary>Labs</summary>

**Objective:** <br>
Objective is to evaluate how our designed circuit's timing behaves under different conditions: Process (manufacturing variations), Voltage (power supply fluctuations), and Temperature (heat variations), collectively referred to as PVT corners. Understanding how these factors affect our circuit's performance is crucial for ensuring its reliability and adherence to specified timing requirements.

During our analysis, we synthesized the design while considering various PVT corners. Our focus was on three key timing parameters: Total Negative Slack (TNS), Worst Negative Slack (WNS), and Worst Hold Slack (WHS). TNS provides an overall assessment of timing issues across the entire design, while WNS and WHS help pinpoint the most critical timing challenges, such as setup and hold violations.

Step-1: Transforming .lib Files into .db Format for Synthesis: <br>
In preparation for the synthesis process using Synopsys Design Compiler (dc_shell), it is essential to convert the required .lib files into a compatible .db format using lc_shell.
Procedure- <br>
```ruby
read_lib <library_name>
write_lib <library_name> -f db -o <name_of_the_db_file>
```

Step-2: To create a constraint file: <br>
```ruby
 set_units -time ns
create_clock -name MYCLK -per 2 [get_pins {pll/CLK}];

set_clock_latency -source 1 [get_clocks MYCLK]
set_clock_uncertainty -setup 0.5 [get_clocks MYCLK]; 
set_clock_uncertainty -hold 0.4 [get_clocks MYCLK]; 

set_input_delay -max 1 -clock \[get_clocks MYCLK] [all_inputs];
set_input_delay -min 0.5 -clock \[get_clocks MYCLK] [all_inputs];
set_output_delay -max 1 -clock \[get_clocks MYCLK] [all_outputs];
set_output_delay -min 0.5 -clock \[get_clocks MYCLK] [all_outputs];

set_input_transition -max 0.2 \[all_inputs];
set_input_transition -min 0.1 \[all_inputs];

set_max_area  800;

set_load -max 0.2 \[all_outputs];
set_load -min 0.1 \[all_outputs];
```

Step-3: Configure the necessary database files (sky130.db, avsddac.db, avsdpll.db), read the design, link the library, and initiate the compile_ultra process:
```ruby
set target_library { <sky130_PVT_corner> , avsddac.db , avsdpll.db}
set link_library {* sky130_PVT_corner> , avsddac.db , avsdpll.db}
read_verilog vsdbabysoc.v
link
source <constraints_file_name>
compile_ultra
report_qor
```

The images below illustrates the setup delay and quality of results (QoR) for different PVT corners:
1. sky130_fd_sc_hd__ff_100C_1v65 <br>
<img  width="1085" alt="db1_1" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day14/db1_1.png">
<img  width="1085" alt="db2_1" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day14/db2_1.png"> <br><br>

2. sky130_fd_sc_hd__ff_100C_1v95
<img  width="1085" alt="db1_2" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day14/db1_2.png">
<img  width="1085" alt="db2_2" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day14/db2_2.png"> <br><br>

3. sky130_fd_sc_hd__ff_n40C_1v56
<img  width="1085" alt="db1_3" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day14/db1_3.png">
<img  width="1085" alt="db2_3" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day14/db2_3.png"> <br><br>

4. sky130_fd_sc_hd__ff_n40C_1v65
<img  width="1085" alt="db1_4" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day14/db1_4.png">
<img  width="1085" alt="db2_4" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day14/db2_4.png"> <br><br>

5. sky130_fd_sc_hd__ff_n40C_1v76
<img  width="1085" alt="db1_5" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day14/db1_5.png">
<img  width="1085" alt="db2_5" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day14/db2_5.png"> <br><br>

6. sky130_fd_sc_hd__ss_100C_1v40
<img  width="1085" alt="db1_6" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day14/db1_6.png">
<img  width="1085" alt="db2_6" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day14/db2_6.png"> <br><br>

7.  sky130_fd_sc_hd__ss_100C_1v60
<img  width="1085" alt="db1_7" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day14/db1_7.png">
<img  width="1085" alt="db2_7" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day14/db2_7.png"> <br><br>

8. sky130_fd_sc_hd__ss_n40C_1v28
<img  width="1085" alt="db1_8" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day14/db1_8.png">
<img  width="1085" alt="db2_8" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day14/db1_8.png"> <br><br>

9. sky130_fd_sc_hd__ss_n40C_1v35
<img  width="1085" alt="db1_9" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day14/db1_9.png">
<img  width="1085" alt="db2_9" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day14/db2_9.png"> <br><br>

10. sky130_fd_sc_hd__ss_n40C_1v40
<img  width="1085" alt="db1_10" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day14/db1_10.png">
<img  width="1085" alt="db2_10" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day14/db2_10.png"> <br><br>

11. sky130_fd_sc_hd__ss_n40C_v44
<img  width="1085" alt="db1_11" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day14/db1_11.png">
<img  width="1085" alt="db2_11" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day14/db2_11.png"> <br><br>

12. sky130_fd_sc_hd__ss_n40C_1v76
<img  width="1085" alt="db1_12" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day14/db1_12.png">
<img  width="1085" alt="db2_12" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day14/db2_12.png"> <br><br>

13. sky130_fd_sc_hd__tt_025C_1v80
<img  width="1085" alt="db1_13" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day14/db1_13.png">
<img  width="1085" alt="db2_13" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day14/db2_13.png"> <br><br>

**Table and Graph for setup:**
<img  width="1085" alt="setup_1" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day14/setup_1.png">
<img  width="1085" alt="setup_2" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day14/setup_2.png"> <br><br>


**Table and Graph for hold:**
<img  width="1085" alt="hold_1" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day14/hold_1.png">
<img  width="1085" alt="hold_2" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day14/hold_2.png"> <br><br>

**Conclusions drawn:**
Hold violations and setup issues are common challenges in digital circuit design. Here's a breakdown of their characteristics and some insight into specific process, voltage, and temperature (PVT) corners:

1. **Hold Violations**: These are more likely to occur in faster cells. Hold time is the minimum amount of time that data must be stable before the clock edge to be reliably captured by a flip-flop. Faster cells process data quickly, leaving less time for data to stabilize. Hence, they are more susceptible to hold violations.

2. **Setup Issues**: Conversely, setup issues tend to arise in slower cells. Setup time is the minimum time that data must be stable after the clock edge to be correctly captured. Slower cells need a longer setup time because they process data more slowly, which can lead to setup violations if not met.

Now, about PVT corners:

- **Worst Setup Corner**: The most critical PVT corner for setup is sky130_fd_sc_hd__ss_n40C_1v28. This means slow process (ss), low temperature (n40C), and a supply voltage of 1.28 volts. If we can ensure that our design meets timing requirements in this challenging corner, it's likely to perform well in all other corners, providing robustness across varying conditions.

- **Best PVT Corner**: On the other hand, the best PVT corner is sky130_fd_sc_hd__ff_n40C_1v76. In this corner, there are no setup violations, and hold violations are minimal. It's considered the most favorable condition because it offers the best overall performance and reliability.


</details>

## Day-15-Inception of open-source EDA, openLANE and sky130PDK


<details>
	<summary>Introduction</summary>

**Simpliflied RTL to GDS2 flow:** <br>
<img  width="1085" alt="WhatsApp Image 2023-10-08 at 18.32.17.jpeg" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/WhatsApp%20Image%202023-10-08%20at%2018.32.17.jpeg">
The RTL to GDS2 flow is a comprehensive process utilized in semiconductor design to transform a high-level hardware description of a digital integrated circuit into a physical layout ready for manufacturing. This intricate journey can be summarized as follows:

RTL Design: <br>
At the outset, designers create a high-level description of the digital circuit's functionality using hardware description languages (HDL) like VHDL or Verilog. This description, known as Register Transfer Level (RTL) code, defines how data is processed and transferred within the circuit.

Synthesis: <br>
The RTL code undergoes synthesis using specialized tools like Synopsys Design Compiler or Cadence Genus. These tools convert the logical RTL description into a gate-level netlist, optimizing for area, power, and timing while adhering to performance requirements.

Floor Planning: <br>
The gate-level netlist serves as the foundation for creating a floorplan. Designers allocate space for functional blocks, standard cells, I/O pads, and establish chip dimensions within the silicon wafer.

Placement: <br>
Placement involves physically arranging the synthesized gates on the chip according to the floorplan. This step aims to minimize wire lengths and optimize signal timing.

Clock Tree Synthesis (CTS): <br>
To ensure synchronous operation, CTS creates a clock distribution network, delivering clock signals with minimal skew to all flip-flops and registers.

Routing: <br>
Routing involves the creation of metal interconnects (wires) that connect various components on the chip to establish logical connections. It must satisfy timing constraints, minimize congestion, and comply with design rules.

Design for Manufacturing (DFM): <br>
DFM checks ensure that the layout adheres to manufacturing constraints, encompassing minimum feature sizes, spacing rules, and design rule checks (DRC) to guarantee manufacturability.

Design for Test (DFT): <br>
DFT techniques are applied to enable efficient testing and debugging of the chip, including the insertion of test logic and scan chains.

Sign-off: <br>
Multiple sign-off steps are conducted, including timing analysis, power analysis, and physical verification (DRC and LVS) to validate the design's compliance with specifications and manufacturability.

GDS2 Generation: <br>
Once the design passes all sign-off checks, the final layout data is generated in GDSII format, a standard used for mask data sent to the semiconductor foundry for manufacturing.

Tapeout: <br>
The GDS2 data is prepared for tapeout, involving the packaging of necessary files and documentation for submission to the foundry, marking a crucial milestone before fabrication begins.

Manufacturing: <br>
The semiconductor foundry employs the GDS2 data to create physical masks necessary for manufacturing the integrated circuit on silicon wafers.

Packaging and Testing: <br>
Following manufacturing, chips are packaged, and rigorous testing is conducted to ensure they meet specifications and operate as intended.

The RTL to GDS2 flow is a highly intricate and collaborative process, requiring expertise, state-of-the-art tools, and rigorous quality checks at each stage to produce a functional and manufacturable integrated circuit.

The openLANE flow takes in the rtl from your design and the PDK's provided by the foundry; then everything else is automated.


**openLANE Architecture:** <br>
<img  width="1085" alt="WhatsApp Image 2023-10-08 at 18.32.51.jpeg" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/WhatsApp%20Image%202023-10-08%20at%2018.32.51.jpeg">
<img  width="1085" alt="WhatsApp Image 2023-10-08 at 18.34.50.jpeg" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/WhatsApp%20Image%202023-10-08%20at%2018.34.50.jpeg">
<img  width="1085" alt="WhatsApp Image 2023-10-08 at 18.35.28.jpeg" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/WhatsApp%20Image%202023-10-08%20at%2018.35.28.jpeg">

OpenLANE's architecture is built upon a stack of open-source EDA (Electronic Design Automation) tools, libraries, and resources, making it accessible to a wide range of designers and researchers. It provides an efficient and automated flow for ASIC design, promoting collaboration and innovation in the field of semiconductor design.

**Introduction to QFN-48 Package, chip, pads, core, die and IP's** <br>
QFN-48 Package: <br>
The QFN-48 package is a type of surface-mount integrated circuit (IC) package. The "48" signifies the total number of electrical connections or pins available on the package.
These packages are widely used in electronics due to their compact size, efficient heat dissipation, and absence of traditional through-hole leads.

Chip: <br>
Within the context of a QFN-48 package, the term "chip" refers to the actual integrated circuit. It contains the functional electronic components responsible for executing specific tasks, such as logic operations or data storage.
Fabricated on a semiconductor wafer, the chip serves as the heart of the IC package.

Pads: <br>
Pads are metallic contact points situated on the underside of the QFN-48 package. These pads facilitate electrical connections between the integrated circuit and the Printed Circuit Board (PCB) on which it is mounted.
The number of pads corresponds to the total number of pins or connections required for the IC to interact with external circuitry.

Core: <br>
In the context of the QFN-48 package, the "core" typically refers to the central region of the package. It may not contain active electrical connections but could play a role in mechanical stability or thermal management.
Some QFN packages use the core area for heat dissipation, especially in ICs with high power consumption.

Die: <br>
The "die" is the term for the semiconductor chip or integrated circuit in its unpackaged form. It is essentially the silicon wafer on which the functional electronic components are fabricated.
The die is much smaller than the final packaged IC and is mounted within the package during the packaging process, connecting to the pads for external connectivity.

IPs (Intellectual Properties): <br>
IPs, in the context of semiconductor design, represent pre-designed and pre-verified blocks of intellectual property. These blocks can include various functionalities such as CPU cores, memory controllers, or specialized hardware accelerators.
Designers integrate IPs into their IC designs to save time and resources, as they provide pre-made and tested components that enhance the capabilities of the IC.

In summary, a QFN-48 package is a specific type of IC package with 48 electrical pads for connecting the integrated circuit (chip) to external circuitry on a PCB. The chip contains active electronic components, while the pads enable electrical connections. The core may have mechanical or thermal significance, and the die is the semiconductor wafer containing the actual electronic components. IPs are pre-designed blocks of functionality that can be integrated into IC designs to enhance their capabilities.

**RISC-V:** <br>
RISC-V is an open-source instruction set architecture (ISA) that has gained significant attention in the field of computer architecture and microprocessor design. Here's an explanation of RISC-V without plagiarism:

RISC-V, often pronounced as "Risk Five," is a modern and open-source instruction set architecture (ISA) designed for a wide range of computing devices, from embedded systems to supercomputers. Unlike proprietary ISAs developed by companies like Intel or ARM, RISC-V is open and freely available for anyone to use, modify, and implement.

Key features and concepts of RISC-V include:

1. **Reduced Instruction Set Architecture (RISC)**:
   - RISC-V follows the principles of RISC design, which emphasizes simplicity and efficiency. It aims to provide a small, well-defined set of instructions that are easy to decode and execute quickly.

2. **Modularity**:
   - One of RISC-V's strengths is its modularity. It offers a base ISA with a minimal set of instructions, and additional optional extensions can be added to support specific application domains (e.g., integer, floating-point, vector processing).
   - This modular approach allows designers to tailor RISC-V implementations to their specific needs, which is particularly useful in embedded systems where resource constraints are common.

3. **Open Source and Open Standard**:
   - RISC-V's open nature means that the ISA specifications are freely available for anyone to access, study, and implement. This openness fosters innovation, collaboration, and a diverse ecosystem of RISC-V-based processors and tools.
   - Various organizations, including universities and industry consortia, actively contribute to the development and enhancement of the RISC-V ISA.

4. **Scalability**:
   - RISC-V supports different bit-width versions (e.g., 32-bit, 64-bit, and 128-bit) to accommodate a wide range of applications. The 32-bit version is suitable for low-power embedded devices, while the 64-bit version is common in servers and workstations.

5. **Compatibility**:
   - RISC-V's compatibility is maintained through a stable base ISA, which ensures that software written for one RISC-V processor can run on another RISC-V processor with the same base ISA.
   - This compatibility simplifies software development and portability.

6. **Ecosystem**:
   - RISC-V has fostered a growing ecosystem of hardware and software tools, including compilers, simulators, development boards, and operating systems. This ecosystem is supported by both academia and industry, making it easier for developers to work with RISC-V-based solutions.

7. **Customization**:
   - RISC-V's open nature allows designers to customize the architecture for specific use cases. This level of flexibility is particularly beneficial for emerging technologies and research projects.

In summary, RISC-V is an open-source and modular instruction set architecture that adheres to RISC principles. Its openness, scalability, compatibility, and ecosystem support have made it a compelling choice for a wide range of computing applications, from small embedded systems to high-performance computing platforms. As an open standard, RISC-V encourages collaboration and innovation in the world of computer architecture.


**Digital ASIC (Application-Specific Integrated Circuit):** <br>
<img  width="1085" alt="WhatsApp Image 2023-10-08 at 18.36.29.jpeg" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/WhatsApp%20Image%202023-10-08%20at%2018.36.29.jpeg">

1. **Specification**: Defining the chip's purpose, performance, and power requirements.

2. **RTL Design**: Creating a high-level description of the chip's behavior using hardware description languages.

3. **Synthesis**: Converting the description into a gate-level netlist for logic gates and flip-flops.

4. **EDA Tools**: Using Electronic Design Automation tools for tasks like layout, clocking, and verification.

5. **PDK Data**: Adhering to Process Design Kit data from foundries to ensure manufacturability.

6. **Testing and Manufacturing**: Fabricating and testing the chip to meet specifications.

ASIC design is highly specialized and crucial for custom hardware solutions.

</details>

<details>
	<summary>Labs</summary>

OpenLANE is an integrated flow that leverages various open-source EDA (Electronic Design Automation) tools, including Yosys for synthesis and OpenSTA for Static Timing Analysis. What sets OpenLANE apart is its automation, requiring minimal human intervention. Given RTL (Register Transfer Level) input and foundry Process Design Kits (PDKs), OpenLANE efficiently generates the final GDSII file for chip fabrication.

In the OpenLANE working directory, you'll find two main folders: "openlane" and "pdks." The "pdks" folder houses essential components such as timing libraries, LEF (Library Exchange Format) files, technology LEF, and cell LEF. Additionally, the "open_pdks" directory contains scripts designed to adapt SkyWater PDKs, originally intended for commercial EDA tools, to work seamlessly with open-source EDA tools. This ensures compatibility and flexibility in the ASIC design process.

The sky130A variant has been tailored for compatibility. It consists of two main components: "libs.ref" for process-specific data and "libs.tech" for tool-specific information. In this context, "netgen" and "openlane" are the tools utilized, while "sky130_fd" represents the process variants integrated within this configuration.
<img  width="1085" alt="day15_2" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day15-16/day15_2.png">
<img  width="1085" alt="day15_4" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day15-16/day15_4.png">


Our design employs the "sky130_fd_sc_hd" process, with "sky130" referring to the 130nm technology, "fd" signifying foundry, "sc" indicating standard cell, and "hd" representing high density.

Within this "sky130_fd_sc_hd" configuration, you'll find crucial files including LEF (Library Exchange Format), tech LEF (Technology Library Exchange Format), and libs. The "libs" encompass data for various Process-Voltage-Temperature (PVT) corners, while the "lef" and "tech LEF" serve specific roles.

To initiate OpenLane, we commence by initializing the Docker environment with the following command:
```ruby
docker run -it -v $(pwd):/openLANE_flow -v $PDK_ROOT:$PDK_ROOT -e PDK_ROOT=$PDK_ROOT -u $(id -u $USER):$(id -g $USER) openlane:rc2
```
But it is aliased as docker
<img  width="1085" alt="day15_9" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day15-16/day15_9.png">


Now, let's delve into the design aspect. Inside the "designs" directory, you'll find various design options. For this demonstration, we'll focus on "picorv32a." Within this design, the "src" directory houses essential RTL (Register Transfer Level) information, including the behavioral code (.v file) and constraints file (.sdc file).

To understand the design configuration, the "config.tcl" file comes into play. It allows you to bypass any prior lane configurations. When specific attributes are undefined, the design defaults to preset values.

The order of precedence for attribute settings is as follows:

Attributes defined by the PVT corner in "config.tcl."
Attributes specified in the main "config.tcl."
Default attribute values provided by OpenLANE.
For every PVT corner in each design, you will find both the main "config.tcl" and a "sky130" variant-specific "config.tcl," ensuring flexibility and adaptability in your design configurations.
<img  width="1085" alt="day15_8" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day15-16/day15_8.png">

To prepare the design, we use the following command. This command links together all the necessary files, including LEF (Library Exchange Format) files, library files, macros, diodes, and other essential components.
```ruby
prep -design picorv32a
```
<img  width="1085" alt="day15_9" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day15-16/day15_9.png"> <br>

Upon the successful completion of this run, OpenLane generates a "runs" directory. Within this directory, you'll find various subdirectories where reports, logs, and results are neatly organized. These directories include:
<img  width="1085" alt="day15_10" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day15-16/day15_10.png"> <br>

Next, we initiate the synthesis process with the "run_synthesis" command. I'm pleased to report that the synthesis has been executed successfully.
<img  width="1085" alt="day15_11" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day15-16/day15_11.png"> <br>

The flop ratio is calculated by dividing the number of flip-flops by the total number of cells in the design. In this case, there are 1613 flip-flops (specifically dfxtp-D flip-flops with positive triggers) and 14876 cells in the design. Therefore,

Flop ratio = Number of flip-flops / Number of cells in the design = 1613 / 14876 ≈ 0.108.

This means that the flop count constitutes approximately 10.8% of the total cells in the design.
<img  width="1085" alt="day15_16" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day15-16/day15_16.png"> <br>
<img  width="1085" alt="day15_17" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day15-16/day15_17.png"> <br>

</details>


## Day-16-Good floorplan vs bad floorplan and introduction to library cells

<details>
	<summary>Introduction</summary>

 **Chip floor planning considerations:** <br>
 Step-1: Define width and height of core and die <br>

 Let's examine a straightforward netlist featuring a register-to-register timing path, comprising two flip-flops and two combinational gates, as depicted below:
<img  width="1085" alt="WhatsApp Image 2023-10-08 at 18.40.04.jpeg" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/WhatsApp%20Image%202023-10-08%20at%2018.40.04.jpeg"> <br>
<img  width="1085" alt="WhatsApp Image 2023-10-08 at 18.44.04.jpeg" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/WhatsApp%20Image%202023-10-08%20at%2018.44.04.jpeg"> <br>
<img  width="1085" alt="WhatsApp Image 2023-10-08 at 18.44.44.jpeg" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/WhatsApp%20Image%202023-10-08%20at%2018.44.44.jpeg"> <br>
The dimensions of the core and die are determined by the combined area of the standard cells within the design. Assuming that each standard cell occupies 1 square unit of area, and each flip-flop also occupies 1 square unit, the minimum area occupied by the netlist is 4 square units, which can be placed as needed.

The core is the specific section of a chip where the primary logic of a design is located. Meanwhile, the die, which includes the core, is a small semiconductor material structure on which the fundamental circuit is fabricated. The core is enclosed within the die. When our design is placed on the core, the logic cells occupy the entire core area, resulting in a utilization factor of 100%.

The utilization factor is calculated as follows: <br>
Utilization Factor = Area occupied by the netlist / Total area of the core

A utilization factor of 1 means that no space is available on the die for further optimization. Therefore, it is common to aim for a utilization factor of around 50-60% to allow for potential optimizations and flexibility.

The aspect ratio is calculated as: <br>
Aspect Ratio = Height / Width

When the aspect ratio is 1, it signifies a square chip. Otherwise, it indicates a rectangular shape.

For example, let's consider a design with a utilization factor of 0.5 and an aspect ratio of 0.5. If the length of the die is 2 units and the height is 4 units, the aspect ratio is calculated as 2/4, resulting in 0.5. The logic requires an area of 4 units, so the utilization factor is calculated as 4/(2 x 4), yielding 1/2 or 0.5.

In this scenario, the utilization factor and aspect ratio are both 0.5, indicating that the design occupies half of the available core area and that the chip has a rectangular shape.
<img  width="1085" alt="WhatsApp Image 2023-10-08 at 18.45.26.jpeg" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/WhatsApp%20Image%202023-10-08%20at%2018.45.26.jpeg"> <br>
<img  width="1085" alt="WhatsApp Image 2023-10-08 at 18.46.06.jpeg" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/WhatsApp%20Image%202023-10-08%20at%2018.46.06.jpeg"> <br>


Now, let's consider another core with an area of 4x4 square units while using the same netlist. The utilization factor in this case would be calculated as (2x2)/(4x4), resulting in 0.25. This means that only 25% of the available area is utilized, leaving the remaining space available for optimization.

Furthermore, in this scenario, the aspect ratio is 1, which indicates that the chip has a square shape due to the equal length and width dimensions.


Step-2: Define locations of preplaced cells
Preplaced cells are specific segments of combinational logic, such as macros or IPs, that are designed for reuse multiple times. These cells are strategically placed based on the design scenario, and their locations must be precisely defined. To illustrate the concept of preplaced cells, consider a combinational logic circuit with 100,000 gates that can be broken down into two distinct blocks.
<img  width="1085" alt="WhatsApp Image 2023-10-08 at 18.49.11.jpeg" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/WhatsApp%20Image%202023-10-08%20at%2018.49.11.jpeg"> <br>
<img  width="1085" alt="WhatsApp Image 2023-10-08 at 18.49.50.jpeg" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/WhatsApp%20Image%202023-10-08%20at%2018.49.50.jpeg"> <br>

Preplaced cells are fundamental building blocks of a chip's design, consisting of I/O pins that extend from these blocks, effectively dividing them into separate IP (Intellectual Property) modules. Within these modules, the inner logic remains concealed, represented as a "black box." The advantage of preplaced cells lies in their reusability throughout the netlist, allowing the designer to create the block's functionality just once.

This approach streamlines the design process, as the block is designed as an IP and declared as a blackbox in the primary netlist, permitting multiple reuses. Importantly, the functionality of these models is defined once and can be applied repeatedly across the chip. This process is established prior to the actual placement and routing stages, with the locations of these cells typically fixed.
The arrangement and placement of these IPs, known as floorplanning, are user-defined, making them pre-placed cells. During the automated placement and routing phase, the tool leaves the locations of these pre-placed cells untouched, ensuring their designated positions.

To ensure optimal performance, pre-placed cells should be surrounded by decoupling capacitors. When the output of a logic gate transitions from 0 to 1, it demands a certain amount of current, which the output capacitance of the gate supplies. Vdd is responsible for providing the necessary voltage for logic switching in the design. Conversely, when transitioning from logic 1 to 0, Vss should be capable of handling the discharged currents produced by the logic in the design.
Physical wires connecting the design components introduce resistance, inductance, and capacitance, which can result in voltage drops. Careful consideration and design of the power distribution network are essential to ensure stable operation and prevent voltage drop-related issues.
<img  width="1085" alt="WhatsApp Image 2023-10-08 at 18.50.29.jpeg" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/WhatsApp%20Image%202023-10-08%20at%2018.50.29.jpeg"> <br>
<img  width="1085" alt="WhatsApp Image 2023-10-08 at 18.51.18.jpeg" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/WhatsApp%20Image%202023-10-08%20at%2018.51.18.jpeg"> <br>
During the switching operation of a circuit, it requires a certain amount of switching current. As a result, there will be a voltage drop across the circuit, causing the voltage to become Vdd - IRdrop. If this value falls below the noise margin, due to the IR drop, the logic level 1 at the output won't be reliably detected as a logic level 1 at the input of the circuit.
In digital circuits, voltage levels are defined within certain voltage ranges. Typically, any voltage between Vol (output low voltage) and Vil (input low voltage) is considered as logic '0,' while any voltage between Voh (output high voltage) and Vih (input high voltage) is considered as logic '1.' The voltage range between Vil and Vih is regarded as an undefined region because the voltage in this range may either rise to Vih or degrade to Vil, making it uncertain and unreliable for logic interpretation.

**Noise margin Summary:**
<img  width="1085" alt="WhatsApp Image 2023-10-08 at 18.51.58.jpeg" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/WhatsApp%20Image%202023-10-08%20at%2018.51.58.jpeg"> <br>

Step-3: Surround pre-placed cells with deoupling capacitors
Decoupling capacitors play a crucial role in mitigating noise caused by the long distance between the circuit and the supply voltage. To achieve this, decoupling capacitors are added in parallel with the circuit. 
Here's how they work: Every time the circuit switches, it draws current from the decoupling capacitor (Cd). An RL network is typically employed to replenish the charge into Cd, ensuring that the capacitor remains charged and can provide a stable and noise-free supply voltage to the circuit during switching operations.
The inclusion of decoupling capacitors serves to prevent issues such as crosstalk and the degradation of logic signals.


Step-4: Power Planning
In a design containing various macros, each macro requires a certain amount of current when it's reused. Let's consider a scenario where the design incorporates multiple macros, each surrounded by decoupling capacitors. The power supply, represented by Vdd and Vss, is connected to each macro as shown.
Now, let's focus on two specific macros, one serving as the driver and the other as the load. The objective is for the signal to propagate from the driver to the load without any degradation. Imagine that the driver initially sends a logic 0 and transitions to logic 1 at the load.
Adding a decoupling capacitor to every single cell within the logic is not practically feasible. Instead, decoupling capacitors are strategically placed within critical blocks of the design. Let's consider a 16-bit bus in this context, where each of the 16 bits undergoes logic transitions, charging and discharging as illustrated. The logic at the output of this bus is connected to an inverter. This means that all the capacitors, initially charged to 'V' volts, must discharge to '0' volts through a single ground tap point.
As a result, this discharge process can create a "bump" in the ground tap point. If this bump exceeds the noise margin level, it can push the output into an undefined region. In this undefined region, the output becomes unpredictable and unreliable for logic interpretation. Hence, careful design and placement of decoupling capacitors are crucial to prevent such issues and ensure reliable signal propagation.
<img  width="1085" alt="WhatsApp Image 2023-10-08 at 18.53.21.jpeg" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/WhatsApp%20Image%202023-10-08%20at%2018.53.21.jpeg"> <br>
<img  width="1085" alt="WhatsApp Image 2023-10-08 at 18.54.15.jpeg" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/WhatsApp%20Image%202023-10-08%20at%2018.56.13.jpeg"> <br>
<img  width="1085" alt="WhatsApp Image 2023-10-08 at 18.56.13.jpeg" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/WhatsApp%20Image%202023-10-08%20at%2018.56.13.jpeg"> <br>
<img  width="1085" alt="WhatsApp Image 2023-10-08 at 18.56.57.jpeg" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/WhatsApp%20Image%202023-10-08%20at%2018.56.57.jpeg"> <br>
<img  width="1085" alt="WhatsApp Image 2023-10-08 at 18.57.48.jpeg" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/WhatsApp%20Image%202023-10-08%20at%2018.57.48.jpeg"> <br>
Furthermore, when all capacitors that were initially at 0 volts need to charge to V volts, they do so through a single Vdd tap point. This situation can lead to a voltage droop, and if it exceeds the noise margin, the circuit's behavior becomes unpredictable.
To address these issues, multiple power supply points are introduced. Each capacitor can then charge and discharge from its nearest power supply point, as illustrated. This approach mitigates voltage droops and ground bounces effectively. This power distribution network, often referred to as Powermesh, offers a precise solution to ensure stable and reliable power delivery in the presence of switching currents.

Step-5: Pin Placement
The interconnections between the gates in a digital design are described using VHDL or Verilog language and are commonly referred to as the netlist. Let's explore an example where the design includes:

1. Two timing paths driven by different clocks.
2. Two timing paths driven by two distinct interclocks (alternate flops).
3. Preplaced cells that are interconnected in the design, as depicted.

<img  width="1085" alt="WhatsApp Image 2023-10-08 at 18.58.24.jpeg" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/WhatsApp%20Image%202023-10-08%20at%2018.58.24.jpeg"> <br>
<img  width="1085" alt="WhatsApp Image 2023-10-08 at 18.59.00.jpeg" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/WhatsApp%20Image%202023-10-08%20at%2018.59.00.jpeg"> <br>

Typically, pins are positioned in the area between the die and the core, which is reserved for pin locations. To ensure that this region remains free for pin placement, logical cell placement blockage is employed. 
Let's consider a scenario where input ports are connected on the left-hand side, while output ports are connected on the right-hand side. The order of the ports depends on the planned placement of cells and can vary. It's essential to avoid placing flip-flops on preplaced cells since the locations of preplaced cells are fixed.
Furthermore, the clock port continuously drives the cells, necessitating the establishment of the path with the least resistance for the clock signal.


**Binding Netlist with Physical Cells:**

In the process of converting functional logic (expressed in behavioral code) into a valid hardware design, a crucial step is Logic Synthesis. This involves organizing gates to replicate the original functionality described at the RTL (Register Transfer Level). To achieve this, a netlist is generated that maps logic gates to their corresponding functionality.

Each cell represented in the synthesis has a specific width and height, defining its physical size and shape. This information is stored in a library file, which also contains vital details like timing characteristics and conditional rules for cells (e.g., when they should be used). Libraries often include various cell flavors, allowing designers to choose based on timing and available floorplan area.

**Placement on Floorplan:**

The floorplan serves as the blueprint for chip layout, featuring well-defined ports and pins. The netlist provides the physical representation of logic gates. During placement, it's essential to ensure that pre-placed cells remain untouched, preserving their fixed positions.

The goal of placement is to position cells as close as possible to the ports they connect to, optimizing for signal integrity. Signal integrity refers to the reliable transmission of signals from one point to another.

Achieving signal integrity often involves using repeaters, which are buffers that recondition the original signal, replicating it and passing it to the next stage. In the placement optimization phase, estimates are made regarding wire lengths and capacitance, ensuring that signal transitions fall within permissible limits.

Slew, which measures how fast a signal switches, is influenced by capacitance. Higher capacitance requires more time to charge or discharge, leading to poor slew rates. To counter this, buffers are inserted when cells are placed farther apart to minimize signal deterioration.

In high-frequency scenarios, minimizing delay is critical. Cells are placed close together to avoid significant delays. Buffers are added to the design under the assumption that the clock is ideal, as the clock has not been generated yet.

Data paths are carefully considered, and if the length exceeds permissible values based on transition and slew rate, buffers are introduced. Timing must be met during placement since any timing violations can worsen in subsequent stages, especially during routing.

**The Need for Characterization:**

In the overall IC design flow:

1. Logic Synthesis arranges gates to replicate functionality.
2. Netlists are imported and core/die dimensions are defined during floorplanning.
3. Placement ensures timing requirements are met.
4. Clock Tree Synthesis (CTS) generates a clock distribution network to minimize skew.
5. Routing adheres to constraints to connect cells.
6. Static Timing Analysis (STA) is the final stage to check for timing violations.

Throughout these stages, cells are a common element. They are carefully modeled to guide the tool in selecting the appropriate cell at each stage, optimizing the design for performance and functionality.

Certainly, let's provide a more detailed explanation:

**Standard Cells and Library**

In digital ASIC design, flip-flops, buffers, and combinational gates are collectively referred to as standard cells. These standard cells are available in a library that contains various information, including timing characteristics, size, shape, functionality, and threshold voltage variations. Within the library, larger buffers typically have higher drive strengths.

**Cell Design Flow**

The design of individual cells, or standard cells, follows a structured flow consisting of inputs, design steps, and outputs:

**Inputs**

1. **Process Design Kits (PDKs)**: These kits provide essential information about the manufacturing process, including rules for Layout Versus Schematic (LVS) and Design Rule Check (DRC).

2. **SPICE Models**: SPICE models include parameters provided by the foundry, which are crucial for accurate simulations.

3. **Library and User-defined Specifications**: Specifications include the separation of power and ground rails, determining cell height and width, as well as timing and noise margin requirements.

4. **Metal Layer Specifications**: Certain cells may need to be designed with specific metal layers.

5. **Pin Locations**: The locations of pins (input and output connections) are defined.

6. **Gate Length**: The drawn gate length may vary within specified limits.

**Design Steps**

1. **Library Cell Selection**: A library cell that matches the design specifications is chosen.

2. **Circuit Design**: This step involves implementing the cell's functionality using NMOS and PMOS transistors while meeting library requirements. The output of this phase is typically a circuit description language (CDL) file.

3. **Layout Design**: Layout design translates the circuit design into physical implementations using NMOS and PMOS transistors. This process combines Euler's path, a path that traverses each segment only once, and stick diagrams. Stick diagrams are derived from Euler's path and are then converted into a typical layout, ensuring compliance with input rules.

4. **Characterization**: Characterization is essential for obtaining timing, noise, and power information. It involves reading SPICE models for NMOS and PMOS transistors, reading the extracted SPICE netlist, recognizing cell behaviors, applying stimuli, and running simulations to generate output files characterizing timing, power, and noise.

**Outputs**

1. **CDL File**: The CDL file is the output of the circuit design step and represents the circuit modeled using NMOS and PMOS transistors.

2. **GDSII File**: This output is the layout design implemented with stick diagrams in GDSII format, ready for manufacturing.

3. **LEF File**: LEF defines the cell's height and width.

4. **CIR File**: The CIR file contains extracted parasitics for each cell, creating an extracted SPICE netlist for further characterization.

**General Timing Characterization Parameters**

Characterization is performed using tools like GUNA software, utilizing inputs such as timing.lib, power.lib, and noise.lib. Timing threshold definitions are crucial for this process:

- **slew_low_rise_thr**: Typically set at 20%, represents points near the lower side of the power supply for rising signals.
- **slew_high_rise_thr**: Typically set at 80%, represents points near the rising side of the power supply for rising signals.
- **slew_low_fall_thr**: Typically set at 20%, represents points near the lower side of the power supply for falling signals.
- **slew_high_fall_thr**: Typically set at 80%, represents points near the rising side of the power supply for falling signals.
- **in_rise_thr**: Typically set at 50%, represents input transition slew for rising inputs.
- **in_fall_thr**: Typically set at 50%, represents input transition slew for falling inputs.
- **out_rise_thr**: Typically set at 50%, represents the slew in the output waveform for a rise in output.
- **out_fall_thr**: Typically set at 50%, represents the slew in the output waveform for a fall in output.

These parameters are used to calculate slew, propagation delay, currents, and more. Selecting appropriate threshold points is crucial, as errors can lead to negative cell delays. Propagation delay is defined as the difference between output and input threshold points, while transition time is the difference between high and low threshold points.

In cases where a circuit is not designed correctly, with more input transitions than the slew at the input, the 50% input slew may lag behind the 50% output slew, potentially causing issues. Properly characterizing cells helps ensure correct operation in the final design.
</details>

<details>
	<summary>Labs</summary>

The README file located in the "openlane/configuration" directory encompasses all the defined switches and parameters for the design flow. Here's a breakdown of the README file's contents:
The switches for synthesis step are:
<img  width="1085" alt="day15_20" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day15-16/day15_20.png"> <br>

The switches for Floorplan step are:
<img  width="1085" alt="day15_21" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day15-16/day15_21.png"> <br>


- **FP_CORE_UTIL**: This switch is used to specify the utilization of the core area.
- **FP_ASPECT_RATIO**: Here, you define the aspect ratio of the core, which is the ratio of its height to its width.
- **FP_CORE_MARGIN**: This switch allows you to set an offset between the core and the die area. It's important to note that not all switches need to be configured, and the specific switches required may vary depending on the design's unique requirements.

The contents pf floorplan.tcl in this folder shows the variables set to values as follows:
<img  width="1085" alt="day15_22" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day15-16/day15_22.png"> <br>

The config.tcl contents inside the design are as follows:
<img  width="1085" alt="day15_8" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day15-16/day15_8.png"> <br>

Now, run_floorplan command is given and the floorplan run is fired. The PDN was created successfully. 
<img  width="1085" alt="day15_18" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day15-16/day15_18.png"> <br>

The metal layers are set to one more than defined value. Here VMETAL is 3 and HMETAL is 4 after the run. The core utilization is 35% in the log after run and before run is as follows:
<img  width="1085" alt="day15_25" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day15-16/day15_25.png"> <br>

The contents of io-placer log is as follows: 
<img  width="1085" alt="day15_24" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day15-16/day15_24.png"> <br>

The contents of def file after floorplan are as follows:
<img  width="1085" alt="day15_27" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day15-16/day15_27.png"> <br>

Inorder to view the floorplan the magic command is used as follows:
This command is executed in the results/floorplan directory after runs.
```ruby
magic -T /Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.placement.def &
```

Now, The floorplan is opened. Press S for selecting the whole design nd V to align the design to center.
<img  width="1085" alt="day15_29" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day15-16/day15_29.png"> <br>
<img  width="1085" alt="day15_30" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day15-16/day15_30.png"> <br>

By selecting a particular object and giving what command in tkcon.tcl gives the description of the shape as follows:
<img  width="1085" alt="day15_31" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day15-16/day15_31.png"> <br>

All the cells are not placed in the design as placement is done. All these cells are present as cluster at the origin point as follows. When a particular cell is selected, it shows a standard cell as OAI cell.
<img  width="1085" alt="day15_33" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day15-16/day15_33.png"> <br>

The placement being done is congestion aware, not for timing optimization.
Global placement is an initial, coarse placement stage where fine-grained legalization has not yet occurred. Legalization involves ensuring that the cells are correctly positioned within rows, abutted against each other, and free of overlaps. Global placement aims to minimize wire length, a critical factor in chip design. In the OpenLANE flow, the Half Parameter Wirelength (HPW) metric is utilized for this purpose. You can initiate the placement stage with the "run_placement" command.
<img  width="1085" alt="day15_35" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day15-16/day15_35.png"> <br>

The following images show that cells are placed in their rows as follows:
<img  width="1085" alt="day15_36" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day15-16/day15_36.png"> <br>
<img  width="1085" alt="day15_37" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day15-16/day15_37.png"> <br>


</details>

## Day-17- Design library cell using Magic Layout and ngspice characterization

<details>
	<summary>Introduction</summary>

**IO Placer:** <br>
OpenLANE offers the flexibility to adjust various variables in real-time, including the IO placer. To modify the congestion of IO pins alignment, you can use the 'magic' command to view the floorplan definition as shown below:
```ruby
magic -T /Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.floorplan.def &
```
We can view the floorplan as follows, with pins evenly spaced:
<img  width="1085" alt="day17_1" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day17_1.png"> <br>


The IO placer is the tool used to position IO pins according to specified requirements. To increase congestion, change the variable to 2 as follows:
<img  width="1085" alt="day17_2" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day17_2.png"> <br>

After running the floorplan again, the pins are now placed closer together, as shown below:
<img  width="1085" alt="day17_3" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day17_3.png"> <br>

**SPICE:** <br>
Before conducting SPICE simulations, it is essential to create a SPICE deck. The SPICE deck serves as a comprehensive document containing information about connectivity in the netlist, provided inputs, and designated tap points for viewing outputs. It is created by specifying component connectivity, component values, identifying nodes, and assigning them appropriate names.
A crucial element in this process is the substrate, which acts as a significant component or pin requiring connectivity information. The substrate plays a critical role in tuning the threshold voltages of NMOS and PMOS transistors. Notably, the substrate pin direction differs between NMOS and PMOS symbols. Calculating the value of the output load capacitance involves intricate computational analysis. This parameter is vital for understanding the behavior of the circuit. Component values for both PMOS and NMOS transistors need to be defined, typically in terms of W/L values (for instance, 0.375u/0.25u). It's important to note that while these values can be assumed the same, in practice, the PMOS transistor should be approximately twice the size of the NMOS transistor for proper performance. The output capacitance, often denoted as, say, 10fF, is another critical parameter that needs to be specified.

In SPICE simulations, the applied gate voltage is typically considered as a multiple of the channel length, often set at, for example, 2.5V. Finally, nodes in the circuit are defined when a component is placed between two nodes, forming the fundamental connectivity structure.

The netlist is structured with components defined in the order of drain, gate, source, and substrate. The definition of a component includes the following key elements:
<img  width="1085" alt="" src=""> <br>
```ruby
M1 out in vdd vdd pmos W=0.375u L=0.25u
M2 out in 0 0 nmos W=0.375u W=0.25u
cload out 0 10f
Vdd vdd 0 2.5
Vin in 0 2.5
```
In this context, consider 'M1' as the component name, with 'PMOS' representing the component type, and specific 'W/L' values defined. The connections are structured as follows: 'out' is connected to the drain, and 'in' is connected to the gate of 'M1.' The 'substrate' and 'source' of the PMOS component are connected to the power supply, whereas for the NMOS component, they are connected to ground. Additionally, a load capacitance of 10fF is connected between the 'out' port and ground. Furthermore, the supply voltages are established between the ground and the respective nodes, each set at a voltage level of 2.5V.
The simulation commands:
```ruby
.op
.dc Vin 0 2.5 0.05
```

This command instructs the variation of gate voltage from 0 to 2.5V in increments of 0.05V. This procedure is employed to observe the output characteristics in relation to input voltage. It is imperative to describe the model file as follows, encompassing the comprehensive model details for both NMOS and PMOS transistors, including their respective dimensions.
```ruby
.LIB "tsmc_025um_model.mod" CMOS_MODELS
.end
```

The SPICE simulation process unfolds as follows:
First, the netlist depicted above is saved in a file named 'cmos_inv.cir,' and the simulation is initiated by running the circuit.
Upon setting up the desired plot options, such as 'op1' and 'dc1,' the 'dc1' option is selected to instruct the tool to generate the DC transfer characteristics.
Next, the 'display' command is used to showcase the voltages present in the design.
Following the 'plot' command, a graph representing the specified characteristics is generated.
```ruby
source cmos_inv.cir
run
setplot
dc1
display
plot out vs in
```
Now, we will proceed with the dynamic simulation of the CMOS inverter. The following netlist illustrates the configuration:
```ruby
M1 out in vdd vdd pmos W=0.375u L=0.25u
M2 out in 0 0 nmos W=0.375u W=0.25u

cload out 0 10f

Vdd vdd 0 2.5
Vin in 0 0 pulse 0 2.5 0 10p 10p 1n 2n

**SIMULATION Commands**
.op
.tran 10p 4n
*** .include mosis_1um_model.mod ***
.LIB "tsmc_025um_model.mod" CMOS_MODELS
.end
```

Clone the 'vsdstdcelldesign' using the 'git clone' command, as shown below:
<img  width="1085" alt="day16_1" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day16_1.png"> <br>

The 'magic' command produces the following inverter, as depicted:
<img  width="1085" alt="day16_4" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day16_4.png"> <br>

**The "16-mask process" in CMOS (Complementary Metal-Oxide-Semiconductor) fabrication involves a series of steps and photolithography masks to create intricate integrated circuits. Each mask defines specific features and patterns on a silicon wafer, allowing the formation of transistors, interconnections, and various components. Below, is the explaination of the 16-mask CMOS fabrication process in detail:**

1. **Wafer Selection**: The process begins with the selection of a silicon wafer. These wafers are typically made from single-crystal silicon and serve as the substrate for the integrated circuit.

2. **Wafer Cleaning**: The silicon wafer undergoes a thorough cleaning process to remove impurities and contaminants, ensuring a clean starting point for the fabrication.

3. **Mask 1 - Gate Oxide Formation**: The first photolithography mask is used to define the areas on the wafer where gate oxide will be formed. Gate oxide acts as an insulating layer between the gate electrode and the silicon substrate in MOSFET transistors.

4. **Mask 2 - Poly-Silicon Gate Formation**: The second mask specifies where the poly-silicon gate material will be deposited. Poly-silicon is commonly used for the gate electrode of MOSFETs due to its compatibility with the process.

5. **Mask 3 - Active Area Implantation**: The third mask defines the active areas of the transistors. Ion implantation is used to introduce specific dopants into the silicon, creating the source and drain regions of the transistors.

6. **Mask 4 - Isolation Oxide Formation**: This mask defines the regions where isolation oxide is created. Isolation oxide is crucial for isolating individual transistors and components, preventing interference between them.

7. **Mask 5 - Metal Layer 1**: The fifth mask is used to define the first metal layer, often made of materials like aluminum or copper. This layer establishes the initial interconnects between different components on the chip.

8. **Mask 6 - Dielectric Layer 1**: A dielectric layer is added to insulate and protect the metal interconnects from unwanted electrical contact and interference.

9. **Mask 7 - Via Holes**: This mask creates via holes, which serve as pathways for electrical signals to pass from one metal layer to another, allowing for interlayer connections.

10. **Mask 8 - Metal Layer 2**: The eighth mask defines the second metal layer, expanding the complexity of interconnections between components.

11. **Mask 9 - Dielectric Layer 2**: Another dielectric layer is added to isolate and protect the second metal layer from the first, reducing the risk of electrical interference.

12. **Mask 10 - Via Holes**: Additional via holes are created to enable connections between the second metal layer and the layers below.

13. **Mask 11 - Metal Layer 3**: The eleventh mask defines the third metal layer, enhancing the circuit's complexity by providing additional interconnectivity options.

14. **Mask 12 - Dielectric Layer 3**: Another insulating layer is added to prevent interference and capacitance effects between the metal layers.

15. **Mask 13 - Via Holes**: Further via holes are introduced to ensure necessary connections between the metal layers.

16. **Mask 14 - Metal Layer 4**: The fourteenth mask defines the fourth metal layer, enabling intricate routing and complex interconnections.

17. **Mask 15 - Dielectric Layer 4**: Another insulating layer is applied to insulate and protect the metal interconnects.

18. **Mask 16 - Contact and Passivation**: The final mask defines contact points for external connections and adds a passivation layer to protect the chip and enhance its reliability.

19. **Testing and Packaging**: After fabrication, the wafer is subjected to rigorous testing to verify its functionality. It is then diced into individual chips, each of which is packaged for protection and to provide electrical connections.

20. **Quality Control and Final Testing**: Comprehensive quality control procedures are executed to identify and eliminate any faulty chips. The packaged chips undergo a final round of testing to confirm that they meet the specified performance and functionality requirements.

The "16-mask process" in CMOS fabrication underscores the complexity and precision required to create modern integrated circuits, enabling the development of sophisticated electronic devices.



<img  width="1085" alt="" src=""> <br>

</details>


<details>
	<summary>Labs</summary>

 A poly crossing an n-diffusion results in an NMOS transistor, while a polysilicon crossing a p-diffusion creates a PMOS transistor.
 The following inverter is gained from the magic commnad:
 <img  width="1085" alt="day16_4" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day16_4.png"> <br>


To select the layer, press 'S,' and the 'what' command provides information about the selected shape, as follows:
<img  width="1085" alt="day16_5" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day16_5.png"> <br>
<img  width="1085" alt="day16_6" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day16_6.png"> <br>

Triple-click 'S' with the cursor on any shape to highlight the connected objects to that shape. In this case, the output port is connected to NMOS and PMOS as shown below:
<img  width="1085" alt="day16_7" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day16_7.png"> <br>

The source of PMOS is connected to powersupply:
<img  width="1085" alt="day16_8" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day16_8.png"> <br>


The drain of NMOS is connected to Ground:
<img  width="1085" alt="day16_9" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day16_9.png"> <br>

To extract the Spice deck file, open the tkcon window and execute the following commands:
```ruby
extract all
ext2spice cthresh 0 rthresh 0
ext2spice
```
<img  width="1085" alt="day16_10" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day16_10.png"> <br>

This action generates a Spice file with a .spice extension and an .ext extension file. Subsequently, the SPICE file is edited, and a netlist is written into it, as shown below:
<img  width="1085" alt="day16_11" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day16_11.png"> <br>

The met3.mag file is loaded after opening an empty magic window using command:
```ruby
magic -d XR
```
<img  width="1085" alt="day16_13" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day16_13.png"> <br>

The various drc errors are present on each box. This can be viewed by selecting a box and drc why in tkcon window:
<img  width="1085" alt="day16_14" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day16_14.png"> <br>
<img  width="1085" alt="day16_15" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day16_15.png"> <br>

Now, using the command the vias are viewed in the rule:
```ruby
cif see VIA2
```
<img  width="1085" alt="day16_16" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day16_16.png"> <br>
<img  width="1085" alt="day16_17" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day16_17.png"> <br>
<img  width="1085" alt="day16_18" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day16_18.png"> <br>

 Loading poly.mag:
 <img  width="1085" alt="day18_7" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day18_7.png"> <br>

The other violations are:
Copy the 3 poly metal and paste it into 2 different places and add pmos and nmos substrate and contact. This is to fix the issue with poly resistor spacing to diff and tap lab2_1_3
<img  width="1085" alt="day16_20" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day16_20.png"> <br>


</details>

## Day-18- Pre-layout timing analysis and importance of good clock tree
<details>
	<summary>Timing modelling using delay tables</summary>

**Timing Models using delay tables:** <br>
OpenLANE is a place-and-route tool that operates without the need for mag information. It exclusively relies on essential data, including the pr boundary (inner box), power, ground, input and output ports information, which are found in the lef file.

The standard cell height guidelines are as follows:

Input and output ports should align with vertical and horizontal tracks.
The width of the standard cell must be odd multiples of the track pitch.
The cell height should be a multiple of the vertical pitch.
During the routing stage, tracks are utilized as routes for metal traces, specifying the interconnections between various components.
You can activate the grid mode as follows, which serves as the reference for drawing a layout:
<img  width="1085" alt="day16_9" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day16_9.png"> <br>

The 'grid' command requires parameters for x spacing, y spacing, x origin, and y origin. For aligning input and output ports, 'li1' serves as the reference. 
Ports are strategically positioned at the intersection of horizontal and vertical tracks, ensuring that routes can efficiently connect them. The PR boundary designates the layer where place and route tools position cells adjacent to one another. For standard cells, the PR boundary typically spans 3 boxes horizontally and 8 boxes vertically.
Here's the resulting grid view:
<img  width="1085" alt="day18_2" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day18_2.png"> <br>

Save the mag file using the command:
```ruby
save sky130_invvishaka.mag
```
<img  width="1085" alt="day18_3" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day18_3.png"> <br>

The lef write creates the lef file with the name same as cell name.

The cofig.tcl is edited as follows: 
<img  width="1085" alt="day18_5" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day18_5.png"> <br>

The following commands are added inorder to ensure the inverter lef is included to the flow:
```ruby
% set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
% add_lefs -src $lefs
```
The synthesis run is fired using the following command:
```ruby
run_synthesis
```
<img  width="1085" alt="day18_6" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day18_6.png"> <br>

The AND gate acts as clock gate that is the other input decides whether it propagates the clock to the clock tree or not. The AND gate with input connected to 1 and OR gate with input connected to 0 can act as clock gate. The advantage is that the short-circuit power is saved during the switching time.

The following clock tree is usually used for splitting load at the driver. The buffer can be swapped with a gate as follows.

The clock tree has levels of buffering and identical buffers(of same size) are present at same level
The load/fanout is same at each level.
The delay tables act as timing models of the cell. The delay table is a function of input slew and output load.

These are the various switches present in the configuration/README.md file:
<img  width="1085" alt="day18_7" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day18_7.png"> <br>

These variables are defined in the flow as follows:
<img  width="1085" alt="day18_8" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day18_8.png"> <br>


The previously dumped netlist is removed, as it is popping a message that synthesis is skipped as the netlist exists. After the run_synthesis command, the design is much optimized such that the worst negative slack (WNS) and total negative slack (TNS) are zero as follows. 
<img  width="1085" alt="day18_11" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day18_11.png"> <br>


The following command is used to run the floorplan.
```ruby
run_floorplan
```
<img  width="1085" alt="day18_12" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day18_12.png"> <br>


This error implies that run is exited while executing or_basic_map.tcl. This happened after the macros being called. So The command that calls macro_placement is commented as follows.
<img  width="1085" alt="day18_13" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day18_13.png"> <br>

Again, In the floorplan.tcl, it calls for global_placement or macro_placement. So, this is also commented as follows: 
<img  width="1085" alt="day18_14" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day18_14.png"> <br>

Now, the floorplan run is successfully done as follows: 
<img  width="1085" alt="day18_15" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day18_15.png"> <br>

The following command is used to run the placement.
```ruby
run_placement
```

The placement run is completed as follows: 
<img  width="1085" alt="day18_16" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day18_16.png"> <br>

The def created after the placement is as follows: 
<img  width="1085" alt="day18_18" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day18_18.png"> <br>
<img  width="1085" alt="day18_20" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day18_20.png"> <br>

</details>

<details>
	<summary>Timing Analysis with ideal clocks using OpenSTA</summary>

Ideal clock means the clock is not built (pre-cts stage). Let us consider the setup analyis with a single clock specifying theclock to be 1GHz (period=1ns). Inorder to avoid setup violation, the sum of internal delay of launch flop and combinational delay should be less than the time period of clock.

Let us say that the clock at launch arrives at 0ns then the data takes a time of clock period to arrive at the capture flop. When the internal delay of a flop is considered, the capture flop also takes some time to produce output for propagated input. So, this internal delay is called setup time. The setup uncertainty is usually caused by the clock jitter, this makes the delay available for the path more stringent. The clock jitter is the uncertainty that causes delay in the clock that needs to reach at 0ns (to 0.1ns). This is usually caused due to the variations of the clock source. 

The STA is usually done with PrimeTime (SYnopsys)tool. The timing analysis here is done using OpenSTA. Let us go to the openlane flow directory and create a file as follows:
```ruby
cd ~/Desktop/work/tools/openlane_working_dir/openlane
gvim pre_sta.conf                               \\for pre-layout STA i.e., with ideal clock conditions
```

The contents of the pre_sta.conf are as follows:
<img  width="1085" alt="day18_21" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day18_21.png"> <br>

The netlist file is written at synthesis stage and then at CTS stage, but not at floorplan and placement stage. As the clock buffers are inserted at the CTS stage, the netlist is being changed, thus new netlist written out.

The contents of my_base.sdc is as follows:
<img  width="1085" alt="day18_22" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day18_22.png"> <br>

The pre-sta is run by using the following command:
```ruby
cd ~/Desktop/work/tools/openlane_working_dir/openlane
sta pre_sta.conf
```
The following reports are generated showing the least positive slack as follows:
<img  width="1085" alt="day18_23" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day18_23.png"> <br>

Now, we set the fanout to 4 using the following command.
```ruby
echo $::env(SYNTH_MAX_FANOUT)
set ::env(SYNTH_MAX_FANOUT) 4
```

Now, remove the synthesis netlist again and fire the synthesis run and subsequent stages as follows:
```ruby
run_synthesis
run_floorplan
run_placement
```

Now the sta is again checked for as follows:
```ruby
sta pre_sta.conf
report_net -connections _16837_
```
The report_net command is used to check all the connected inputs, outputs and nets as follows. 
<img  width="1085" alt="day18_25" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day18_25.png"> <br>

The buffers can be upsized using the replace_cell command. Upsizing the cell improves transition, thus reducing cell delay.

The following command is used to check the report of timing path as follows:
```ruby
report_checks -fields {net cap slew input pins} -digits 4
```
<img  width="1085" alt="day18_26" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day18_26.png"> <br>

A timing ECO is generated and fed to the PnR tools once the timming is met.

</details>


<details>
	<summary>Clock Tree Synthesis and Signal Integrity</summary>

The time difference required by clock to reach the launch and capture flops is referred as skew. Skew should be as minimal as possible. 

**H-tree algorithm:** <br>
The tool calculates the distance from the clock port to all the clock points that needs to be connected to that port. The clock is routed to the midpoint of distance and then, to the midpoint of the nearby flops and so on. This midpoint procedure makes the skew almost zero, or as minimal as possible. 

**Clock Tree Buffering:** <br>
The clock repeaters have equal rise and fall delay and the datapath buffers do not have equal rise and fall delay. The cells are connected with wires that have some resistance and capacitance. The long length wires causing more transition and more net delays. So The buffers are added inorder to break these long length nets.


**Clock Net Shielding:** <br>
The clock nets are encapsulated from the external world to avoid any coupling between other wires and clock net causing glitch or crosstalk. The shield can be connected to ground or to Vdd, as long as there is no switching activity occurring. Critical data nets are also necessary to be shielded. The unshielded nets can interact with other and act as capacitor causing ground bounds or voltage droop (glitch). This may impact the logical performance of the design. 

When both agressor and victim are switching as follows, the agressor impacts the victim such that it charges instead of discharging for certain time, increasing the cell delay.

The netlist is written out, after the STA using OpenSTA using the following command:
```ruby
write_verilog ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/12-10_12-49/results/synthesis/picorv32a.synthesis.v
```

So, The pre-existing netlist of the synthesis stage is usually overwritten with additional buffers to meet the timing. As there are no aditional buffers required, same netlist is being used. Now, thwe synthesis netlist is generated and timing is met. Let us continue with the consecutive steps as follows:
```ruby
run_floorplan
run_placement
run_cts
```
<img  width="1085" alt="day18_27" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day18_27.png"> <br>

Each stage in PnR has the relative .tcl files in openroad. The files for CTS are or_cts.tcl and cts.tcl. The contents of cts.tcl are as follows: 
<img  width="1085" alt="day18_28" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day18_28.png"> <br>


Let us check the following variables defined in openlane.
```ruby
echo $::env(LIB_TYPICAL)
echo $::env(CURRENT_DEF)
echo $::env(CTS_MAX_CAP)
echo $::env(CTS_CLK_BUFFER_LIST)
echo $::env(CTS_ROOT_BUFFER)
```
<img  width="1085" alt="day18_29" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day18_29.png"> <br>

</details>


<details>
	<summary>Timing Analysis with real clocks using OpenSTA</summary>

Due to addition of clock buffers, clock network delay has been introduced and it will combine all the delays.With real clocks, we will need to have buffers inserted into the clock path to ensure the clock signal integrity.Because of the buffer insertion, the clock edge will reach the clock pin with consideration to the delays of the buffers inserted.

The clock network delay will also need to take into consideration the delays from the buffers inserted.The window will become shifted as a result of the delays from the buffers inserted. The skew for this design will now be the difference between the deltas, and the equation for setup timing analysis will also changed based on the image shown.If the data arrival time is higher than the data required time, then we will have negative slack on the path, meaning we have violations.
For hold timing analysis, where the capture edge is on the 0 clock rise edge, the combinational delay should be greater than the hold time of the flop. Hold time refers to the second mux delay, which is the time required for the data to be sent after the clock edge within the flop. So the data needs to be arrived after the hold time, so the new data can be captured into the flop, after existing data is launched out. 
Jitter for the launch clock and capture flop will not need to be taken into consideration as the design is on the 0 clock edge, and the arrival difference for the capture and launch flop will be the same. So, the uncertainty should be kept low for the hold analysis.

"slack = data arrival time – data required time"

If data required time is higher, we will have negative slack, meaning the timing path for hold will be violated.The equations for setup time and hold time are as follows:

The following steps are executed after CTS stage.

In openroad, the timing analysis is done by creating db using the lef and def files. The lef and def are read and the db is written out as follows. Now, the db is read and the steps are same as in conf.

```ruby
openroad                                                                          \\Invoking openroad
read_lef /openLANE_flow/designs/picorv32a/runs/13-01_14-09/tmp/merged.lef
read_def /openLANE_flow/designs/picorv32a/runs/13-01_14-09/results/cts/picorv32a.cts.def
write_db pico_cts.db
read_db pico_cts.db
read_verilog /openLANE_flow/designs/picorv32a/runs/13-01_14-09/results/synthesis/picorv32a.synthesis_cts.v
read_liberty -max $::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd_slow.lib
read_liberty -min $::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd_fast.lib
set_propagated_clock [all_clocks]
read_sdc designs/picorv32a/src/my_base.sdc   \\calculates actual cell delay in clockpath
report_checks -path_delay min_max -format full_clock_expanded -digits 4
```

<img  width="1085" alt="day18_30" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day18_30.png"> <br>


The above analysis stands incorrect because the design is defined for typical corner and the libs for analysis are min and max. So, the correct way of analysis is as follows. Now, the same steps are follwed but the liberty file used is typical corner.

```ruby
exit        \\Exit openroad...Do it twice if read_sdc command doesn't work
openroad
read_db pico_cts.db
read_verilog /openLANE_flow/designs/picorv32a/runs/13-01_14-09/results/synthesis/picorv32a.synthesis_cts.v
read_liberty $::env(LIB_SYNTH_COMPLETE)
link_design picorv32a
read_sdc designs/picorv32a/src/my_base.sdc
set_propagated_clock [all_clocks]
report_checks -path_delay min_max -fields {slew trans net cap input pin} -format full_clock_expanded
echo $::env(CTS_CLK_BUFFER_LIST)                              (To see the list of buffers)
```
<img  width="1085" alt="day18_33" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day18_33.png"> <br>

```ruby
exit 
echo $::env(CTS_CLK_BUFFER_LIST)
set ::env(CTS_CLK_BUFFER_LIST) [lreplace $::env(CTS_CLK_BUFFER_LIST) 0 0]
echo $::env(CURRENT_DEF)
set ::env(CURRENT_DEF) /openLANE_flow/designs/picorv32a/runs/13-01_14-09/results/placement/picorv32a.placement.def
run_cts
```

```ruby
openroad
read_lef /openLANE_flow/designs/picorv32a/runs/13-01_14-09/tmp/merged.lef
read_def /openLANE_flow/designs/picorv32a/runs/13-01_14-09/results/cts/picorv32a.cts.def
write_db pico_cts1.db
read_db pico_cts1.db
read_verilog /openLANE_flow/designs/picorv32a/runs/13-01_14-09/results/synthesis/picorv32a.synthesis_cts.v
read_liberty $::env(LIB_SYNTH_COMPLETE)
link_design picorv32a
read_sdc designs/picorv32a/src/my_base.sdc
set_propagated_clock [all_clocks]
report_checks -path_delay min_max -fields {slew trans net cap input pin} -format full_clock_expanded
```

After changing clock buffers, the new timing reports are generated.

Let us check the clock skew of the design as follows:

```ruby
report_clock_skew -hold
report_clock_skew -setup
set ::env(CTS_CLK_BUFFER_LIST) [linsert $::env(CTS_CLK_BUFFER_LIST) 0 sky130_fd_sc_hd__clkbuf_1]      (Adding back clkbuf1)
```
<img  width="1085" alt="day18_34" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day17-18/day18_34.png"> <br>


</details>

## Day-19- Final steps for RTL2GDS using tritonRoute and openSTA

<details>
	<summary>Routing and Design Rule Check</summary>

 **Maze routing - Lee algorithm:**
Routing is the vital process of establishing physical wire connections within a design. It involves optimizing the path between two endpoints, aiming for the shortest and most efficient route with minimal twists and turns. Importantly, routes cannot traverse pre-placed cells within the design.

The routing algorithm typically operates on the backside of the floorplan, beginning by labeling the grids adjacent to the points to be connected as '1', followed by their neighboring layers as '2', and so forth. This stepwise approach helps ensure an orderly and efficient connection between components.

The grids beneath the blockage are not labeled, as routing cannot pass through them. Choosing the left-hand side (LHS) of the figure below is preferable, as it offers a more optimal route with fewer bends (L-shaped) compared to the right-hand side (RHS) of the figure.

While routing for a single route is relatively straightforward, the complexity escalates when dealing with a multitude of start and endpoint pairs in a large design. This approach can be time and memory-intensive for substantial designs. To mitigate this, there are algorithms available that can help reduce both time and memory consumption, such as the line-search algorithm and the stanner-tree algorithm.

**Design Rule Check:**
Design Rule Checks (DRC) encompass the set of regulations that must be adhered to during the design routing process. These rules include:

Minimal wire width: The width of wires must not fall below a specified threshold, determined by the constraints of the fabrication process.

Wire pitch: The center-to-center spacing between two wires should not be smaller than a defined distance, ensuring appropriate separation.

Wire spacing rule: The distance between any two wires should be no smaller than a certain specified value, preventing undesired proximity.

These rules are vital because the creation of these wires involves a photolithographic process, where the desired width and pitch are crucial for accurate and reliable design implementation.

A common type of DRC violation is a signal short, which occurs when two wires that are not meant to be connected come into contact on the same layer, potentially leading to functional failure. To resolve this issue, the solution is often as simple as relocating one of the wires to a different metal layer. The updated DRC rules, following this adjustment, typically include:

Via width: Specifies a minimum width requirement for vias, ensuring they meet a specified value.

Via spacing: Enforces a minimum separation distance between any two vias, ensuring that they are not placed too closely together. It's worth noting that upper metal layers in the design are typically wider than lower metal layers for various reasons, including reducing resistance and enabling more significant current-carrying capacity.


</details>
 <details>
	 <summary>PDN and routing</summary>

If you wish to preserve the configurations from the previous OpenLane job, you should use the following command: prep -design -tag.

If you want to initiate a new run with fresh configurations while keeping the same tag name, you should use: prep -design -tag -overwrite.

Here's an example of how to use these commands within the OpenLane environment:
```ruby
cd work/tools/openlane_working_dir/openlane
./flow.tcl -interactive
package require openlane 0.9
prep -design picorv32a -tag 13-01_14-09
```

These commands will help you manage the configurations and run OpenLane with the desired settings.


The power and ground rails need to be a part of floorplan, this is done using gen_pdn command to build the power distribution network. The standard cell height should be multiple of pitch of layers(metal1), so that cell gets power and ground rails alog its edges for proper connectivity.

Inorder to generate the pdn network, the following commands are used.
```ruby
echo $::env(CURRENT_DEF)    \\Ensure current_def is on the CTS stage
gen_pdn                     \\To generate power distribution network
```

This is giving an error as follows:
<img  width="1085" alt="day19_1" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day19/day19_1.png"> <br>

Due to this error, the pdn def is not generated so CTS def is used for routing.

The design is covered with IO pads around them. These pads contain the power and ground pads.

The current def is set to the CTS def and the routing run is fired.
```ruby
echo $::env(CURRENT_DEF)            
echo $::env(ROUTING_STRATEGY)
run_routing
```

The ROUTING_STRATEGY variable implies the optimized routing in the design. The value 0 specifies the routing is not much optimized. 
<img  width="1085" alt="day19_2" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day19/day19_2.png"> <br>



 </details>

 <details>
	 <summary>TritonRoute Features</summary>

The routing stage can be broken down into two essential phases:

1. Global Routing: This step involves generating routing guides capable of accommodating all the nets within the design. FastRoute is the tool typically employed for this task.

2. Detailed Routing: Building upon the routing guides provided by the global routing phase, the detailed routing step connects the pins with minimal wire usage and bends. TritonRoute is the tool commonly utilized to achieve this detailed routing.

**Triton Route:**
TritonRoute is a crucial component in the routing process, and it operates using the following methodology:

1. **Global Routing Engine**: FastRoute is employed as the global routing engine to create a preliminary routing draft. This phase divides the design region into grid cells, forming a routing guide for TritonRoute to use in detailed routing.

2. **Routing Grid**: During global routing, the design area is divided into grid cells, which serve as the basis for TritonRoute's detailed routing. Algorithms are employed to find the optimal connections between points, leveraging the preprocessed route guides obtained from the fast routes. TritonRoute aims to route as much as possible within these guides, assuming that each net adheres to inter-guide connectivity requirements.

3. **Routing Approach**: TritonRoute uses a proposed Mixed Integer Linear Programming (MILP) based panel routing scheme. This scheme incorporates intra-layer parallel and inter-layer sequential routing frameworks to determine the most efficient routing paths. Intra-layer routing pertains to routing within a single layer, while inter-layer routing involves connecting layers through the use of vias.

4. **Preprocessed Route Guides**: The preprocessed route guides are critical to TritonRoute's operation. These guides should have unit width and align with the preferred direction of the layer. FastRoute initially generates the global route and outputs the routing guide. These initial guides are transformed into preprocessed guides through techniques like splitting, merging, and bridging.

5. **Preferred Routing Direction**: TritonRoute ensures that each layer or panel has an assigned preferred routing direction. Routing in higher layers only commences once the routing in lower layers is complete. Connectivity between guides is established when they are on the same metal layer with touching edges or on neighboring metal layers with non-zero vertically overlapped areas. Additionally, each unconnected terminal, such as the pin of a standard cell instance, should have its pin shape overlapped by a route guide.

6. **Inputs and Outputs**: TritonRoute takes inputs in the form of LEF (Library Exchange Format) files, DEF (Design Exchange Format) files, and the preprocessed route guides. The outputs from TritonRoute consist of a detailed routing solution that optimizes wire length and via count. It operates under various constraints, including route guide honoring, connectivity constraints, and design rules.

**TritonRoute Connectivity Handling**:
TritonRoute manages connectivity through two key methods:

- **Access Point (AP)**: Access points are on-grid locations on the metal layer of the route guide and serve to connect lower-layer segments, upper-layer segments, pins, or IO ports. These are where vias can be placed to facilitate inter-layer connectivity.

- **Access Point Cluster (APC)**: Access Point Clusters represent a collection of access points derived from the same lower-layer segment, upper-layer guide, pin, or IO port.

The primary objective of TritonRoute's Mixed Integer Linear Programming (MILP) is to optimally connect one access point to another, determining where vias should be placed and how they will facilitate connections between these points.
 </details>


## Day-20- Floorplanning and Powerplanning Labs

<details>
	<summary>Introduction</summary>

Physical design encompasses the process of transforming a high-level logical description of a circuit into a detailed physical representation suitable for manufacturing. This stage involves creating a layout that precisely defines the positions, sizes, and interconnections of individual components like transistors, gates, and wires on the silicon wafer. Physical design is a critical phase in the chip design process, directly impacting aspects such as performance, power consumption, and manufacturability.

The key steps in the Physical Design flow are as follows:

1. **Technology Selection**: Choose the semiconductor process technology, which sets the manufacturing parameters, transistor sizes, and available components.

2. **Floorplanning**: Define the chip's overall layout, specifying the positions of major components and areas for routing.

3. **Placement**: Position standard cells and macro blocks within the floorplan to optimize for area, power, and performance.

4. **Global Routing**: Create a high-level interconnection structure, connecting the blocks and ensuring power and clock signals reach all chip areas.

5. **Detailed Placement**: Fine-tune the placement of standard cells to meet performance and area objectives, considering factors like signal propagation delay and wirelength.

6. **Clock Tree Synthesis**: Develop a clock distribution network for synchronous operation of circuit elements.

7. **Routing**: Route wires to connect all components while adhering to design rules and optimizing for minimal wirelength and congestion.

8. **Design Rule Checking (DRC)**: Verify that the layout complies with manufacturing constraints and design rules.

9. **Layout vs. Schematic (LVS) Verification**: Ensure that the physical layout matches the intended logical design.

10. **Extraction**: Extract parasitic information from the layout, essential for precise timing analysis.

11. **Static Timing Analysis (STA)**: Analyze the circuit's timing behavior to ensure it meets performance specifications.

12. **Power Analysis**: Evaluate power consumption and optimize for low power, if necessary.

13. **Physical Verification**: Perform additional checks such as Antenna Checks, Metal Fill, and Design for Manufacturability (DFM).

14. **Tapeout**: Prepare the final design data for manufacturing.

Each of these steps is critical in creating a physically realizable chip design that meets its functional and performance requirements while adhering to manufacturing constraints and design rules.

**Inputs for Physical Design**:

1. **Technology File (.tf or .db)**: Contains information about the semiconductor process technology, including manufacturing parameters, transistor characteristics, and available components.

2. **Physical Libraries (LEF or GDS)**: These libraries provide detailed information about design elements like macros, standard cells, and IO pads, including their physical dimensions and characteristics.

3. **Timing, Logical, and Power Libraries**: These libraries contain critical data regarding timing constraints, logical elements, and power requirements.

4. **TDF File (.tdf or .io)**: The Technology Dependency File specifies technology-specific information and dependencies that impact the design process.

5. **Constraints (.sdc)**: The Synopsys Design Constraints (SDC) file defines constraints related to timing, area, power, and other design aspects.

6. **Physical Design Exchange Format (PDEF, optional)**: PDEF is an optional format used for exchanging physical design data between different tools in the design flow.

7. **Design Exchange Format (DEF, optional)**: DEF files are optionally used to exchange design data with other tools or platforms.

**Outputs from Physical Design**:

1. **Standard Delay Format (.sdf)**: This file provides delay information for different logical paths within the design, which is crucial for timing analysis and simulation.

2. **Parasitic Format (.spef, .dspf)**: These files contain parasitic information extracted from the physical layout, aiding in accurate timing analysis and simulation.

3. **Post-Routed Netlist (.v)**: This file represents the logical and physical netlist after the routing phase, reflecting the actual connections between components.

4. **Physical Layout (.gds)**: The Graphic Data System (GDS) file is the physical layout of the design in a format that can be used for fabrication.

5. **Design Exchange Format (.def)**: The DEF file can serve as an output, providing a representation of the design for exchange with other tools or for archival purposes.

These inputs and outputs are vital in the physical design process as they facilitate the exchange of critical design information and ensure that the design meets performance, power, and manufacturability goals.

**Floorplan**:
**Objectives**:
- Minimize Area.
- Reduce wire length.
- Facilitate easy routing.
- Minimize delay.
- Reduce IR Drop.

**Issues with Bad Floorplan**:
- Congestion.
- IR Drop.
- Reduced lifespan of the IC.
- Noise.
- Increased area.
- Routing difficulties, and more.

**Types**:
1. **Abutted**: Components are placed side by side with no space between them.
2. **Non-Abutted**: Components have space between them.
3. **Mixed**: A combination of both abutted and non-abutted placement.

**Steps in Floor Planning**:
1. Links Netlist with physical library.
2. Creates the initial core area.
3. Establishes I/O pin placement and pad rings.
4. Positions macros and standard cells.
5. Defines placement blockages.
6. Specifies power and ground nets.
7. Creates power rings and macro rings.
8. Routes power and ground nets.
9. Checks for violations.

**Power Plan**:
Power planning is focused on providing power to the chip while considering issues like Electro-Migration (EM) and IR Drop. Key components of power planning include:

- Calculating the number of power pins required.
- Determining the number of power rings and stripes.
- Specifying the width of power rings and stripes.
- Addressing IR Drop issues.

These steps ensure that the chip receives adequate and stable power, minimizing potential power-related problems.


</details>

<details>
	<summary>Labs</summary>

	
 **Clone the following repositories for the physical design flow setup:**
```ruby
git clone https://github.com/manili/VSDBabySoC.git
git clone https://github.com/Devipriya1921/VSDBabySoC_ICC2.git
git clone https://github.com/bharath19-gs/synopsys_ICC2flow_130nm.git
git clone https://github.com/kunalg123/icc2_workshop_collaterals.git
git clone https://github.com/google/skywater-pdk-libs-sky130_fd_sc_hd.git
git clone https://github.com/kunalg123/sky130RTLDesignAndSynthesisWorkshop.git
```
The contents to my path are changed to the locations where files are cloned. The changes in vsdbabysoc.tcl are as follows:
<img  width="1085" alt="day20_1" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day20/day20_1.png"> <br>

The unwanted pins in avsdpll.lib are already commented out. 
<img  width="1085" alt="day20_2" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day20/day20_2.png"> <br>


The vsdbabysoc.tcl file is sourced to generate the area, power, timing and sdc as follows:
```ruby
cd ~/Physical_Design/VSDBabySoC_ICC2
csh
dc_shell
source vsdbabysoc.tcl
```
<img  width="1085" alt="day20_3" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day20/day20_3.png"> <br>

*The reports generated:*
1. Area report:
<img  width="1085" alt="day20_4" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day20/day20_4.png"> <br>

2. Power report:
<img  width="1085" alt="day20_5" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day20/day20_5.png"> <br>

3. Timing report:
<img  width="1085" alt="day20_6" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day20/day20_6.png"> <br>
<img  width="1085" alt="day20_7" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day20/day20_7.png"> <br>
The timing is met with a positive slack of 30ps. The worst slack is considered as the critical slack.

4. Constraints report:
<img  width="1085" alt="day20_8" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day20/day20_8.png"> <br>

*Gui based circuit of the design as follows:*
<img  width="1085" alt="day20_9" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day20/day20_9.png"> <br>

*The schematic of the BabySoC is as follows:*
<img  width="1085" alt="day20_10" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day20/day20_10.png"> <br>

*The RYMTH core schematic is as follows:*
<img  width="1085" alt="day20_11" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day20/day20_11.png"> <br>
<img  width="1085" alt="day20_12" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day20/day20_12.png"> <br>
<img  width="1085" alt="day20_13" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day20/day20_13.png"> <br>

**Physical design:**
Inorder to setup the flow, the following files are edited with present working constraints of design and location of files. The following files are edited:

**top.tcl:**
The floorplan switch is added for create_placement command and all linking paths are updated.
<img  width="1085" alt="day20_14" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day20/day20_14.png"> <br>

**icc2_common_setup.tcl:**
All the paths are updated and the metal routing layers are defined. 
<img  width="1085" alt="day20_15" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day20/day20_15.png"> <br>

**icc2_dp_setup.tcl:**
<img  width="1085" alt="day20_16" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day20/day20_16.png"> <br>
All paths are updated in the icc2_dp_setup.tcl file also.

**init_design.read_parasitic_tech_example.tcl:**
Inorder to generate tluplus file from itf file, the following command is used.
```ruby
grdgenxo -itf2TLUPlus -i skywater130.nominal.itf -o skywater130.nominal.tluplus
```
<img  width="1085" alt="day20_17" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day20/day20_17.png"> <br>

**init_design.mcmm_example.auto_expanded.tcl:**

The SDC path in the file is updated to the generated SDC after the synthesis. 
<img  width="1085" alt="day20_18" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day20/day20_18.png"> <br>

**pns_example.tcl:**
The power grid pattern for supply and ground rails requires the definition of the layers to be used. The vertical and horizontal layers are changed as shown.
<img  width="1085" alt="day20_19" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day20/day20_19.png"> <br>


Invoking the icc2_shell, inorder to run the design using following commands.
```ruby
cd ~/Physical_Design/icc2_workshop_collaterals/standaloneflow
csh
icc2_shell
source top.tcl
```
<img  width="1085" alt="day20_20" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day20/day20_20.png"> <br>

The gui based design is as follows:
<img  width="1085" alt="day20_21" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day20/day20_21.png"> <br>
<img  width="1085" alt="day20_22" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day20/day20_22.png"> <br>

*Check for the timing violations.:*
```ruby
icc2_shell> set_propagated_clock [all_clocks]             //Converting clock object from ideal clock to propagated clock
icc2_shell> report_timing
```
<img  width="1085" alt="day20_24" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day20/day20_24.png"> <br>

```ruby
icc2_shell> estimate_timing
```
<img  width="1085" alt="day20_25" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day20/day20_25.png"> <br>

```ruby
icc2_shell> report_constraints -all_violators -nosplit -verbose -significant_digits 4 > violators.rpt
icc2_shell> sh gvim violators.rpt &
```
<img  width="1085" alt="day20_28" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day20/day20_28.png"> <br>

*Changing the utilization to 0.07:*
<img  width="1085" alt="day20_31" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day20/day20_31.png"> <br>

Rerunning the icc2_shell
<img  width="1085" alt="day20_21" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day20/day20_21.png"> <br>

Now if we set the boundary using command
```rby
intialize_floor -boundary { from left hand side in anticlockwise direction> -core_utilization }
```
The one used in our case was - boundary {{0 0} (1200 0} {1200 650} {0 650}} -core_utilization 0.07

 ```ruby
set_propagated_clock [all_clocks]
report_timing
```
<img  width="1085" alt="day20_26" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day20/day20_26.png"> <br>

Again checking violators.rpt

We see that slacks have got reduced.
</details>



## Day-21- Placement and CTS Labs

<details>
	<summary>Introduction</summary>

**Pre-Placement::** <br>
*Physical Cells:* <br>
These are fundamental building blocks in chip design. They are devoid of signal connectivity and serve as the foundational components for implementing various logical functions. Physical cells, commonly referred to as standard cells, are pivotal for the layout and manufacturing of integrated circuits.

*Functions:* <br>
Functionality: Physical cells encapsulate the essential functions required for logical operations.
Cell Libraries: They are part of the extensive cell libraries that provide a diverse range of components for chip design.
Fixed Cell Height and Variable Width: Physical cells typically have a constant height and flexible width, enabling designers to tailor their dimensions to fit the chip's layout.
Well Taps: Well taps play a critical role in preventing latch-up and maintaining proper biasing of transistors in CMOS processes.

*Types:* <br>
N-Well Taps: These are employed to connect the n-well regions of PMOS transistors to the ground (Vss), ensuring the correct biasing of PMOS devices.
P-Well Taps: Conversely, p-well taps are used with NMOS transistors to connect the p-well regions to the supply voltage (Vdd).

*Functions:*
<ul>
	<li>Preventing Latch-Up: Well taps break parasitic thyristor structures and prevent latch-up, a condition that can cause chip failure.</li>
	<li>Substrate Bias Control: They ensure proper connectivity of the substrate to the supply or ground.</li>
	<li>Maintains Isolation: Well taps help to isolate different regions within the chip.</li>
	<li>>End Cap Cells: Also known as filler cells, end cap cells serve a range of important functions and are strategically placed at the periphery of a chip.</li>
</ul>

*Functions:* <br>
<ul>
	<li>Planarity and Uniformity: End cap cells contribute to maintaining the planarity and uniformity of the chip's layout.</li>
	<li>Densification: They aid in optimizing the chip's physical space, making it more efficient.</li>
	<li>Isolation and Protection: End cap cells provide isolation and protection, safeguarding the chip's integrity.</li>
	<li>Enhanced Manufacturing Yield: Their presence enhances manufacturing yield by addressing irregularities at the chip's edges.</li>
</ul>

*Types of End Cap Cells:* <br>
Standard Fillers: Basic end cap cells used to fill empty spaces and ensure a uniform chip design. They come in various shapes and sizes to accommodate different gaps.
Corner Fillers: Specifically designed to fill irregular L-shaped or T-shaped gaps at the chip's corners, ensuring structural integrity.
Edge Cells: These elongated cells are tailored to fit gaps along the long edges of the chip and can be optimized to meet specific design requirements.
Special Cells: These custom or macro cells fulfill specific functions that cannot be represented by standard or generic cells. They are often used for memory storage, analog processing, arithmetic operations, or I/O functions.
Spare Cells: Redundant cells integrated into the chip design to replace malfunctioning standard cells, ensuring chip functionality and reliability.

*Decap Cells:* <br>
*Functions:* <br>
Power Supply Noise Reduction: Decap cells help reduce noise in the power supply, ensuring stable and clean voltage levels.
Stabilizing the Power Distribution Network: They play a crucial role in stabilizing the distribution of power across the chip.
Improving Signal Integrity: By mitigating voltage fluctuations and noise, decap cells contribute to improved signal integrity.
Mitigating Electromagnetic Interference (EMI): These cells aid in reducing electromagnetic interference, which can disrupt the chip's operation.
Types of Decap Cells:

Standard Decap Cells: These have fixed capacitance values and are commonly used across the chip.
Switchable or Programmable Decap Cells: These offer flexibility by allowing designers to configure the capacitance based on the specific requirements of different chip regions or functional blocks.
Cell Padding: Cell padding is the practice of reserving space on the chip layout to avoid routing congestion, ensuring efficient interconnection of components.


**Placement:** <br>
Placement is a crucial stage in chip design where standard cells are not only arranged in the synthesized netlist but also optimized to enhance the overall design and determine its routability.

*Goals and Objectives:* <br>
Timing, Power, and Area Optimization: Achieving the best balance among timing performance, power consumption, and chip area utilization.
Minimum Congestion: Reducing design bottlenecks and ensuring smooth interconnection.
Minimum Cell Density and Pin Density: Optimizing the distribution of cells and pins for efficient routing.
Inputs for Placement: Key inputs for the placement process include technology files (.tf), netlists, SDC files (.sdc), library files (.lib and .lef), floor planning data, and power planning DEF files.

*Placement Methods:* <br>
Timing Driven: Prioritizes timing constraints and requirements during placement.
Congestion Driven: Focuses on minimizing congestion issues in the layout.

*Steps:* <br>
Defining Design Constraints: Establishing the design parameters and requirements. <br>
Reading Gate-Level Netlist from Synthesis: Importing the synthesized netlist for placement. <br>
Global Placement: Initial placement of cells on the chip's grid. <br>
Detailed Placement: Fine-tuning the positions of cells to meet timing and other constraints. <br>
Placement Optimization: Further refinement of cell placements. <br>
Cell Sizing: Adjusting the sizes of cells for optimal design. <br>
Cloning: Creating multiple copies of the same cell. <br>
Buffering Outputs of Placement: Inserting buffers to improve signal quality. <br>
Providing Physical Layout Information: Ensuring the layout adheres to physical constraints. <br>
Cell Placement Location: Determining the precise positions of each cell. <br>
Incorporating Timing and Technology Information from Reference Libraries: Using data from reference libraries to guide placement decisions. <br>


**Clock Tree Synthesis (CTS):** <br>
Clock tree synthesis is a critical phase in chip design involving the creation of a clock distribution network. <br>

*Key Objectives of Clock Tree Synthesis:* <br>
Efficient Clock Signal Distribution: Ensuring the clock signal is distributed from a single source (the clock buffer) to all flip-flops, latches, and sequential elements throughout the chip. <br>
Minimizing Skew: Skew, or variation in clock signal arrival times, is minimized to ensure synchronous operation. <br>
Balanced Load: The capacitive load on each branch of the clock tree is balanced to maintain signal integrity. <br>
Reducing Power Consumption: Efficient CTS reduces power consumption by optimizing the placement and number of clock buffers. <br>

*Key Steps in Clock Tree Synthesis:*  <br>
Clock Tree Construction: The clock tree network is built, creating a hierarchical structure of clock buffers and wires. <br>
Buffer Sizing and Insertion: The right type and size of clock buffers are selected and strategically placed to balance drive strength and capacitive load. <br>
Clock Tree Balancing: Efforts are made to distribute the clock signal uniformly to all parts of the chip, reducing skew. <br>
Skew Minimization: Advanced techniques are employed to further reduce clock skew, ensuring synchronous and efficient operation. <br>
</details>

<details>
	<summary>Labs</summary>

The image below displays the reports generated during the place_opt, clock_opt and route_auto stages.
<img  width="1085" alt="day21_01" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day21/day21_01.png"> <br>

The SDC file does not include latency information, as it is computed in real-time during the construction of the Clock Tree Synthesis (CTS). The "create_placement" command is employed to generate the placement for the design. The "floorplan" option is chosen to align the design planning with the placement. Pin placement is accomplished by utilizing the "pns.tcl" script to synchronize with the current technology file, especially in relation to power grid creation.
<img  width="1085" alt="day21_02" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day21/day21_02.png"> <br>

Post-execution, reports are automatically generated in a directory named "rpts_icc2" as specified in the SDC file. Among these reports, "check_design.pre_pin_placement" is one of them. It's important to note that prior to pin placement, a check is performed using the "check_design" command, and no errors or warnings are identified in this initial assessment.
<img  width="1085" alt="day21_1" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day21/day21_1.png"> <br>

The "report_port_placement.rpt" provides a detailed account of the top-level design's ports, along with the metals designated for routing and their respective offset values.
<img  width="1085" alt="day21_2" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day21/day21_2.png"> <br>

The "report_placement.rpt" provides a comprehensive overview of the current design placement, with the following key details:

- **Total Net Length**: The report specifies that the total net length in the design amounts to 65790 microns. This metric is crucial for evaluating the overall routing efficiency and wirelength in the design.

- **Hard Macros Overlaps**: The report confirms that there are no instances of hard macros overlapping. Hard macros are pre-designed, reusable blocks of circuitry, and ensuring their non-overlapping placement is essential for correct chip functionality.

- **Placement Violations**: The report indicates that no placement violations have been detected. Placement violations can encompass various issues, including cells being too close to each other or improperly positioned, which may impact signal integrity or manufacturing.

- **Voltage Areas Compliance**: It affirms that all cells have been successfully placed within their respective voltage areas. This is vital for guaranteeing the proper power distribution and electrical isolation, ensuring that cells operate under the correct voltage levels in the chip design.

<img  width="1085" alt="day21_03" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day21/day21_03.png"> <br>

"vsdbabysoc.post_estimated_timing.rpt," 

<img  width="1085" alt="day21_8" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day21/day21_8.png"> <br>

Within the "vsdbabysoc.post_estimated_timing.qor" report, the Quality of Results (QOR) section provides a comprehensive summary of several key design attributes, including:

- **Cell Count**: This section specifies the total number of cells used in the design, offering insight into the design's complexity.

- **Critical Path**: It highlights the critical path within the design, which is the longest path in terms of delay and can be vital for determining overall performance.

- **Critical Slack**: This report provides the critical slack value, which represents the timing margin or delay allowance on the critical path. A positive slack indicates that the timing requirements are met, and the design is operating with a margin.

- **Macros Used**: This section enumerates the macros utilized within the design. Macros are pre-designed blocks that can significantly impact design efficiency and functionality.

- **Area Used**: It specifies the total area occupied by the design, which is critical for understanding the chip's physical footprint and overall layout.

Overall, this report offers a detailed breakdown of the cells placed in the design, providing valuable information about the design's characteristics and performance metrics.
<img  width="1085" alt="day21_3" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day21/day21_3.png"> <br>


The "vsdbabysoc.post_estimated_timing.qor.sum" report offers a concise summary of two important aspects:

- **DRC Violations**: It presents any Design Rule Check (DRC) violations found in the design. DRCs are constraints that ensure the chip adheres to specified manufacturing rules, and violations can lead to manufacturing issues.

- **Timing Violations of Estimated Corners**: This section highlights any timing violations in relation to estimated corners. Timing violations occur when the design fails to meet specified timing requirements, potentially impacting the chip's functionality and performance.


For clock tree analysis, when you open the graphical user interface (GUI), navigate to the "Window" section. Within this section, select the "Clock Tree Synthesis Analysis" window. 

In the context of clock analysis, the provided image illustrates the connection of the PLL source to various cells in the design.
<img  width="1085" alt="day21_9" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day21/day21_9.png"> <br>
<img  width="1085" alt="day21_10" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day21/day21_10.png"> <br>



The image below presents a fanout view of the clock within the design. It visually displays the nets connecting all cells from the clock source to the respective clock pins.
<img  width="1085" alt="day21_11" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day21/day21_11.png"> <br>

</details>


## Day-22- CTS analysis Labs

<details>
	<summary>Introduction</summary>

The primary objective of Clock Tree Synthesis (CTS) is to achieve the uniform and minimal skew distribution of the clock signal to all sequential elements (such as flip-flops and registers) within the VLSI chip. This synchronization is crucial to maintain proper timing and ensure the synchronous operation of the digital circuit. The overarching goal of CTS is to minimize both skew and insertion delay.

CTS employs various algorithms to attain this synchronization and minimize delay. Some of the algorithms used for CTS include:
<ul>
	<li>Clock-wise conventional CTS</li>
	<li>Clock-wise multisource CTS</li>
	<li>Clock-wise H-tree CTS</li>
	<li>Clock-wise mesh CTS</li>
</ul>

*H-tree algorithm:* <br>
The H-tree algorithm is a specific approach used in Clock Tree Synthesis (CTS) to distribute the clock signal uniformly to all the flip-flops in a VLSI chip. Here's a detailed breakdown of the H-tree algorithm's steps:

1. **Identification of Flip-Flops**: The first step involves identifying all the flip-flops present in the chip. These flip-flops are the sequential elements that require a synchronized clock signal.

2. **Center Point Determination**: Next, the algorithm calculates the center point of all the identified flip-flops. This central location serves as the starting point for the clock signal distribution.

3. **Initial Clock Signal Trace**: The clock signal is traced from the clock source to the central point calculated in the previous step. This establishes the initial connection between the clock source and the central location.

4. **Core Division and Further Tracing**: The chip's core area is then divided into two parts. Clock signal traces are extended from the central point to each of these divided sections, reaching the centers of each part. This division and tracing are performed to maintain signal integrity and minimize skew.

5. **Recursive Division and Tracing**: The algorithm continues to recursively divide the areas into two, effectively creating an H-tree structure. Clock signal traces extend from each new center to the centers at both ends of the divided areas. This recursive process continues until the clock signal reaches the clock pins of the flip-flops.

In summary, the H-tree algorithm systematically traces and distributes the clock signal from a central point to flip-flops throughout the chip, minimizing skew and ensuring synchronous operation. This approach creates a structured, tree-like network of clock distribution, optimizing clock signal integrity and timing.


*Clock Tree Synthesis comprises several crucial stages:* <br>
1. **Clock Tree Generation:** This initial step establishes a hierarchical tree structure, originating from the primary clock source and extending to various regions within the chip. The purpose is to minimize clock skew and enhance signal distribution efficiency.

2. **Buffer Insertion:** Buffers are strategically inserted along the clock tree. These buffers serve to maintain signal integrity and reduce clock skew, especially in cases involving long clock lines, thereby mitigating signal delay.

3. **Clock Skew Optimization:** CTS algorithms prioritize the minimization of clock skew. This is essential to ensure that all flip-flops across the chip receive the clock signal simultaneously. Eliminating clock skew helps prevent setup and hold time violations, vital for maintaining proper circuit operation.

4. **Clock Gating:** In some scenarios, clock gating elements are introduced into the clock tree. These elements allow the selective disabling of the clock signal for specific sections of the design when they are not in active use. Clock gating optimizes power consumption by reducing dynamic power.

5. **Verification:** Following CTS implementation, the design undergoes thorough verification. This process ensures that the clock signal is distributed correctly and complies with stringent timing requirements, essential for robust and reliable chip operation.


*The role of Clock Tree Synthesis (CTS) in Very Large-Scale Integration (VLSI) design is paramount:* <br>
1. **Timing Closure**: CTS plays a pivotal role in achieving timing closure, assuring that the digital design functions seamlessly within specified clock frequencies, free from setup and hold time violations. This is crucial for meeting performance targets and design reliability.

2. **Reducing Clock Skew**: CTS diligently minimizes clock skew, which is instrumental in enabling synchronous operation and guarding against metastability issues in sequential elements. Clock signals reaching flip-flops simultaneously are vital for stable and predictable operation.

3. **Power Optimization**: The inclusion of clock gating techniques in CTS contributes to efficient power management. By disabling clock signals in inactive regions of the chip, dynamic power consumption is reduced. This not only conserves energy but also enhances the chip's overall efficiency.

4. **Enhancing Chip Performance**: A well-structured and optimized clock tree, created through CTS, leads to improved chip performance. It reduces clock distribution delays and fosters effective synchronization, which is fundamental for reliable and high-performing VLSI designs.

*Clock Tree Synthesis (CTS) is not without its challenges:* <br>
1. **Skew Minimization**: Attaining minimal clock skew can prove to be a challenging task, particularly in intricate designs with numerous clock domains. Managing skew across these domains requires meticulous planning and execution.

2. **Trade-offs**: CTS often involves a trade-off between power consumption and clock distribution delay. Striking the right balance between the two is a delicate task that necessitates thoughtful design decisions to optimize both parameters effectively.

3. **Hierarchical Design**: In hierarchical Very Large-Scale Integration (VLSI) designs, CTS can become more intricate. Synthesizing clock trees at various hierarchical levels introduces an added layer of complexity and requires special attention to ensure seamless integration of clocks across the design hierarchy.


*Some commands at CTS:* <br>
Create Clock Tree: Generate the clock tree structure using CTS algorithms.
```ruby
create_clock_tree
```

```ruby
check_legality
```

```ruby
compile_clock_tree
optimize_clock_tree
```


</details>

<details>
	<summary>Labs</summary>


```ruby
check_clock_tree
```

Usage of check_clock_tree:

Analysis: The check_clock_tree command is used to analyze the quality and characteristics of the generated clock tree. It checks for issues such as skew, insertion delay, and hold time violations, which could affect the functionality and performance of the design.

Optimization: After running the command, you can make adjustments to the clock tree, if necessary, to improve its quality. This might involve changing buffer placements, resizing buffers, or altering the clock tree topology.

Verification: It's important to ensure that the clock tree meets the design specifications and requirements. The check_clock_tree command helps in verifying that the clock tree adheres to these specifications and constraints.

The report provides a comprehensive assessment of the Quality of Results (QoR) of the clock tree that has been constructed. It offers insights into various key aspects, including:

- **Multi-Voltage Violations**: The report examines whether there are any violations related to multi-voltage domains. Managing voltage domains is critical for proper chip operation and avoiding voltage-related issues.

- **Skew Balancing**: It assesses the skew balancing within the clock tree. Achieving balanced clock skew is essential to ensure that all sequential elements operate synchronously.

- **Capacitance & Transition in Clock Network**: The report delves into the capacitance and signal transition aspects of the clock network. These are key factors in signal integrity and performance.

- **Reference Cells**: It scrutinizes the reference cells defined as "don't use" or "don't touch" cells. Ensuring that these cells are not used or modified as intended is crucial for maintaining design consistency.

Remarkably, the output of this command indicates that there are "None" to all the potential violations in these critical areas. This signifies that the clock tree synthesis has been executed successfully without encountering any notable issues in these aspects, demonstrating a robust and reliable clock distribution structure.
<img  width="1085" alt="day21_12" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day21/day21_12.png"> <br>


```ruby
check_legality
```
The `check_legality` command in IC Compiler II (ICC2) is a critical tool used in the field of digital integrated circuit design. Its primary purpose is to assess the legality and compliance of your physical design with a range of design rules and constraints. This verification process is crucial to ensure that your design aligns with the necessary specifications and constraints, particularly during the placement and routing phases. This compliance is essential for creating a manufacturable and functional integrated circuit.

Key functions of the `check_legality` command include:

**Checking for Design Rule Violations:** A primary role of the `check_legality` command is to examine your design for compliance with design rules. These rules, typically provided by the semiconductor foundry or the design team, encompass various criteria such as minimum spacing, minimum width, metal layer usage, and more. Their purpose is to guarantee that the manufacturing process can yield a functional chip. This tool helps identify and rectify any violations of these rules to ensure manufacturability and functionality.

This command performs a comprehensive check of design rules, inspecting for potential issues such as overlaps in the design and improper routing on metal layers. In the assessment, all checked aspects are reported as having a value of 0, indicating that no violations or errors have been detected. This successful evaluation confirms the design's compliance with established design rules and its adherence to the required legal guidelines.
<img  width="1085" alt="day21_13" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day21/day21_13.png"> <br>
<img  width="1085" alt="day21_14" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day21/day21_14.png"> <br>

```ruby
report_clock_timing -type summary
```
The `report_clock_timing` command, specifically of type "summary," within IC Compiler II (ICC2), is employed to produce a condensed summary report encompassing the clock timing details of your digital integrated circuit design. This command offers a bird's-eye view of the clock timing performance, a crucial factor in guaranteeing the correct operation of synchronous digital circuits.

**Output:** Upon executing this command, it generates a summary report containing essential timing information pertaining to the clock signals within your design. This report presents an overview of the clock timing characteristics, helping designers assess and ensure the synchronicity and proper operation of their digital circuits.
<img  width="1085" alt="day21_15" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day21/day21_15.png"> <br>


```ruby
report_clock_timing -type skew
```
The `report_clock_timing` command, specifically of type "skew," within IC Compiler II (ICC2), serves the purpose of generating a report that offers insight into the skew within the clock tree of your digital integrated circuit design. Clock skew, in this context, refers to the disparity in arrival times of clock signals at various elements within the design, such as flip-flops or latches. Having a grasp of clock skew and being able to manage it effectively is crucial for guaranteeing the dependable operation of synchronous digital circuits. This report is a valuable tool for assessing and addressing skew-related issues in your design.
<img  width="1085" alt="day21_16" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day21/day21_16.png"> <br>


```ruby
report_clock_timing -type latency
report_clock_timing -type transition
```
The `report_clock_timing` command, particularly of type "latency," within IC Compiler II (ICC2), is employed to produce a report offering insights into the clock latency within your digital integrated circuit design. Clock latency signifies the duration it takes for a clock signal to traverse the clock tree and reach specific elements within the design, such as flip-flops or latches. A comprehensive understanding of clock latency and the ability to manage it effectively are paramount in ensuring the correct operation and optimal performance of synchronous digital circuits. This report assists in assessing and addressing clock latency issues in your design.

The `report_clock_timing` command, specifically when using the "transition" type, within IC Compiler II (ICC2), is utilized to create a report offering details about the transition times of signals within your digital integrated circuit design. Transition time, in this context, represents the duration it takes for a signal to transition from one logic state (e.g., high or low) to another. An in-depth comprehension and effective management of signal transition times are critical for analyzing signal integrity, power consumption, and the overall performance of your design. This report is a valuable tool for assessing and optimizing signal transition characteristics in your design.

<img  width="1085" alt="day21_17" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day21/day21_17.png"> <br>
<img  width="1085" alt="day21_18" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day21/day21_18.png"> <br>

</details>

## Day-23- Clock Gating techniques
<details>
	<summary>Introduction</summary>

 <!DOCTYPE html>
<html>

<head>

	
 **Clock Tree Synthesis (Advanced H-Tree):**
</head>

<body>

<h1>Clock Tree Synthesis (Advanced H-Tree)</h1>
<p>A digital circuit having a lot of clocks, so if designing a clock tree will be huge with many buffers, etc. So the whole chip will section into smaller versions, and then each section will have its own clock tree, and then finally a complete routed tree.</p>

<h2>Clock Gating</h2>
<p>Besides area and timing, there is another important factor which is power - the need for power "aware" CTS. Clock gating is one of the techniques used to save the dynamic power of clock elements in the design. The principle behind clock gating is to stop the clock of those sequential elements whose data is not toggling. Clock gating technique uses AND, OR, or Universal NAND gates.</p>
<p>It has been found that 50% of the dynamic power originates from clock-related circuits. Clock gating is inserted during synthesis stage and optimized in the implementation stage (Physical Design stage).</p>
<p>Example scenario why required clock gating: If there is a block that only needs a clock signal for 10 minutes but the clock signal is running for 1 hour, a lot of power is dissipating (due to switching activity), so we need clock gating which acts as a switch.</p>

<h2>Routing</h2>
<p>The last step of the physical design flow is making physical connections between signal pins using metal layers. There are mainly three types of routing:</p>
<ul>
  <li>P/G routing</li>
  <li>Clock routing</li>
  <li>Signal routing</li>
</ul>
<p>Routing is accomplished through a multi-step process, including global routing and detailed routing. The "route_opt" command is a key command that facilitates and optimizes these routing tasks, enabling the chip's physical connections to be efficiently established.</p>

</body>

</html>

**Clock gating technique** is a pivotal strategy in digital circuit design employed to address power consumption concerns, especially in circuits with numerous clocks. It involves segmenting the chip into smaller sections, each having its own clock tree, and implementing clock gating at multiple levels. This approach offers precise control over clock signals, resulting in reduced power usage in inactive parts of the circuit.

In more detail, Clock Gating (CG) is a power-saving methodology widely used in digital circuit design to diminish dynamic power consumption within synchronous systems, particularly within clock trees. It functions by selectively enabling or disabling clock signals to specific sections or components of a digital circuit, depending on their operational requirements. This selective control allows for a substantial reduction in power consumption while preserving proper functionality.

To elaborate on the concept of Clock Gating:

1. **Dynamic Power Consumption**: In digital circuits, dynamic power consumption is a critical concern, as it occurs whenever transistors switch states, synchronized with clock cycles. The more frequent these clock toggles, the higher the power consumption becomes.

2. **Clock Tree**: A clock tree is a hierarchical structure responsible for distributing clock signals from a single source, typically a Phase-Locked Loop (PLL) or oscillator, to various parts of a digital chip. It ensures that clock signals reach flip-flops, registers, and other synchronous elements while adhering to skew and delay constraints.

3. **Clock Gating**: Clock Gating is a technique for selectively enabling or disabling clock signals to specific regions or components within the chip. To implement this, special logic gates, known as clock gating cells, are inserted into the clock tree. These gating cells determine whether to propagate the clock signal or block it based on predefined conditions.

4. **Conditions for Gating**: Clock gating can be controlled by a range of conditions, including:
   - **Functional Requirements**: Clock signals can be gated based on the actual need of logic within a specific block. If a module is not actively processing data, its clock can be gated off to conserve power.
   - **Activity or Idle Status**: Clock gating can rely on the activity or idle status of a module. When a module is inactive, its clock can be disabled.
   - **Data Dependencies**: Some clock gating may be contingent on the availability of valid data or control signals.
   - **Power Management Modes**: In low-power modes, certain clock domains may be entirely shut down.

Benefits of Clock Gating:

1. **Reduced Power Consumption**: Clock gating efficiently reduces dynamic power consumption by decreasing the number of clock cycles during which circuits remain active.
2. **Improved Timing**: Selectively gating the clock allows for better management of clock skew and enhanced timing closure in complex designs.
3. **Heat Reduction**: Lower power consumption translates to decreased heat generation, which is particularly crucial for high-performance and high-density chips.

Challenges of Clock Gating:

1. **Timing Constraints**: Careful consideration of timing constraints is imperative to ensure that clock gating does not violate setup and hold times, which can affect the reliability of the circuit.
2. **Verification and Testing**: Complex clock gating logic can introduce new challenges in the process of design verification and testing, demanding rigorous evaluation and validation procedures."

This reframe offers a more detailed and comprehensive explanation of the clock gating technique, its significance, and the associated benefits and challenges.


</details>

<details>
	<summary>Labs</summary>

**Routing:**
Script in routing stage
<ul>
	<li>
		
*P/G routing:*
	<img  width="1085" alt="day23_1" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day23/day23_1.png"> <br>
 	<img  width="1085" alt="day23_2" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day23/day23_2.png"> <br>
  	<img  width="1085" alt="day23_3" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day23/day23_3.png"> <br>
	</li>
	<li>
		
*Clock and Signal Routing:*

- **place_opt:** This command is employed for placing and optimizing the current design, ensuring that the design components are efficiently arranged for improved performance and adherence to design constraints.

- **clock_opt:** It serves the purpose of synthesizing and routing the clock signals within the design. Additionally, it optimizes the overall design based on the clock latencies that are propagated through the design, ensuring synchronized and timely clock delivery.

- **route_auto:** This command automates multiple aspects of routing, including global routing, trace assignment, and detailed routing. It streamlines and accelerates the routing process, simplifying the steps required for successful chip design.
<img  width="1085" alt="day23_4" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day23/day23_4.png"> <br>

</li>
</ul>


To align with our library's 1.8-volt standard, the initial step involves adjusting the voltage level as follows:
<img  width="1085" alt="1_voltage_change" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day23-24/1_voltage_change.png"> <br>

**Clock and Signal Routing in ICC2:**

1. **place_opt:**
   - *Description*: The **place_opt** command within ICC2, part of Cadence Design Systems' suite of Electronic Design Automation (EDA) tools, is a crucial tool for optimizing the placement of components in digital integrated circuit design. This process significantly impacts various design aspects, including performance, power efficiency, and area utilization.
   - *Usage*: **place_opt** is employed primarily in the design of Application-Specific Integrated Circuits (ASICs) and Field-Programmable Gate Arrays (FPGAs).

2. **clock_opt:**
   - *Description*: The **clock_opt** command, also found within Cadence's ICC2, plays a pivotal role in clock tree synthesis and optimization during digital integrated circuit design. Clock tree synthesis ensures efficient distribution of clock signals throughout the chip, while adhering to stringent timing, power, and skew constraints.
   - *Usage*: It is an integral part of the design process, critical for ASICs and FPGAs, ensuring that clock signals are handled optimally.

3. **route_auto:**
   - *Description*: The **route_auto** command, integrated within Cadence's ICC2, serves the purpose of automatic routing for digital integrated circuits. It streamlines the generation of routing paths for connections between various components in your design, based on the netlist and specified constraints.
   - *Usage*: This command simplifies and accelerates the routing process, making it an invaluable tool in digital integrated circuit design.

4. **set_lib_cell_purpose:**
   - *Description*: The **set_lib_cell_purpose** command in Cadence's ICC2 facilitates the specification of usage purposes for standard cells sourced from technology libraries in your digital integrated circuit design. By categorizing cells into specific functions, such as combinational logic, flip-flops, or latches, this command provides essential guidance to the tool.
   - *Usage*: It aids in clearly defining the intended role of each standard cell, enhancing the tool's understanding of how to utilize them effectively in the design process. This is especially beneficial for ASIC and FPGA design projects.

This detailed explanation clarifies the functions and significance of these commands in the context of digital integrated circuit design using ICC2, ensuring a comprehensive understanding of their roles and applications.

The following TCL commands in the script file demonstrate these functionalities:
<img  width="1085" alt="2_placement_tcl_change" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day23-24/2_placement_tcl_change.png"> <br>

Source the top.tcl script:
<img  width="1085" alt="3_souirce_top_tcl" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day23-24/3_souirce_top_tcl.png"> <br>


Let's begin by running 'start_gui', and from there, we can inspect the clock buffer cells within the design:
<img  width="1085" alt="4_gui" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day23-24/4_gui.png"> <br>
<img  width="1085" alt="5_gui_zoomed_standard_cells" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day23-24/5_gui_zoomed_standard_cells.png"> <br>
<img  width="1085" alt="6_cts_buffers" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day23-24/6_cts_buffers.png"> <br>
<img  width="1085" alt="7_cts_buffers_zoomed" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day23-24/7_cts_buffers_zoomed.png"> <br>

Below, you can find the clock buffer cells and ICG cells of the design:
```ruby

Buffer/Inverter reference list for clock tree synthesis:
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__buf_1
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__buf_12
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__buf_16
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__buf_2
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__buf_4
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__buf_6
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__buf_8
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__bufbuf_16
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__bufbuf_8
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__clkbuf_1
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__clkbuf_16
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__clkbuf_2
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__clkbuf_4
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__clkbuf_8
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__clkdlybuf4s15_1
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__clkdlybuf4s15_2
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__clkdlybuf4s18_1
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__clkdlybuf4s18_2
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__clkdlybuf4s25_1
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__clkdlybuf4s25_2
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__clkdlybuf4s50_1
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__clkdlybuf4s50_2
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__dlygate4sd1_1
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__dlygate4sd2_1
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__dlygate4sd3_1
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__dlymetal6s2s_1
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__dlymetal6s4s_1
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__dlymetal6s6s_1
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__probe_p_8
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__probec_p_8
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__lpflow_clkbufkapwr_1
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__lpflow_clkbufkapwr_16
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__lpflow_clkbufkapwr_2
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__lpflow_clkbufkapwr_4
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__lpflow_clkbufkapwr_8
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__bufinv_16
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__bufinv_8
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__clkinv_1
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__clkinv_16
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__clkinv_2
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__clkinv_4
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__clkinv_8
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__clkinvlp_2
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__clkinvlp_4
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__inv_1
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__inv_12
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__inv_16
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__inv_2
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__inv_4
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__inv_6
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__inv_8
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__lpflow_clkinvkapwr_1
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__lpflow_clkinvkapwr_16
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__lpflow_clkinvkapwr_2
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__lpflow_clkinvkapwr_4
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__lpflow_clkinvkapwr_8

ICG reference list:
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__dlclkp_1
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__dlclkp_2
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__dlclkp_4
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__sdlclkp_1
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__sdlclkp_2
   sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__sdlclkp_4
```

Next, compare the 'report_clock_timing' summary report with the one from day 22:
<img  width="1085" alt="8_clock_summary_report" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day23-24/8_clock_summary_report.png"> <br>

Below, you'll find the timing reports:
<img  width="1085" alt="9_timing_setup" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day23-24/9_timing_setup.png"> <br>
<img  width="1085" alt="10_timing_setup" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day23-24/10_timing_setup.png"> <br>
<img  width="1085" alt="11_timing_hold" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day23-24/11_timing_hold.png"> <br>

It's evident that there are timing violations; in the coming days, we will work on enhancing the timing profile.

</details>

## Day-24- Timing violations and ECO

<details>
	<summary>Introduction and labs</summary>

 Below, you'll find the setup violation report for our design:
<img  width="1085" alt="9_timing_setup" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day23-24/9_timing_setup.png"> <br>
<img  width="1085" alt="10_timing_setup" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day23-24/10_timing_setup.png"> <br><br>

To view this path in the GUI, you can use the following command in the GUI console: <br><br>
`change_selection [get_timing_path -from <start_point> -to <end_point>]`. <br>
These start and endpoints can be found in the setup timing report of the design. <br><br>
The screenshot below displays the worst negative slack (WNS) path for the setup:
<img  width="1085" alt="15_hold_path_in_gui" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day23-24/15_hold_path_in_gui.png"> <br><br>


To address the setup violations, we will increase the size of the combinational path cells to reduce data path delay. The figure below illustrates the cells that have been upsized for this purpose, then re-evaluate the setup timing report. We can observe that the setup slack now meets the requirements by 84 ps, as illustrated in the figures below:
<img  width="1085" alt="12_fixing_setup" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day23-24/12_fixing_setup.png"> <br><br>

Next, let's examine the hold violation in the design:
<img  width="1085" alt="11_timing_hold" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day23-24/11_timing_hold.png"> <br><br>

Lets see this path in the GUI:
<img  width="1085" alt="15_hold_path_in_gui" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day23-24/15_hold_path_in_gui.png"> <br><br>

To address the hold violation, we can introduce a buffer into the data path. However, before proceeding, it's essential to assess the setup margin:
<img  width="1085" alt="13_hold_path_setup_margin" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day23-24/13_hold_path_setup_margin.png"> <br><br>

In the image above, we can observe that we have an adequate setup margin to insert a buffer. To do this, you can use the following command: 
`insert_buffer <instance name of the pin before/after which the buffer needs to be placed> <reference name of the buffer>`

Hold timing report following the buffer insertion and the global timing report for the design, there are no remaining hold or setup violations, as evidenced in the image below::
<img  width="1085" alt="17_hold_violation_met" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day23-24/17_hold_violation_met.png"> <br>
<img  width="1085" alt="18_hold_violation_met_global_report" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day23-24/18_hold_violation_met_global_report.png"> <br><br>

The previously violated hold path, which has now been resolved, is displayed in the GUI:
<img  width="1085" alt="16_hold_path_in_gui" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day23-24/16_hold_path_in_gui.png"> <br><br>

report_qor:
<img  width="1085" alt="19_report_qor" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day23-24/19_report_qor.png"> <br><br>

We have identified a total of 4 transition violations in the design. <br>
To address these violations, we begin by identifying the net's driving cell. This can be accomplished by running the command <br>
`report_timing -through <net_name>`. <br>
Within the timing report, you'll find a cell marked with an arrow, signifying the net's driving cell. <br><br>
To resolve the violation, you can use the command <br>
`size_cell <instance_name> <ref_name_upsized_cell>` <br>
to upsize this cell. This process should be repeated for all nine nets with timing violations, as illustrated in the images below: <br>
<img  width="1085" alt="20_fix_tran_net_one" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day23-24/20_fix_tran_net_one.png"> <br>
<img  width="1085" alt="21_fix_tran_net_one" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day23-24/21_fix_tran_net_one.png"> <br>
<img  width="1085" alt="22_fix_tran_net_two" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day23-24/22_fix_tran_net_two.png"> <br>
<img  width="1085" alt="23_fix_tran_net_two" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day23-24/23_fix_tran_net_two.png"> <br>
<img  width="1085" alt="24_fix_tran_net_three" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day23-24/24_fix_tran_net_three.png"> <br>
<img  width="1085" alt="25_fix_tran_net_three" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day23-24/25_fix_tran_net_three.png"> <br>
<img  width="1085" alt="26_fix_tran_net_four" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day23-24/26_fix_tran_net_four.png"> <br>
<img  width="1085" alt="27_fix_tran_net_four" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day23-24/27_fix_tran_net_four.png"> <br><br>

Now, after addressing all the transition violations, we can recheck using the command `report_constraints -max_transition -all-violators`. In this report, we'll notice that all the transition violations have been successfully resolved:
QOR report of the desing is shown below:
<img  width="1085" alt="28_report_qor" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day23-24/28_report_qor.png"> <br>
<img  width="1085" alt="29_report_qor" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day23-24/29_report_qor.png"> <br><br>

In the Quality of Results (QOR) report, it is evident that there are no:

- Setup timing violations
- Hold timing violations
- Max Transition Violations
- Max Capacitance Violations"



</details>

## Day-26- Introduction to mixed signal flow

<details>
	<summary>Introduction</summary>

**Mixed Signal Flow:** <br>
Mixed signal flow is a sophisticated approach that involves the simultaneous utilization and seamless integration of both analog and digital signals within a complex system or process. This harmonious coexistence of analog and digital components enables the exploitation of the unique advantages offered by each signal type to accomplish specific functionalities with utmost efficiency.

**Analog Signals:** <br>
Analog signals, at their core, are continuous and fluid representations of data. They convey information through smooth, uninterrupted waveforms that can take on an infinite range of values within a specific range. Examples of analog signals include variations in voltage, current, and temperature. These signals are versatile and well-suited for capturing the nuances of real-world phenomena.

**Digital Signals:** <br>
In contrast, digital signals express information in a discrete, binary format, typically using 0s and 1s. Digital signals are commonly found in computing systems and exhibit distinct levels, often denoted as on/off or high/low. The discrete nature of digital signals makes them highly reliable for tasks such as storage, processing, and data transmission. They excel at precise and error-free representation of information.

**Analog-to-Digital and Digital-to-Analog Converters (ADCs/DACs):** <br>
Central to mixed signal design are Analog-to-Digital Converters (ADCs) and Digital-to-Analog Converters (DACs). ADCs play a pivotal role by transforming analog signals into a digital format. In contrast, DACs perform the reverse operation by converting digital signals back into analog form. These components act as essential intermediaries, facilitating seamless communication between the analog and digital sections of a system. ADCs and DACs demand unique design and process technology considerations, setting them apart from conventional digital circuits. Their precision and performance are critical in maintaining the fidelity and accuracy of data as it transitions between the analog and digital domains in a mixed signal environment.

*In our vsdbabysoc design, we incorporate a combination of analog and digital blocks. Specifically, the PLL (Phase-Locked Loop) and DAC (Digital-to-Analog Converter) are the analog components, while the RVMYTH processor functions as a digital block within the system. This mixed configuration allows us to harness the unique strengths of both analog and digital elements to achieve the desired functionality and performance.*

**Various Files Required in ASIC Design:** <br>
1. *LEF (Library Exchange Format):*
   - The LEF file is an essential component of ASIC design, providing physical information about standard cells.
   - It consists of two parts: the Technology LEF, which contains information about metal interconnects, vias, design rules, and other backend-of-line (BEOL) details; and the Cell LEF, which specifies the geometry of individual cells.
   - Technology LEF includes details like LEF version, units (for database, time, resistance, capacitance), manufacturing grids, layer names (e.g., poly, contact, via1, metal1), layer types (routing, masterslice, cut), preferred direction (horizontal or vertical), pitch, minimum width, spacing, and sheet resistance.
   - Cell LEF provides information on cell names (e.g., AND2X2, CLKBUF1), classes (CORE or PAD), origin, size (width x height), symmetry (XY, X, Y), and pin details such as name, direction, use, shape (abutment for power pins), layer, and rectangular pin coordinates.

2. *LIB (Liberty File):*
   - The LIB file contains critical timing and power parameters associated with cells in the standard cell library of a specific technology node.
   - It serves as a timing model file and includes data on cell delay, cell transition time, and setup and hold time requirements for the cells.
   - The data in the LIB file is obtained through simulation of cells in various operating conditions, making it a key resource for ASIC designers.

3. *GDSII File (Graphic Data System II):*
   - GDSII is a widely used file format in the semiconductor industry for storing and transferring design data related to integrated circuits.
   - GDSII files encapsulate geometric shapes that define the layout of an integrated circuit, including polygons, paths, and other structures representing different elements of the chip design.
   - These files are organized into layers, each representing specific aspects of the chip design.
   - GDSII supports hierarchical data, text labels, data compression, and technology-specific parameters.

4. *OASIS File (Open Artwork System Interchange Standard):*
   - OASIS is an alternative file format designed to address the limitations of GDSII, particularly for modern and complex chip designs.
   - OASIS files offer more efficient data representation and handling capabilities.
   - They allow for organized and manageable layouts with varying levels of detail and incorporate features like reusability of cell libraries.
   - OASIS files are known for their ability to handle larger data volumes and complex geometries effectively through variable-sized elements and serialization techniques.

**Physical Design Tools (PnR Tools):**
   - The Physical Design (PnR, Place and Route) tools are essential in ASIC design for converting high-level descriptions into a physical layout.
   - Prominent PnR tools include Innovus by Cadence Design Systems, IC Compiler II by Synopsys, and Olympus SOC by Mentor Graphics.
   - These tools take several inputs to generate the final GDSII file, which represents the physical layout of the integrated circuit.

**Additional Input Files:**
   - In addition to the above-mentioned files, various other input files may be required for ASIC design, depending on the specific project and toolset. These may include:
   - Block partition files (.fp) for defining block-level partitioning.
   - I/O pin locations files (e.g., pad_placement_constraints.tcl) for specifying the placement of input/output pins.
   - Power planning scripts or rules to determine power distribution strategies.
   - Power intent files that describe power management requirements.
   - SAIF files (Switching Activity Information Format) that provide information about signal switching activities, aiding in power analysis and optimization.

These input files collectively form the foundation for the physical design and manufacturing process of an ASIC, enabling the transformation of a logical design into a physical, manufacturable chip.


**IP Cores (Intellectual Property Cores):** <br>
IP cores play a crucial role in the design and implementation of semiconductor chips, such as Field-Programmable Gate Arrays (FPGAs) or Application-Specific Integrated Circuits (ASICs). These cores consist of blocks of logic or data that are utilized as building blocks for chip design, and they are typically the intellectual property of a specific individual, company, or entity. IP cores are instrumental in accelerating the development of complex integrated circuits and can be created, customized, and integrated into various projects to enhance efficiency and reduce design complexity.

There are two primary categories of IP cores:
1. *Soft IP Cores:*
   - Soft IP cores are characterized by their flexibility and adaptability. They can be customized during the physical design phase to match the requirements of a specific project and can be mapped to different process technologies.
   - Designers can configure and modify the functionality of soft IP cores to suit their specific needs, making them versatile and well-suited for a wide range of applications.
   - Soft IP cores are like a blueprint that can be tailored to different design contexts, offering adaptability in terms of logic and functionality.

2. *Hard IP Cores:*
   - Hard IP cores, in contrast, are fixed and inflexible in terms of both logic implementation and physical layout. These cores come with a predefined, unalterable physical implementation.
   - The physical layout of a hard macro-IP core is already completed and fixed in a particular process technology, making it less adaptable and suitable for specific use cases.
   - Hard IP cores are like pre-built, ready-to-use components that are designed for optimal performance and efficiency in a specific process technology. They are typically used in situations where strict performance and manufacturing requirements are critical.

In summary, IP cores serve as valuable resources for semiconductor chip design, offering a range of pre-designed building blocks that can significantly reduce the time and effort required to develop complex integrated circuits. The choice between soft and hard IP cores depends on the specific needs of a project, with soft IP cores providing customization and adaptability and hard IP cores offering performance and manufacturing advantages but with less flexibility.
</details>


## Day-27- Introduction to crosstalk - glitch and delta delay

<details>
	<summary>Introduction</summary>

**Crosstalk, Signal Integrity, and Glitches in Semiconductor Design:** <br>
1. **Signal Integrity and Crosstalk**:
   - Signal integrity is a critical aspect of semiconductor design and refers to the ability of an electrical signal to reliably carry information while resisting the adverse effects of high-frequency electromagnetic interference generated by nearby signals.
   - Crosstalk is one of the key challenges within the domain of signal integrity. It occurs when undesirable electrical interactions take place between two or more physically adjacent signal nets due to capacitive cross-coupling.
   - Crosstalk manifests as a type of noise signal that interferes with the accurate transmission of data through the communication medium. It can corrupt the actual signal, leading to data errors and reliability issues.

2. **Causes of Crosstalk**:
   - Several factors contribute to crosstalk in semiconductor design:
     - **Number of Metal Layers**: An increase in the number of metal layers in the design can lead to greater opportunities for cross-coupling and crosstalk.
     - **Routing Congestion**: High routing congestion, where signal paths are tightly packed, can exacerbate crosstalk.
     - **Low Voltage Design**: Low-voltage design can make signals more susceptible to crosstalk.
     - **Thin and Long Metal Layers**: Thin and long metal layers used for routing can amplify crosstalk effects.

3. **Mitigation of Crosstalk**:
   - Various techniques are employed to mitigate crosstalk, including:
     - **Guard Rings**: These are structures added around signal nets to isolate them from neighboring nets.
     - **Downsizing Aggressor Nets**: Reducing the size or aggressiveness of signals that are causing crosstalk.
     - **Shielding**: Adding shielding layers to protect sensitive signal nets.
     - **Layer Promotion**: Moving signal nets to higher layers with fewer adjacent nets.
     - **Breaking Long Nets**: Breaking up long signal paths to reduce cross-coupling.

4. **Victim and Aggressor Nets**:
   - In the context of crosstalk, a "victim net" is a signal net that experiences undesirable cross-coupling effects from a nearby "aggressor net." An aggressor net is a signal net that causes these adverse effects in a victim net.
   - It's important to note that an aggressor net can also become a victim net, and vice versa. The timing effects of an aggressor net on a victim net depend on various factors, including the direction of signal transitions (rise and fall), relative timings, slew rates, cross-coupled capacitance, and the combinational effects of multiple aggressor nets on a single victim net.

5. **Glitches**:
   - Glitches are unwanted signal transitions that can occur due to crosstalk. They are often the result of a switching net causing voltage spikes on another net.
   - When a net is in a constant state (steady signal) and experiences a voltage change due to the charge transferred by a switching aggressor net through coupling capacitances, this can lead to a glitch.
   - Glitches can be significant enough to be misinterpreted as a different logic value by downstream components connected to the victim nets.
   - Common types of glitches include rise glitches, fall glitches, overshoot (when the signal exceeds its intended voltage level), and undershoot (when the signal falls below its intended voltage level).

In semiconductor design, managing crosstalk and its associated glitches is crucial for ensuring that signals are transmitted accurately and reliably, which is essential for the proper operation of integrated circuits. Effective signal integrity and crosstalk mitigation techniques are vital to maintain the quality and performance of the designed systems.

**Rise, Fall, Overshoot, and Undershoot Glitches in Semiconductor Design:** <br>
1. **Rise Glitch**:
   - A rise glitch occurs when the voltage on an aggressor net transitions from a low state to a high state.
   - This transition induces a voltage spike on a nearby victim net that is in a steady low state.
   - The result is a brief and unintended rise in voltage on the victim net, causing it to deviate from its expected low value.

2. **Fall Glitch**:
   - A fall glitch takes place when the voltage on an aggressor net transitions from a high state to a low state.
   - This transition induces a voltage dip or drop on a nearby victim net that is in a steady high state.
   - As a result, the victim net experiences a temporary fall in voltage, deviating from its expected high value.

3. **Overshoot Glitch**:
   - An overshoot glitch occurs when the voltage on an aggressor net rises rapidly and exceeds its intended high value.
   - This overshoot, or voltage spike, can affect a nearby victim net that is in a steady high state.
   - The voltage on the victim net is momentarily driven above its expected high value, which can lead to misinterpretation by downstream components.

4. **Undershoot Glitch**:
   - An undershoot glitch takes place when the voltage on an aggressor net falls rapidly and drops below its intended low value.
   - This undershoot, or voltage dip, can influence a nearby victim net that is in a steady low state.
   - The voltage on the victim net temporarily falls below its expected low value, potentially causing misinterpretation by downstream components.

These glitches are undesirable phenomena resulting from crosstalk in semiconductor design. They can be particularly problematic because they may cause downstream logic gates to misread the signal, potentially leading to incorrect operation or data errors. To prevent and mitigate these glitches, designers employ various techniques such as adjusting signal timing, adding buffers, and optimizing signal routing to reduce the impact of crosstalk and its associated glitches on the integrity of the designed circuits.
</details>

<details>
	<summary>Labs</summary>

Prior to generating reports for crosstalk and Signal Integrity (SI) analysis using PrimeTime, the necessary input files and configurations for reading the design by the PrimeTime tool are prepared and generated using icc2_shell. This preparatory step ensures that the design data is compatible with PrimeTime for accurate analysis and validation.

**Creating the SPEF File:**
```ruby
source top1.tcl
update_timing
write_parasitics -format spef -output vsdbabysoc_spef
```

The image below illustrates the process of generating the Standard Parasitic Exchange Format (SPEF) file: <br>
<img  width="1085" alt="27_1" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day27/27_1.png"> <br><br>


Then we unzip the generated ZIP file using the following command:
```ruby
cd write_data_dir/vsdbabysoc
gzip -d vsdbabysoc.pt.v.gz
gzip -d func1.sdc.gz
cp vsdbabysoc.pt.v /home/vishaka.p/Day20/VSDbabysoc_ICC2/standaloneFlow
cp func1.sdc /home/vishaka.p/Day20/VSDbabysoc_ICC2/standaloneFlow
```

Copying these files to the main directory of the standalone flow.

**The design is read into the pt_shell are as follows:**
```ruby
set target_library {list set target_library "avsddac.db avsdpll.db sky130_fd_sc_hd__tt_025C_1v80.db"
set link_library [list avsddac.db avsdpll.db sky130_fd_sc_hd__tt_025C_1v80.db]
read_verilog vsdbabysoc.pt.v
link_design vsdbabysoc_1
current_design
```
<img  width="1085" alt="27_2" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day27/27_2.png"> <br><br>
<img  width="1085" alt="27_3" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day27/27_3.png"> <br><br>


The sdc is read into the design:
```ruby
read_sdc func1.sdc
set_app_var si_enable_analysis true
read_parasitics -keep_capacitive_coupling vsdbabysoc_spef.temp1_25.spef
```

<img  width="1085" alt="27_4" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day27/27_4.png"> <br><br>


The following image shows the report of check_timing as follows:
<img  width="1085" alt="27_5" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day27/27_5.png"> <br><br>


**Specific Crosstalk Analysis Checks and Reports:** <br>
Crosstalk analysis involves various checks and reports to ensure the accuracy and reliability of the analysis. Here are some key checks and reports specific to crosstalk analysis:

**Checks:**

1. **no_driving_cell:**
   - This check identifies input ports that have no driving cell and don't have case analysis set on them. These nets are assigned as stronger drivers to model aggressors, ensuring accurate crosstalk analysis.

2. **ideal_clocks:**
   - The ideal_clocks check reports nets that do not have propagated clocks. A design must have a propagating clock tree to calculate crosstalk accurately, so this check helps ensure the presence of a clocking structure.

3. **partial_input_delay:**
   - This check identifies delays set with the `set_max_delay` and `set_min_delay` commands in the SDC (Synopsys Design Constraints) file. Delays can impact crosstalk analysis, and this check helps capture any user-defined delays that may affect the results.

4. **unexpandable_clocks:**
   - The unexpandable_clocks check reports any clocks that are not expanded to a common time base. Clock expansion is crucial for consistent and accurate crosstalk analysis across the design.

**Reports (in pt_shell, PrimeTime's interactive shell):**

1. **report_si_bottleneck:**
   - This report provides insights into signal integrity bottlenecks in the design. It helps identify critical paths and areas that may require attention to ensure signal integrity.

2. **report_bottleneck:**
   - The report_bottleneck command generates a comprehensive report on bottleneck analysis. It helps designers understand where potential issues or limitations may exist within the design, which is essential for optimizing signal integrity.

3. **report_si_delay_analysis:**
   - This report offers a detailed analysis of signal delays, helping designers assess the timing characteristics of the design. It is essential for addressing issues related to signal integrity and crosstalk.

4. **report_si_aggressor_exclusion:**
   - The report_si_aggressor_exclusion report provides information on how aggressor nets are excluded from the crosstalk analysis. Understanding this exclusion is critical for accurately modeling and analyzing crosstalk effects.

5. **report_si_noise_analysis:**
   - This report provides a comprehensive analysis of noise within the design, particularly noise resulting from crosstalk. It offers insights into potential noise-related issues that need to be addressed for reliable design performance.

These checks and reports are valuable tools for designers to ensure that crosstalk analysis is conducted effectively, and the design's signal integrity is maintained within acceptable limits. Proper identification and resolution of crosstalk issues are vital for achieving a robust and reliable semiconductor design.

**The various reports:**
```ruby
report_si_bottleneck              
report_bottleneck                
report_si_delay_analysis
report_si_aggressor_exclusion
report_si_noise_analysis
```
<img  width="1085" alt="27_6" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day27/27_6.png"> <br><br>
<img  width="1085" alt="27_7" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day27/27_7.png"> <br><br>
<img  width="1085" alt="27_8" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day27/27_8.png"> <br><br>
<img  width="1085" alt="27_9" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day27/27_9.png"> <br><br>



</details>

## Day-28-Introduction to DRC/LVS

<details>
	<summary>Introduction</summary>

 
The skywater 130nm PDK is like an open-source magic wand for chip design, offering everything from design rules to device models. The beauty of open PDKs is that they empower anyone to craft circuits using open source tools. Enter the caravel chip with its RISC-V processor, providing users with a canvas to bring their designs to life. PDK, short for process design kit, is the backstage pass for chip designers, guiding them through the intricacies of a specific foundry process.

The 130 in sky130 symbolizes the feature size, setting the stage for the tiniest transistors at 130nm. It's like the resolution of a designer's dreams. The sky130PDK is a trio of documentation (skywater PDK), library files (GitHub repo), and a lively community (Slack group). The plot thickens when it comes to tool compatibility – the PDKs cozy up to open source EDA tools but throw a fit with commercialized ones, thanks to the intricate dance of file formats.

Open source EDA tools emerge as the unsung heroes, the trusted companions in this journey of creativity and innovation.

**Opensource EDA tools:** <br>
At opencircuitdesign.com, the open_pdks files take center stage. Crafted as a makefile-based installer, open_pdks ingeniously grabs files from the skywater PDK and transforms them into a format compatible with various open source tools. To install open_pdks, the following steps unfold like a well-choreographed dance:

```ruby
git clone https://github.com/RTimothyEdwards/open_pdks
cd open_pdks
configure –enable-sky130-pdk
make 
sudo make install
```
Given the universal support of open-source PDKs across various processes, the delineation of the configured process is paramount. Executed through the 'make' command, this process involves retrieving the skywater PDKs from Google, immersing them into the system, and maintaining them for subsequent installation. Subsequently, the construction of libraries from the repository transpires post-installation.

**Magic:** <br>
Prior to executing the open_pdk file, the installation of Magic, a pivotal open-source EDA tool, is imperative. Magic exhibits versatile functionality, adept at reading and writing diverse command formats. Proficient in extraction and DRC processes, Magic seamlessly manages GDS, LEF, and DEF formats. Its capabilities extend to generating design layouts from parameterized descriptions. Crucially, Magic assumes responsibility for generating any missing files of diverse formats within the repository source files.

**Klayout:** <br>
Klayout serves as an alternative layout editor and viewer with additional capabilities for Design Rule Checking (DRC). The installation of open-source PDKs includes a crucial step of scrutinizing the DRCs using Klayout.
 
**Openlane:** <br>
This package encompasses synthesis, place, and route functionalities, built upon the foundation of OpenROAD tools. Essentially acting as a wrapper around OpenROAD, it consists of a curated set of scripts designed to seamlessly integrate and support SkyWater PDKs.

**Xschem:** <br>
This tool functions as a schematic editing tool and is not directly integrated into open_pdks. Instead, it operates as a third-party repository that open_pdks can pull from and subsequently copy to the designated installation location.

**Netgen:** <br>
Netgen serves as a Layout versus Schematic (LVS) tool, collaborating with an extracted netlist from layout via Magic and a netlist generated from XSCem within OpenLane.

**Ngspice :** <br>
It serves as the analog simulation tool, grounded in SPICE. Through open_pdks, all model files are systematically installed, ensuring Ngspice can locate them seamlessly through the correct include statements.


Various tools complement the open_pdks ecosystem, including qflow, IRSIM (a switch-level simulator and power analyzer), and xcircuit. In addition to the suite of open-source EDA tools, open_pdks installs both foundry and third-party libraries, establishing a unified directory structure across the source.

Diverse digital libraries, tailored to speed and power considerations, coexist. The sky130_fd_pr stands as the standard library for analog components. Analog elements like transistors undergo extraction and don't necessitate specific libraries. Conversely, components such as RF layouts, bipolar devices, and parallel plate capacitors have validated layouts, serving as IP formats within the library.

Operating within the voltage range of 1.8V to 20V, with common voltages being 1.8V and 3.3V, the sky130_fd_io library caters to IO pads and pad frame cells, encompassing power, ground pads, and general-purpose IO pads. The sky130_ml_xx_hd, a third-party library, features alpha-numeric text layouts, facilitating text integration into the layout.

The sky130A encapsulates libs.tech and libs.ref directories. While libs.tech accommodates the setup for all open-source EDA tools, libs.ref houses reference libraries. Described as a hybrid 130nm-180nm standard CMOS fabrication process, the sky130 process involves five layers of aluminum metal and titanium nitride, referred to as local interconnect (li). This local interconnect serves purposes like power and ground rails in skywater standard layouts. Poly contacts necessitate a nitride polycut around them, with metal layers exhibiting progressive thickness, typically utilizing higher-order metal for routing.

Metal layers in vias constitute the back-end layers, whereas the layers below are deemed front-end layers. Front-end fabrication primarily involves diffusion and ion-implantation, while backend processes include metal deposition through sputtering. Distinctions in masks accommodate higher and lower concentration areas, with diff having higher concentration for drain and source, and tap having lower concentration for substrate and wells.

The HVI (high voltage layer) contributes to high voltage tolerance, enabling dual voltage design. N-wells implanted with HVI tolerate high voltages, and gate oxide withstands up to 5V, with thin oxides tolerating up to 2.2V, reflecting the dual-domain voltage methodology. Pads in the skywater library adhere to this methodology, featuring a core voltage of 1.8V and a pad voltage of 3.3V.

MiM (Metal-Insulator-Metal) cap layers, a part of the back-end process, incorporate capacitors formed by adding metal plates between routing layers. The Redistribution layer, constituted by copper, is not fabricated by skywater; it is deposited on the chip, with solder bumps added. This layer, distinct from a design layer, serves as a packaging layer for the chip.

In the realm of skywater PDKs, devices are not characterized by a continuous change in width and length. Instead, reference layouts, presented as GDS files, are delivered to users unaltered. This practice extends to various device types, including:

**Bipolar Devices:** <br>
- **NPN Transistor:** <br>
  - Emitter: n-diffusion
  - Base: p-well
  - Collector: deep n-well
- **PNP Transistor:** <br>
  - Emitter: p-diffusion
  - Base: n-well
  - Collector: p-substrate

**Polysilicon Resistors:** <br>
- P+ Polyresistor: Poly resistance of 1Kohm/square
- P- Polyresistor: Sheet resistance of 2Kohm/square

**Diffusion Resistors:** <br>
- n-Diffusion Resistor on substrate
- p-Diffusion Resistor in n-well

**Hidden Mask Layers:** <br>
- PSDM Mask
- RPM Mask
- POLYRES ID layer

Certain layers, such as bipolar and capacitor identifiers, need not be identified for Design Rule Checking (DRC). Three distinct library types are available in skywater PDKs:

1. **Digital Standard Cells:** <br>
   - Includes layout and GDS formats used in the synthesis flow.
   - Various cell flavors cover high speed, high density, high voltage, and low leakage.
   - Follows a naming convention: `sky130_vendor_library_type[_name]`.
   - For example, `sky130_fd_sc_hd` stands for foundry (vendor), standard cell (library type), and high density (library name).
   - Cells must be placed to ensure abuttment bounding boxes touch each other.

2. **I/O Cells:** <br>
   - Contains complete power and ground pads, including entire disconnected blocks.
   - Overlay connects clamps/pads to power rails.

3. **Primitive Devices and Models:** <br>
   - Encompasses designs like bipolar transistors, varactors, ESD devices, etc.

To comprehend physical verification, a layout is crafted. A simple circuit is represented by a schematic illustrating the cells and layout hierarchy. Xschem is employed for layout creation, complemented by ngspice for analog simulation and gaw for waveform viewing. Schematics are utilized to generate netlists, which are then simulated with ngspice. The layout is generated using Magic, with device adjustments made to address DRC checks. Lastly, Layout versus Schematic (LVS) checks are conducted as the final step.

</details>

<details>
	<summary>Labs</summary>

 **Tool installations:** <br>

*Magic:* <br>
Magic unfolds its capabilities through two distinct windows: the layout window and the console window. In the console window, a command prompt operates as a Tcl interpreter, executing commands specifically related to layout operations. This design provides a seamless and interactive environment for users to navigate and manipulate the layout using intuitive Tcl commands.

Magic offers flexibility in its invocation. To launch Magic without the layout window, the `-dnull` option can be employed, and similarly, the `-noconsole` option allows Magic to run without opening the console window. This versatile command-line approach caters to user preferences and specific workflow requirements.

<img  width="1085" alt="ss_1" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day_28/ss_1.png"> <br><br>

*Netgen:* <br>
Netgen operates in a command-driven fashion, devoid of a graphical interface. Its functionality is initiated and controlled solely through command inputs, emphasizing a streamlined and efficient approach to layout verification.
Netgen gui is run with the command:
```ruby
/usr/local/lib/netgen/python/lvs_manager.py
```
<img  width="1085" alt="ss_3" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day_28/ss_3.png"> <br><br>


*Xschem:* <br>
Xschem, unlike some tools, doesn't feature a dedicated console window; instead, the terminal serves as its console. It lacks a quick command interface, relying on a terminal-based interaction for command execution. This design underscores a straightforward and terminal-centric user experience.
<img  width="1085" alt="ss_2" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day_28/ss_2.png"> <br><br>

*ngspice:* <br>
Ngspice simplifies its user interface by forgoing additional consoles. Executed directly on the terminal, Ngspice operates with its own interpreter, distinct from both Tcl and Python. This terminal-centric approach streamlines the user experience, making it a self-contained and efficient tool for circuit simulation.
<img  width="1085" alt="ss_4" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day_28/ss_4.png"> <br><br>

These tools can also be opened in batch mode as well.


Inorder to create a basic circuit like inverter, the tools must be linked to present working directory as shown.
```ruby
mkdir inverter
cd inverter
mkdir xschem
mkdir mag
mkdir netgen
cd xschem
ln -sf /usr/share/pdk/sky130A/libs.tech/xschem/xschemrc
ln -sf /usr/share/pdk/sky130A/libs.tech/ngspice/spinit .spiceinit
cd ../mag/
ln -sf /usr/share/pdk/sky130A/libs.tech/magic/sky130A.magicrc .magicrc
cd ../netgen/
ln -sf /usr/share/pdk/sky130A/libs.tech/netgen/sky130A_setup.tcl setup.tcl
```

xschem has a lot of example devices as shown.
<img  width="1085" alt="ss_5" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day_28/ss_5.png"> <br><br>

*Important note:* <br>
Accessing examples is conveniently achieved by clicking the relevant rectangle and pressing the "E" key on the keyboard. To return to the menu promptly, simply press "CTRL+E". Additionally, resizing the schematic to fit the window is effortlessly accomplished by pressing the "F" key. Now, on an empty window, let's explore some magic shortcuts:
```ruby
magic -d XR
```

Mouse Controls: <br>
- Left and right mouse buttons: Adjust the cursor box
- Shift + Z: Zoom out
- Middle mouse button/pk: Select a layer (also known as painting)
- Key E: Erase whatever is present in the cursor box (can also be done by clicking the middle mouse button on an empty part of the layout)
- Key V: View the entire layout
- CTRL + P: Opens up the parameter options for the selected device
- S key: Select layers
- Typing "what" command in the Magic console: Provides information on the selected layer

Magic Console Commands: <br>
- ; (semicolon) key: Type commands in the Magic console without moving between windows, until the Enter key is pressed
- I key: Select a device
- M key: Move the selected device

Device Editing: <br>
To edit devices, use drop-down buttons:
- Click on Devices 1 -> nmos (MOSFET) and select nmos (MOSFET) under "Devices 1"
- Set the width to 2 um, length to 0.5 um, and fingers to 3 as shown.
When applied, the NMOS viewed is as follows:
<img  width="1085" alt="ss_7" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day_28/ss_7.png"> <br><br>

By removing the guard rings, the NMOS is viewed as follows:
<img  width="1085" alt="ss_8" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day_28/ss_8.png"> <br><br>

Now, let's switch the device type to `sky130_fd_pr__nfet_g5v0d10v5` to observe a change in the voltage value while maintaining a similar layout view. When a specific layer is selected, the "what" command is employed to glean details about the chosen layer.
<img  width="1085" alt="ss_11" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day_28/ss_11.png"> <br><br>

**Creating schematic:** <br>
Now, let's generate the inverter schematic using Xschem.
```ruby
cd ../xschem/
xschem
```

To begin, open a new schematic window and press the "Insert" button on the keyboard. This action will prompt a window to appear, allowing you to select devices. Specify the directory path to the SkyWater library and choose the `fd_pr` library. For an inverter, both an NFET and PFET are required. Consequently, select the NFET and PFET devices from the insert window and position them anywhere in the schematic, following the provided illustration.
<img  width="1085" alt="ss_14" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day_28/ss_14.png"> <br><br>

Since pins are not PDK-specific, locate them under the xschem library in the insert window, named as `ipin.sym`, `opin.sym`, and `iopin.sym`.

Position the pins on the schematic and use the following keys for schematic connections: <br>
- Press 'M' key to move components around the schematic window.
- 'C' key to copy components, and 'Del' key to erase components.
- 'W' key to insert wires between components and establish connections.

Rename each pin appropriately using the 'Q' key to bring up the parameter window.

Select the components by clicking on them and press 'Q' to bring up the parameter windows, configuring the properties of the devices.

For the NFET, adjust the length to 0.18 since the default value of 0.15 is restricted to SRAM devices only. Set the number of fingers to 3, and the width of each finger to 1.5. With 3 fingers, the total width in the parameter window should be set to 3 times the finger width, which is 4.5.
<img  width="1085" alt="ss_16" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day_28/ss_16.png"> <br><br>

Likewise, for the PFET, tailor the parameters to 3 fingers, a width of 1 per finger, and a length of 0.18. It's crucial to specify that the body is connected to the Vdd pin since it's a 3-pin PFET.
<img  width="1085" alt="ss_15" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day_28/ss_15.png"> <br><br>

Similarly, the pins such as in,out and vdd, vss are given names.
Save the design by clicking tab File --> save as --> inverter.sch
<img  width="1085" alt="ss_17" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day_28/ss_17.png"> <br><br>

**Ccreating the symbol and exporting the schematic:** <br>
For functional validation of the schematic, it's essential to create a separate testbench.

Begin by crafting a symbol for the schematic, which will manifest as a symbol in the testbench. Navigate to the Symbol menu and opt for "Make symbol from schematic." Subsequently, generate a testbench schematic using the "New Schematic" option. Insert the previously created symbol from the local directory into the testbench schematic using the "Insert" key.

Select the new schematic in the File tab, navigate to the home directory, choose "inverter.sch," and paste it onto the schematic window.

The testbench will be very simple where we will generate a ramp input and observe the output response after connecting the power supplies. To do this, insert 2 voltage sources from the default xschem library, one for the input and one for the supply. Connect these and add a GND node to the supply connections. Create "ipins" and "opins" for the input and output signals to observe in Ngspice. Supply voltage is set to 1.8 V.

For the input voltage, we must set the supply to a piece-wise linear function to get ramp. PWL function has voltage and time values stated that the supply will start at 0v, then start to ramp up from 20 ns till it reaches its final value at 900 ns of 1.8 V.


Moving forward, add two more statements for Ngspice, but since these statements aren't specific to any particular component, they need to be placed in text boxes. To incorporate a text box, select the `code_shown.sym` component under the xschem library.

The first text box is designed to define the location of the device models used in the schematic. It employs a `.lib` statement, selecting a top-level file that guides Ngspice to the location of all the models. This block also specifies a simulation corner for all the models, with the first block representing the typical corner using the value ".lib /usr/share/pdk/sky130A/libs.tech/ngspice/sky130.lib.spice tt".

For the second block, it specifies:

```ruby
value = ".control tran 1n 1u plot V(in) V(out) .endc"
```

This instructs Ngspice to execute a transient simulation for 1 ns, monitoring voltages for the in and out pins.

While specifying same name to in and out, in the symbol and output pins, it throws a warning during simulation. SO, Use the different names.

Hence, the comprehensive testbench schematic is depicted above. Save this configuration as "inverter_tb.sch". To generate the netlist, click on the Netlist button, followed by simulating it in Ngspice by clicking the Simulate button. The resulting waveform serves as confirmation that the schematic functions as an inverter, as illustrated below.
<img  width="1085" alt="ss_18" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day_28/ss_18.png"> <br><br>
<img  width="1085" alt="ss_19" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day_28/ss_19.png"> <br><br>
<img  width="1085" alt="ss_20" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day_28/ss_20.png"> <br><br>


Once the schematic is verified, proceed to create a layout for it. Return to the inverter schematic.

Firstly, navigate to the Simulation menu and choose the "LVS netlist: Top Level is a .subckt" option. Allow a few seconds and revisit the Simulation menu to ensure a tick mark appears beside the mentioned option. This confirms the proper definition of a sub-circuit, essential for creating a layout cell with pins in the layout. Lastly, generate a netlist for the schematic by clicking the Netlist button, and exit Xschem.

**Importing Schematic to Layout:** <br>
```ruby
cd ../mag/
magic -d XR
```

Import the schematic to the layout in Magic by running the magic, then click on File -> Import SPICE and then select the inverter.spice file from the xschem directory. If done correctly, the following layout has been opened up in magic.
<img  width="1085" alt="ss_21" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day_28/ss_21.png"> <br><br>

Regarding the generated layout above, the schematic import lacks the capability to perform intricate analog placing and routing. Consequently, manual intervention is required to position the components optimally and establish the necessary connections. 

Begin by placing the PFET device above the NFET, carefully adjusting the placement of the input, output, and supply pins. R

Now, configure specific parameters in the layout that are only adjustable in this context, enhancing the overall convenience for wiring. To access the parameter editing section, use the 'S' key. Press 'I' to select the object, and then use CTRL+P to open the parameter options for the chosen device.


Adjust the parameters for optimal layout by setting the "Top guard ring via coverage" to 100. This action introduces a local interconnect to metal1 via the top of the guard ring. Following that, set "Source via coverage" to +40 and "Drain via coverage" to -40. This configuration effectively splits the source and drain contacts, simplifying the connection process with a wire.


Start to paint the wires using metal1 layers by connecting the source of the pfet to Vdd and source of the nfet to Vss. 


Next, connect the drains of both mosfets to the output.
Finally, connect the input to all the poly contacts of the gate.
<img  width="1085" alt="ss_22" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day_28/ss_22.png"> <br><br>

Save the file and select the autowrite option.

Run the following commands in the magic console as shown.
```ruby
extract do local    (Ensuring that magic writes all results to the local directory)
extract all         (Performing the actual extraction)
ext2spice lvs       (Simulating and setting up the netlist to hierarchical spice output in ngspice format with no parasitic components)
ext2spice           (Generating the spice netlist)
```

<img  width="1085" alt="ss_23" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day_28/ss_23.png"> <br><br>

```ruby
rm *.ext                                          (Clear any unwanted files -> .ext files are just intermediate results from the extraction)
/usr/share/pdk/bin/cleanup_unref.py -remove .     (Clean up extra .mag files -> files containing paramaterised cells that were created and saved but not used in the design)
netgen -batch lvs "../mag/inverter.spice inverter" "../xschem/inverter.spice inverter"    (Run LVS by entering the netgen subdirectory)
```
<img  width="1085" alt="ss_24" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day_28/ss_24.png"> <br><br>

When utilizing the netgen command, it is crucial to follow a specific sequence: prioritize the layout netlist first, followed by the schematic netlist. This arrangement ensures a side-by-side comparison, positioning the layout on the left and the schematic on the right for a comprehensive analysis.

Each netlist is denoted by a pair of keywords enclosed in quotes. The initial keyword signifies the location of the netlist file, while the second represents the name of the subcircuit to be compared. This pairing structure facilitates an organized and systematic examination of the netlists.

Upon reviewing the results, a discernible issue in the wiring becomes apparent. The netlists, when compared, exhibit disparities, indicating a mismatch between the layout and schematic. This inconsistency can be attributed to wiring errors present in the layout, emphasizing the significance of meticulous attention to wiring details to ensure accurate netlist alignment and subsequent circuit analysis.
<img  width="1085" alt="ss_25" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day_28/ss_25.png"> <br><br>

**Debugging errors in netlist, rerun and save layout:** <br>

```ruby
extract do local
extract all
ext2spice lvs
ext2spice cthresh 0     (Tells magic to add all the parasitic capacitances to the spice netlist)
ext2spice
```
 <img  width="1085" alt="ss_26" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day_28/ss_26.png"> <br><br>

In the provided netlist file, observe several lines commencing with the letter C, delineating the various parasitic capacitances within the circuit.
```ruby
gvim inverter.spice
```
<img  width="1085" alt="ss_27" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day_28/ss_27.png"> <br><br>
<img  width="1085" alt="ss_28" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day_28/ss_28.png"> <br><br>

```ruby
cp ../xschem/inverter_tb.spice .
vim inverter_tb.spice
```
After the Modification of the test bench netlist file:
<img  width="1085" alt="ss_29" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day_28/ss_29.png"> <br><br>

```ruby
/usr/share/pdk/bin/cleanup_unref.py -remove .
cp ../xschem/.spiceinit .
ngspice inverter_tb.spice
```

We observe that the result is nearly same as in previous simulation in xschem:
<img  width="1085" alt="ss_30" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day_28/ss_30.png"> <br><br>

</details>

## Day-29-Low power design using opensource sky130
<details>
	<summary>Introduction</summary>
Distinguishing "power" and "energy" and their impact on performance:

**Power:**
- **Definition:** Power is the rate at which energy is transferred or converted, measured as the amount of energy transferred or converted per unit of time.
- **Formula:** In electrical terms, power (P) is calculated as the product of voltage (V) and current (I): P = V × I.
  
  As power increases, the following observations can be made:
  - Heat dissipation increases.
  - Cooling costs rise.
  - Frequency is limited.
  - Overall material degradation occurs faster.

**Energy:**
- **Definition:** Energy is the capacity to do work or produce heat, existing in various forms such as electrical, mechanical, and thermal.
- **Formula:** In electrical terms, energy (E) can be calculated by multiplying power (P) by time (t): E = P × t or E = V × I × t.

**Economics of Power/Energy:**
- Performance.
- Cost.
- Packaging.
- Battery capacity.
- Shipping.
- Weight.
- Form factor.
- Functionality.
- Context of use.
- Comfort/Safety.

**Low Power Designs:**
Low-power designs are essential for various electronic devices and systems for several reasons:

1. **Battery Life:** Extends the battery life for portable devices like smartphones and wearables.
2. **Heat Dissipation:** Reduces heat generation, preserving electronic component performance and lifespan.
3. **Environmental Impact:** Enhances energy efficiency, reducing the environmental footprint.
4. **Cost Reduction:** Lowers production costs and enhances device affordability.
5. **Portability and Mobility:** Enables smaller, lighter devices, crucial for user comfort and convenience.
6. **Reliability:** Improves device reliability with lower power consumption and reduced operating temperatures.
7. **Regulatory Compliance:** Helps meet energy consumption regulations and standards.

**Portable vs. Mobile vs. Mobility:**
In low-power IC design, "portable," "mobile," and "mobility" describe different aspects of devices:

- **Portable:** Easily carried devices like laptops and tablets benefit from low-power designs for extended battery life.
- **Mobile:** Devices designed for use on the go, like smartphones, rely on low-power ICs for prolonged battery life during constant connectivity and multimedia use.
- **Mobility:** In IC design, refers to creating circuits that cater to dynamic requirements of portable and mobile devices, optimizing power consumption during various operating modes.

**Power Management Techniques:**
- **Basic Techniques:** Clock gating and Multi-Threshold.
- **Advanced Techniques:** MTCMOS power gating, Power gating with state retention, DVFS, and Low VDD StandBy.



</details>


<details>
	<summary>Low power fundamentals</summary>

Creating low-power designs involves a combination of strategies, methodologies, and techniques across various levels of IC and system design. Here are the essential aspects and practices in low-power design:

### Design Goals and Requirements Analysis:

#### Power Budgeting:
- Determine acceptable power consumption limits for different parts of the system.
  
#### Use Case Analysis:
- Understand different usage scenarios to optimize power usage during various modes of operation.

### Architecture-Level Strategies:

#### Power-Aware Architectures:
- Design with power efficiency in mind, utilizing techniques like clock gating, power gating, and voltage/frequency scaling.

#### Partitioning and Power Domains:
- Divide the system into power domains, enabling selective activation/deactivation of parts to conserve power.

### Circuit-Level Techniques:

#### Transistor Level Optimization:
- Use low-leakage transistors, sub-threshold operation, and other techniques to minimize leakage currents.

#### Clock and Data Management:
- Implement clock gating, data encoding, and other logic techniques to reduce dynamic power consumption.

### System-Level Strategies:

#### Dynamic Power Management:
- Employ techniques like DVFS (Dynamic Voltage and Frequency Scaling) and AVS (Adaptive Voltage Scaling) to adjust power according to workload.

#### Low-Power Modes:
- Utilize sleep, idle, or power-down modes during periods of inactivity.

### Verification and Validation:

#### Power-Aware Simulation and Verification:
- Use specialized tools and methodologies to validate power consumption estimations and optimize power-critical paths.

#### Hardware/Software Co-Design:
- Collaborate on power optimization between hardware and software to maximize efficiency.

### Technological Innovations:

#### Advanced Process Nodes:
- Benefit from newer process technologies that inherently offer better power efficiency.

#### Emerging Design Methodologies:
- Explore novel design methodologies like approximate computing, probabilistic computing, or energy harvesting for specific applications.

### Tools and Methodologies:

#### Power Analysis Tools:
- Utilize simulation tools that provide accurate power estimates at different design stages.

#### Power-Aware Synthesis Tools:
- Employ tools that optimize circuits and architectures for reduced power consumption.

### Standard Compliance and Optimization:

#### Compliance with Power Standards:
- Ensure designs meet regulatory standards for power consumption.

#### Trade-off Analysis:
- Balance performance, area, and power to achieve optimal design results.

### Documentation and Knowledge Sharing:

#### Document Power Considerations:
- Maintain comprehensive documentation detailing power design decisions, methodologies, and trade-offs.

#### Knowledge Sharing:
- Encourage knowledge sharing among design teams to propagate best practices and lessons learned.

### Voltage Control Techniques:

#### Power Gating:

##### How Power Gating Works:

- **Isolation Transistors:** Power gating involves the use of isolation transistors to disconnect the power supply from inactive blocks or sections of the chip. These transistors act as switches, completely cutting off power when the block is powered down.
  
- **Control Logic:** Control logic determines when to enable or disable the power gates based on the activity or inactivity of the specific block. It ensures that power is gated off when the block is idle and restores power when it needs to become operational.
  
- **Retention Elements:** To preserve critical data or state information when the block is powered down, retention elements (such as flip-flops with isolated power supplies) are often used to maintain the data during power-off periods.

##### Benefits of Power Gating:

- **Reduction in Leakage Power:** By disconnecting power to inactive blocks, leakage current flowing through transistors in those sections is significantly reduced, minimizing static power consumption.

- **Improved Energy Efficiency:** Power gating contributes to overall energy efficiency in the system, especially in battery-powered devices, by conserving power when not actively in use.

- **Enhanced Battery Life:** Extending the battery life of portable devices by minimizing power consumption during idle or standby modes through efficient power gating techniques.

- **Heat Reduction:** Shutting off power to inactive blocks reduces heat dissipation, contributing to a cooler operating temperature for the IC.

##### Challenges and Considerations:

- **Design Complexity:** Implementing power gating adds complexity to the design, requiring additional control logic and ensuring proper synchronization to avoid issues such as glitches or improper power-up sequences.

- **Switching Overhead:** Switching power gates on and off introduces some overhead in terms of delay and power consumption associated with the control logic.

- **Design Verification:** Proper verification and testing are crucial to ensure correct functionality of power gating to prevent issues like data loss or corruption during power transitions.

#### Dynamic Voltage Scaling (DVS):

##### Mechanism:

- **Voltage-Frequency Scaling:** DVS involves adjusting the voltage and frequency supplied to the processor. Lowering voltage reduces power consumption, while altering frequency impacts performance.
  
- **Real-time Adaptation:** DVS algorithms continuously monitor the workload and dynamically adjust voltage and frequency levels to meet performance requirements while minimizing power usage.
  
- **Dynamic Optimization:** It optimizes power consumption by scaling voltage and frequency to match the current processing demands. This extends battery life in mobile devices and reduces heat dissipation in computing systems.

##### Benefits:

- **Energy Efficiency:** By adapting the power supply to match processing needs, DVS significantly reduces power consumption during idle or low-demand periods.

- **Heat Reduction:** Lower voltage operation leads to less heat generation, improving thermal management and extending device lifespan.

- **Battery Life Extension:** Particularly beneficial for portable devices, DVS extends battery life by intelligently managing power consumption.

##### Challenges:

- **Performance vs. Power Tradeoff:** Lowering voltage for power savings can impact performance, requiring a careful balance between energy efficiency and computing speed.

- **Complex Algorithms:** Implementing efficient DVS algorithms that accurately predict workload and adjust voltages/frequencies in real-time is challenging.

- **Voltage/Frequency Scaling Limits:** Hardware limitations and operational constraints may restrict the extent to which voltage and frequency can be scaled without compromising stability and functionality.

##### Applications:

- **Mobile Devices:** Smartphones, tablets, and laptops use DVS to optimize battery life without sacrificing performance.

- **Server Farms:** Data centers leverage DVS to manage power consumption in large-scale computing environments, reducing operational costs.

- **Embedded Systems:** DVS is crucial in embedded systems, where power efficiency is paramount (e.g., IoT devices, automotive electronics).

#### Low VDD Standby:

##### Mechanism:

- **Voltage Reduction:** During standby or idle states, the voltage supplied to the circuitry is significantly lowered, reducing power consumption.

- **Maintaining Functionality:** Despite the reduced voltage, the circuit is designed to retain the necessary functionalities required for quick resumption of normal operation when activated.

- **Retentive States:** Certain parts of the circuit might enter a low-power, retentive state, preserving critical data or configurations while operating at minimal power levels.

##### Benefits:

- **Power Savings:** Low VDD Standby significantly reduces power consumption during idle periods, extending battery life in portable devices and reducing energy costs in large-scale systems.

- **Quick Resumption:** The circuit remains in a state where it can quickly return to active operation without a significant delay when required.

- **Environmental Impact:** Lower power consumption contributes to reduced carbon footprint and energy conservation.

##### Challenges:

- **Maintaining Stability:** Ensuring that the circuit operates reliably and maintains data integrity while at reduced voltage levels.

- **Compatibility:** Designing circuits
 
</details>

<details>
	<summary>More about low power</summary>

 ### Power State Space

In low-power design, the "power state space" encompasses the various states or modes in which a semiconductor device can operate concerning power consumption. Effective management of the power state space is crucial, especially in modern electronics like portable devices, IoT devices, and battery-powered systems.

The power state space typically includes different operational modes or states that an IC can transition between to optimize power usage. Common power states in low-power design include:

- **Active Mode:** The typical operating state where the IC performs its functions at full capacity, consuming the most power.
  
- **Sleep or Standby Mode:** Parts of the IC are powered down or put into a low-power mode, reducing power consumption while allowing quick return to an active state.
  
- **Idle Mode:** Similar to sleep mode but with slightly higher power consumption, reducing power while remaining ready to resume full operation quickly.
  
- **Power-Off Mode:** The IC is completely powered down, consuming minimal power but requiring a longer time to resume normal operation.

Low-power IC design involves optimizing transitions between these power states, utilizing techniques such as power gating, voltage scaling, clock gating, and various design methodologies to minimize power consumption without compromising functionality or responsiveness.

Designers use power management units (PMUs) or power management integrated circuits (PMICs) to regulate power delivery to different chip sections, ensuring efficient utilization of power states based on the device's requirements.

Balancing performance with power consumption is crucial in low-power IC design to prolong battery life, reduce heat dissipation, and enhance overall energy efficiency.

### Low Power VMM Testbench

A low-power VMM testbench is specifically designed for verifying and validating the functionality, performance, and power management features of low-power IC designs. It employs various strategies and methodologies to ensure correct operation while minimizing power consumption.

**Key Components of a Low-Power VMM Testbench:**

1. **Power-Aware Testbench Architecture:**
   - Modification or extension of the testbench architecture to include components modeling power management units (PMUs), power domains, power modes, and transitions between power states.

2. **Power-Aware Stimulus Generation:**
   - Generation of stimuli covering various power modes and transitions to ensure correct behavior when switching between different power states. Includes scenarios for power-up, power-down, sleep modes, and transitions between active and low-power states.

3. **Checkers for Power Consumption:**
   - Integration of checkers or monitors within the testbench to verify power consumption levels against specified criteria. These checkers analyze power-related signals to ensure the DUT operates within acceptable power limits in different operational modes.

4. **Power-Aware Coverage Metrics:**
   - Definition and tracking of coverage metrics specifically targeting power-related scenarios and transitions. This includes coverage for different power modes exercised during testing to ensure comprehensive verification.

5. **Simulation and Emulation Environments:**
   - Leveraging simulation and emulation environments to validate low-power features. Emulation platforms enable extensive testing of power states, transitions, and interactions with software running on the DUT.

6. **Advanced Verification Techniques:**
   - Employment of advanced techniques such as assertion-based verification, formal verification, and power-aware simulation to comprehensively validate low-power features.

7. **Scenario-Based Testing:**
   - Creation of test scenarios stressing the DUT under different power conditions to ensure proper functionality and performance across various power modes.

### Island Ordering

The concept of "island ordering" is integral to the power optimization strategy in low-power design. It involves organizing and prioritizing power domains or islands within a chip to optimize power management and reduce overall consumption.

**Key Aspects of Island Ordering:**

1. **Dependency and Hierarchical Structure:**
   - Determination of dependencies and relationships between different functional blocks or islands within the chip. Some blocks may need to be powered up before others to maintain proper functionality.

2. **Power-Up Sequence:**
   - Establishment of the order in which power domains or islands are powered up to ensure that essential blocks required for the chip's initial operation are activated first.

3. **Power-Down Sequence:**
   - Definition of the sequence for powering down the islands to avoid potential hazards like data loss, signal glitches, or unintended interactions between different parts of the chip.

4. **Power Management Control:**
   - Implementation of control mechanisms and protocols to manage power state transitions efficiently. This might involve using power management units (PMUs) or dedicated hardware/software mechanisms.

5. **Verification and Testing:**
   - Rigorous verification and testing to validate the correctness of the power sequencing and ensure that the power domains operate as intended under different scenarios and use cases.

### Basic Multivoltage Terminology

In most ICs, different parts of the chip require distinct voltage levels for proper operation. These voltage supply lines, often referred to as "rails," power specific sections of the chip. Some common types of rails include Core Voltage Rail, I/O Voltage Rail, Memory Voltage Rail, and Analog/Digital Voltage Rails.

"Multi Vdd" is a design technique used in low-power design where different sections or blocks of a chip are powered by independent and separate voltage supplies (Vdd). Each voltage domain operates at its designated voltage level, optimizing power consumption, improving performance, and addressing specific design requirements.

**Advantages of Multi Vdd:**

1. **Power Efficiency:**
   - Allows each section to operate at its optimal voltage level,

 
</details>

<details>
	<summary>Module 4</summary>

 ### ARM-based SoCs Power Management

ARM-based System-on-Chips (SoCs) are prevalent in diverse devices such as smartphones, tablets, IoT devices, and embedded systems. Effective power management in these systems is essential to optimize performance, extend battery life, and manage thermal constraints. Several power management schemes are commonly implemented in ARM-based SoCs:

1. **Dynamic Voltage and Frequency Scaling (DVFS):**
   - Adjusts CPU voltage and frequency dynamically based on workload, optimizing power usage. Frequency and voltage decrease during low workload and increase during higher demands.

2. **CPU Power Modes (Idle States):**
   - Implements multiple power states (e.g., C-states) allowing the CPU to enter low-power states during idle times. This involves powering down or reducing frequencies of specific CPU parts.

3. **Heterogeneous Multi-Processing (HMP):**
   - Leverages multiple CPU cores with varying power-performance characteristics. Tasks are assigned to different cores based on their power-performance trade-offs, optimizing power usage.

4. **Peripheral Power Management:**
   - Applies power management techniques (e.g., clock gating, power gating) to peripherals like GPUs, DSPs, and I/O controllers. Selective enabling or disabling of peripherals reduces overall power consumption.

5. **Adaptive Voltage Scaling (AVS):**
   - Dynamically adjusts voltage levels supplied to components based on performance requirements. AVS scales voltage to the lowest level maintaining stable operation, reducing power consumption without sacrificing performance.

6. **Temperature and Thermal Management:**
   - Incorporates thermal management schemes to monitor and regulate temperature. Dynamic thermal management techniques, like throttling, prevent overheating while maintaining stability.

7. **Software-Based Power Governors:**
   - Embedded in the operating system or firmware, power governors manage power states. They determine transitions between different power modes based on system demands and user settings.

These power management schemes, often combined, aim to balance performance and power consumption, providing efficient and responsive ARM-based devices while optimizing energy usage and extending battery life.

### Power Management Bugs and Conflicting Events

#### Power Management Bugs:

Power management introduces new bug types that need attention during design:

1. **Isolation/Level Shifting Bugs:**
   - Errors in isolating or shifting voltage levels can lead to signal integrity issues.

2. **Control Sequencing Bugs:**
   - Errors in the sequence of power control operations can impact stability and functionality.

3. **Retention Scheme/Control Errors:**
   - Flaws in retention schemes or control mechanisms may result in data loss during power-down.

4. **Retention Selection Errors:**
   - Incorrect selection of retention policies can lead to loss of critical data.

5. **Electrical Problems:**
   - Memory corruption and other electrical issues can arise during power state transitions.

6. **Power Sequencing/Voltage Scheduling Errors:**
   - Mistakes in sequencing or scheduling can cause glitches during transitions.

7. **Hardware-Software Deadlock:**
   - Conflicts between hardware and software power management instructions can result in deadlock scenarios.

8. **Power Gating Collapse/Dysfunction:**
   - Failures in power gating mechanisms can lead to excessive power consumption.

9. **Power On Reset/Bring Up Problems:**
   - Issues during power-on can affect the stability of the system.

10. **Thermal Runaway/Overheating:**
    - Inadequate thermal management can lead to overheating issues.

#### Conflicting Events in Low-Power Design:

Conflicts arise between various power-saving techniques or design constraints:

1. **Voltage-Frequency Conflicts:**
   - DVFS aiming for power savings may conflict with high-performance demands, impacting power efficiency.

2. **Clock Gating vs. Timing Requirements:**
   - Timing requirements of certain blocks may conflict with the idea of clock gating, balancing power savings with meeting timing requirements.

3. **Power Gating and Wake-up Time:**
   - Power gating, while saving power, may conflict with the need for instant responsiveness, impacting the balance between power savings and responsiveness.

4. **Multiple Power Domains Coordination:**
   - Managing multiple power domains can create conflicts in timing and sequencing during transitions.

5. **Trade-offs between Power and Functionality:**
   - Aggressive power-saving methods may compromise system functionality, creating conflicts between power efficiency and functional requirements.

Resolving conflicting events involves careful trade-offs, optimizations, and compromises, considering specific system requirements and achieving a balance between power efficiency and functionality.

### Combining Multiple CPUs

When combining multiple CPUs, a hierarchical sub-system view is crucial. Consideration of software threads and hardware events in each sub-system is necessary. An FSM (Finite State Machine) view of power states should be commonly understood across sub-system boundaries, often facilitated by standards like ACPI. While homogeneous subsystems allow code reuse, heterogeneous subsystems introduce challenges, but this is common.

### Power Management Verification

Power management verification ensures that power-saving features operate correctly and efficiently within an IC design. Key verification methods include:

1. **Functional Verification:**
   - Ensures power management features function as intended, validating power state transitions, power-on/off sequences, and power control logic.

2. **Simulation and Emulation:**
   - Uses simulation tools and emulation platforms to model and simulate power states and transitions, validating behavior under various conditions.

3. **Coverage Analysis:**
   - Defines and measures coverage metrics specific to power management scenarios to ensure comprehensive testing.

4. **Assertion-Based Verification:**
   - Utilizes assertions to check and validate specific power-related conditions during simulation or emulation.

5. **Formal Verification:**
   - Applies formal methods to mathematically verify the correctness of power management implementations against specified requirements.

6. **Low-Power Design Verification Tools:**
   - Leverages specialized tools for low-power designs to identify and optimize power-related issues.

7. **Hardware Emulation and Prototyping:**
   - Uses hardware emulation or prototyping for real-world testing, providing a more accurate representation of power behavior.

8. **Dynamic Power Analysis:**
   - Performs power analysis during simulation or post-silicon testing to measure actual power consumption against expected budgets.

Power management verification ensures reliability, efficiency, and correctness of power-saving features, preventing issues related to power states, transitions, and overall power control in the IC design. It is vital for optimal power efficiency while meeting functional and performance requirements.


</details>

<details>
	<summary>Module 5</summary>

 #### Island Ordering in Low-Power Design:

**Overview:**
- **Definition:** Island ordering is a technique employed in low-power design to minimize power consumption by strategically placing different voltage islands on the chip.
- **Voltage Islands:** These are clusters of logic blocks operating at distinct supply voltages.
- **Objective:** Placing islands with similar voltages in close proximity reduces power supply wire length, subsequently lowering voltage drop and overall power consumption.

**Two Approaches:**
1. **Top-Down Island Ordering:**
   - *Description:* Divides the chip into islands based on a high-level power analysis.
   - *Simplicity:* Simple to implement but may not be as effective as bottom-up ordering.
   
2. **Bottom-Up Island Ordering:**
   - *Description:* Utilizes a power grid analysis tool for optimal placement of individual logic blocks.
   - *Complexity:* More intricate but potentially achieves greater power savings.
   - *Process:* Considers power consumption, resistance, and capacitance of power supply wires.

**Implementation Steps:**
1. **Power Grid Analysis:**
   - *Tool Usage:* Utilizes a power grid analysis tool to determine optimal logic block placement.
   - *Considerations:* Factors in power consumption, resistance, and capacitance for accurate results.

2. **Island Placement:**
   - *Optimization:* Places voltage islands with similar levels closer together.
   - *Objective:* Minimizes power supply wire length, optimizing power efficiency.

**Significance:**
- **Power Reduction:** Island ordering significantly contributes to lowering power consumption in low-power design.
- **Wire Length Impact:** By strategically organizing voltage islands, the length of power supply wires is minimized, reducing voltage drop and, consequently, power usage.

---

#### Power Formats in Low-Power Design:

**Introduction:**
- **Role in Low-Power Design:** Power formats are instrumental in managing and optimizing power consumption effectively.
- **Standardization:** These formats provide a standardized representation for power intent, aiding informed decision-making in power-saving techniques.

**Common Power Formats:**
1. **Unified Power Format (UPF):**
   - *Standard:* Industry-standard defined by IEEE 1801.
   - *Comprehensiveness:* Comprehensive framework covering supply voltages, power domains, leakage models, and design constraints.
   - *Hierarchical Support:* Enables hierarchical power management for varying levels of abstraction.

2. **Power Analysis Markup Language (PAM-XML):**
   - *Developed by:* Mentor Graphics.
   - *Characteristics:* Lightweight, XML-based format suitable for early-stage power analysis.
   - *Syntax:* Simpler and more intuitive syntax compared to UPF.

3. **Common Power Format (CPF):**
   - *Developed by:* Synopsys.
   - *Features:* Similar to UPF but includes additional features for power-aware synthesis and optimization.
   - *Applications:* Supports power-aware clock tree synthesis, scan insertion, and other power-saving techniques.

4. **PowerIntent (PI):**
   - *Developed by:* Cadence Design Systems.
   - *Advancements:* A newer format gaining popularity for advanced process technologies.
   - *Enhancements:* Offers advanced features for power modeling, including leakage currents, crosstalk effects, and power grid analysis.

**Choosing the Right Power Format:**
- **Considerations:** Selection depends on design methodology, tool preferences, and required power analysis detail.
- **UPF Standardization:** UPF is the industry standard, well-supported by EDA tools, suitable for complex power management scenarios.
- **PAM-XML Simplicity:** PAM-XML is apt for early-stage estimation and designers preferring a simpler format.
- **CPF Synopsys-Specific:** CPF is designed for power-aware synthesis and optimization.
- **PowerIntent Advancements:** PowerIntent gains traction for its advanced features in power modeling for advanced process technologies.

**Benefits of Power Formats:**
- **Standardized Representation:** Provides a standardized way to represent power intent, ensuring clarity and consistency across teams and tools.
- **Early Power Analysis:** Supports early-stage power analysis, allowing early identification and resolution of power issues.
- **Power-Aware Optimization:** Enables optimization techniques like power gating, voltage scaling, and clock gating.
- **Design for Manufacturability (DFM):** Facilitates power grid analysis to meet power delivery requirements.
- **Design Reuse:** Facilitates power intent reuse, reducing design time and enhancing consistency.

---

#### UPF (Unified Power Format):

**Introduction:**
- **Standard Specification:** Unified Power Format (UPF) is an industry-standard specification for conveying power intent in integrated circuits (ICs).
- **Structured Representation:** Provides a structured and consistent way to convey power management information throughout various design phases.

**Key Features of UPF:**
1. **Supply Voltages:**
   - Defines supply voltages for different power domains, ensuring efficient power distribution and minimizing voltage drops.
  
2. **Power Domains:**
   - Allows grouping of logic blocks into power domains, providing granular control over power management.
  
3. **Leakage Models:**
   - Supports leakage models for different transistor types, aiding accurate power estimation and optimization.
  
4. **Power-Aware Constraints:**
   - Provides mechanisms to specify power-aware constraints, such as power gating and voltage scaling thresholds.
  
5. **Hierarchical Power Management:**
   - Supports hierarchical power management, enabling specification of power intent at different abstraction levels.
  
6. **Tool Control Language (TCL):**
   - Utilizes TCL for scripting and automation, ensuring compatibility and integration with various EDA tools.

**Applications of UPF:**
- **Power Estimation:** Utilized for early-stage power estimation, enabling proactive identification and resolution of power-related issues.
  
- **Power Optimization:** Guides the implementation of power-saving techniques such as power gating, voltage scaling, and clock gating.
  
- **Physical Design:** Used in generating power delivery networks, ensuring adherence to power delivery requirements.
  
- **Design Verification:** Employed in simulations to verify functionality and power behavior under diverse operating conditions.
  
- **Signoff:** Incorporated into signoff tools to verify compliance with power requirements and manufacturing specifications.
</details>


## Day-30-TCL Programming

<details>
	<summary>Introduction to TCL and VSDSYNTH tool box usage</summary>
TCL scripting involves several key steps:

1. **Command Creation:** Develop a command to transmit a .csv file from the UNIX shell to the TCL script.

2. **Input Conversion:** Transform all inputs into format[1] and SDC format, transmitting these to the 'yosys' synthesis tool.

3. **Format Transformation:** Convert format[1] and SDC to format[2] and feed them into the timing tool 'Opentimer.'

4. **Report Generation:** Finally, execute the TCL task to generate an output report containing WNS, TNS, runtime, and other design metrics. <br>


 
**Creating a command entails handling various user scenarios:** <br>

1. **No CSV File Provided:** <br>
   ```ruby
   if ($#argv != 1) then
      echo "Info: Please provide the csv file"
      exit 1
   endif
   ```

2. **Providing a Nonexistent CSV File:** <br>
   ```ruby
   ./vsdflow my.csv
   ```

3. **Usage Inquiry:** <br>
   ```ruby
   ./vsdflow -help
   ```

These snippets effectively cover scenarios like missing CSV input, providing a non-existing file, and seeking usage information. <br>
This is achieved with the following snip of code as follows:
```ruby
if (! -f $argv[1] || $argv[1] == "-help") then
        if ($argv[1] != "-help") then
                echo "Error:  Cannot find csv file $argv[1]. Exiting..."
                exit 1
        else
                echo USAGE: ./vsdflow \<csv file\>
                echo
                echo         where \<csv file\> consists of 2 columns, below keyword being in 1st column and is Case Sensitive. Please request VSD team for sample csv file
                echo
                echo         \<Design Name\> is the name of top level module
                echo
                echo         \<Output Directory\> is the name of output directory where you want to dump synthesis script, synthesized netlist and timing reports
                echo
                echo         \<Netlist Directory\> is the name of directory where all RTL netlist are present
                echo
                echo         \<Early Library Path\> is the file path of the early cell library to be used for STA
                echo
                echo         \<Late Library Path\> is file path of the late cell library to be used for STA
                echo
                echo         \<Constraints file\> is csv file path of constraints to be used for STA
                echo
                exit 1
        endif
else
		tclsh vsdflow.tcl $argv[1]
endif
```

</details>

<details>
	<summary>Variable creation and processing constraints from CSV</summary>


Let's break down the detailed process of converting inputs into format[1] and SDC, passing them to the 'yosys' synthesis tool, and creating variables: <br>

1. **Variable Creation:** <br>
   - Accessing inputs in the .csv file and assigning file names to variables: <br>
     ```ruby
     set filename [lindex $argv 0]
     ```

   - Reading values from the .csv file and creating a matrix using packages csv and struct::matrix: <br>
     ```ruby
     package require csv
     package require struct::matrix
     struct::matrix m
     ```

   - Opening the .csv file in read mode: <br>
     ```ruby
     set f [open $filename]
     ```

   - Mapping the opened file to the matrix using csv::read2matrix: <br>
     ```ruby
     csv::read2matrix $f m , auto
     ```

   - Closing the file: <br>
     ```ruby
     close $f
     ```

   - Identifying the size of the matrix: <br>
     ```ruby
     set columns [m columns]
     m link arr
     set rows [m rows]
     ```

2. **Matrix and Array Linking:** <br>
   - Linking the matrix to an array for convenient access: <br>
     ```ruby
     m link arr
     ```

   - Accessing values using array indices: <br>
     ```ruby
     arr($row, $column)
     ```


These steps demonstrate the meticulous process of handling CSV file inputs, creating variables, and establishing connections between matrices and arrays for effective data access in Tcl scripting.



```ruby
set i 0
while {$i < $n_rows} {
        puts "\nInfo: Setting $csv_arr(0,$i) as '$csv_arr(1,$i)'"
        if { ![string match "*/*" $csv_arr(1,$i)] && ![string match "*.*" $csv_arr(1,$i)] } {
                        set [string map {" " "_"} $csv_arr(0,$i)] $csv_arr(1,$i)
        } else {
                set [string map {" " "_"} $csv_arr(0,$i)] [file normalize $csv_arr(1,$i)]
        }
        set i [expr {$i+1}]
}
```
The provided code initializes the following crucial variables:

- **Design Name:** 'openMSP430'
- **Output Directory:** './outdir_openMSP430'
- **Netlist Directory:** './verilog'
- **Early Library Path:** 'osu018_stdcells.lib'
- **Late Library Path:** 'osu018_stdcells.lib'
- **Constraints File:** 'openMSP430_design_constraints.csv'
- **Output directory:** /home/vsduser/vsdsynth/outdir_openMSP430
- **RTL netlist directory:** /home/vsduser/vsdsynth/verilog
- **Early cell library:** /home/vsduser/vsdsynth/osu018_stdcells.lib
- **Late cell library:** /home/vsduser/vsdsynth/osu018_stdcells.lib
- **Constraints file:** /home/vsduser/vsdsynth/openMSP430_design_constraints.csv

To validate the existence of all the files and directories, the following code snippet is employed:

```ruby
foreach item [list $output_directory $rtl_netlist_directory $early_cell_library $late_cell_library $constraints_file] {
    if {![file exists $item]} {
        puts "Error: $item does not exist."
        exit 1
    }
}
```

This code iterates through the list of directories and files, checking their existence. If any item is not found, it raises an error message and exits the script with a status code of 1. This ensures that all required elements are in place before proceeding with further tasks.
```ruby
if { ![file isdirectory $Output_Directory] } {
        puts "\nInfo: Cannot find output file directory $Output_Directory. Creating $Output_Directory"
        file mkdir $Output_Directory
} else {
        puts "\nInfo: Output directory found in path $Output_Directory"
}
# Checking if netlist directory exists if not exits
if { ![file isdirectory $Netlist_Directory] } {
        puts "\nError: Cannot find RTL netlist directory in path $Netlist_Directory. Exiting..."
        exit
} else {
        puts "\nInfo: RTL netlist directory found in path $Netlist_Directory"
}
# Checking if early cell library file exists if not exits
if { ![file exists $Early_Library_Path] } {
        puts "\nError: Cannot find early cell library in path $Early_Library_Path. Exiting..."
        exit
} else {
        puts "\nInfo: Early cell library found in path $Early_Library_Path"
}
# Checking if late cell library file exists if not exits
if { ![file exists $Late_Library_Path] } {
        puts "\nError: Cannot find late cell library in path $Late_Library_Path. Exiting..."
        exit
} else {
        puts "\nInfo: Late cell library found in path $Late_Library_Path"
}
# Checking if constraints file exists if not exits
if { ![file exists $Constraints_File] } {
        puts "\nError: Cannot find constraints file in path $Constraints_File. Exiting..."
        exit
} else {
        puts "\nInfo: Constraints file found in path $Constraints_File"
}  
```

Now, to handle the constraints, the following code snippet is employed:
```ruby
# Constraints csv file data processing for convertion to format[1](excel) and SDC

puts "\nInfo: Dumping SDC constraints for $Design_Name"
::struct::matrix cons
set f1 [open $Constraints_File]
csv::read2matrix $f1 cons , auto
close $f1
set n_rows_concsv [cons rows]
set n_columns_concsv [m1 columns]
# Finding row number starting for CLOCKS section
set clocks_start_row [lindex [lindex [cons search all CLOCKS] 0] 1]
# Finding column number starting for CLOCKS section
set clocks_start_column [lindex [lindex [cons search all CLOCKS] 0] 0]
# Finding row number starting for INPUTS section
set inputs_start [lindex [lindex [cons search all INPUTS] 0] 1]
# Finding row number starting for OUTPUTS section
set outputs_start [lindex [lindex [cons search all OUTPUTS] 0] 1]

puts "\nInfo: Listing value of variables for user debug"
puts "Number of rows in CSV file = $n_rows_concsv"
puts "Number of columns in CSV file = $n_columns_concsv"
puts "CLOCKS starting row in CSV file = $clocks_start_row"
puts "CLOCKS starting column in CSV file = $clocks_start_column"
puts "INPUTS starting row in CSV file = $inputs_start "
puts "OUTPUTS starting row in CSV file = $outputs_start "
```

</details>

<details>
	<summary>Processing Clock and input constraints</summary>

After converting the file into a matrix 'm' containing essential input details, we proceed to read all the constraints from the CSV file in a similar fashion. Each cell element is assigned to variables, and for verification purposes, they are printed as follows:
```ruby
# Constraints csv file data processing for convertion to format[1](excel) and SDC

puts "\nInfo: Dumping SDC constraints for $Design_Name"
::struct::matrix cons
set f1 [open $Constraints_File]
csv::read2matrix $f1 cons , auto
close $f1
set n_rows_concsv [cons rows]
set n_columns_concsv [cons columns]
# Finding row number starting for CLOCKS section
set clocks_start_row [lindex [lindex [cons search all CLOCKS] 0] 1]
# Finding column number starting for CLOCKS section
set clocks_start_column [lindex [lindex [cons search all CLOCKS] 0] 0]
# Finding row number starting for INPUTS section
set inputs_start [lindex [lindex [cons search all INPUTS] 0] 1]
# Finding row number starting for OUTPUTS section
set outputs_start [lindex [lindex [cons search all OUTPUTS] 0] 1]

puts "\nInfo: Listing value of variables for user debug"
puts "Number of rows in CSV file = $n_rows_concsv"
puts "Number of columns in CSV file = $n_columns_concsv"
puts "CLOCKS starting row in CSV file = $clocks_start_row"
puts "CLOCKS starting column in CSV file = $clocks_start_column"
puts "INPUTS starting row in CSV file = $inputs_start "
puts "OUTPUTS starting row in CSV file = $outputs_start "
```
<img  width="1085" alt="1_1" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day_30/1_1.png"> <br><br>


To handle constraints in a CSV file, particularly for clocks and inputs, and generate SDC commands with the processed data dumped into a .sdc file, the following steps have been successfully executed:

The CSV file containing CLOCK data has been processed, resulting in the generation of clock-based SDC commands. Each command includes a unique clock name achieved by appending "_synyui" to the SDC create_clock command. These processed commands have been successfully written into the .sdc file.

```ruby
##############################################################################################
################### Day 3 ###################################################################
# Conversion of constraints csv file to SDC
# -----------------------------------------
# CLOCKS section
# Finding column number starting for clock latency in CLOCKS section
#
#puts "$n_columns_concsv"
set clk_erd_st_col [lindex [lindex [m1 search rect $clocks_start_column $clocks_start_row [expr { $n_columns_concsv - 1}] [expr {$inputs_start-1}] early_rise_delay] 0 ] 0 ]
set clk_efd_st_col [lindex [lindex [m1 search rect $clocks_start_column $clocks_start_row [expr { $n_columns_concsv - 1}] [expr {$inputs_start-1}] early_fall_delay] 0 ] 0 ]
set clk_lrd_st_col [lindex [lindex [m1 search rect $clocks_start_column $clocks_start_row [expr { $n_columns_concsv - 1}] [expr {$inputs_start-1}] late_rise_delay] 0 ] 0 ]
set clk_lfd_st_col [lindex [lindex [m1 search rect $clocks_start_column $clocks_start_row [expr { $n_columns_concsv - 1}] [expr {$inputs_start-1}] late_fall_delay] 0 ] 0 ]

# Finding column number starting for clock transition in CLOCKS section
#

set clk_ers_st_col [lindex [lindex [m1 search rect $clocks_start_column $clocks_start_row [expr { $n_columns_concsv - 1}] [expr {$inputs_start-1}] early_rise_slew] 0 ] 0 ]
set clk_efs_st_col [lindex [lindex [m1 search rect $clocks_start_column $clocks_start_row [expr { $n_columns_concsv - 1}] [expr {$inputs_start-1}] early_fall_slew] 0 ] 0 ]
set clk_lrs_st_col [lindex [lindex [m1 search rect $clocks_start_column $clocks_start_row [expr { $n_columns_concsv - 1}] [expr {$inputs_start-1}] late_rise_slew] 0 ] 0 ]
set clk_lfs_st_col [lindex [lindex [m1 search rect $clocks_start_column $clocks_start_row [expr { $n_columns_concsv - 1}] [expr {$inputs_start-1}] late_fall_slew] 0 ] 0 ]

# Finding column number starting for frequency and duty cycle in CLOCKS section only
set clk_freq_st_col [lindex [lindex [m1 search rect $clocks_start_column $clocks_start_row [expr { $n_columns_concsv - 1}] [expr {$inputs_start-1}] frequency] 0 ] 0 ]
set clk_dc_st_col [lindex [lindex [m1 search rect $clocks_start_column $clocks_start_row [expr { $n_columns_concsv - 1}] [expr {$inputs_start-1}] duty_cycle] 0 ] 0 ]

# Creating .sdc file with design name in output directory and opening it in write mode
#
set sdc_file [open $Output_Directory/$Design_Name.sdc "w"]

# Setting variables for actual clock row start and end
#
set i [expr {$clocks_start_row+1}]
set end_of_clocks [expr {$inputs_start-1}]

puts "\nInfo-SDC: Working on clock constraints and creating clocks. Please wait"

# while loop to write constraint commands to .sdc file
while { $i < $end_of_clocks } {
	#Create SDC command to create clocks.
	puts -nonewline $sdc_file "\ncreate_clock -name [concat [m1 get cell 0 $i]_synui] -period [m1 get cell $clk_freq_st_col $i] -waveform \{0 [expr {[m1 get cell $clk_freq_st_col $i]*[m1 get cell $clk_dc_st_col $i]/100}]\} \[get_ports [m1 get cell 0 $i]\]"

	# set_clock_transition SDC command to set clock transition values
	puts -nonewline $sdc_file "\nset_clock_transition -min -rise [m1 get cell $clk_ers_st_col $i] \[get_clocks [m1 get cell 0 $i]\]"
	puts -nonewline $sdc_file "\nset_clock_transition -min -fall [m1 get cell $clk_efs_st_col $i] \[get_clocks [m1 get cell 0 $i]\]"
	puts -nonewline $sdc_file "\nset_clock_transition -max -rise [m1 get cell $clk_lrs_st_col $i] \[get_clocks [m1 get cell 0 $i]\]"
	puts -nonewline $sdc_file "\nset_clock_transition -max -fall [m1 get cell $clk_lfs_st_col $i] \[get_clocks [m1 get cell 0 $i]\]"

	# set_clock_latency SDC command to set clock latency values
	puts -nonewline $sdc_file "\nset_clock_latency -source -early -rise [m1 get cell $clk_erd_st_col $i] \[get_clocks [m1 get cell 0 $i]\]"
	puts -nonewline $sdc_file "\nset_clock_latency -source -early -fall [m1 get cell $clk_efd_st_col $i] \[get_clocks [m1 get cell 0 $i]\]"
	puts -nonewline $sdc_file "\nset_clock_latency -source -late -rise [m1 get cell $clk_lrd_st_col $i] \[get_clocks [m1 get cell 0 $i]\]"
	puts -nonewline $sdc_file "\nset_clock_latency -source -late -fall [m1 get cell $clk_lfd_st_col $i] \[get_clocks [m1 get cell 0 $i]\]"

	set i [expr {$i+1}]
}
set clocks_start_row_actual [expr {$clocks_start_row+1}]
puts "\n Clocks created in .sdc file. Values for debugging: "
puts "\n Clock early rise delay start column in constraint file = $clk_erd_st_col"
puts "\n Clock early fall delay start column in constraint file = $clk_efd_st_col"
puts "\n Clock late rise delay start column in constraint file = $clk_lrd_st_col"
puts "\n Clock late fall delay start column in constraint file = $clk_lfd_st_col"
puts "\n Clock early rise slew start column in constraint file = $clk_ers_st_col"
puts "\n Clock early fall slew start column in constraint file = $clk_efs_st_col"
puts "\n Clock late rise slew start column in constraint file = $clk_lrs_st_col"
puts "\n Clock late fall slew start column in constraint file = $clk_lfs_st_col"
puts "\n Clock frequency start column in constraint file = $clk_freq_st_col"
puts "\n Clock duty cycle start column in constraint file = $clk_dc_st_col"
puts "\n Clock actual starting row = $clocks_start_row_actual"
puts "\n Clock actual ending row = $end_of_clocks"
```

The image below illustrates the SDC constraints defined for Design 3:
<img  width="1085" alt="2_2" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day_30/2_2.png"> <br><br>

The CSV file, housing CLOCK data, has been processed to generate clock-based SDC commands, which have been seamlessly compiled into the .sdc file. This file, formatted with all necessary constraints for the design, was created using the following code snippet:

```ruby
# Finding the starting column number for input clock latency in INPUTS section
set ip_erd_st_col [lindex [lindex [m1 search rect $clocks_start_column $inputs_start [expr {$n_columns_concsv-1}] [expr {$outputs_start-1}] early_rise_delay] 0 ] 0 ]
set ip_efd_st_col [lindex [lindex [m1 search rect $clocks_start_column $inputs_start [expr {$n_columns_concsv-1}] [expr {$outputs_start-1}] early_fall_delay] 0 ] 0 ]
set ip_lrd_st_col [lindex [lindex [m1 search rect $clocks_start_column $inputs_start [expr {$n_columns_concsv-1}] [expr {$outputs_start-1}] late_rise_delay] 0 ] 0 ]
set ip_lfd_st_col [lindex [lindex [m1 search rect $clocks_start_column $inputs_start [expr {$n_columns_concsv-1}] [expr {$outputs_start-1}] late_fall_delay] 0 ] 0 ]

# Finding column number starting for input clock transition in INPUTS section only
set ip_ers_st_col [lindex [lindex [m1 search rect $clocks_start_column $inputs_start [expr {$n_columns_concsv-1}] [expr {$outputs_start-1}] early_rise_slew] 0 ] 0 ]
set ip_efs_st_col [lindex [lindex [m1 search rect $clocks_start_column $inputs_start [expr {$n_columns_concsv-1}] [expr {$outputs_start-1}] early_fall_slew] 0 ] 0 ]
set ip_lrs_st_col [lindex [lindex [m1 search rect $clocks_start_column $inputs_start [expr {$n_columns_concsv-1}] [expr {$outputs_start-1}] late_rise_slew] 0 ] 0 ]
set ip_lfs_st_col [lindex [lindex [m1 search rect $clocks_start_column $inputs_start [expr {$n_columns_concsv-1}] [expr {$outputs_start-1}] late_fall_slew] 0 ] 0 ]

# Finding column number starting for input related clock in INPUTS section only
set ip_rc_st_col [lindex [lindex [m1 search rect $clocks_start_column $inputs_start [expr {$n_columns_concsv-1}] [expr {$outputs_start-1}] clocks] 0 ] 0 ]

# Setting variables for actual input row start and end
set i [expr {$inputs_start+1}]
set end_of_inputs [expr {$outputs_start-1}]

puts "\nInfo-SDC: Working on input constraints.."
puts "\nInfo-SDC: Categorizing input ports as bits and busses"

# while loop to write constraint commands to .sdc file
while { $i < $end_of_inputs } {
# Checking if input is bussed or not
	set netlist [glob -dir $Netlist_Directory *.v]
	set tmp_file [open /tmp/1 w]
	foreach f $netlist {
		set fd [open $f]
		while { [gets $fd line] != -1 } {
			set pattern1 " [m1 get cell 0 $i];"
			if { [regexp -all -- $pattern1 $line] } {
				set pattern2 [lindex [split $line ";"] 0]
				if { [regexp -all {input} [lindex [split $pattern2 "\S+"] 0]] } {
					set s1 "[lindex [split $pattern2 "\S+"] 0] [lindex [split $pattern2 "\S+"] 1] [lindex [split $pattern2 "\S+"] 2]"
					puts -nonewline $tmp_file "\n[regsub -all {\s+} $s1 " "]"
				
				}
			}
		}
		close $fd
	}
	close $tmp_file
	set tmp_file [open /tmp/1 r]
	set tmp2_file [open /tmp/2 w]
	puts -nonewline $tmp2_file "[join [lsort -unique [split [read $tmp_file] \n]] \n]"
	close $tmp_file
	close $tmp2_file
	set tmp2_file [open /tmp/2 r]
	set count [llength [read $tmp2_file]]
	close $tmp2_file
	if {$count > 2} {
		set inp_ports [concat [m1 get cell 0 $i]*]
	} else {
		set inp_ports [m1 get cell 0 $i]
	}
		# set_input_transition SDC command to set input transition values
	puts -nonewline $sdc_file "\nset_input_transition -clock \[get_clocks [m1 get cell $ip_rc_st_col $i]\] -min -rise -source_latency_included [m1 get cell $ip_ers_st_col $i] \[get_ports $inp_ports\]"
	puts -nonewline $sdc_file "\nset_input_transition -clock \[get_clocks [m1 get cell $ip_rc_st_col $i]\] -min -fall -source_latency_included [m1 get cell $ip_efs_st_col $i] \[get_ports $inp_ports\]"
	puts -nonewline $sdc_file "\nset_input_transition -clock \[get_clocks [m1 get cell $ip_rc_st_col $i]\] -max -rise -source_latency_included [m1 get cell $ip_lrs_st_col $i] \[get_ports $inp_ports\]"
	puts -nonewline $sdc_file "\nset_input_transition -clock \[get_clocks [m1 get cell $ip_rc_st_col $i]\] -max -fall -source_latency_included [m1 get cell $ip_lfs_st_col $i] \[get_ports $inp_ports\]"
# set_input_delay SDC command to set input latency values
	puts -nonewline $sdc_file "\nset_input_delay -clock \[get_clocks [m1 get cell $ip_rc_st_col $i]\] -min -rise -source_latency_included [m1 get cell $ip_erd_st_col $i] \[get_ports $inp_ports\]"
	puts -nonewline $sdc_file "\nset_input_delay -clock \[get_clocks [m1 get cell $ip_rc_st_col $i]\] -min -fall -source_latency_included [m1 get cell $ip_efd_st_col $i] \[get_ports $inp_ports\]"
	puts -nonewline $sdc_file "\nset_input_delay -clock \[get_clocks [m1 get cell $ip_rc_st_col $i]\] -max -rise -source_latency_included [m1 get cell $ip_lrd_st_col $i] \[get_ports $inp_ports\]"
	puts -nonewline $sdc_file "\nset_input_delay -clock \[get_clocks [m1 get cell $ip_rc_st_col $i]\] -max -fall -source_latency_included [m1 get cell $ip_lfd_st_col $i] \[get_ports $inp_ports\]"
	set i [expr {$i+1}]

}
```
</details>

<details>
	<summary>Scripting and yosys synthesis</summary>

 The following code will process the CSV file for output data and subsequently generate the output-based SDC instructions in the SDC file.
 ```ruby
# Finding column number starting for output clock latency in OUTPUTS section only
set op_erd_st_col [lindex [lindex [m1 search rect $clocks_start_column $outputs_start [expr {$n_columns_concsv-1}] [expr {$n_rows_concsv-1}] early_rise_delay] 0 ] 0 ]
set op_efd_st_col [lindex [lindex [m1 search rect $clocks_start_column $outputs_start [expr {$n_columns_concsv-1}] [expr {$n_rows_concsv-1}] early_fall_delay] 0 ] 0 ]
set op_lrd_st_col [lindex [lindex [m1 search rect $clocks_start_column $outputs_start [expr {$n_columns_concsv-1}] [expr {$n_rows_concsv-1}] late_rise_delay] 0 ] 0 ]
set op_lfd_st_col [lindex [lindex [m1 search rect $clocks_start_column $outputs_start [expr {$n_columns_concsv-1}] [expr {$n_rows_concsv-1}] late_fall_delay] 0 ] 0 ]

# Finding column number starting for output related clock in OUTPUTS section only
set op_rc_st_col [lindex [lindex [m1 search rect $clocks_start_column $outputs_start [expr {$n_columns_concsv-1}] [expr {$n_rows_concsv-1}] clocks] 0 ] 0 ]

# Finding column number starting for output load in OUTPUTS section only
set op_load_st_col [lindex [lindex [m1 search rect $clocks_start_column $outputs_start [expr {$n_columns_concsv-1}] [expr {$n_rows_concsv-1}] load] 0 ] 0 ]

# Setting variables for actual input row start and end
set i [expr {$outputs_start+1}]
set end_of_outputs [expr {$n_rows_concsv-1}]

puts "\nInfo-SDC: Working on output constraints.."
puts "\nInfo-SDC: Categorizing output ports as bits and busses"

# while loop to write constraint commands to .sdc file
while { $i < $end_of_outputs } {
	# Checking if input is bussed or not
	set netlist [glob -dir $Netlist_Directory *.v]
	set tmp_file [open /tmp/1 w]
	foreach f $netlist {
		set fd [open $f]
		while { [gets $fd line] != -1 } {
			set pattern1 " [m1 get cell 0 $i];"
			if { [regexp -all -- $pattern1 $line] } {
				set pattern2 [lindex [split $line ";"] 0]
				if { [regexp -all {output} [lindex [split $pattern2 "\S+"] 0]] } {
					set s1 "[lindex [split $pattern2 "\S+"] 0] [lindex [split $pattern2 "\S+"] 1] [lindex [split $pattern2 "\S+"] 2]"
					puts -nonewline $tmp_file "\n[regsub -all {\s+} $s1 " "]"
				}
			}
		}
	close $fd
	}
	close $tmp_file
	set tmp_file [open /tmp/1 r]
	set tmp2_file [open /tmp/2 w]
	puts -nonewline $tmp2_file "[join [lsort -unique [split [read $tmp_file] \n]] \n]"
	close $tmp_file
	close $tmp2_file
	set tmp2_file [open /tmp/2 r]
	set count [llength [read $tmp2_file]]
	close $tmp2_file
	if {$count > 2} {
		set op_ports [concat [m1 get cell 0 $i]*]
	} else {
		set op_ports [m1 get cell 0 $i]
	}

	# set_output_delay SDC command to set output latency values
	puts -nonewline $sdc_file "\nset_output_delay -clock \[get_clocks [m1 get cell $op_rc_st_col $i]\] -min -rise -source_latency_included [m1 get cell $op_erd_st_col $i] \[get_ports $op_ports\]"
	puts -nonewline $sdc_file "\nset_output_delay -clock \[get_clocks [m1 get cell $op_rc_st_col $i]\] -min -fall -source_latency_included [m1 get cell $op_efd_st_col $i] \[get_ports $op_ports\]"
	puts -nonewline $sdc_file "\nset_output_delay -clock \[get_clocks [m1 get cell $op_rc_st_col $i]\] -max -rise -source_latency_included [m1 get cell $op_lrd_st_col $i] \[get_ports $op_ports\]"
	puts -nonewline $sdc_file "\nset_output_delay -clock \[get_clocks [m1 get cell $op_rc_st_col $i]\] -max -fall -source_latency_included [m1 get cell $op_lfd_st_col $i] \[get_ports $op_ports\]"

	# set_load SDC command to set load values
	puts -nonewline $sdc_file "\nset_load [m1 get cell $op_load_st_col $i] \[get_ports $op_ports\]"

	set i [expr {$i+1}]
}
close $sdc_file
puts "\nInfo-SDC: SDC created. Please use constraints in path $Output_Directory/$Design_Name.sdc"
```

The subsequent code incorporates the implementation of error-handling for hierarchy checks:
```ruby
# Hierarchy Check
puts "\nInfo: Creating hierarchy check script to be used by Yosys"
set data "read_liberty -lib -ignore_miss_dir -setattr blackbox ${Late_Library_Path}"
set filename "$Design_Name.hier.ys"
set fileId [open $Output_Directory/$filename "w"]
puts -nonewline $fileId $data
set netlist [glob -dir $Netlist_Directory *.v]
foreach f $netlist {
	set data $f
	puts -nonewline $fileId "\nread_verilog $f"
	puts "\nInfo: Netlist being read for user debug: $f" 
}
puts -nonewline $fileId "\nhierarchy -check"
close $fileId
```

```ruby
# Hierarchy check error handling
# Hierarchy check error handling done to see any errors popping up in above script.
# Running hierarchy check in yosys by dumping log to log file and catching execution message
set error_flag [catch {exec yosys -s $Output_Directory/$Design_Name.hier.ys >& $Output_Directory/$Design_Name.hierarchy_check.log} msg]
puts "Errfor flag value for user debug: $error_flag"
if { $error_flag } {
	set filename "$Output_Directory/$Design_Name.hierarchy_check.log"
	# EDA tool specific hierarchy error search pattern
	set pattern {referenced in module}
	set count 0
	set fid [open $filename r]
	while { [gets $fid line] != -1 } {
		incr count [regexp -all -- $pattern $line]
		if { [regexp -all -- $pattern $line] } {
			puts "\nError: Module [lindex $line 2] is not part of design $Design_Name. Please correct RTL in the path '$Netlist_Directory'"
			puts "\nInfo: Hierarchy check FAIL"
		}
	}
	close $fid
	puts "\nInfo: Please find hierarchy check details in '[file normalize $Output_Directory/$Design_Name.hierarchy_check.log]' for more info. Exiting..."
	
} else {
	puts "\nInfo: Hierarchy check PASS"
	puts "\nInfo: Please find hierarchy check details in '[file normalize $Output_Directory/$Design_Name.hierarchy_check.log]' for more info"
}
```

Now, it's time to synthesize the memory module. The Verilog code for this process is as follows:

```ruby
verilog
module memory (CLK, ADDR, DIN, DOUT);

parameter wordSize = 1;
parameter addressSize = 1;

input ADDR, CLK;
input [wordSize-1:0] DIN;
output reg [wordSize-1:0] DOUT;
reg [wordSize:0] mem [0:(1<<addressSize)-1];

always @(posedge CLK) begin
	mem[ADDR] <= DIN;
	DOUT <= mem[ADDR];
	end

endmodule
```

Below is the fundamental Yosys script, memory.ys, which can be executed to obtain a gate-level netlist and a 2D representation of the memory module in gate components:

```ruby
# Reading the library
read_liberty -lib -ignore_miss_dir -setattr blackbox /home/vsduser/Desktop/work/openmsp430/openmsp430/osu018_stdcells.lib
# Reading the verilog
read_verilog verilog/memory.v
synth top memory
splitnets -ports -format ___
dfflibmap -liberty /home/vsduser/Desktop/work/openmsp430/openmsp430/osu018_stdcells.lib
opt
abc -liberty /home/vsduser/Desktop/work/openmsp430/openmsp430/osu018_stdcells.lib
flatten
clean -purge
opt
clean
# Writing the netlist
write_verilog memory_synth.v
# Representation of netlist with it's components
show
~
```
<img  width="1085" alt="3_3" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day_30/3_3.png"> <br><br>

The write process is as follws:

<img  width="1085" alt="4_4" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day_30/4_4.png"> <br><br>

<img  width="1085" alt="5_5" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day_30/5_5.png"> <br><br>

The following code is written for hierarchy check redumping as follows:
```ruby
puts "\nInfo: Creating hierarchy check script to be used by Yosys"
set data "read_liberty -lib -ignore_miss_dir -setattr blackbox ${Late_Library_Path}"
set filename "$Design_Name.hier.ys"
set fileId [open $Output_Directory/$filename "w"]
puts -nonewline $fileId $data
set netlist [glob -dir $Netlist_Directory *.v]
foreach f $netlist {
	set data $f
	puts -nonewline $fileId "\nread_verilog $f"
	puts "\nInfo: Netlist being read for user debug: $f" 
}

puts -nonewline $fileId "\nhierarchy -check"
close $fileId
```
```
</details>


<details>
	<summary>Advanced scripting and QoR generation</summary>

 The following code is written for checking any errors in the above script:

```ruby
# Main Synthesis Script for yosys
# ---------------------
puts "\nInfo: Creating main synthesis script to be used by Yosys"
set data "read_liberty -lib -ignore_miss_dir -setattr blackbox ${Late_Library_Path}"
set filename "$Design_Name.ys"
set fileId [open $Output_Directory/$filename "w"]
puts -nonewline $fileId $data
set netlist [glob -dir $Netlist_Directory *.v]
foreach f $netlist {
	puts -nonewline $fileId "\nread_verilog $f"
}
puts -nonewline $fileId "\nhierarchy -top $Design_Name"
puts -nonewline $fileId "\nsynth -top $Design_Name"
puts -nonewline $fileId "\nsplitnets -ports -format ___\ndfflibmap -liberty ${Late_Library_Path} \nopt"
puts -nonewline $fileId "\nabc -liberty ${Late_Library_Path}"
puts -nonewline $fileId "\nflatten"
puts -nonewline $fileId "\nclean -purge\niopadmap -outpad BUFX2 A:Y -bits\nopt\nclean"
puts -nonewline $fileId "\nwrite_verilog $Output_Directory/$Design_Name.synth.v"
close $fileId
puts "\nInfo: Synthesis script created and can be accessed from path $Output_Directory/$Design_Name.ys"
```

Procs can be used to create user-defined commands.Different procs used throught the training is given below:

1. reopenStdout.proc

```ruby
#!/bin/tclsh
#proc to redirect screen log to file
proc reopenStdout {file} {
    close stdout
    open $file w       
}
```

2. set_multi_cpu_usage.proc
```ruby
#!/bin/tclsh
proc set_multi_cpu_usage {args} {
        array set options {-localCpu <num_of_threads> -help "" }
        foreach {switch value} [array get options] {
        puts "Option $switch is $value"
        }
        while {[llength $args]} {
        puts "llength is [llength $args]"
        puts "lindex 0 of \"$args\" is [lindex $args 0]"
                switch -glob -- [lindex $args 0] {
                -localCpu {
                           puts "old args is $args"
                           set args [lassign $args - options(-localCpu)]
                           puts "new args is \"$args\""
                           puts "set_num_threads $options(-localCpu)"
                          }
                -help {
                           puts "old args is $args"
                           set args [lassign $args - options(-help) ]
                           puts "new args is \"$args\""
                           puts "Usage: set_multi_cpu_usage -localCpu <num_of_threads> -help"
                           puts "\t-localCpu - To limit number of threads used"
                           puts "\t-help - To print details of proc"
                      }
                }
        }
}
#set_multi_cpu_usage -localCpu 5 -help
```


3. read_lib
```ruby
#!/bin/tclsh
proc read_lib args {
	# Setting command parameter options and its values
	array set options {-late <late_lib_path> -early <early_lib_path> -help ""}
	while {[llength $args]} {
		switch -glob -- [lindex $args 0] {
		-late {
			set args [lassign $args - options(-late) ]
			puts "set_late_celllib_fpath $options(-late)"
		      }
		-early {
			set args [lassign $args - options(-early) ]
			puts "set_early_celllib_fpath $options(-early)"
		       }
		-help {
			set args [lassign $args - options(-help) ]
			puts "Usage: read_lib -late <late_lib_path> -early <early_lib_path>"
			puts "-late <provide late library path>"
			puts "-early <provide early library path>"
			puts "-help - Provides user deatails on how to use the command"
		      }	
		default break
		}
	}
}
```

4. read_verilog
```ruby
proc read_verilog {arg1} {
puts "set_verilog_fpath $arg1"
}
```

5.read_sdc
```ruby
set sdc_dirname [file dirname $arg1]
set sdc_filename [lindex [split [file tail $arg1] .] 0 ]
set sdc [open $arg1 r]
set tmp_file [open /tmp/1 w]
puts -nonewline $tmp_file [string map {"\[" "" "\]" " "} [read $sdc]]     
close $tmp_file
#-----------------------------------------------------------------------------#
#----------------converting create_clock constraints--------------------------#
#-----------------------------------------------------------------------------#
set tmp_file [open /tmp/1 r]
set timing_file [open /tmp/3 w]
set lines [split [read $tmp_file] "\n"]
set find_clocks [lsearch -all -inline $lines "create_clock*"]
foreach elem $find_clocks {
	set clock_port_name [lindex $elem [expr {[lsearch $elem "get_ports"]+1}]]
	set clock_period [lindex $elem [expr {[lsearch $elem "-period"]+1}]]
	set duty_cycle [expr {100 - [expr {[lindex [lindex $elem [expr {[lsearch $elem "-waveform"]+1}]] 1]*100/$clock_period}]}]
	puts $timing_file "clock $clock_port_name $clock_period $duty_cycle"
	}
close $tmp_file
#-----------------------------------------------------------------------------#
#----------------converting set_clock_latency constraints---------------------#
#-----------------------------------------------------------------------------#
set find_keyword [lsearch -all -inline $lines "set_clock_latency*"]
set tmp2_file [open /tmp/2 w]
set new_port_name ""
foreach elem $find_keyword {
        set port_name [lindex $elem [expr {[lsearch $elem "get_clocks"]+1}]]
	if {![string match $new_port_name $port_name]} {
        	set new_port_name $port_name
        	set delays_list [lsearch -all -inline $find_keyword [join [list "*" " " $port_name " " "*"] ""]]
        	set delay_value ""
        	foreach new_elem $delays_list {
        		set port_index [lsearch $new_elem "get_clocks"]
        		lappend delay_value [lindex $new_elem [expr {$port_index-1}]]
        	}
		puts -nonewline $tmp2_file "\nat $port_name $delay_value"
	}
}
close $tmp2_file
set tmp2_file [open /tmp/2 r]
puts -nonewline $timing_file [read $tmp2_file]
close $tmp2_file
#-----------------------------------------------------------------------------#
#----------------converting set_clock_transition constraints------------------#
#-----------------------------------------------------------------------------#
set find_keyword [lsearch -all -inline $lines "set_clock_transition*"]
set tmp2_file [open /tmp/2 w]
set new_port_name ""
foreach elem $find_keyword {
        set port_name [lindex $elem [expr {[lsearch $elem "get_clocks"]+1}]]
        if {![string match $new_port_name $port_name]} {
		set new_port_name $port_name
		set delays_list [lsearch -all -inline $find_keyword [join [list "*" " " $port_name " " "*"] ""]]
        	set delay_value ""
        	foreach new_elem $delays_list {
        		set port_index [lsearch $new_elem "get_clocks"]
        		lappend delay_value [lindex $new_elem [expr {$port_index-1}]]
        	}
        	puts -nonewline $tmp2_file "\nslew $port_name $delay_value"
	}
}
close $tmp2_file
set tmp2_file [open /tmp/2 r]
puts -nonewline $timing_file [read $tmp2_file]
close $tmp2_file
#-----------------------------------------------------------------------------#
#----------------converting set_input_delay constraints-----------------------#
#-----------------------------------------------------------------------------#
set find_keyword [lsearch -all -inline $lines "set_input_delay*"]
set tmp2_file [open /tmp/2 w]
set new_port_name ""
foreach elem $find_keyword {
        set port_name [lindex $elem [expr {[lsearch $elem "get_ports"]+1}]]
        if {![string match $new_port_name $port_name]} {
                set new_port_name $port_name
        	set delays_list [lsearch -all -inline $find_keyword [join [list "*" " " $port_name " " "*"] ""]]
		set delay_value ""
        	foreach new_elem $delays_list {
        		set port_index [lsearch $new_elem "get_ports"]
        		lappend delay_value [lindex $new_elem [expr {$port_index-1}]]
        	}
        	puts -nonewline $tmp2_file "\nat $port_name $delay_value"
	}
}
close $tmp2_file
set tmp2_file [open /tmp/2 r]
puts -nonewline $timing_file [read $tmp2_file]
close $tmp2_file
#-----------------------------------------------------------------------------#
#----------------converting set_input_transition constraints------------------#
#-----------------------------------------------------------------------------#
set find_keyword [lsearch -all -inline $lines "set_input_transition*"]
set tmp2_file [open /tmp/2 w]
set new_port_name ""
foreach elem $find_keyword {
        set port_name [lindex $elem [expr {[lsearch $elem "get_ports"]+1}]]
        if {![string match $new_port_name $port_name]} {
                set new_port_name $port_name
        	set delays_list [lsearch -all -inline $find_keyword [join [list "*" " " $port_name " " "*"] ""]]
        	set delay_value ""
        	foreach new_elem $delays_list {
        		set port_index [lsearch $new_elem "get_ports"]
        		lappend delay_value [lindex $new_elem [expr {$port_index-1}]]
        	}
        	puts -nonewline $tmp2_file "\nslew $port_name $delay_value"
	}
}
close $tmp2_file
set tmp2_file [open /tmp/2 r]
puts -nonewline $timing_file [read $tmp2_file]
close $tmp2_file
#-----------------------------------------------------------------------------#
#---------------converting set_output_delay constraints-----------------------#
#-----------------------------------------------------------------------------#
set find_keyword [lsearch -all -inline $lines "set_output_delay*"]
set tmp2_file [open /tmp/2 w]
set new_port_name ""
foreach elem $find_keyword {
        set port_name [lindex $elem [expr {[lsearch $elem "get_ports"]+1}]]
        if {![string match $new_port_name $port_name]} {
                set new_port_name $port_name
        	set delays_list [lsearch -all -inline $find_keyword [join [list "*" " " $port_name " " "*"] ""]]
        	set delay_value ""
        	foreach new_elem $delays_list {
        		set port_index [lsearch $new_elem "get_ports"]
        		lappend delay_value [lindex $new_elem [expr {$port_index-1}]]
        	}
        	puts -nonewline $tmp2_file "\nrat $port_name $delay_value"
	}
}

close $tmp2_file
set tmp2_file [open /tmp/2 r]
puts -nonewline $timing_file [read $tmp2_file]
close $tmp2_file
#-----------------------------------------------------------------------------#
#-------------------converting set_load constraints---------------------------#
#-----------------------------------------------------------------------------#
set find_keyword [lsearch -all -inline $lines "set_load*"]
set tmp2_file [open /tmp/2 w]
set new_port_name ""
foreach elem $find_keyword {
        set port_name [lindex $elem [expr {[lsearch $elem "get_ports"]+1}]]
        if {![string match $new_port_name $port_name]} {
                set new_port_name $port_name
        	set delays_list [lsearch -all -inline $find_keyword [join [list "*" " " $port_name " " "*" ] ""]]
        	set delay_value ""
        	foreach new_elem $delays_list {
        	set port_index [lsearch $new_elem "get_ports"]
        	lappend delay_value [lindex $new_elem [expr {$port_index-1}]]
        	}
        	puts -nonewline $timing_file "\nload $port_name $delay_value"
	}
}
close $tmp2_file
set tmp2_file [open /tmp/2 r]
puts -nonewline $timing_file  [read $tmp2_file]
close $tmp2_file
#-----------------------------------------------------------------------------#
close $timing_file
set ot_timing_file [open $sdc_dirname/$sdc_filename.timing w]
set timing_file [open /tmp/3 r]
while {[gets $timing_file line] != -1} {
        if {[regexp -all -- {\*} $line]} {
                set bussed [lindex [lindex [split $line "*"] 0] 1]
                set final_synth_netlist [open $sdc_dirname/$sdc_filename.final.synth.v r]
                while {[gets $final_synth_netlist line2] != -1 } {
                        if {[regexp -all -- $bussed $line2] && [regexp -all -- {input} $line2] && ![string match "" $line]} {
                        puts -nonewline $ot_timing_file "\n[lindex [lindex [split $line "*"] 0 ] 0 ] [lindex [lindex [split $line2 ";"] 0 ] 1 ] [lindex [split $line "*"] 1 ]"
                        } elseif {[regexp -all -- $bussed $line2] && [regexp -all -- {output} $line2] && ![string match "" $line]} {
                        puts -nonewline $ot_timing_file "\n[lindex [lindex [split $line "*"] 0 ] 0 ] [lindex [lindex [split $line2 ";"] 0 ] 1 ] [lindex [split $line "*"] 1 ]"
                        }
                }
        } else {
        puts -nonewline $ot_timing_file  "\n$line"
        }
}
close $timing_file
puts "set_timing_fpath $sdc_dirname/$sdc_filename.timing"
}
```

These procs are used to create timing configuration files required for the OpenTimer tool:
```ruby
puts "\nInfo: Timing Analysis Started...."
puts "\nInfo: Initializing number of threads, libraries, sdc, verilog netlist path..."
puts " Invoking required procs"
puts "reopenStdout.proc \nset_multi_cpu_usage,proc \nread_lib.proc \nread_verilog.proc \nread_sdc.prc"
source /home/vsduser/vsdsynth/procs/reopenStdout.proc
source /home/vsduser/vsdsynth/procs/set_multi_cpu_usage.proc
source /home/vsduser/vsdsynth/procs/read_lib.proc
source /home/vsduser/vsdsynth/procs/read_verilog.proc
source /home/vsduser/vsdsynth/procs/read_sdc.proc
reopenStdout $Output_Directory/$Design_Name.conf
read_lib -early $Early_Library_Path
read_lib -late $Late_Library_Path
read_verilog $Output_Directory/$Design_Name.final.synth.v
read_sdc $Output_Directory/$Design_Name.sdc
```

**Preparation of .CONF and SPEF file for OpenTimer STA:**

Procs are used to generate the .conf and .SPEF file required for the OpenTimer tool for timing analysis.
```ruby
set enable_prelayout_timing 1
if {$enable_prelayout_timing == 1} {
	puts "\nInfo: enable_prelayout_timing is $enable_prelayout_timing. Enabling zero-wire load parasitics"
	set spef_file [open $Output_Directory/$Design_Name.spef w]
	puts $spef_file "*SPEF \"IEEE 1481-1998\" "
	puts $spef_file "*DESIGN \"$Design_Name\" "
	puts $spef_file "*DATE \"[clock format [clock seconds] -format {%a %b %d %I:%M:%S %Y}]\" "
	puts $spef_file "*VENDOR \"TAU 2015 Contest\" "
	puts $spef_file "*PROGRAM \"Benchmark Parasitic Generator\" "
	puts $spef_file "*VERSION \"0.0\" "
	puts $spef_file "*DESIGN_FLOW \"NETLIST_TYPE_VERILOG\" "
	puts $spef_file "*DIVIDER / "
	puts $spef_file "*DELIMITER : "
	puts $spef_file "*BUS_DELIMITER \[ \] "
	puts $spef_file "*T_UNIT 1 PS "
	puts $spef_file "*C_UNIT 1 FF "
	puts $spef_file "*R_UNIT 1 KOHM "
	puts $spef_file "*L_UNIT 1 UH "
	close $spef_file
}
# Appending to .conf file
set conf_file [open $Output_Directory/$Design_Name.conf a]
puts $conf_file "set_spef_fpath $Output_Directory/$Design_Name.spef"
puts $conf_file "init_timer "
puts $conf_file "report_timer "
puts $conf_file "report_wns "
puts $conf_file "report_worst_paths -numPaths 10000 "
close $conf_file
```

Running STA and generating the QOR:
```ruby
set tcl_precision 3
set time_elapsed_in_us [time {exec /home/vsduser/OpenTimer-1.0.5/bin/OpenTimer < $Output_Directory/$Design_Name.conf >& $Output_Directory/$Design_Name.results}]
set time_elapsed_in_sec "[expr {[lindex $time_elapsed_in_us 0]/1000000}]sec"
puts "\nInfo: STA finished in $time_elapsed_in_sec seconds"
puts "\nInfo: Refer to $Output_Directory/$Design_Name.results for warnings and errors"
```

Data extraction from .results file for QOR:
```ruby
# Find worst output violation
set worst_RAT_slack "-"
set report_file [open $Output_Directory/$Design_Name.results r]
set pattern {RAT}
while { [gets $report_file line] != -1 } {
	if {[regexp $pattern $line]} {
		set worst_RAT_slack "[expr {[lindex $line 3]/1000}]ns"
		break
	} else {
		continue
	}
}
close $report_file
# Find number of output violation
set report_file [open $Output_Directory/$Design_Name.results r]
set count 0
while { [gets $report_file line] != -1 } {
	incr count [regexp -all -- $pattern $line]
}
set Number_output_violations $count
close $report_file
# Find worst setup violation
set worst_negative_setup_slack "-"
set report_file [open $Output_Directory/$Design_Name.results r]
set pattern {Setup}
while { [gets $report_file line] != -1 } {
	if {[regexp $pattern $line]} {
		set worst_negative_setup_slack "[expr {[lindex $line 3]/1000}]ns"
		break
	} else {
		continue
	}
}
close $report_file
# Find number of setup violation
set report_file [open $Output_Directory/$Design_Name.results r]
set count 0
while { [gets $report_file line] != -1 } {
	incr count [regexp -all -- $pattern $line]
}
set Number_of_setup_violations $count
close $report_file
# Find worst hold violation
set worst_negative_hold_slack "-"
set report_file [open $Output_Directory/$Design_Name.results r]
set pattern {Hold}
while { [gets $report_file line] != -1 } {
	if {[regexp $pattern $line]} {
		set worst_negative_hold_slack "[expr {[lindex $line 3]/1000}]ns"
		break
	} else {
		continue
	}
}
close $report_file
# Find number of hold violation
set report_file [open $Output_Directory/$Design_Name.results r]
set count 0
while {[gets $report_file line] != -1} {
	incr count [regexp -all -- $pattern $line]
}
set Number_of_hold_violations $count
close $report_file
# Find number of instance
set pattern {Num of gates}
set report_file [open $Output_Directory/$Design_Name.results r]
while {[gets $report_file line] != -1} {
	if {[regexp -all -- $pattern $line]} {
		set Instance_count [lindex [join $line " "] 4 ]
		break
	} else {
		continue
	}
}
close $report_file
# Capturing end time of the script
set end_time [clock clicks -microseconds]
# Setting total script runtime to 'time_elapsed_in_sec' variable
set time_elapsed_in_sec "[expr {($end_time-$start_time)/1000000}]sec"
puts "\nInfo: Design Name = $Design_Name"
puts "\nInfo: Worst RAT slack = $worst_RAT_slack"
puts "\nInfo: Number of output violations = $Number_output_violations"
puts "\nInfo: Worst negative setup slack = $worst_negative_setup_slack"
puts "\nInfo: Number of setup violation = $Number_of_setup_violations"
puts "\nInfo: Worst Negative Hold Slack = $worst_negative_hold_slack"
puts "\nInfo: Number of Hold Violations = $Number_of_hold_violations"
puts "\nInfo: Number of Instances = $Instance_count"
puts "\nInfo: Time elapsed = $time_elapsed_in_sec"
```

Final QOR Report generation:
```ruby
puts "\n"
puts "                                                           ****PRELAYOUT TIMING RESULTS_TCLBOX****\n"
set formatStr {%15s%14s%21s%16s%16s%15s%15s%15s%15s}
puts [format $formatStr "-----------" "-------" "--------------" "---------" "---------" "--------" "--------" "-------" "-------"]
puts [format $formatStr "Design Name" "Runtime" "Instance Count" "WNS Setup" "FEP Setup" "WNS Hold" "FEP Hold" "WNS RAT" "FEP RAT"]
puts [format $formatStr "-----------" "-------" "--------------" "---------" "---------" "--------" "--------" "-------" "-------"]
foreach design_name $Design_Name runtime $time_elapsed_in_sec instance_count $Instance_count wns_setup $worst_negative_setup_slack fep_setup $Number_of_setup_violations wns_hold $worst_negative_hold_slack fep_hold $Number_of_hold_violations wns_rat $worst_RAT_slack fep_rat $Number_output_violations {
	puts [format $formatStr $design_name $runtime $instance_count $wns_setup $fep_setup $wns_hold $fep_hold $wns_rat $fep_rat]
}
puts [format $formatStr "-----------" "-------" "--------------" "---------" "---------" "--------" "--------" "-------" "-------"]
puts "\n"
```


</details>
