# SAMSUNG-PD-TRAINING-
This github repository summarizes the progress made in the training duration.

Quick links:
- [Day-0-Installation](#day-0-Installation)

- [Day-1-Introduction to Verilog RTL design and Synthesis](#Day-1--Introduction-to-Verilog-RTL-design-and-Synthesis)


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
icc2_shell (Integrated Circuit Compiler 2 Shell) is a command-line-based EDA tool primarily used for the physical design stages of integrated circuits, which includes tasks like placement, routing, and physical verification; provided by Synopsys, Inc.
It is typically used through scripts written in languages like TCL (Tool Command Language). Designers create scripts to specify the physical design flow, provide input files, and set various design constraints. The tool then executes these scripts to perform the physical design tasks.  
The tool can be invoked by using the command "icc2_shell" in a UNIX shell.

Here is the snapshot of successful launch of icc2_shell:    
<img width="1085" alt="icc2_shell" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day0/icc2_shell.png">
</details>

<details>
<summary>lc_shell</summary>
lc_shell (Library Compiler Shell) is a command-line based EDA tool provided by Synopsys, Inc.
The core of any ASIC design is the technology library containing a set oflogic cells. The library may contain functional description, timing, area andother pertinent information of each cell. Library Compiler (LC) parses thistextual information for completeness and correctness, before converting it toa format, used globally by all Synopsys applications.
The tool can be invoked by using the command "lc_shell" in a UNIX shell.

Here is the snapshot of successful launch of lc_shell:   
<img width="1085" alt="lc_shell" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day0/lc_shell.png">
</details>

<details>
<summary>pt_shell</summary>
pt_shell (Prime Time Shell) is a command-line based EDA tool provided by Synopsys, Inc.
It is primarily used for static timing analysis. 
It verifies the timing of a design by considering factors such as gate delays, interconnect delays, clock constraints, and setup/hold times and also calculates the best-case and worst-case timing paths in the design to ensure that all signals meet their timing requirements under various conditions.
The tool can be invoked by using the command "pt_shell" in a UNIX shell.

Here is the snapshot of successful launch of pt_shell:  
<img width="1085" alt="pt_shell" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day0/pt_shell.png">
</details>

<details>
<summary>iverilog</summary>
iverilog (Icarus verilog) is an open-source Verilog simulation and synthesis tool used for the development of digital circuits and systems. 
One of the primary purposes of Icarus Verilog is to simulate digital designs. Designers can write Verilog code to describe the behavior of digital circuits, and Icarus Verilog can simulate the operation of these circuits over time, helping to verify their functionality.
The tool can be invoked by using the command "iverilog [options] [input_files]" in a UNIX shell.

Here is the snapshot of successful launch of iverilog:
<img width="1085" alt="iverilog" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day0/iverilog.png">
</details>

<details>
<summary>gtkwave</summary>
gtkwave is an open-source waveform viewer tool used primarily for analyzing and displaying simulation results from digital circuit simulations. It is a popular choice for visualizing and debugging digital designs described in hardware description languages (HDLs) such as Verilog or VHDL.
It is primarily used as a waveform viewer. It allows you to load and display simulation waveforms, which represent signals' behavior over time during a digital simulation.
The tool can be invoked by using the command "gtkwave" in a UNIX shell.

Here is the snapshot of successful launch of gtkwave:
<img width="1085" alt="gtkwave" src="https://github.com/18vishaka/SAMSUNG-PD-TRAINING-/blob/master/practice_1%23day0/gtkwave.png">
</details>

<details>
<summary>yosys</summary>
yosys is an open-source framework for RTL (Register-Transfer Level) synthesis and formal verification of digital circuits. RTL synthesis is a crucial step in the design flow of digital integrated circuits, where high-level descriptions of a circuit (usually written in a hardware description language like Verilog or VHDL) are converted into gate-level representations that can be used for physical design and manufacturing. It provides a suite of tools and algorithms to perform this transformation efficiently.
The tool can be invoked by using the command "yosys" in a UNIX shell.

Here is the snapshot of successful launch of yosys:
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

 
**Testbench**: It is a program written in any language for the purposes of exercising and verifying the functional correctness of the hardware model as coded. We write this testbench in Verilog. Using this testbench we apply a stimulus to the RTL Design and verify its functionality by checking the output.

**Simulator**: RTL design is checked for adherence to its design specification using simulation by giving simple inputs. The tool used for this purpose is called Simulator. The simulator looks at the input changes and then evaluates the output. It produces an output in the form of a .vcd file.  

</details>	

 
