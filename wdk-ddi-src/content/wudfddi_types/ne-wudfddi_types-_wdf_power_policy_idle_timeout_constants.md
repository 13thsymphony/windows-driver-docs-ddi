---
UID: NE.wudfddi_types._WDF_POWER_POLICY_IDLE_TIMEOUT_CONSTANTS
title: _WDF_POWER_POLICY_IDLE_TIMEOUT_CONSTANTS
author: windows-driver-content
description: The WDF_POWER_POLICY_IDLE_TIMEOUT_CONSTANTS enumeration is reserved for internal use.
old-location: wdf\wdf_power_policy_idle_timeout_constants.htm
old-project: wdf
ms.assetid: a707c7b9-2fc9-48c8-9492-b911c126668b
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: _WDF_POWER_POLICY_IDLE_TIMEOUT_CONSTANTS, WDF_POWER_POLICY_IDLE_TIMEOUT_CONSTANTS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wudfddi_types.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 1.9
req.alt-api: WDF_POWER_POLICY_IDLE_TIMEOUT_CONSTANTS
req.alt-loc: wdfdevice.h,wudfddi_types.h
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
req.product: Windows 10 or later.
---

# _WDF_POWER_POLICY_IDLE_TIMEOUT_CONSTANTS enumeration



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_POWER_POLICY_IDLE_TIMEOUT_CONSTANTS</b> enumeration is reserved for internal use.



## -syntax

````
typedef enum _WDF_POWER_POLICY_IDLE_TIMEOUT_CONSTANTS { 
  IdleTimeoutDefaultConstant  = 0
} WDF_POWER_POLICY_IDLE_TIMEOUT_CONSTANTS;
````


## -enum-fields

### -field IdleTimeoutDefaultConstant

For internal use only.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum KMDF version

</th>
<td width="70%">
1.0

</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
1.9

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdfdevice.h (include Wdf.h); </dt>
<dt>Wudfddi_types.h</dt>
</dl>
</td>
</tr>
</table>