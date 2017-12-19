---
UID: NF.wdfdevice.WdfDeviceRetrieveCompanionTarget
title: WdfDeviceRetrieveCompanionTarget function
author: windows-driver-content
description: For internal use only.
old-location: wdf\wdfdeviceretrievecompaniontarget.htm
old-project: wdf
ms.assetid: 2ca34fb7-72c1-4253-ad5b-bc829a1ba540
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: WdfDeviceRetrieveCompanionTarget
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.23
req.umdf-ver: 
req.alt-api: WdfDeviceRetrieveCompanionTarget
req.alt-loc: wdfdevice.h
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
req.product: Windows 10 or later.
---

# WdfDeviceRetrieveCompanionTarget function



## -description
For internal use only.



## -syntax

````
NTSTATUS WdfDeviceRetrieveCompanionTarget(
  _In_  WDFDEVICE          Device,
  _Out_ WDFCOMPANIONTARGET *CompanionTarget
);
````


## -parameters

### -param Device [in]


### -param CompanionTarget [out]


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum KMDF version

</th>
<td width="70%">
1.23

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdfdevice.h</dt>
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