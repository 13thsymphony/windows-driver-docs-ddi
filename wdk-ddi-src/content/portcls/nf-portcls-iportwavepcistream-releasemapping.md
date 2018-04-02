---
UID: NF:portcls.IPortWavePciStream.ReleaseMapping
title: IPortWavePciStream::ReleaseMapping method
author: windows-driver-content
description: The ReleaseMapping method releases a mapping that was obtained by a previous call to IPortWavePciStream::GetMapping.
old-location: audio\iportwavepcistream_releasemapping.htm
old-project: audio
ms.assetid: c4464fba-cc23-47d2-87d6-82b3eba8ddbe
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: IPortWavePciStream, IPortWavePciStream interface [Audio Devices], ReleaseMapping method, IPortWavePciStream::ReleaseMapping, ReleaseMapping method [Audio Devices], ReleaseMapping method [Audio Devices], IPortWavePciStream interface, ReleaseMapping,IPortWavePciStream.ReleaseMapping, audio.iportwavepcistream_releasemapping, audmp-routines_a4e274f7-02f8-4775-854f-befdc7dc6f03.xml, portcls/IPortWavePciStream::ReleaseMapping
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IPortWavePciStream.ReleaseMapping
product:
- Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# IPortWavePciStream::ReleaseMapping method
The <code>ReleaseMapping</code> method releases a mapping that was obtained by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff536909">IPortWavePciStream::GetMapping</a>.

## Syntax

```
NTSTATUS ReleaseMapping(
  PVOID Tag
);
```

## Parameters

`Tag`

Specifies a tag value identifying the mapping that is to be released. For more information, see the following Remarks section.


## Return Value

<code>ReleaseMapping</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.

## Remarks

Set the <i>Tag</i> parameter to the same tag value that you used to identify the mapping in the call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff536909">IPortWavePciStream::GetMapping</a> that originally obtained the mapping.

The miniport driver must keep track of the order in which it acquires its mappings from calls to <b>IPortWavePciStream::GetMapping</b>, and it must release the mappings in the same order.

To avoid potential deadlocks, the miniport driver must avoid holding a spin lock during its call to <code>ReleaseMapping</code>. See the ac97 sample audio driver in the Microsoft Windows Driver Kit (WDK) for a code example that uses a spin lock to serialize accesses to shared data structures and peripherals in a multiprocessor system. The sample code calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff553145">KeReleaseSpinLock</a> before calling <code>ReleaseMapping</code> and calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff551917">KeAcquireSpinLock</a> after calling <code>ReleaseMapping</code>. Between the calls to release and acquire the spin lock, the driver thread must not assume that it has exclusive access to the data or peripherals that are guarded by the spin lock. The Driver Verifier tool (see the description of this tool at the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557262">Driver Verifier</a> website) checks for active spin locks during calls to <code>ReleaseMapping</code>; if it detects one, it generates a 0xC4 (deadlock detection) bug check.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | portcls.h (include Portcls.h) |
| **IRQL** | "<=DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536730">IMiniportWavePciStream::RevokeMappings</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536907">IPortWavePciStream</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536909">IPortWavePciStream::GetMapping</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551917">KeAcquireSpinLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553145">KeReleaseSpinLock</a>