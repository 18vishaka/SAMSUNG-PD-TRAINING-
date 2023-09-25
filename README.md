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
	<summary>Post-Synthesis of 8:1 Multiplexer</summary>

 **Gate level Simulation:** <br>

 The 8:1 multiplexer output discussed in the pre-synthesis simulation matches the post-synthesis simulation output. 
 The following are the sequence of steps for simulating the output:
 
 ```ruby
iverilog <netlist_file_name> <testbench>
./a.out
gtkwave <vcd_file_name>
```

The 'iverilog' command utilizes the simulated gate-level netlist and the same testbench for post-synthesis simulation. Running './a.out' generates a VCD format file corresponding to the netlist, which can be viewed using 'gtkwave'.
The post-simulaation output is as follows:
<img  width="1085" alt="lab13_14" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day13/lab13_14.png"><br>
Thus the exact match between the post-synthesis and pre-synthesis outputs verifies the logical correctness of the design.


**Synthesis of 8:1 Multiplexer using DC shell:**
The following are the sequence of steps:
```ruby
set target_library <path_of_the_target_library>
set linl_library {* <path_of_the_target_library>}
read_verilog <file_name.v>
link
compile_ultra
```
The schematic of 8:1 Multiplexer in design vision:
<img  width="1085" alt="lab13_22" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/day13/lab13_22.png"><br>


</details>
