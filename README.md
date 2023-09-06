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
	 
 </ul>

**Common Terminologies Associated with DC:**
	1. SDC (Synopsys Design Constraints)-
   	<ul>
	   	<li>These are the design constraints which are supplied to DC to enable appropriate optimization suitable for achieving the best implementation.</li>
	   	<li>It is more like industrial standard and it is used across EDA (Electronic Design Automation) implementation tools.</li>
	   	<li>SDC is based on TCL.</li>
   	</ul>
	2. .lib-
   	Design library which contains the standard cells.

	3. .db-
   	Same as .lib but in a different format. DC understands libraries in .db format.

	4. DDC(Design Data Center)-
   	Synopsys proprietary format for storing the design information. DC can write out and read in DDC.

	5. Design-
   	RTL files which has the behavioral model of the design.


 **DC Setup:**
 <img  width="1085" alt="" src=""><br><br>
A DC (Design Compiler) setup involves using Synopsys Design Compiler, a popular tool in the digital design and synthesis flow, to convert RTL (Register-Transfer Level) descriptions of a digital circuit into a gate-level netlist. This process includes specifying library files and SDC (Synopsys Design Constraints) constraints as inputs and obtaining outputs such as a Verilog netlist, DDC (Design Data Container), and synthesis reports.
The DC setup process typically involves the following steps:
<ul>
	<li>RTL Compilation: The RTL files are read and compiled by the DC tool, which performs logic synthesis to map the design to the target technology using the library files.</li>
	<li>Constraint Application: The SDC constraints are applied to guide the synthesis tool in optimizing the design for timing, power, and area.</li>
	<li>Synthesis: The synthesis tool generates the Verilog netlist and optimization reports based on the provided RTL, library, and constraint files.</li>
	<li>Output Generation: The Verilog netlist, DDC, and synthesis reports are the final outputs of the synthesis process and can be used for further stages in the design flow, such as place-and-route and verification.</li>
</ul>

 **Implementation flow of ASIC:**
 <img  width="1085" alt="" src=""><br><br>
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


 **DC Synthesis Flow:**
 <img  width="1085" alt="" src=""><br><br>
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
	<li>>Write Out Netlist:
		The final step involves writing out the gate-level netlist in a format that can be used for subsequent stages of the design flow, such as place-and-route or simulation. Common formats for the output netlist include Verilog or EDIF (Electronic Design Interchange Format).</li>
</ul>
Throughout the synthesis flow, design engineers may iterate and fine-tune the constraints and optimization settings to achieve the desired results.
    
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



-  foreach is a general tcl statement.
```ruby
  foreach var list {
  statements
  }
```
	  

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
