# Dynamic Adaptation of Software-defined Networks for IoT Systems: A Search-based Approach  

This page contains the artifacts of our paper, entitled "Dynamic Adaptation of Software-defined Networks for IoT Systems: A Search-based Approach," accepted to the SEAMS 2020 conference.

## Overview

The concept of Internet of Things (IoT) has led to the development of many complex and critical systems such as smart emergency management systems. IoT-enabled applications typically depend on a communication network for transmitting large volumes of data in unpredictable and changing environments. These networks are prone to congestion when there is a burst in demand, e.g., as an emergency situation is unfolding, and therefore rely on configurable software-defined networks (SDN). In this paper, we propose a dynamic adaptive SDN configuration approach for IoT systems. The approach enables resolving congestion in real time while minimizing network utilization, data transmission delays and adaptation costs. Our approach builds on existing work in dynamic adaptive search-based software engineering (SBSE) to reconfigure an SDN while simultaneously ensuring multiple quality of service criteria. We evaluate our approach on an industrial national emergency management system, which is aimed at detecting disasters and emergencies, and facilitating recovery and rescue operations by providing first responders with a reliable communication infrastructure. Our results indicate that (1) our approach is able to efficiently and effectively adapt an SDN to dynamically resolve congestion, and (2) compared to two baseline data forwarding algorithms that are static and non-adaptive, our approach increases data transmission rate by a factor of at least 3 and decreases data loss by at least 70%.

DICES: Dynamic adaptive congestion control algorithm for SDN

## [Quick Guide]

### Prerequisite
- Virtual Machine: VirtualBox https://www.virtualbox.org/
  - Version: 6.0
- Virtual Image: Preconfigured virtual machine image
  - Download: https://dropit.uni.lu/invitations/?share=92b452c1068f3a51d164&dl=0
- Note:
  - The virtual image is tested on a virtual machine equipped with three CPUs and 16GB of memory.
  - Experiment results obtained from this virtual setting will be different from the results described in our paper due to the limited processing power of a virtual machine. To reproduce our experiment results, please follow the "Developer Guide" section.
  - All artifacts are located under the ~/DICES directory.

## How to perform experiments with DICES?
- Step 0: Login
  - Password: rocks  
- Step 1. Run SDN controllers
  - Double-click on the "Setup ONOS Cluster" icon
  - You will see "onos>" command line
- Step 2. Install and activate DICES
  - Double-click on the "Run DICES" icon
- Step 3. Build a network
  - Double-click on the "Build Network" icon
  - You will see "mininet>" command line
- Step 4. Generate traffic flows
- Step 4.1. Run receivers
  - Double-click on the "Run Receivers" icon
- Step 4.2. Run senders
  - Double-click on the "Run Senders" icon
  - You will see eight "Finished sending packets" messages
- Step 5. Analyze Results
  - Double-click on the "Analyze Packets" icon


## [Developer Guide]

### Prerequisite
The following software are required to execute DICES.
- ONOS: https://onosproject.org/
  - Version: 1.15.0
  - Installation: https://wiki.onosproject.org/display/ONOS/Getting+the+ONOS+core+source+code+using+git+and+Gerrit
- Mininet: http://mininet.org/
  - Version: 2.3.0
  - Installation: http://mininet.org/download/
- D-ITG: http://www.grid.unina.it/software/ITG/
  - Version: 2.8.1
  - Installation: http://www.grid.unina.it/software/ITG/download.php

### How to perform experiments with DICES?
- Step 1. Run ONOS
- Step 2. Install and activate DICES
- Step 3. Run Mininet scripts (and configure ONOS network topology for EXP3)
- Step 4. Run D-ITG scripts
- Step 4.1. Run receiver scripts
- Step 4.2. Run sender scripts

### File: DICES.zip
- Description: DICES is implemented as an application of ONOS.  
- Instruction:
  - Compilation: Maven
  - Installation and activation: https://wiki.onosproject.org/display/ONOS/Managing+ONOS+applications

### File: EXP1_scripts.zip
- Description: Synthetic networks and traffile profiles for EXP1 (Section 4.5). 
- Mininet scripts (networks): net_rq1.py. 
- D-ITG scripts (traffic pofiles): receiver - run_rq1_recv.sh, sender - run_rq1_send_*.sh

### File: EXP2_scripts.zip
- Description: Synthetic networks and traffic profiles for EXP2 (Section 4.5). 
- Mininet scripts (networks): net_rq2.py. 
- D-ITG scripts (traffic pofiles): receiver - run_rq2_recv.sh, sender - run_rq2_send*.sh

### File: EXP3_scripts.zip
- Description: Emergency management system (EMS) - network and traffic profile (Section 4.5). 
- Mininet scripts (networks): dmsSat.py. 
- D-ITG scripts (traffic pofiles): receiver - run_rq3_recv_*.sh, sender - run_rq3_send_*.sh. 
- ONOS scripts (topologies): dmsSat.json. 
- ONOS network configuration: https://wiki.onosproject.org/display/ONOS/The+Network+Configuration+Service

### File: OSPF.zip
- Description: OSPF-based data forwarding algorithm. 
- Instruction:
  - Compilation: Maven
  - Installation and activation: https://wiki.onosproject.org/display/ONOS/Managing+ONOS+applications

### File: RQ1_results.zip, RQ2_results.zip, and RQ3_results.zip
- Description: Experiment results (Section 4.7)
