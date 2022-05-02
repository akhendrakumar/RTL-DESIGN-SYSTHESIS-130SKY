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

 
 
 
 
 
 

 
