---
UID: NF:wdfcompanion.WdfCompanionWdmGetSecureDeviceHandle
title: WdfCompanionWdmGetSecureDeviceHandle function
author: windows-driver-content
description: For internal use only.
old-location: wdf\wdfcompanionwdmgetsecuredevicehandle.htm
old-project: wdf
ms.assetid: 8fc3dc6f-8a21-490b-adbf-5f735cb953de
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: WdfCompanionWdmGetSecureDeviceHandle
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfcompanion.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 2.23
req.alt-api: WdfCompanionWdmGetSecureDeviceHandle
req.alt-loc: wdfcompanion.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: WDF_TASK_QUEUE_DISPATCH_TYPE
req.product: Windows 10 or later.
---

# WdfCompanionWdmGetSecureDeviceHandle function



## -description

			For internal use only.



## -syntax

````
HANDLE WdfCompanionWdmGetSecureDeviceHandle(
  _In_ WDFCOMPANION Companion
);
````


## -parameters

### -param Companion [in]


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
2.23

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdfcompanion.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>