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
    fullname: Gen Chen
    organization: Huawei
    email: chengen@huawei.com
 -
    fullname: Mohamed Boucadair
    organization: Orange
    email: mohamed.boucadair@orange.com
 -
    fullname: Qin Wu
    organization: Huawei
    email: bill.wu@huawei.com
 -
    fullname: Luis M. Contreras
    organization: Telefonica
    email: luismiguel.contrerasmurillo@telefonica.com
 -
    fullname: Marisol Palmero
    organization: Individual
    email: marisol.ietf@gmail.com

contributor:

 -
    fullname: Shailesh Prabhu
    organization: Nokia
    email: shailesh.prabhu@nokia.com

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

 TS28.554:
    title: Management and orchestration; 5G end to end Key Performance Indicators (KPI)
    target: https://www.3gpp.org/ftp/Specs/archive/28_series/28.554/28554-i70.zip
    date: 2024

--- abstract

Energy-efficient network management is primarily meant to enhance conventional
network management with energy-related management capabilities
that optimize overall network energy consumption. To that aim,
specific features and capabilities are required to control (and thus optimize)
the energy use of involved network elements and their components.

This document defines a set of key terms used within the IETF when discussing energy efficiency in network management.
Such reference document helps framing discussion and agreeing upon a set of main concepts in this area.

--- middle

# Introduction

With rising energy costs and increasing awareness of the environmental impact of running networks, servers, and various
equipment, Energy Efficiency is considered by operators as a critical component to be integrated in the overall Network
Management systems. Such integration is ambitioned to feed strategies for achieving environmental objectives but also
mastering related operational cost. Energy Efficiency Management is thus complementing conventional network management.

{{sec-def}} defines a set of terms used within the IETF when discussing energy-efficient networks.
The purpose is to (1) ensure consistent use of a set of terms in this area, (2) help with the characterization of Energy
Efficiency (and relevant aspects), (3) assist in the development of the YANG data models at the different levels in the
IETF, and (4) bring clarity to the Energy Efficiency related discussions between different groups within the IETF, in
particular.

This document does not intend to define a comprehensive list of energy-related terms. Only key terms are defined.
Some of these terms are extracted from existing IETF documents and beyond.

Also, {{sec-metrics}} provides an inventory of currently used metrics to assess/compute energy-related consumption,
efficiency ratio, etc.

{{sec-sdos}} provides a list of SDOs where relevant energy efficiency effort is ongoing.

# Abbreviations

The following abbreviations are used in the document:

CLEE:
: Component Level Energy Efficiency

DLEE:
: Device Level Energy Efficiency

DSLAM:
: Digital Subscriber Line Access Multiplexer

EER
: Energy Efficiency Ratio

GEPON:
: Gigabit Ethernet Passive Optical Network

GPON:
:  Gigabit-capable Passive Optical Network

MSAN:
:  Multiservice Access Node

NDR:
:  None-Drop Rate

NLEE:
: Network Level Energy Efficiency

PUE:
: Power Usage Effectiveness

# Definitions {#sec-def}

Terms are listed so that terms that are needed to understand other terms are listed first.

Energy:
: Is generally a reference to electrical energy and is measured in kilowatt-hours (kWh) ({{?RFC7326}}).

Power:
: Refers to the time rate at which energy is emitted, transferred, or
  received; power is usually expressed in watts (joules per second) ({{?RFC7326}}).

Energy Management:
: Is a set of functions for measuring, modeling,
  planning, and optimizing networks to ensure that the network and
  network-attached devices use energy efficiently and appropriately
  for the nature of the application and the cost constraints of the
  organization ({{?RFC7326}}).

Energy Monitoring:
: Is a part of Energy Management that deals with
  collecting or reading information from devices to aid in Energy
  Management ({{?RFC7326}}).

Energy Control:
: Is a part of Energy Management that deals with
  directing influence over devices ({{?RFC7326}}).
: This control can span a network or a subset of it.

Energy Efficiency:
: Refers to optimizing energy usage in network components, devices, and across the network
  to minimize energy use as much as possible, thus eliminating energy waste.
  Examples to improve Energy efficiency include, but are not limited to, deactivation of some or
  all components of network nodes during specific periods (e.g., periods with low traffic),
  adjusting the speed of an interface based on network traffic load changes, switching
  to more efficient power supplies and silicon, or developing more efficient transmission or signal
  processing algorithms.


Energy Efficiency Management:
: Refers to a set of processes used to maintain an inventory of capabilities,
use specific metrics to measure, report, and assess energy consumption of the network,
and control the use of available energy in an optimized manner.
The overall goal is to ensure that the network and underlying devices use energy in
a resource-conserving manner and at low cost for the nature of the
the services it provides and the cost constraints while achieving the
network’s functional and performance requirements (e.g., improving overall network
utilization).

Energy Efficiency Observability:
: Is a component of Energy Efficiency Management that deals with collecting, reporting, and
reading metrics information from devices and evaluating the effectiveness of
energy-aware policies to aid in Energy Efficiency Management.

Energy Efficiency Control:
: Is a component of Energy Efficiency Management that deals with directing influence over
devices.

Energy Efficiency Capabilities:
: 	Network Capabilities to optimize energy usage in network components, devices, and across the network
   through configurable static attributes (e.g., power saving capable attribute which can be applied to
   both component level and device level, or power setting attributes which specify absolute power,
   relative power, who provide power, who consume, who is the meter, measurement frequency, or temperature
   setting, voltage, ampere setting).

Energy Efficiency Metric:
: Refers to a metric that is used for the assessment of energy consumption of
  a network, device, or component. One or more metrics can be defined. These metrics are also
  used for network performance purposes to characterize the effectiveness of an Energy
  Efficiency management strategy. Developing energy efficiency metrics for internetworking
  and associated measurement methodologies and conditions as well as consistently collecting this
  data over time are essential to demonstrating Energy Efficiency improvements.  An example of
  a common outcome-oriented metric is energy consumption per data volume or traffic unit.

Energy Proportionality
: Is the correlation between energy used and the associated useful
 output.  For internetworking this is generally interpreted as the
 proportionality of traffic or traffic throughput and energy used.
 This concept is broadly applicable to networking infrastructure,
 data center, and other communication architectures.  There
 might not be a one-to-one correlation between traffic and
 energy use, notably due to the materially significant idle power
 use by devices, as well as the overall network capacity being
 allocated to serve at times of highest traffic utilization.

Energy Efficiency/Energy Efficiency Ratio (EER):
: The energy efficiency is expressed as the ratio between the useful output and input of an
  energy conversion process of a network, device, or component.
: For instance, in relation with a networking device, it can be stated as the ratio of total
  throughput (e.g., of a network element capacity) to the total power consumed (bits/Joule).
: This ratio (i.e., Energy Efficiency Ratio, EER) is the throughput forwarded by 1 watt
  (e.g., {{?I-D.cprjgf-bmwg-powerbench}}).
: A higher EER indicates a better energy efficiency.

Power Usage Effectiveness (PUE):
: Refers to the metric used to measure the energy efficiency of an infrastructure.
: This metric is calculated as the ratio between the total energy consumed by an infrastructure
  and the energy needed for a network element/component.

Network Level Energy Efficiency (NLEE):
: Denotes the Energy Efficiency of an entire network or a subset part of it (e.g., access network).

Device Level Energy Efficiency (DLEE):
: Denotes the Energy Efficiency of a network element.  It can be used, e.g., to compare network
  elements providing the same functionality or a target to optimize the configuration of a
  network element. Here "Device Level" is equivalent to "System Level", which is considered as a
  "single device" or "single entity" from the measurement and reporting point of view.

Component Level Energy Efficiency (CLEE):
: Denotes the Energy Efficiency of a component of a network element. It can be used in the design,
  development, and manufacturing of energy efficient network elements. Here "Component Level" is
  equivalent to "Sub-System Level", which is considered as an "abstract " or "incomplete specification"
  of a portion of a system from the measurement and reporting point of view.
  
: CLEE is useful to evaluate the energy efficiency performance of individual components of a network element.

: Measuring and understanding the energy efficiency or energy consumption of each component within
  a network element may be used to identify key components in a system with regard to energy saving.


# Sample Energy Efficiency Metrics and Measurement Methods {#sec-metrics}

This section lists some metrics that are adopted by other SDOs.

> DISCUSS: Should we maintain this section?

## Metrics for DSLAM, MSAN, GPON, and GEPON Equipment

Equipment with line cards working at different profiles/states are characterized with different
metric values for each specific profile/state.

                          Pport = Peq/Nports[W/port]

Where 'Peq' is the power (in watts) of a fully equipped wireline network equipment with all its line cards
working in a specific profile/state. The formula is defined in {{L.1310}}.

## Metric for Wireless Access Technologies

The energy efficiency metric at Radio Frequency (RF) unit level is as follows:

                         EErfu = Eoutput/Erfu

Where:

* 'Eoutput' is daily RF output energy consumption [Wh] under different load.
* 'Erfu' is daily RF units energy consumption [Wh] under different load.

The formula is defined in {{L.1310}}.

## Metrics for Routers and Ethernet Switches

The metric for routers and Ethernet switches is as follows:

                        EER = Ti/Pw [Mbit/s/W]

Where 'Ti' is NDR throughput, 'Pw' is weighted power (energy consumption rate). The formula is defined in {{L.1310}}.

                        Pw = a*Pu1 + b*Pu2 + c*Pu3

Where:

* 'a'/'b'/'c' are the relative weight at different usage percentage with  `a+b+c=1`.

* 'Pu1'/'Pu2'/'Pu3' are the power at different usage percentage.

## Metrics for Small Network Devices

A metric for small networking devices intended for home/domestic or small office use is as follows:

                       EER = Ti/Pw [Mbit/s/W]

Where Ti is NDR throughput between wide area network (WAN) and local area network (LAN) ports
in the ingress direction, Pw is the average power during Full load, Idle load and Low power, the formula is defined in {{L.1310}}.

                      Ti = 0.35T_idle+0.5T_lowpower+0.15T_maximum
                      Pw = 0.35P_idle+0.5P_lowpower+0.15P_maximum

where:

* (0.35,0.5,0.15) is the relative weight at different usage mode.

* 'P_idle'/'P_lowpower'/'P_maximum' is the average power at different usage mode.

* 'T_idle'/'T_lowpower'/'T_maximum' is NDR throughput at different usage mode.

## Metric for Power Equipment

                               δ = Po/Pi

Where:

* 'Po' is output power.

* 'Pi' is input power.

This energy efficiency value is measured or calculated from the testing data over a given time period.
The formula is defined in {{L.1320}}.

## Metric for Cooling Equipment

                              η = Qt/Pi

Where:

* 'η' is the energy efficiency of the air conditioner.

* 'Pi' is the input power.

* 'Qt' is the sum of the sensible cooling capacity and the latent cooling capacity.

The formula is defined in {{L.1320}}.

# Operations and Manageability Considerations

This document defines terminology intended to ensure consistency among various efforts and deployment levels. No other operations or manageability requirements are introduced by this document.

# Security Considerations

Security is not discussed in this document.

--- back

# Standards Bodies and Standards {#sec-sdos}

This appendix provides a list of SDOs where relevant energy efficiency effort is ongoing.
This appendix does not aim to be comprehensive. The appendix may be removed in future versions of the document.

## ITU-T SG5

ITU-T Study Group 5 (SG5) has already worked on developing standards on energy efficiency.
ITU-T SG5 has many standards in the environment efficiency field. These standards include {{L.1310}}, {{L.1315}},
{{L.1316}}, and {{L.1320}} covering energy efficiency terminology, framework, metrics, and measurement methods.

ITU-T SG5 is also responsible for other standards that might be of interest to protocol developers
and network operators. For example:

* {{L.1331}} specifies assessment of mobile network energy efficiency.
* {{L.1333}} specifies the correlation between the carbon intensity indicator and energy efficiency metric. The
   carbon KPI defined in {{L.1333}} refers to the energy efficiency metric defined in ITU-T L.1331.
* {{L.1410}} focuses on the assessment of the environmental impact of information and communication technology (ICT)
  goods, networks and services. It provides specific guidance on energy and greenhouse gas (GHG) impacts.


## ETSI TCEE

ETSI Technical Committee (TC) Environment Engineering (EE) is collaborating with ITU-T SG5 to develop technically
aligned standards on energy efficiency and environment aspect. These standards include energy efficiency, power
feeding solution, circular economy and network efficiency KPI and eco-design requirement for ICT, with the aim to
build an international eco-environmental standardization.

{{ETSI-ES-203-136}} defines the energy consumption metrics and measurement methods for router and Ethernet switch
equipment. It specifies a methodology and the test conditions to measure the power consumption of router and switch
equipment and is also applicable to Core, edge, and access routers.


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

Specifically, {{TS28.554}} defines a number of energy efficiency KPIs, including a generic Network Slice Energy Efficiency
KPI, defined as the ratio between the performance of the network slice and its energy consumption.

# Changes between Revisions

   v02 - v03

   * Update Energy Efficiency Capability Definition.

   * Change Marisol's affiliation.

   v01 - v02

   * Add one new section on Operations and Manageability Considerations;

   * Add three new energy efficiency related terms based on comments raised during the interim meeting;

   * Update 4 existing terms such as energy efficiency definition, energy efficiency metric, energy efficiency capabilities
     energy proportionality based on comments raised on the list.

# Acknowledgments

This work has benefited from the discussions that occurred during GREEN interim meeting and on GREEN mailing list.
Thanks Benoit Claise, Gen Chen, Emile Stephan, Rob Wilton for valuable review and comments. Thanks Peter Liu for helping
provide input to initial version of the draft.
