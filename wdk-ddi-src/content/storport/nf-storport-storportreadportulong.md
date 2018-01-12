---
UID: NF:storport.StorPortReadPortUlong
title: StorPortReadPortUlong function
author: windows-driver-content
description: The StorPortReadPortUlong routine reads a value from a specified port address.
old-location: storage\storportreadportulong.htm
old-project: storage
ms.assetid: b04ef64a-cf1f-4de5-acb3-e57687f64719
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: StorPortReadPortUlong
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
req.alt-api: StorPortReadPortUlong
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
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortReadPortUlong function



## -description
The <b>StorPortReadPortUlong</b> routine reads a value from a specified port address. 



## -syntax

````
STORPORT_API ULONG StorPortReadPortUlong(
  _In_ PVOID  HwDeviceExtension,
  _In_ PULONG Port
);
````


## -parameters

### -param HwDeviceExtension [in]

Pointer to the hardware device extension.


### -param Port [in]

Pointer to the address from which to read. 


## -returns
<b>StorPortReadPortUlong</b> returns a data item of length <b>sizeof</b>(ULONG).


## -remarks
For more information, see the <a href="..\srb\nf-srb-scsiportreadportulong.md">ScsiPortReadPortUlong</a> routine. For a buffered version of this routine see <a href="..\storport\nf-storport-storportreadportbufferulong.md">StorPortReadPortBufferUlong</a>.


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
<a href="..\srb\nf-srb-scsiportreadportbufferulong.md">ScsiPortReadPortBufferUlong</a>
</dt>
<dt>
<a href="..\storport\nf-storport-storportreadportulong.md">StorPortReadPortUlong</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortReadPortUlong routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

