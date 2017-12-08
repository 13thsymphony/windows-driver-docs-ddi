---
UID: NF.poscx.PosCxClose
title: PosCxClose function
author: windows-driver-content
description: PosCxClose is called to delete an opened PosCx library instance. This function releases the device if the caller is the owner, and cancels pending requests. It should be called from the driver's EVT_WDF_FILE_CLOSE callback.
old-location: pos\poscxclose.htm
old-project: pos
ms.assetid: 90D097B9-EE7B-49FA-B0F7-6A255D140C06
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: PosCxClose
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
req.alt-api: PosCxClose
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

# PosCxClose function



## -description
      PosCxClose is called to delete an opened PosCx library instance. This function releases the device if the caller is the owner, 

      and cancels pending requests. It should be called from 

      the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_file_close.md">EVT_WDF_FILE_CLOSE</a> callback.


## -syntax

````
NTSTATUS PosCxClose(
  _In_ WDFDEVICE     device,
  _In_ WDFFILEOBJECT fileObject
);
````


## -parameters

### -param device [in]

A handle to a framework device object that represents the device.

### -param fileObject [in]

      A handle to a framework file object that identifies the caller associated with the open instance.

## -returns
An appropriate NTSTATUS error code that indicates the close instance completion status.

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