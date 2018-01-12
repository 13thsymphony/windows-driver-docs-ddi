---
UID: NE:ucmtypes._UCM_PD_POWER_DATA_OBJECT_TYPE
title: _UCM_PD_POWER_DATA_OBJECT_TYPE
author: windows-driver-content
description: Defines Power Data Object types.
old-location: buses\ucm_pd_power_data_object_type.htm
old-project: usbref
ms.assetid: FCDD6B04-339D-4BBA-9D19-AE74CCB27666
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _UCM_PD_POWER_DATA_OBJECT_TYPE, UCM_PD_POWER_DATA_OBJECT_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ucmtypes.h
req.include-header: Ucmcx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 2.15
req.alt-api: UCM_PD_POWER_DATA_OBJECT_TYPE
req.alt-loc: Ucmtypes.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.typenames: UCM_PD_POWER_DATA_OBJECT_TYPE
req.product: Windows 10 or later.
---

# _UCM_PD_POWER_DATA_OBJECT_TYPE enumeration



## -description
Defines Power Data Object types.



## -syntax

````
typedef enum _UCM_PD_POWER_DATA_OBJECT_TYPE { 
  UcmPdPdoTypeFixedSupply               = 0,
  UcmPdPdoTypeBatterySupply             = 1,
  UcmPdPdoTypeVariableSupplyNonBattery  = 2
} UCM_PD_POWER_DATA_OBJECT_TYPE;
````


## -enum-fields

### -field UcmPdPdoTypeFixedSupply

Indicates the PD data object type is a fixed supply.


### -field UcmPdPdoTypeBatterySupply

Indicates the PD data object type is a battery supply.


### -field UcmPdPdoTypeVariableSupplyNonBattery

Indicates the PD data object type is a non-battery variable supply.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2016

</td>
</tr>
<tr>
<th width="30%">
Minimum KMDF version

</th>
<td width="70%">
1.15

</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
2.15

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ucmtypes.h (include Ucmcx.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ucmtypes\nf-ucmtypes-ucm_pd_power_data_object_get_type.md">UCM_PD_POWER_DATA_OBJECT_GET_TYPE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCM_PD_POWER_DATA_OBJECT_TYPE enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

