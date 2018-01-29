---
UID : NF:portcls.IPortWaveRTStream.FreePagesFromMdl
title : IPortWaveRTStream::FreePagesFromMdl method
author : windows-driver-content
description : The FreePagesFromMdl method frees a memory descriptor list (MDL).
old-location : audio\iportwavertstream_freepagesfrommdl.htm
old-project : audio
ms.assetid : 8839c0ab-08c5-4cc7-a526-aa1ebe2fde15
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : IPortWaveRTStream interface [Audio Devices], FreePagesFromMdl method, portcls/IPortWaveRTStream::FreePagesFromMdl, audio.iportwavertstream_freepagesfrommdl, FreePagesFromMdl method [Audio Devices], IPortWaveRTStream::FreePagesFromMdl, IPortWaveRTStream, FreePagesFromMdl, audmp-routines_7e3477c5-08b8-4e7c-bfb9-36945bf765c4.xml, FreePagesFromMdl method [Audio Devices], IPortWaveRTStream interface
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
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : portcls.h
req.dll : 
req.irql : Passive level.
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# FreePagesFromMdl method
The <code>FreePagesFromMdl</code> method frees a memory descriptor list (<a href="..\wdm\ns-wdm-_mdl.md">MDL</a>).

## Syntax

````
VOID FreePagesFromMdl(
  [in] PMDL MemoryDescriptorList
);
````

## Parameters

`MemoryDescriptorList`

Pointer to the MDL.


## Return Value

None

## Remarks

The miniport driver must call this method to free an MDL that was previously allocated by calling either <a href="https://msdn.microsoft.com/library/windows/hardware/ff536925">IPortWaveRTStream::AllocatePagesForMdl</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff536924">IPortWaveRTStream::AllocateContiguousPagesForMdl</a>.

<code>FreePagesFromMdl</code> frees both the physical memory pages described in the MDL and the MDL itself. On return, the MDL pointer value in the <i>MemoryDescriptorList</i> parameter is no longer valid.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | portcls.h |
| **Library** |  |
| **IRQL** | Passive level. |
| **DDI compliance rules** |  |

## See Also

<a href="..\portcls\nn-portcls-iportwavertstream.md">IPortWaveRTStream</a>

<a href="https://msdn.microsoft.com/976f7e83-9b2a-4e1b-ab76-76d8e9711bff">IPortWaveRTStream::AllocateContiguousPagesForMdl </a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536925">IPortWaveRTStream::AllocatePagesForMdl</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IPortWaveRTStream::FreePagesFromMdl method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>