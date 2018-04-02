---
UID: NF:portcls.IPortWaveRTStream.GetPhysicalPageAddress
title: IPortWaveRTStream::GetPhysicalPageAddress method
author: windows-driver-content
description: The GetPhysicalPageAddress method returns the physical address for a page within a memory descriptor list (MDL).
old-location: audio\iportwavertstream_getphysicalpageaddress.htm
old-project: audio
ms.assetid: 24c22102-f91d-4ea1-81fb-98052b8d0153
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: GetPhysicalPageAddress method [Audio Devices], GetPhysicalPageAddress method [Audio Devices], IPortWaveRTStream interface, GetPhysicalPageAddress,IPortWaveRTStream.GetPhysicalPageAddress, IPortWaveRTStream, IPortWaveRTStream interface [Audio Devices], GetPhysicalPageAddress method, IPortWaveRTStream::GetPhysicalPageAddress, audio.iportwavertstream_getphysicalpageaddress, audmp-routines_44b6b9ed-368b-4bf1-9a21-e0e0b2b90728.xml, portcls/IPortWaveRTStream::GetPhysicalPageAddress
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
req.irql: Passive level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Portcls.h
api_name:
-	IPortWaveRTStream.GetPhysicalPageAddress
product:
- Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# IPortWaveRTStream::GetPhysicalPageAddress method
The <code>GetPhysicalPageAddress</code> method returns the physical address for a page within a memory descriptor list (<a href="https://msdn.microsoft.com/library/windows/hardware/ff554414">MDL</a>).

## Syntax

```
PHYSICAL_ADDRESS GetPhysicalPageAddress(
  PMDL  MemoryDescriptorList,
  ULONG Index
);
```

## Parameters

`MemoryDescriptorList`

Pointer to the MDL.

`Index`

Index to the target page within the MDL.


## Return Value

The <code>GetPhysicalPageAddress</code> method returns the physical address for a page within an MDL.

## Remarks

The miniport driver calls this method to determine the physical memory address for pages within an MDL that was previously allocated by calling either <a href="https://msdn.microsoft.com/library/windows/hardware/ff536925">IPortWaveRTStream::AllocatePagesForMdl</a> or <b>IPortWaveRTStream::AllocateContiguousPagesForMdl</b>.

The miniport typically calls this for each page in the MDL in order to program the physical address into the DMA.  The <i>Index</i> parameter is used to select the desired page, and can range from zero to the count returned by <a href="https://msdn.microsoft.com/8126af29-a7ee-4ab7-8902-45b4baf33b9e">GetPhysicalPagesCount</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later Windows operating systems.  |
| **Target Platform** | Universal |
| **Header** | portcls.h |
| **IRQL** | Passive level |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536922">IPortWaveRTStream</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536924">IPortWaveRTStream::AllocateContiguousPagesForMdl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536925">IPortWaveRTStream::AllocatePagesForMdl</a>



<a href="https://msdn.microsoft.com/8126af29-a7ee-4ab7-8902-45b4baf33b9e">IPortWaveRTStream::GetPhysicalPagesCount </a>