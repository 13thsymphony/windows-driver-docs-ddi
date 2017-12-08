---
UID: NF.poscx.PosCxIsPosApp
title: PosCxIsPosApp function
author: windows-driver-content
description: PosCxIsPosApp checks if the open instance is associated with a point-of-service application.
old-location: pos\poscxisposapp.htm
old-project: pos
ms.assetid: 890A0ACB-9717-4BF8-87B5-A6C1FAD661C2
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: PosCxIsPosApp
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: poscx.h
req.include-header: Poscx.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PosCxIsPosApp
req.alt-loc: poscx.h
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

# PosCxIsPosApp function



## -description
PosCxIsPosApp checks if the open instance is associated with a point-of-service application.


## -syntax

````
BOOLEAN PosCxIsPosApp(
  _In_ WDFDEVICE     device,
  _In_ WDFFILEOBJECT fileObject
);
````


## -parameters

### -param device [in]

A handle to a framework device object that represents the device.

### -param fileObject [in]

A handle to a framework file object that identifies the caller, usually acquired with <a href="wdf.wdfrequestgetfileobject">WdfRequestGetFileObject</a>.

## -returns
Returns TRUE if <i>fileObject</i> is associated with a point-of-service application. Otherwise, returns FALSE.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Product
</th>
<td width="70%">
Windows 10 or later.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Poscx.h (include Poscx.h)</dt>
</dl>
</td>
</tr>
</table>