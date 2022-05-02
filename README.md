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








 
 
 
 
 

 
