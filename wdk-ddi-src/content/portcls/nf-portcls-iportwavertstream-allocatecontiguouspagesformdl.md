---
UID : NF:portcls.IPortWaveRTStream.AllocateContiguousPagesForMdl
title : IPortWaveRTStream::AllocateContiguousPagesForMdl method
author : windows-driver-content
description : The AllocateContiguousPagesForMdl method allocates a list of contiguous, nonpaged, physical memory pages and returns a pointer to a memory descriptor list (MDL) that describes them.
old-location : audio\iportwavertstream_allocatecontiguouspagesformdl.htm
old-project : audio
ms.assetid : 976f7e83-9b2a-4e1b-ab76-76d8e9711bff
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : IPortWaveRTStream, IPortWaveRTStream::AllocateContiguousPagesForMdl, AllocateContiguousPagesForMdl
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : portcls.h
req.include-header : 
req.target-type : Universal
req.target-min-winverclnt : Available in Windows Vista and later Windows operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IPortWaveRTStream.AllocateContiguousPagesForMdl
req.alt-loc : Portcls.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : Passive level
req.typenames : PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# AllocateContiguousPagesForMdl method
The <code>AllocateContiguousPagesForMdl</code> method allocates a list of contiguous, nonpaged, physical memory pages and returns a pointer to a memory descriptor list (<a href="..\wdm\ns-wdm-_mdl.md">MDL</a>) that describes them.

## Syntax

````
PMDL AllocateContiguousPagesForMdl(
  [in] PHYSICAL_ADDRESS LowAddress,
  [in] PHYSICAL_ADDRESS HighAddress,
  [in] SIZE_T           TotalBytes
);
````

## Parameters

`LowAddress`

Specifies the low end of the address range from which the storage for the MDL can be allocated.

`HighAddress`

Specifies the high end of the address range from which the storage for the MDL can be allocated.

`TotalBytes`

Specifies the total number of bytes to allocate for the MDL. This method always allocates an integral number of memory pages.


## Return Value

<code>AllocateContiguousPagesForMdl</code> returns a pointer to an MDL (PMDL) that describes a list of physical memory pages. If the method is unable to allocate the requested buffer, it returns <b>NULL</b>.

## Remarks

The driver calls this method to allocate a block of physically contiguous memory pages. All of the physical memory pages in the MDL fall within the address range specified by the <i>LowAddress</i> and <i>HighAddress</i> parameters. If sufficient memory is available, the memory allocation is the requested size rounded up to the next page; otherwise, the call fails.

After a system has been running for some time, the system's pool of nonpaged memory tends to become fragmented, which increases the probability that a request to allocate a large block of contiguous physical memory will fail. If the DMA controller of the audio device does not require the physical memory pages to be contiguous, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff536925">IPortWaveRTStream::AllocatePagesForMdl</a> instead. Unlike <code>AllocateContiguousPagesForMdl</code>, the <b>AllocatePagesForMdl</b> method is not affected by memory fragmentation.

The <code>AllocateContiguousPagesforMdl</code> method allocates memory pages that are locked (nonpaged) but unmapped. If the miniport driver requires software access to this memory, the miniport driver must make a subsequent call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff536932">IPortWaveRTStream::MapAllocatedPages</a> to map the pages into kernel-mode address space.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | portcls.h |
| **Library** |  |
| **IRQL** | Passive level |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\portcls\nn-portcls-iportwavertstream.md">IPortWaveRTStream</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536925">IPortWaveRTStream::AllocatePagesForMdl</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536932">IPortWaveRTStream::MapAllocatedPages</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IPortWaveRTStream::AllocateContiguousPagesForMdl method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>