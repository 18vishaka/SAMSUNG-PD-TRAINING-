# SAMSUNG-PD-TRAINING-
This github repository summarizes the progress made throughout the training duration.

Quick links:
- [Day-0-Installation](#day-0-Installation)

- [Day-1-Introduction to Verilog RTL design and Synthesis](#Day-1--Introduction-to-Verilog-RTL-design-and-Synthesis)

- [Day-2-Timing libs, Hierarchical vs flat synthesis and efficient flop coding styles](#Day-2--Timing-libs,-Hierarchical-vs-flat-synthesis-and-efficient-flop-coding-styles)


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
/* Generated by Yosys 0.9+4081 (git sha1 862e84eb, gcc 7.5.0-3ubuntu1~18.04 -fPIC -Os) */

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

</details>	
