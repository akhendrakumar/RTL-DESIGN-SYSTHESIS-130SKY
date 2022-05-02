# RTL-DESIGN-SYSTHESIS-130SKY
This repository is created as part of workshop 
![image](https://user-images.githubusercontent.com/104430712/166086350-d8b6664b-1ef5-4044-b15b-30789923e87a.png)
Project Scope
This repository provides in detail steps of 5-day workshop organized by VLSI System Design on  RTL Design in Verilog using the SKY130 Technology during 27/04/2022 to 1/04/2022
SKY130 is a 130nm Process development kit (PDK) released by Sky Water Technology Foundry in collaboration with Google for the ASIC Intellectual properties for more details here.
The main objective of this workshop is cover the various aspects of design in Verilog HDL both theoretically and practically with labs using open-source software's through their VSD-IAT portal. 
![image](https://user-images.githubusercontent.com/104430712/166086823-513c3c90-2f56-464e-a82d-e6d8c5c90229.png)
![image](https://user-images.githubusercontent.com/104430712/166086827-2d099777-c7ba-4ac6-93c4-3fc65dc73a5d.png)

 ASIC Design Flow - An Overview
In this post, ASIC (Application Specific Integrated Circuit) Design flow has been explained. The very first step of ASIC flow is design specification, which comes from the customer end.
The complete ASIC design process can be divided into two parts.

1.	Front End Design
2.	Back End Design
3.	
Front End Design:
Front end design process starts with the specification received from the customer end. RTL (Register Transfer Level) design engineer converts the specification into an RTL code using the HDL (Hardware Description Language). Once the RTL code is written, RTL designer simulates the code in RTL Simulator and check the functionality of the design.
Back End Design:

RTL code received from the front end engineer is technology independent, now the next step is Logic synthesis. 

Logic Synthesis:  In this process RTL code is converter into an optimized gate-level representation of a given standard cell library and certain design constraints. Now the code is in the form of a gate-level netlist of a particular standard cell library.

Place and Route (PnR):  The goal of PnR stage is to place all the standard cells, Macros and I/O pads with minimal area, with minimal delay and Route them together in such a way that there is no DRC (Design Rule Check) error. 

Signoff: If there are some timing violations in the post route design, we have a further stage called ECO (Engineering Change Order) where we can fix the timing violations. 


In this repository, I only concentrate on synthesis part using open source tool called Yosys using sky130nmPDK. 
Lab access: As part of this workshop VPN based lab access is provided. 

 Day-1 Verilog RTL Simulation Synthesis and Design
RTL Simulation

Verilog simulator is required to verify the correctness of the design, iverilog is one of the open source tool available to verify the given design

![image](https://user-images.githubusercontent.com/104430712/166182026-46e2d74b-dab6-4ffd-bf85-e8d69c2996dd.png)
Lab for Setting up the Lab
Here I will be covering how we are going to setup our lab server to simulate, view and synthesis the given specification of a design.
Initially we will be creating a VLSI directory using mkdir VLSI and then we cd into the directory using cd VLSI as shown below
![image](https://user-images.githubusercontent.com/104430712/166182049-d3ec2ac6-2849-4a3c-a4d5-b154cf4eb853.png)
VSDFLOW repository can be cloned by git clone
![image](https://user-images.githubusercontent.com/104430712/166182060-be765957-da8c-46c1-9704-51e25cc3c8c7.png)

![image](https://user-images.githubusercontent.com/104430712/166182092-1a8f8c8d-8cf4-425f-88bc-3ef4828331a3.png)
![image](https://user-images.githubusercontent.com/104430712/166182098-c20488cb-63e1-4adc-b26e-60c352f46afd.png)
![image](https://user-images.githubusercontent.com/104430712/166182105-e7a3f1ba-c81d-4b60-b8eb-d9b91cac7e5e.png)
![image](https://user-images.githubusercontent.com/104430712/166182112-01872e6d-13f9-4702-8e83-870b836efa1b.png)
![image](https://user-images.githubusercontent.com/104430712/166182121-a4900e7d-c9dd-4259-af0a-06e9b70bec11.png)
![image](https://user-images.githubusercontent.com/104430712/166182128-9d51f084-adab-4d58-9b3f-4a5a12ef2356.png)
![image](https://user-images.githubusercontent.com/104430712/166182139-cdb2deeb-e869-4d28-807a-b7780bf45646.png)
![image](https://user-images.githubusercontent.com/104430712/166182143-1d4d20c1-c6f0-4f5b-a98a-c1d91d24d4a6.png)
![image](https://user-images.githubusercontent.com/104430712/166182154-ba0b109f-f187-47f0-9e34-79bfaf4414ab.png)
![image](https://user-images.githubusercontent.com/104430712/166182164-05c1d394-226f-4f67-8d45-4c62bf60e682.png)
Note: The testbench and the design code can be passed using iverilog command in any order. In the above example we can give iverilog good_mux.v tb_good_mux.v 
Synthesis using YOSYS open-source tool
After simulation of the RTL design with the respective test bench, The Next step is to generate the synthesis file and that can be performed using synthesizer. In this Yosys considered as a Synthesizer. A Synthesizer is a tool used to convert the RTL Design into a netlist file (Standard Cell Format). The basic input files to YOSYS include the RTL Design file and .lib (library) files.
	lib files are a collection of logical modules which include logic gates like AND, OR, NOT, NAND, NOR etc. Each logic gate is stored in one or more flavours depending on the number of inputs and speed of the circuit (slow, fast & medium).
![image](https://user-images.githubusercontent.com/104430712/166182186-7f39a4e9-5046-4c05-90f3-48d720850ed9.png)
Coding scripts for Synthesis using YOSYS

![image](https://user-images.githubusercontent.com/104430712/166182233-11ce25cd-1b53-4617-a8d9-c13a58775857.png)
![image](https://user-images.githubusercontent.com/104430712/166182239-f7998ad2-a91f-4d40-a34a-7e416d58b5aa.png)
![image](https://user-images.githubusercontent.com/104430712/166182243-b95fc922-682d-42ee-81e1-c7c2207d9793.png)
![image](https://user-images.githubusercontent.com/104430712/166182248-339ba50b-b1b9-43e5-9bec-bc97b7ad097b.png)
![image](https://user-images.githubusercontent.com/104430712/166182253-127ca821-eec2-4cdb-88fe-6487a8e3c5a8.png)
![image](https://user-images.githubusercontent.com/104430712/166182258-53384baa-33bd-4671-9dfc-bfe84f9940ae.png)
![image](https://user-images.githubusercontent.com/104430712/166182266-9347f8bb-197e-4077-8fac-7d8e6a5f3f83.png)
![image](https://user-images.githubusercontent.com/104430712/166182273-c81d6039-d79e-4947-b387-9d81ddc1c9cc.png)
![image](https://user-images.githubusercontent.com/104430712/166182280-3f181ca5-fc8b-49f0-8a26-9df6c05c5eab.png)
![image](https://user-images.githubusercontent.com/104430712/166182287-b6a6806c-4d9f-4002-b5aa-bf0902168dd5.png)

Day 2 - Timing libs, Hierarchical   vs  Flat Synthesis & Efficient Flip Flop coding styles
The .lib file
The .lib file is a collection of standard cells with different Process corners. In this workshop, the sky130_fd_sc_hd_tt_025C_1v80.lib is considered for synthesis purpose. From the name .lib we can identify the following parameters.

                             S.No	            parameter	       Abbreviation
                               1	               fd	               Foundry 
                               2	              130nm 	        Effective Transistor length
                               3	                tt	               typical
                               4	                25oC	             Temperature
                               5	               hd	               High Density
                               6	               sd	                Standard cell
                               7	             tt_025C_1v80	       PVT variations

Lab Access explanation
Open the .lib file using g
vim command


![image](https://user-images.githubusercontent.com/104430712/166254676-10af81f1-a022-43c6-8be7-d2f128aad73b.png)
![image](https://user-images.githubusercontent.com/104430712/166254685-8556c2c5-39ec-4fd4-bbb4-c1eb80b0eff3.png)
![image](https://user-images.githubusercontent.com/104430712/166254707-9976d439-eda2-4304-800d-5765fd022a34.png)


Based on the above images, it can be inferred that even though the behavioural logic are same, they differ in their internal parameters like leakage power and area
Hierarchical vs Flat Synthesis
Consider am example code multiple_modules which instantiates an AND & and OR gate logic in separate sub-modules sub_module1 & sub_module2 respectively. The Verilog code for the same is displayed below by invoking the following 
>>>>>   gvim multiple_modules.v
![image](https://user-images.githubusercontent.com/104430712/166254791-e89a4d95-1292-46ad-8ac3-5bc6ee680f2f.png)
![image](https://user-images.githubusercontent.com/104430712/166254819-09278743-0e4d-46f3-af8b-5f3eab2ba83e.png)

Hierarchical Analysis 
Invoke yosys
![image](https://user-images.githubusercontent.com/104430712/166254865-6d8895bf-49f8-48a2-8782-6e4b45498abd.png)
![image](https://user-images.githubusercontent.com/104430712/166254882-d1a3f079-c390-4016-89a3-7cfa5b5bc8ff.png)
![image](https://user-images.githubusercontent.com/104430712/166254900-35be16dc-7d7d-4f9b-bb65-169444ed1b31.png)
![image](https://user-images.githubusercontent.com/104430712/166254926-b920d845-0045-4e40-9b46-9705e35d3618.png)
![image](https://user-images.githubusercontent.com/104430712/166254981-469c5783-2ed5-4f3b-b9a2-e70de3f94b17.png)
![image](https://user-images.githubusercontent.com/104430712/166254996-b56e091b-d983-4a32-a006-d72cecb2985b.png)
![image](https://user-images.githubusercontent.com/104430712/166255025-886aa611-72db-4360-9476-980adf8373b4.png)
![image](https://user-images.githubusercontent.com/104430712/166255042-d5254b3e-0567-4a35-8ff0-9cb2c4ba7fe1.png)
![image](https://user-images.githubusercontent.com/104430712/166255066-f67ce9ee-af9c-4871-86ea-3d4abfb3c97b.png)

The figure shows the  netlist comprising of sub_module1 & sub_module2 instead of the logic gates AND & OR based netlist. This is because, the multiple_modules RTL design even though is implementing two logic gates based circuit, the gates are actually instances inside two separate sub_modules that are instantiated to obtain the specific logic. This type of sub_module level synthesis is known as Hierarchical Synthesis as the sub_modules are preserved in its hierarchy.
Now, we can write out the netlist of the hierarchical netlist file and look at the behavioral implementation of the same.

![image](https://user-images.githubusercontent.com/104430712/166255116-a2e6a27e-3e7d-4227-8dda-1a023c90b787.png)
>>>>>>>Flatting


![image](https://user-images.githubusercontent.com/104430712/166255165-06306053-58e0-4664-8e39-24935715ea0e.png)
This command will implement the synthesis procedure without preserving the sub_module hierarchy and we obtain a netlist file of the multiple_modules RTL design implemented using the AND & OR gates
The flattened netlist and verilog module of the netlist file are obtained and listed as follows:
![image](https://user-images.githubusercontent.com/104430712/166255232-99c8e123-7eb5-4dbb-9135-30a1611b0a90.png)
![image](https://user-images.githubusercontent.com/104430712/166255263-b8929abb-8011-4778-a35a-6a67e0cba180.png)
![image](https://user-images.githubusercontent.com/104430712/166255288-f725b26d-03c4-41f0-a36d-363b2ccbe6ab.png)
![image](https://user-images.githubusercontent.com/104430712/166255312-d909b622-20ba-4d71-a288-60f8ae9ff3a6.png)


Efficient Flip-flop coding styles and Optimizations
Flipflops are devices which store a single bit (binary digit) of data in two states '1' or '0'. One common application of these flipflops is in large combinational circuits to avoid glitch errors due to propagation delays between logic gates which cause instability in output. The most common types of flip-flops are D-Flipflop, SR-Flipflop, JK Flipflop, T-Flipflop. There are various different methods of implementing these flipflops like synchronous reset and synchronous set or asynchronous reset and set etc. Listed below are different implementation / coding style of D-flipflop with async-reset or sync-reset or async set etc.

![image](https://user-images.githubusercontent.com/104430712/166255403-1b7e0319-92b1-4600-b81d-cd27bd010ab5.png)
![image](https://user-images.githubusercontent.com/104430712/166255417-39804c98-870f-49d7-acfc-3199b436f8f9.png)


Further, the design files can be synthesized in YOSYS as we have done in the previous sessions. The one new command we use here is the dfflibmap command, that is used when we deploy D-FlipFlops in the RTL design. The dfflibmap command links or maps the library files that contain the details of D-Flipflops to be used for synthesis. The coding snippet for synthesizing a D-Flipflop in YOSYS is given below:


![image](https://user-images.githubusercontent.com/104430712/166255461-09505bf4-5b0c-441b-908a-786575274e45.png)
![image](https://user-images.githubusercontent.com/104430712/166255473-95113766-0e54-4cd9-ad04-c62a74166539.png)
![image](https://user-images.githubusercontent.com/104430712/166255496-d91ad129-60ed-48bc-9c74-11c3b3844f4e.png)
![image](https://user-images.githubusercontent.com/104430712/166255523-1984738c-79a2-49cc-9864-6f9f02b96766.png)
![image](https://user-images.githubusercontent.com/104430712/166255539-d69225ed-b08f-47cc-81d4-caa7e48adc7c.png)

In the above netlist, it can be seen that the asynchronous reset D-Flipflop is implemented as a D-Flipflop with Active Low reset. This Active low reset is fed with an inverter to convert it into an Active High reset as an input to reset port of the flop. Similarly, using the above snippet, synthesis can be done for other D-Flipflop models in the verilog_models folder and netlist can be obtained for your study.
 
 day-3 : Combinational and Sequential Optimizations
Intro to Combinational Logic Optimizations
•	Primarily to squeeze the logic to get the most optimized design
o	An optimized design results in comprehensive Area and Power saving
Types of Combinational Optimizations
•	Constant Propagation
o	Direct Optimization Technique
•	Boolean Logic Optimization
o	K-Map based
o	Quine Mckluskey Algorithms
CONSTANT PROPAGATION
In Constant propagation techniques, inputs that are no way related or affecting the changes in the output are ignored/optimized to simplify the combination logic thereby saving area and power usage by those input pins.

BOOLEAN LOGIC OPTIMIZATION
Boolean logic optimization is nothing simplifying a complex boolean expression into a simplified expression by utilizing the laws of boolean logic algebra.

 ![image](https://user-images.githubusercontent.com/104430712/166256012-d3275027-1baf-4f87-9659-a490a22e4089.png)

Thus, the complex ternary operator based equation is simplified into a simple xor gate with two inputs a and c
The following pictures depict the various versions of combination logic expressions simplified using Combinational logic optimization techniques.

![image](https://user-images.githubusercontent.com/104430712/166256075-ea02ec83-6ebc-4efa-b634-b6fc7572d924.png)

 ![image](https://user-images.githubusercontent.com/104430712/166256190-17a7ff72-22a9-4f2e-a94b-0545c6563397.png)

 ![image](https://user-images.githubusercontent.com/104430712/166256212-2352637a-2bf8-47a3-96d2-f7526347f842.png)
 
![image](https://user-images.githubusercontent.com/104430712/166256236-4caedb58-f93a-4c7b-a526-397dc6141d24.png)

![image](https://user-images.githubusercontent.com/104430712/166256261-4fd9e5f7-140f-4e29-8ce7-ed3bdfdb356e.png)

![image](https://user-images.githubusercontent.com/104430712/166256345-de750dfd-b985-492a-a42e-1307a5764618.png)

![image](https://user-images.githubusercontent.com/104430712/166256384-0bebcecf-31f3-4563-8573-5559a1cfd315.png)

In the above snippet, we see a new code opt_clean -purge which is used to optimize the design by removing un-used net and components in the design after the design top level is synthesized using synt -top

The above images depict various optimizations done on the expressions being simplified by boolean logic optimization.
Similarly, incase we use multiple modules in a single code, we use flatten command as used in Flat Synthesis to perform the logic optimization of multiple modules after they are reduced to simple modules using flatten.
Some examples implemented are listed below:

![image](https://user-images.githubusercontent.com/104430712/166256445-29f7602e-30ce-4854-9621-0d73fa99dd8c.png)
![image](https://user-images.githubusercontent.com/104430712/166256482-2e78540a-5db5-448c-8ff2-3e8ac45dd5c1.png)
![image](https://user-images.githubusercontent.com/104430712/166256510-a7021a28-d04b-4c82-9b5e-4b574645c7b7.png)

![image](https://user-images.githubusercontent.com/104430712/166256529-ff012ae0-6fad-4f6f-a2ab-5f811d00a542.png)

![image](https://user-images.githubusercontent.com/104430712/166256580-840a2833-7539-4d1c-b322-d933460f1862.png)

Day 4 - Gate Level Simulation(GLS), Blocking vs Non-blocking and Synthesis-Simulation Mismatch
What is Gate Level Simulation (GLS) ?
Running the testbench against the synthesized netlist ouput as a DUT is known as Gate Level Simulation (GLS). The Output netlist should logically be same as the RTL code so that the testbench will align itself when we simulate both the files to obtain the waveforms.
Why GLS?
GLS is required to verify the logical correctness of the design post synthesis with the help of the netlist file. It ensures whether the timing of the design is met and for thi, the GLS used to run with delay annotations.
How to perform GLS after obtaining a netlist output for a specific RTL design?
To perform GLS using iverilog simulator, we need to add the path of the primitives and sky130 library files along with the netlist verilog code and testbench to successfully obtain the waveforms of post synthesis simulation.
![image](https://user-images.githubusercontent.com/104430712/166256700-7082d413-1e63-4598-9290-5b0cb749d957.png)
![image](https://user-images.githubusercontent.com/104430712/166256725-16387502-0b24-4630-8c76-1a3a06a4b8ac.png)
![image](https://user-images.githubusercontent.com/104430712/166256750-237afcd9-d722-4135-bcc2-27b1c6e908b4.png)
![image](https://user-images.githubusercontent.com/104430712/166256780-bf54046a-4905-4640-a2e1-84d3a995cfd1.png)
![image](https://user-images.githubusercontent.com/104430712/166257373-b1fa627d-ca9d-4ebe-9bb8-1e2ec4b4b4b4.png)
![image](https://user-images.githubusercontent.com/104430712/166257392-c999ec5d-7311-4429-b35d-47cd20430c0b.png)
![image](https://user-images.githubusercontent.com/104430712/166257468-3af4589c-b1b7-4f08-8f8f-ff6b8acaa2a4.png)
![image](https://user-images.githubusercontent.com/104430712/166257481-69eb257e-c40a-489f-80ad-b02e0bdae5e4.png)
![image](https://user-images.githubusercontent.com/104430712/166257501-06c913f3-5dcb-4677-b76a-e75aadeae61c.png)
![image](https://user-images.githubusercontent.com/104430712/166257513-d03c5b4b-9566-42e3-87ff-efd71e457458.png)
![image](https://user-images.githubusercontent.com/104430712/166257537-b6ccce6b-1838-4654-ae78-7b9037728dc7.png)

>>>>>>>>BAD_MUX

![image](https://user-images.githubusercontent.com/104430712/166257584-c838228d-78fc-4bcc-8030-916b91e63a3a.png)

![image](https://user-images.githubusercontent.com/104430712/166257604-b9577089-1942-4667-9f49-ad2c7d0f8dfc.png)

![image](https://user-images.githubusercontent.com/104430712/166257635-a4147cde-2da9-480b-9880-c093a3b9457b.png)

![image](https://user-images.githubusercontent.com/104430712/166257666-1b08a73a-72fa-4d26-9dcf-64284a230dbd.png)

![image](https://user-images.githubusercontent.com/104430712/166257678-27246d2b-b899-4662-8441-2c6ab0458e5c.png)

![image](https://user-images.githubusercontent.com/104430712/166257696-a2a9cfc5-b383-4b2e-a017-d42054461f09.png)

![image](https://user-images.githubusercontent.com/104430712/166257708-456ec4e7-ef26-459a-8c49-34906fa7d09f.png)

![image](https://user-images.githubusercontent.com/104430712/166257728-dab45063-b984-47d1-985d-8a62cbf04c4d.png)

![image](https://user-images.githubusercontent.com/104430712/166257747-33602631-e2e4-4534-9ced-6b6b53ef41e4.png)

GLS simulation

$ iverilog ../my_lib/verilog_model/primitives.v ../my_lib/verilog_model/sky130_fd_sc_hd.v bad_mux_net.v tb_bad_mux.v

![image](https://user-images.githubusercontent.com/104430712/166257863-71ab401b-62dc-4050-a4ab-e4f8f8ed67da.png)

![image](https://user-images.githubusercontent.com/104430712/166257876-fe7d3b91-22b8-4826-a01e-157171969e9a.png)

![image](https://user-images.githubusercontent.com/104430712/166257907-c3a175de-4eae-4f27-af14-b204f75b48dd.png)

![image](https://user-images.githubusercontent.com/104430712/166257931-8fca7c44-2326-4a62-8198-06d666fbbc84.png)

![image](https://user-images.githubusercontent.com/104430712/166257958-a7e7f4d0-1792-492e-8bf0-556443746216.png)

![image](https://user-images.githubusercontent.com/104430712/166257983-b2fc6b75-bf81-41fb-add3-22abc9559a44.png)

![image](https://user-images.githubusercontent.com/104430712/166258009-2f9c1f52-bc7c-4784-aa8f-1a0867dea9d0.png)

![image](https://user-images.githubusercontent.com/104430712/166258032-dbbc3bc3-77e7-48b2-b564-f4b596a6f3f7.png)

![image](https://user-images.githubusercontent.com/104430712/166258053-ba4450c2-775a-4db5-b7db-2ecf65e54b9b.png)

![image](https://user-images.githubusercontent.com/104430712/166258076-978b0577-0119-46ed-9f52-31fed43048c6.png)

 ![image](https://user-images.githubusercontent.com/104430712/166258111-b7fffd84-1aba-45eb-8a45-a11c1b4bba55.png)

Day-5 If Case For Loop and for Generate statements

![image](https://user-images.githubusercontent.com/104430712/166258180-daeba9a2-331f-4c8a-aa20-6255a2945d37.png)

![image](https://user-images.githubusercontent.com/104430712/166258207-c6e7b39d-80f6-40dc-ac80-55b9d9305ed9.png)

![image](https://user-images.githubusercontent.com/104430712/166258227-b36d7f15-3097-4795-a8bb-140a2c54fcb0.png)

![image](https://user-images.githubusercontent.com/104430712/166258246-172613ae-1c3c-4d14-802a-1478fb3fb7df.png)

![image](https://user-images.githubusercontent.com/104430712/166258261-219cbb59-e338-4c24-9435-c624bb05c2ba.png)

![image](https://user-images.githubusercontent.com/104430712/166258277-7f66bbe6-8486-4469-b48f-909a977faa9e.png)

![image](https://user-images.githubusercontent.com/104430712/166258304-71c51548-4721-494d-9192-207d37803c15.png)

![image](https://user-images.githubusercontent.com/104430712/166258312-055b0c5d-f2cd-42fd-880a-c051b35e4655.png)

![image](https://user-images.githubusercontent.com/104430712/166258328-0c273db4-e0eb-4f42-af38-464d408a8730.png)

![image](https://user-images.githubusercontent.com/104430712/166258358-11624e47-c3e4-47eb-a297-f39d2738327f.png)

![image](https://user-images.githubusercontent.com/104430712/166258379-c55f6013-0e23-4dc5-adba-e68145fbdd1a.png)

![image](https://user-images.githubusercontent.com/104430712/166258392-74c283fb-9939-4d72-8eb2-bdc787c12410.png)

![image](https://user-images.githubusercontent.com/104430712/166258427-d9bcef8c-ddef-469a-bba7-325744d5aff9.png)

![image](https://user-images.githubusercontent.com/104430712/166258447-83a48aff-5725-4e2f-8644-f8a8e19a849f.png)

![image](https://user-images.githubusercontent.com/104430712/166258418-1c652c34-74be-4a90-8c84-0e842f556e9a.png)

![image](https://user-images.githubusercontent.com/104430712/166258457-f9054711-949c-4227-b33f-1e475bc301ce.png)

![image](https://user-images.githubusercontent.com/104430712/166258502-13310cb4-353a-46cc-bc6e-9e1a28cbe41e.png)

![image](https://user-images.githubusercontent.com/104430712/166258483-26fd455f-d011-413c-a33f-a69193ce1987.png)

![image](https://user-images.githubusercontent.com/104430712/166258527-9db61c34-4bcf-4910-8608-6933b2231394.png)

![image](https://user-images.githubusercontent.com/104430712/166258560-aad5a733-b809-45fd-848a-be1fabf02e83.png)

![image](https://user-images.githubusercontent.com/104430712/166258547-de8ba192-9335-4264-884c-be3d92cc749a.png)

![image](https://user-images.githubusercontent.com/104430712/166258573-6ca54d8d-3e76-45df-b171-89079f313394.png)

![image](https://user-images.githubusercontent.com/104430712/166258590-e651d9d9-d895-4bf7-9923-6e477d5998de.png)

![image](https://user-images.githubusercontent.com/104430712/166258609-90f163e0-860d-490c-b14d-213cb2da3ab0.png)

![image](https://user-images.githubusercontent.com/104430712/166258632-6cd747cf-33ca-4a2c-8df7-01181b1dbd88.png)

![image](https://user-images.githubusercontent.com/104430712/166258655-412bef65-d45e-48f3-84a8-732f11e4a9ed.png)

For loop statements and For generate statements
Looping constructs uses for loop and generate for loop statements
For loop statement
For loops can be used only inside always block. These loops can be used for evaluating expressions but not for instantaiating hardware. Example we are taking is a 32:1 Mux is as shown below:
integer i;
always @(*)
begin 
 for(i=0; i<32; i=i=1)
 begin
 if (i==sel)
   y= inp[i];    //Assuming that inp[32:0] bus is declared in the main module.
 end
end     
Generate for loop statement
Generate for loop cannot be used inside always block but outside always block. Generate for loop is used in instantiating hardware. Taking an example for generate foor loop as shown below
Suppose we need to instantiate and u_and( .a(), .b(), .y()) for 20 times it is not feasible to and u_and( .a(), .b(), .y()) this many times ie
   and u_and( .a(), .b(), .y())
   and u_and( .a(), .b(), .y())
   and u_and( .a(), .b(), .y())
   ..................
   ..................
   ..................
   ..................
   Till 20th and gate instantiation
Here we use generate for loops to instantiate gates and smaller modules in main modules as my times we want.
 genvar i
 generate
  for (i=0; i,8; i=i+1) begin 
  and u_and( .a(a[i]), .b(b[i]), .y(y[i]));
end
 end
![image](https://user-images.githubusercontent.com/104430712/166258736-ecda48a3-5cf9-4506-94e2-8b32b293a20c.png)

Here we see that the waveform obtained in normal simulation and GLS simulation are the same.
By this, we have come to the end of 5 days workshop so by now I have sucessfully learnt theoretical and practical approach on how to simulate, displaying waveform, synthesize, do gate level synthesis (netlist generation) and finally again display the waveforms to check the correctness of the design starting from smaller verilog codes to complex ones.
Acknowledgements
1.	Kunal Ghosh - Co-founder(VSD Corp. Pvt. Ltd)
2.	Shon Taware - VSD Teaching Assistant





















 
