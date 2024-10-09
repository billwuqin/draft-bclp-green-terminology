---
title: "Terminology for Energy Efficiency Network Management"
abbrev: "Energy Efficiency Terminology"
category: info

docname: draft-bclp-green-terminology-latest
submissiontype: IETF
number:
date:
consensus: true
v: 3
area: "Operations and Management"
workgroup: "GREEN Working Group"
keyword:
 - Energy Efficient
 - Energy Saving
 - Energy Management

author:
 -
    fullname: Chunchi Liu
    organization: Huawei
    email: liuchunchi@huawei.com
 -
    fullname: Qin Wu
    organization: Huawei
    email: bill.wu@huawei.com
 -
    fullname: Marisol Palmero
    organization: Cisco
    email: mpalmero@cisco.com
 -
    fullname: Mohamed Boucadair
    organization: Orange
    email: mohamed.boucadair@orange.com
 -
    fullname: Luis M. Contreras
    organization: Telefonica
    email: luismiguel.contrerasmurillo@telefonica.com

informative:

 ETSI-ES-203-136:
   title: Environmental Engineering (EE); Measurement methods for energy efficiency of router and switch equipment
   target: https://www.etsi.org/deliver/etsi_es/203100_203199/203136/01.02.00_50/es_203136v010200m.pdf
   date: 2017

 L.1310:
   title: Energy efficiency metrics and measurement methods for telecommunication equipment
   target: https://www.itu.int/rec/T-REC-L.1310-202409-P
   date: 2024

 L.1315:
   title: Standardization terms and trends in energy efficiency
   target: https://www.itu.int/rec/T-REC-L.1315-201705-I
   date: 2017

 L.1316:
   title: Energy efficiency framework
   target: https://www.itu.int/rec/T-REC-L.1316-201911-I
   date: 2019

 L.1320:
   title: Energy efficiency metrics and measurement for power and cooling equipment for telecommunications and data centres
   target: https://www.itu.int/rec/T-REC-L.1320-201403-I
   date: 2014

 L.1331:
   title: Assessment of mobile network energy efficiency
   target: https://www.itu.int/rec/T-REC-L.1331-202009-S
   date: 2020

 L.1333:
   title: Carbon data intensity for network energy performance monitoring
   target: https://handle.itu.int/11.1002/1000/15028
   date: 2022

 L.1410:
   title: Methodology for environmental life cycle assessments of information and communication technology goods, networks and services
   target: https://www.itu.int/rec/T-REC-L.1410-201412-I
   date: 2014

--- abstract

Energy efficient network management is primary meant to enhance conventional
network management with energy-related management capabilities
to optimize the overall energy consumption at the level of a network. To that aim,
specific features and capabilities are required to control (and thus optimize)
the energy use of involved network devices, and their components.

This document defines a set of terms used within the IETF when discussing energy efficiency in network management.
Such reference document helps framing discussion and agreeing upon a set of main concepts in this area.

--- middle

# Introduction

With rising energy costs and increasing awareness of the ecological impact of running networks, servers, and various
equipment, Energy Efficiency is considered by operators as a critical issue for network management systems in relation to
environmental impact and related operational cost. Energy Efficiency management is thus complementing conventional network management.

This document defines a set of terms used within the IETF when discussing Energy Efficiency network management.
The purpose is to ensure a consistent set of terminology and help with the characterization of Energy
Efficiency (and relevant aspects), assist in the development of the YANG data models at the different levels in the
IETF, bring clarity to the Energy Efficiency related discussions between different groups within IETF, in particular.

This document does not intend to define a comprehensive list of energy-related terms. Only key terms are defined.
Some of these terms are extracted from existing IETF documents and beyond.

# Terms and Definitions

The following terms are used in this document as defined below:
DSLAM: Digital Subscriber Line Access Multiplexer
MSAN:  Multiservice Access Node
GPON:  Gigabit-capable Passive Optical Network
GEPON: Gigabit Ethernet Passive Optical Network
Energy Efficiency:
:   The concept of energy efficiency refers to the ability to use available of energy to achieve a specific benefit
in a resource conserved manner and at low cost. The energy efficiency is ratio between the useful output and input
of an energy conversion process of network devices.

Energy Efficiency metrics:
:   A set of metrics that are used for evaluation of energy consumption and network performance characterize the
effectiveness of energy management strategy.

Energy Efficiency Ratio:
:  The ratio of total throughput (system capacity) to the total power consumed (bits/Joule). It is the throughput forwarded
by 1 watt and it is introduced in {{?I-D.cprjgf-bmwg-powerbench}}.  A higher EER corresponds to a better the energy efficiency.

Power Usage Effectiveness:
:  The metric used to measure data center energy efficiency. It is calculated by the ratio between the total energy
consumed by the data center and the energy needed for IT equipment.

Network level Energy Efficiency:
:  Network level metrics are used to evaluate the energy efficiency of an entire network or part of it.

Device level Energy Efficiency:
:  Equipment/system level metrics are mostly used to compare Network equipment of the same functionality and place in
a network. They evaluate the overall energy efficiency performance at the equipment/system level

Component Level Energy Efficiency:
:  Component-level metrics can be used in the design, development and manufacture of energy efficient equipment. They
regard equipment as an "open box" and evaluate the energy efficiency performance of its individual components.
Measuring and understanding the energy efficiency or energy consumption of each component within the equipment
helps to identify the “hot spots” and key components in a system with regard to energy saving.

## Energy efficiency Metrics and Measurement Method

Metric for DSLAM, MSAN,GPON, GEPON equipment:

Equipment with line cards working at different profiles/states shall be characterized with different
metric values for each specific profile/state.

                          Pport = Peq/Nports[W/port]

Where Peq is the power (in watts) of a fully equipped wireline network equipment with all its line cards
working in a specific profile/state.

Metric for wireless access technologies:

The proposed energy efficiency metric at RF (Radio-Frequency) unit level is

                         EErfu = Eoutput/Erfu

Where Eoutput is daily RF output energy consumption [Wh] under different load
Erfu is daily RF units energy consumption [Wh] under different load.

Metric for routers and Ethernet switches:

The proposed metric for router and Ethernet switches is

                        EER = Ti/Pw [Mbit/s/W]

Where Ti is weighted throughput, Pw is weighted power (energy consumption rate)

Metric for small network devices:

The metrics adopted for small networking devices intended for home/domestic or small office use is

 EER = (0.35Tidle+0.5Tlowpower+0.15TMaximum)/(0.35Pidle+0.5Plowpower_0.15Pmaximum) (Mbit/s/W)

Where throughput is maximum non drop data rate beween wide area Network and
local area network kport in the ingress direction;
Line rate/speed is maximum possible number of transmitted/received bits.
Power shall be averaged over 5 minutes, taking measurements every 30 seconds.
During idle power,IP pings shall be sent via the user interface.

Metric for power equipment:

                               δ = Po/Pi

Where Po is output power, Pi is input power. This energy efficiency value is
measured or calculated from the testing data over specified time period.

Metric for cooling equipment

                              η = Qt/Pi

Where η is the energy efficiency of the air conditioner
Pi is the input power, Qt is the sum of the sensible cooling capacity and the
latent cooling capacity.

# Security Considerations

Security is not discussed in this document.

--- back

# Standards Bodies and Standards

This appendix provides a list of SDOs where relevant energy efficiecny effort is ongoing.
This appendix does not aim to be comprehensive. The appendix may be removed in future versions of the document.

## ITU-T SG5

ITU-T Study Group 5 (SG5) has already worked on developing standards on energy efficiency.
ITU-T SG5 has many standards in the environment efficiency field. These standards include {{L.1310}}, {{L.1315}},
{{L.1316}}, and {{L.1320}} covering energy efficiency terminology, framework, metrics, and measurement methods.

ITU-T SG5 is also responsible for other standards that might be of interest to protocol developers
and network operators. For example:

* {{L.1331}} specifies assessment of mobile network energy efficiency.
* {{L.1333}} specifies the correlation between the carbon intensity indicator and energy efficiency metric. The carbon KPI defined in {{L.1333}}
refers to the energy efficiency metric defined in ITU-T L.1331.
* {{L.1410}} focuses on the assessment of the environmental impact of information and communication technology (ICT) goods, networks and services. It provides
specific guidance on energy and greenhouse gas (GHG) impacts.


## ETSI TCEE

ETSI Technical Committee (TC) Environment Engineering (EE) is collaborating with ITU-T SG5 to develop technically
aligned standards on energy efficiency and environment aspect. These standards include energy efficiency, power
feeding solution, circular economy and network efficiency KPI and eco-design requirement for ICT, with the aim to
build an international eco-environmental standardization.

{{ETSI-ES-203-136}} defines the energy consumption metrics and measurement methods for router and Ethernet switch equipment. It specifies a methodology and the test conditions to measure the power consumption of router and switch equipment and is also applicable to Core, edge, and access routers.


## 3GPP SA5

3GPP SA5 has, in Release 17, extended its scope from RAN only to the whole 5G System (5GS) and worked on Energy Efficiency
(EE) and Energy Saving (ES) of mobile networks. EE Key Performance Indicators (KPI) have been defined for the 5G Core
network and Network Slices.

The 3GPP Energy Efficiency in the RAN is defined by the performance divided by the Energy Consumption (EC), where
the definition of the performance depends on the type of network entity it applies to. From this, SA5 work aimed at
defining the best metrics for each of them, and their measurement method.

In Rel-18, WG SA5 works with ETSI NFV to explore more accurate virtual CPU usage measurements from ETSI NFV MANO,
Introduce additional metrics when estimating the Energy Consumption of Virtual Machines, e.g., their virtual disk or
link usage. In addition new use cases for Energy Saving, applied to NG-RAN, 5GC, and Network Slicing, AI/ML assisted
energy saving scenarios are also being investigated.

# Acknowledgments

TODO acknowledge.
