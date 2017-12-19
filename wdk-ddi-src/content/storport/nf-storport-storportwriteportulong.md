---
UID: NF.storport.StorPortWritePortUlong
title: StorPortWritePortUlong function
author: windows-driver-content
description: The StorPortWritePortUlong routine writes a value to a specified register address.
old-location: storage\storportwriteportulong.htm
old-project: storage
ms.assetid: 7c6d61c6-40e5-46fd-8c18-1f9d89c58515
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: StorPortWritePortUlong
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
req.alt-api: StorPortWritePortUlong
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

# StorPortWritePortUlong function



## -description
The <b>StorPortWritePortUlong</b> routine writes a value to a specified register address. 



## -syntax

````
STORPORT_API VOID StorPortWritePortUlong(
  _In_ PVOID  HwDeviceExtension,
  _In_ PULONG Port,
  _In_ ULONG  Value
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
For more information, see <a href="storage.scsiportwriteportulong">ScsiPortWritePortUlong</a>. For a buffered equivalent of this routine, see <a href="storage.storportwriteportbufferulong">StorPortWritePortBufferUlong</a>. 


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
<a href="storage.scsiportwriteportulong">ScsiPortWritePortUlong</a>
</dt>
<dt>
<a href="storage.storportwriteportbufferulong">StorPortWritePortBufferUlong</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortWritePortUlong routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

