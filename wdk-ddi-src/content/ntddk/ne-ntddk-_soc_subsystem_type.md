---
UID : NE:ntddk._SOC_SUBSYSTEM_TYPE
title : "_SOC_SUBSYSTEM_TYPE"
author : windows-driver-content
description : The SOC_SYBSYSTEM_TYPE enumeration defines different types of System on a Chip (SoC) subsystems.
old-location : whea\soc_sybsystem_type.htm
old-project : whea
ms.assetid : 179D61E3-C2EE-4821-93F8-DB763892DD3D
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : SOC_SUBSYSTEM_TYPE enumeration [WHEA Drivers and Applications], ntddk/SOC_SUBSYS_VENDOR_DEFINED, ntddk/SOC_SUBSYS_SENSORS, SOC_SUBSYS_WIRELSS_CONNECTIVITY, SOC_SUBSYS_SENSORS, ntddk/SOC_SUBSYSTEM_TYPE, _SOC_SUBSYSTEM_TYPE, SOC_SUBSYSTEM_TYPE, SOC_SUBSYS_AUDIO_DSP, SOC_SUBSYS_VENDOR_DEFINED, ntddk/SOC_SUBSYS_WIRELSS_CONNECTIVITY, SOC_SUBSYSTEM_WIRELESS_MODEM, *PSOC_SUBSYSTEM_TYPE, whea.soc_sybsystem_type, ntddk/SOC_SUBSYSTEM_WIRELESS_MODEM, ntddk/SOC_SUBSYS_AUDIO_DSP
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : ntddk.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 8
req.target-min-winversvr : Windows Server 2012
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PSOC_SUBSYSTEM_TYPE, SOC_SUBSYSTEM_TYPE"
---

# _SOC_SUBSYSTEM_TYPE Enumeration
The <b>SOC_SYBSYSTEM_TYPE</b> enumeration defines different types of System on a Chip (SoC) subsystems.

The <b>SybsysType</b> member of the <a href="..\ntddk\ns-ntddk-_soc_subsystem_failure_details.md">SOC_SUBSYSTEM_FAILURE_DETAILS</a> structure is a value from this enumeration. The <b>SOC_SUBSYSTEM_FAILURE_DETAILS</b> structure is used by these bug codes:
<ul>
<li>
<a href="https://msdn.microsoft.com/CC42D634-90CE-43F1-8552-E5DE711D2117">Bug Check 0x14B SOC_SUBSYSTEM_FAILURE</a>
</li>
<li>
<a href="https://msdn.microsoft.com/F7903E88-1706-46E6-A5D0-6972702058A8">Bug Check 0x15D SOC_SUBSYSTEM_FAILURE_LIVEDUMP</a>
</li>
</ul>

## Syntax
````
typedef enum _SOC_SUBSYSTEM_TYPE { 
  SOC_SUBSYSTEM_WIRELESS_MODEM     = 0,
  SOC_SUBSYS_AUDIO_DSP             = 1,
  SOC_SUBSYS_WIRELSS_CONNECTIVITY  = 2,
  SOC_SUBSYS_SENSORS               = 3,
  SOC_SUBSYS_VENDOR_DEFINED        = 0x10000
} SOC_SUBSYSTEM_TYPE;
````

## Constants

<table>

<tr>
<td>SOC_SUBSYS_AUDIO_DSP</td>
<td>Audio digital signal processor (DSP)</td>
</tr>

<tr>
<td>SOC_SUBSYS_SENSORS</td>
<td>Sensors</td>
</tr>

<tr>
<td>SOC_SUBSYS_VENDOR_DEFINED</td>
<td>Subsystem types in the range 0x10000 through 0x80000000 are reserved for independent hardware vendors.</td>
</tr>

<tr>
<td>SOC_SUBSYS_WIRELESS_MODEM</td>
<td></td>
</tr>

<tr>
<td>SOC_SUBSYS_WIRELSS_CONNECTIVITY</td>
<td>Wireless connectivity</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddk.h |