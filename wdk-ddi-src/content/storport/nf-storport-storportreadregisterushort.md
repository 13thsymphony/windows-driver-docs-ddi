---
UID: NF:storport.StorPortReadRegisterUshort
title: StorPortReadRegisterUshort function
author: windows-driver-content
description: The StorPortReadRegisterUshort routine reads a value from a specified register address.
old-location: storage\storportreadregisterushort.htm
old-project: storage
ms.assetid: 11659e7d-db54-401c-a179-75cc5d411b55
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: StorPortReadRegisterUshort
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
req.alt-api: StorPortReadRegisterUshort
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

# StorPortReadRegisterUshort function



## -description
The <b>StorPortReadRegisterUshort</b> routine reads a value from a specified register address. 



## -syntax

````
STORPORT_API USHORT StorPortReadRegisterUshort(
  _In_ PVOID   HwDeviceExtension,
  _In_ PUSHORT Register
);
````


## -parameters

### -param HwDeviceExtension [in]

Pointer to the hardware device extension.


### -param Register [in]

Pointer to the register where the data is to be read. 


## -returns
<b>StorPortReadRegisterUshort</b> returns an unsigned character of data read from the indicated register address. 


## -remarks
For more information, see <a href="..\srb\nf-srb-scsiportreadregisterushort.md">ScsiPortReadRegisterUshort</a>. For a buffered version of this routine, see <a href="..\storport\nf-storport-storportreadregisterbufferushort.md">StorPortReadRegisterBufferUshort</a>.


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
<a href="..\srb\nf-srb-scsiportreadregisterushort.md">ScsiPortReadRegisterUshort</a>
</dt>
<dt>
<a href="..\storport\nf-storport-storportreadregisterbufferushort.md">StorPortReadRegisterBufferUshort</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortReadRegisterUshort routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

