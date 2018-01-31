---
UID : NE:ucmtypes._UCM_PD_POWER_DATA_OBJECT_TYPE
title : "_UCM_PD_POWER_DATA_OBJECT_TYPE"
author : windows-driver-content
description : Defines Power Data Object types.
old-location : buses\ucm_pd_power_data_object_type.htm
old-project : usbref
ms.assetid : FCDD6B04-339D-4BBA-9D19-AE74CCB27666
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : UCM_PD_POWER_DATA_OBJECT_TYPE, buses.ucm_pd_power_data_object_type, UcmPdPdoTypeFixedSupply, UcmPdPdoTypeVariableSupplyNonBattery, ucmtypes/UCM_PD_POWER_DATA_OBJECT_TYPE, UcmPdPdoTypeBatterySupply, _UCM_PD_POWER_DATA_OBJECT_TYPE, UCM_PD_POWER_DATA_OBJECT_TYPE enumeration [Buses], ucmtypes/UcmPdPdoTypeVariableSupplyNonBattery, ucmtypes/UcmPdPdoTypeBatterySupply, ucmtypes/UcmPdPdoTypeFixedSupply
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : ucmtypes.h
req.include-header : Ucmcx.h
req.target-type : Windows
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : Windows Server 2016
req.kmdf-ver : 1.15
req.umdf-ver : 2.15
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
req.typenames : UCM_PD_POWER_DATA_OBJECT_TYPE
req.product : Windows 10 or later.
---

# _UCM_PD_POWER_DATA_OBJECT_TYPE Enumeration
Defines Power Data Object types.

## Syntax
````
typedef enum _UCM_PD_POWER_DATA_OBJECT_TYPE { 
  UcmPdPdoTypeFixedSupply               = 0,
  UcmPdPdoTypeBatterySupply             = 1,
  UcmPdPdoTypeVariableSupplyNonBattery  = 2
} UCM_PD_POWER_DATA_OBJECT_TYPE;
````

## Constants

<table>

<tr>
<td>UcmPdPdoTypeBatterySupply</td>
<td>Indicates the PD data object type is a battery supply.</td>
</tr>

<tr>
<td>UcmPdPdoTypeFixedSupply</td>
<td>Indicates the PD data object type is a fixed supply.</td>
</tr>

<tr>
<td>UcmPdPdoTypeVariableSupplyNonBattery</td>
<td>Indicates the PD data object type is a non-battery variable supply.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** | 1.15 |
| **Minimum UMDF version** | 2.15 |
| **Header** | ucmtypes.h (include Ucmcx.h) |

## See Also

<a href="..\ucmtypes\nf-ucmtypes-ucm_pd_power_data_object_get_type.md">UCM_PD_POWER_DATA_OBJECT_GET_TYPE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCM_PD_POWER_DATA_OBJECT_TYPE enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>