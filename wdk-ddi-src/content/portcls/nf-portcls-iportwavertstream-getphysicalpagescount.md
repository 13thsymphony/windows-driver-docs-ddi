---
UID: NF:portcls.IPortWaveRTStream.GetPhysicalPagesCount
title: IPortWaveRTStream::GetPhysicalPagesCount method
author: windows-driver-content
description: The GetPhysicalPagesCount method returns the count of the physical pages in a memory descriptor list (MDL).
old-location: audio\iportwavertstream_getphysicalpagescount.htm
old-project: audio
ms.assetid: 8126af29-a7ee-4ab7-8902-45b4baf33b9e
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: GetPhysicalPagesCount method [Audio Devices], GetPhysicalPagesCount method [Audio Devices], IPortWaveRTStream interface, GetPhysicalPagesCount,IPortWaveRTStream.GetPhysicalPagesCount, IPortWaveRTStream, IPortWaveRTStream interface [Audio Devices], GetPhysicalPagesCount method, IPortWaveRTStream::GetPhysicalPagesCount, audio.iportwavertstream_getphysicalpagescount, audmp-routines_bdc74102-0337-436b-b3ac-68187fb323a4.xml, portcls/IPortWaveRTStream::GetPhysicalPagesCount
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Portcls.h
api_name:
-	IPortWaveRTStream.GetPhysicalPagesCount
product:
- Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# IPortWaveRTStream::GetPhysicalPagesCount method
The <code>GetPhysicalPagesCount</code> method returns the count of the physical pages in a memory descriptor list (<a href="https://msdn.microsoft.com/library/windows/hardware/ff554414">MDL</a>).

## Syntax

```
ULONG GetPhysicalPagesCount(
  PMDL MemoryDescriptorList
);
```

## Parameters

`MemoryDescriptorList`

Pointer to the MDL.


## Return Value

<code>GetPhysicalPagesCount</code> method returns the count of physical pages in the MDL.

## Remarks

The miniport driver uses this call to determine the number of physical pages that are contained within an MDL. The count is typically used in the process of programming the DMA hardware.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later Windows operating systems.  |
| **Target Platform** | Universal |
| **Header** | portcls.h |
| **IRQL** | Passive level. |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536922">IPortWaveRTStream</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536924">IPortWaveRTStream::AllocateContiguousPagesForMdl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536925">IPortWaveRTStream::AllocatePagesForMdl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536928">IPortWaveRTStream::GetPhysicalPageAddress</a>