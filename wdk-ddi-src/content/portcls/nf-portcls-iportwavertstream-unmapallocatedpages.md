---
UID: NF:portcls.IPortWaveRTStream.UnmapAllocatedPages
title: IPortWaveRTStream::UnmapAllocatedPages method
author: windows-driver-content
description: The UnmapAllocatedPages method releases a mapping.
old-location: audio\iportwavertstream_unmapallocatedpages.htm
old-project: audio
ms.assetid: 558636ed-4bab-42bc-8925-df01e032439a
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: IPortWaveRTStream::UnmapAllocatedPages, portcls/IPortWaveRTStream::UnmapAllocatedPages, UnmapAllocatedPages method [Audio Devices], audio.iportwavertstream_unmapallocatedpages, IPortWaveRTStream interface [Audio Devices], UnmapAllocatedPages method, UnmapAllocatedPages method [Audio Devices], IPortWaveRTStream interface, IPortWaveRTStream, audmp-routines_2d402b1b-6951-48db-89bb-81f3cc7e0076.xml, UnmapAllocatedPages
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
req.lib: portcls.h
req.dll: 
req.irql: Passive level.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Portcls.h
apiname:
-	IPortWaveRTStream.UnmapAllocatedPages
product: Windows
targetos: Windows
req.typenames: "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY"
---


# UnmapAllocatedPages method
The <code>UnmapAllocatedPages</code> method releases a mapping.

## Syntax

````
VOID UnmapAllocatedPages(
  [in] PVOID BaseAddress,
  [in] PMDL  MemoryDescriptorList
);
````

## Parameters

`BaseAddress`

Pointer to the base virtual address to which the physical pages were mapped.

`MemoryDescriptorList`

Pointer to a memory descriptor list (<a href="..\wdm\ns-wdm-_mdl.md">MDL</a>) that describes the physical pages.


## Return Value

None

## Remarks

The miniport driver must call this method to release a mapping that was set up by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff536932">IPortWaveRTStream::MapAllocatedPages</a>. The driver must release the mapping before calling <a href="https://msdn.microsoft.com/8839c0ab-08c5-4cc7-a526-aa1ebe2fde15">IPortWaveRTStream::FreePagesFromMdl </a> to free the MDL.

This method is similar in operation to the <a href="..\wdm\nf-wdm-mmunmaplockedpages.md">MmUnmapLockedPages</a> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later Windows operating systems.  |
| **Target Platform** | Universal |
| **Header** | portcls.h |
| **Library** | portcls.h |
| **IRQL** | Passive level. |

## See Also

<a href="..\wdm\nf-wdm-mmunmaplockedpages.md">MmUnmapLockedPages</a>



<a href="..\portcls\nn-portcls-iportwavertstream.md">IPortWaveRTStream</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536926">IPortWaveRTStream::FreePagesFromMdl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536932">IPortWaveRTStream::MapAllocatedPages</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IPortWaveRTStream::UnmapAllocatedPages method%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>