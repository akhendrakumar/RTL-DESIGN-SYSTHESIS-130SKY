# RTL-DESIGN-SYSTHESIS-130SKY
This repository is created as part of workshop
ASIC Design Flow - An Overview
In this post, ASIC (Application Specific Integrated Circuit) Design flow has been explained. The very first step of ASIC flow is design specification, which comes from the customer end.
The complete ASIC design process can be divided into two parts.
1.	Front End Design
2.	Back End Design

Front End Design:
Front end design process starts with the specification received from the customer end. RTL (Register Transfer Level) design engineer converts the specification into an RTL code using the HDL (Hardware Description Language). Once the RTL code is written, RTL designer simulates the code in RTL Simulator and check the functionality of the design.
Back End Design:
RTL code received from the front end engineer is technology independent, now the next step is Logic synthesis. 

Logic Synthesis:  In this process RTL code is converter into an optimized gate-level representation of a given standard cell library and certain design constraints. Now the code is in the form of a gate-level netlist of a particular standard cell library. 

Place and Route (PnR):  The goal of PnR stage is to place all the standard cells, Macros and I/O pads with minimal area, with minimal delay and Route them together in such a way that there is no DRC (Design Rule Check) error. 

Signoff: If there are some timing violations in the post route design, we have a further stage called ECO (Engineering Change Order) where we can fix the timing violations. 

In this repository i only concentrate on synthesis part using open source tool called Yosys using sky130nmPDK. 
Lab access: As part of this workshop VPN based lab access is provided. These are the steps i followed to login
Login to VSD website then move to the Lab instance 
 
 ![image](https://user-images.githubusercontent.com/104430712/166086257-8301d275-f044-48ce-96b0-716f40fa95db.png)
![image](https://user-images.githubusercontent.com/104430712/166086263-6467e74b-a745-4b45-86a3-b9a952b0c414.png)







