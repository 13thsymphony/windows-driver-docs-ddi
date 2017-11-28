---
UID: NF.ucmtypes.UCM_PD_POWER_DATA_OBJECT_INIT_VARIABLE_NON_BATTERY
title: UCM_PD_POWER_DATA_OBJECT_INIT_VARIABLE_NON_BATTERY
author: windows-driver-content
description: Initializes a UCM_PD_POWER_DATA_OBJECT structure as a Variable Supply Non Battery type Power Data Object.
old-location: buses\ucm_pd_power_data_object_init_variable_non_battery.htm
old-project: usbref
ms.assetid: BBC8975A-E5B1-4137-83D8-891075A8F4D0
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: UCM_PD_POWER_DATA_OBJECT_INIT_VARIABLE_NON_BATTERY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ucmtypes.h
req.include-header: Ucmcx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 2.15
req.alt-api: UCM_PD_POWER_DATA_OBJECT_INIT_VARIABLE_NON_BATTERY
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
req.iface: 
req.product: Windows 10 or later.
---

# UCM_PD_POWER_DATA_OBJECT_INIT_VARIABLE_NON_BATTERY function



## -description
<p>Initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/mt187935">UCM_PD_POWER_DATA_OBJECT</a> structure as a Variable Supply Non Battery type Power Data Object.</p>


## -syntax

````
FORCEINLINE void UCM_PD_POWER_DATA_OBJECT_INIT_VARIABLE_NON_BATTERY(
  _Out_ PUCM_PD_POWER_DATA_OBJECT Pdo
);
````


## -parameters
<dl>

### -param <i>Pdo</i> [out]

<dd>
<p>A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt187935">UCM_PD_POWER_DATA_OBJECT</a> structure in which the <b>VariableSupplyNonBatteryPdo.VariableSupportNonBattery</b> member is set to <b>UcmPdPdoTypeVariableSupplyNonBattery</b>.</p>
</dd>
</dl>

## -returns
<p>This function does not return a value.</p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 10</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2016</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum KMDF version</p>
</th>
<td width="70%">
<p>1.15</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum UMDF version</p>
</th>
<td width="70%">
<p>2.15</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/mt187935">UCM_PD_POWER_DATA_OBJECT</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCM_PD_POWER_DATA_OBJECT_INIT_VARIABLE_NON_BATTERY function%20 RELEASE:%20(11/20/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
