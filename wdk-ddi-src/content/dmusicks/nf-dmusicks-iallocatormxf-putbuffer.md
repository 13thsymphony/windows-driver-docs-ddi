---
UID: NF.dmusicks.IAllocatorMXF.PutBuffer
title: IAllocatorMXF::PutBuffer method
author: windows-driver-content
description: This method is not currently used by the miniport driver. The PutBuffer method passes a buffer to the allocator, but this occurs automatically when IMXF::PutMessage is called anyway.
old-location: audio\iallocatormxf_putbuffer.htm
old-project: audio
ms.assetid: 20daf292-9476-4435-915d-f97fba3a6ec2
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IAllocatorMXF, IAllocatorMXF::PutBuffer, PutBuffer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dmusicks.h
req.include-header: Dmusicks.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IAllocatorMXF.PutBuffer
req.alt-loc: dmusicks.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
---

# IAllocatorMXF::PutBuffer method



## -description

   This method is not currently used by the miniport driver. The <code>PutBuffer</code> method passes a buffer to the allocator, but this occurs automatically when <a href="audio.imxf_putmessage">IMXF::PutMessage</a> is called anyway.



## -syntax

````
NTSTATUS PutBuffer(
  [in] PBYTE pbBuffer
);
````


## -parameters

### -param pbBuffer [in]

Pointer to the buffer being passed to the allocator


## -returns
<code>PutBuffer</code> returns S_OK if the call was successful. Otherwise, the method returns an appropriate error code.


## -remarks
The miniport driver does not need to use this method because when the miniport driver calls <a href="audio.imxf_putmessage">IMXF::PutMessage</a>, the allocator looks at the <b>cbEvent</b> member of the <a href="audio.dmus_kernel_event">DMUS_KERNEL_EVENT</a> structure to determine if <b>uData</b> is a pointer or just data. If <b>cbEvent</b> specifies that the event data is greater than the storage capacity of <b>uData</b> (4 bytes on a 32-bit system and 8 bytes on a 64-bit system), the allocator simply assumes that <b>uData</b> points to a buffer that can be reused.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Dmusicks.h (include Dmusicks.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;=DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\dmusicks\nn-dmusicks-iallocatormxf~r1.md">IAllocatorMXF</a>
</dt>
<dt>
<a href="audio.imxf_putmessage">IMXF::PutMessage</a>
</dt>
<dt>
<a href="audio.dmus_kernel_event">DMUS_KERNEL_EVENT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IAllocatorMXF::PutBuffer method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

