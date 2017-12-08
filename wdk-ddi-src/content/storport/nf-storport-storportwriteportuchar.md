---
UID: NF.storport.StorPortWritePortUchar
title: StorPortWritePortUchar function
author: windows-driver-content
description: The StorPortWritePortUchar routine writes a value to a specified register address.
old-location: storage\storportwriteportuchar.htm
old-project: storage
ms.assetid: 421bd075-e919-4389-af38-e0dd686f7c05
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: StorPortWritePortUchar
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: StorPortWritePortUchar
req.alt-loc: Storport.lib,Storport.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Storport.lib
req.dll: 
req.irql: 
req.product: Windows 10 or later.
---

# StorPortWritePortUchar function



## -description
The <b>StorPortWritePortUchar</b> routine writes a value to a specified register address. 


## -syntax

````
STORPORT_API VOID StorPortWritePortUchar(
  _In_ PVOID  HwDeviceExtension,
  _In_ PUCHAR Port,
  _In_ UCHAR  Value
);
````


## -parameters

### -param HwDeviceExtension [in]

Pointer to the hardware device extension.

### -param Port [in]

Contains the address of the port to be written to. 

### -param Value [in]

Contains the value to be written. 

## -returns
None 

## -remarks
For more information, see <a href="storage.scsiportwriteportuchar">ScsiPortWritePortUchar</a>. For a buffered equivalent of this routine, see <a href="storage.storportwriteportbufferuchar">StorPortWritePortBufferUchar</a>. 

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Storport.h (include Storport.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Storport.lib</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.scsiportwriteportuchar">ScsiPortWritePortUchar</a>
</dt>
<dt>
<a href="storage.storportwriteportbufferuchar">StorPortWritePortBufferUchar</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortWritePortUchar routine%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
