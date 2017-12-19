---
UID: NF.portcls.IPortWaveRTStream.GetPhysicalPagesCount
title: IPortWaveRTStream::GetPhysicalPagesCount method
author: windows-driver-content
description: The GetPhysicalPagesCount method returns the count of the physical pages in a memory descriptor list (MDL).
old-location: audio\iportwavertstream_getphysicalpagescount.htm
old-project: audio
ms.assetid: 8126af29-a7ee-4ab7-8902-45b4baf33b9e
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IPortWaveRTStream, IPortWaveRTStream::GetPhysicalPagesCount, GetPhysicalPagesCount
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPortWaveRTStream.GetPhysicalPagesCount
req.alt-loc: Portcls.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Passive level.
---

# IPortWaveRTStream::GetPhysicalPagesCount method



## -description
The <code>GetPhysicalPagesCount</code> method returns the count of the physical pages in a memory descriptor list (<a href="kernel.mdl">MDL</a>).



## -syntax

````
ULONG GetPhysicalPagesCount(
  [in] PMDL MemoryDescriptorList
);
````


## -parameters

### -param MemoryDescriptorList [in]

Pointer to the MDL.


## -returns
<code>GetPhysicalPagesCount</code> method returns the count of physical pages in the MDL.


## -remarks
The miniport driver uses this call to determine the number of physical pages that are contained within an MDL. The count is typically used in the process of programming the DMA hardware.


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
Version

</th>
<td width="70%">
Available in Windows Vista and later Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Portcls.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
Passive level.

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\portcls\nn-portcls-iportwavertstream.md">IPortWaveRTStream</a>
</dt>
<dt>
<a href="audio.iportwavertstream_allocatepagesformdl">IPortWaveRTStream::AllocatePagesForMdl</a>
</dt>
<dt>
<a href="audio.iportwavertstream_allocatecontiguouspagesformdl">IPortWaveRTStream::AllocateContiguousPagesForMdl</a>
</dt>
<dt>
<a href="audio.iportwavertstream_getphysicalpageaddress">IPortWaveRTStream::GetPhysicalPageAddress</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IPortWaveRTStream::GetPhysicalPagesCount method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

