---
UID: NF.poscx.PosCxOpen
title: PosCxOpen function
author: windows-driver-content
description: PosCxOpen is called to create an open PosCx library instance. This function initializes all resources it needs to manage a single open instance. It should be called from the driver's EVT_WDF_DEVICE_FILE_CREATE callback.
old-location: pos\poscxopen.htm
old-project: pos
ms.assetid: 6AB1BB0A-B350-44D7-B0D0-9A19FD6DEE19
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: PosCxOpen
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
req.alt-api: PosCxOpen
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

# PosCxOpen function



## -description
PosCxOpen is called to create an open PosCx library instance. This function initializes all resources it needs to manage a single open instance. It should be called from the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_file_create.md">EVT_WDF_DEVICE_FILE_CREATE</a>   callback.



## -syntax

````
NTSTATUS PosCxOpen(
  _In_ WDFDEVICE     device,
  _In_ WDFFILEOBJECT fileObject,
  _In_ ULONG         deviceInterfaceTag
);
````


## -parameters

### -param device [in]

A handle to a framework device object that represents the device.


### -param fileObject [in]

A handle to a framework file object that identifies the caller associated with the open instance.


### -param deviceInterfaceTag [in]

An identifier used to specify the caller's device interface in a multi-function device.  For a single-interface device, this value should be 0.


## -returns
An appropriate NTSTATUS error code that indicates the open instance completion status.


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