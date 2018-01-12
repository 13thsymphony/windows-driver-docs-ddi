---
UID: NF:dmusicks.IAllocatorMXF.GetBufferSize
title: IAllocatorMXF::GetBufferSize method
author: windows-driver-content
description: The GetBufferSize method gets the buffer size from the allocator.
old-location: audio\iallocatormxf_getbuffersize.htm
old-project: audio
ms.assetid: b3a35769-a98a-40f5-bdc1-db964d2a967c
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IAllocatorMXF, IAllocatorMXF::GetBufferSize, GetBufferSize
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
req.alt-api: IAllocatorMXF.GetBufferSize
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
req.irql: Any level
req.typenames: DMUS_STREAM_TYPE
---

# IAllocatorMXF::GetBufferSize method



## -description
The <code>GetBufferSize</code> method gets the buffer size from the allocator.



## -syntax

````
USHORT GetBufferSize(
    None
);
````


## -parameters

### -param None 


## -returns
<code>GetBufferSize</code> returns the size in bytes of the buffer.


## -remarks
<code>GetBufferSize</code> simply returns the size of the buffer that the allocator provides through the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536492">IAllocatorMXF::GetBuffer</a> call. (For more information, see <a href="..\dmusicks\nn-dmusicks-iallocatormxf.md">IAllocatorMXF</a> introduction.) Because this is constant for any version of the port driver, <code>GetBufferSize</code> typically needs to be called only once, at the time that the stream is created.


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
Any level

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\dmusicks\nn-dmusicks-iallocatormxf.md">IAllocatorMXF</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536492">IAllocatorMXF::GetBuffer</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IAllocatorMXF::GetBufferSize method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

