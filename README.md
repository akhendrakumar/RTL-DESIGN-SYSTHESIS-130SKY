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
 ASIC (Application Specific Integrated Circuit) Design flow started with design specifications.
The design time depending on the complexity inside the chip.
The complete ASIC design process can be divided into two parts.
1. Front End Design
2. Back End Design
Front End Design:
RTL (Register Transfer Level) design engineer converts the specification into an RTL code using the HDL (Hardware Description Language) generally either in Verilog or VHDL. Once the RTL code is written, RTL designer simulates the code in RTL Simulator and check the functionality of the design. 

![image](https://user-images.githubusercontent.com/104430712/166151445-79cea488-40e3-4eca-9388-3d5715572c14.png)

Back End Design:
RTL code received from the front end engineer is technology independent, now the next step is Logic synthesis. 

Logic Synthesis:  In logic synthesis, a high-level description of the design (RTL Code) is converted into an optimized gate-level representation of a given standard cell library and certain design constraints. Now the code is in the form of a gate-level netlist of a particular standard cell library. LEC (Logic Equivalence Check is must in this stage to make sure that there are not logical changes occurred during the synthesis. During logical Synthesis, we also get various reports on timing power and area of design. We also get an SDC (Synopsys Design Constraint) file in this stage which is used in the next stage. DFT (Design For Testability) Insertion is also done in this stage to verify the chip after fabrication is done. 

Place and Route (PnR): Gate level netlist after DFT Insertion and SDC file is taken as input for the PnR and based on standard cells library, PnR starts. The goal of PnR stage is to place all the standard cells, Macros and I/O pads with minimal area, with minimal delay and Route them together in such a way that there is no DRC (Design Rule Check) error. The final output of this stage is the layout of design in the form of GDSII file which is defacto standard of layout file in the industry. 
PnR stage is a very challenging stage with large design cycle time depending on the complexity of a chip. This stage is further divided into various sub-stages. The main stages are starting from Design Import, followed by FloorPlan, Power Plan, Placement, CTS (Clock Tree Synthesis), and Routing. 
After routing we expect the design has met the timing and all DRC, But in the modern chip, it's not easy to close the design in this stage. So Further we go to Signoff stage.

Signoff: If there are some timing violations in the post route design, we have a further stage called ECO (Engineering Change Order) where we can fix the timing violations. Apart from timing violation, there may be issues like IR Drop, DRC Violations all these are fixed in this stage and a final layout file free from all the violation is streamed out in GDSII format. This process is known as tapeout in ASIC flow. This is the final design stage and the gdsII file is sent to fabrication lab for the fabrication of chip.
![image](https://user-images.githubusercontent.com/104430712/166151490-12f27c41-896b-4e85-b0b9-d39ca0a7ce7b.png)
![image](https://user-images.githubusercontent.com/104430712/166151496-835d30c0-fc00-4a07-b920-fa999a8a428c.png)
![image](https://user-images.githubusercontent.com/104430712/166151503-74c7257d-198f-498b-b20b-303bb6f13cc2.png)
![image](https://user-images.githubusercontent.com/104430712/166151506-68c1c6b2-979d-4bcb-9d12-82e0d5d991ab.png)
![image](https://user-images.githubusercontent.com/104430712/166151512-4ba562a5-2767-44c1-9c0e-00d1efe8bb05.png)
![image](https://user-images.githubusercontent.com/104430712/166151521-143b8ea5-5cbb-4f29-80f8-92747ca471f2.png)
![image](https://user-images.githubusercontent.com/104430712/166151530-6d46b694-a13c-46d5-b0a1-6a8e077b222f.png)
![image](https://user-images.githubusercontent.com/104430712/166151533-779cc22b-f380-4399-8ec0-515d95185949.png)
![image](https://user-images.githubusercontent.com/104430712/166151539-c605e543-d621-4001-aaa6-1f8c4653835e.png)
![image](https://user-images.githubusercontent.com/104430712/166151582-75da0eda-0ba9-4b18-a69c-87b2af1ce3e1.png)
![image](https://user-images.githubusercontent.com/104430712/166151588-2dbdbbd2-ed8a-41d0-911d-4b2135f28a2b.png)
![image](https://user-images.githubusercontent.com/104430712/166151592-35704302-f018-4df1-8f7f-3c0bbf9f4ed6.png)
![image](https://user-images.githubusercontent.com/104430712/166151597-d9ccb8e6-9c91-4c40-bad2-3df227235a36.png)
![image](https://user-images.githubusercontent.com/104430712/166151600-6041c1d7-cb90-4abb-902e-41fef5b228f4.png)
![image](https://user-images.githubusercontent.com/104430712/166151605-0f390d87-1961-4f4d-87da-ac36ccaf2aae.png)
![image](https://user-images.githubusercontent.com/104430712/166151608-a8b44c84-443f-4437-bbd4-73220d2423d6.png)
![image](https://user-images.githubusercontent.com/104430712/166151617-4058feb5-112f-45cd-89ee-69e8e106fd5b.png)
![image](https://user-images.githubusercontent.com/104430712/166151622-e32021c9-a009-437d-b530-d21392691209.png)
![image](https://user-images.githubusercontent.com/104430712/166151627-c8717456-4eba-4de7-8b6c-5808b6a03e8e.png)
![image](https://user-images.githubusercontent.com/104430712/166151635-b3604509-00eb-46a3-ace6-2f70de3f0685.png)


 

 
 
 
 
 
 
 
 
 
 

 
