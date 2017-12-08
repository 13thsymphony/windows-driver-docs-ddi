---
UID: NF.poscx.PosCxMarkPosApp
title: PosCxMarkPosApp function
author: windows-driver-content
description: PosCxMarkPosApp marks the open instance as associated or not associated with a point-of-service application.
old-location: pos\poscxmarkposapp.htm
old-project: pos
ms.assetid: 6BFFD014-E9DC-495C-9810-0D23BD93C41A
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: PosCxMarkPosApp
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
req.alt-api: PosCxMarkPosApp
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

# PosCxMarkPosApp function



## -description
PosCxMarkPosApp marks the open instance as associated or not associated with a point-of-service application.
This optional method provides value if the driver implements multiple device interfaces. It helps to  identify which interface is currently in use.


## -syntax

````
NTSTATUS PosCxMarkPosApp(
  _In_ WDFDEVICE     device,
  _In_ WDFFILEOBJECT fileObject,
  _In_ BOOLEAN       isPosApp
);
````


## -parameters

### -param device [in]

A handle to a framework device object that represents the device.

### -param fileObject [in]

A handle to a framework file object that identifies the caller, usually acquired with <a href="wdf.wdfrequestgetfileobject">WdfRequestGetFileObject</a>.

### -param isPosApp [in]

Specifies if the open instance is associated with a point-of-service application. Set to TRUE if it is associated with a point-of-service application. Otherwise, set to FALSE.

## -returns
Possible return values are:

 

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