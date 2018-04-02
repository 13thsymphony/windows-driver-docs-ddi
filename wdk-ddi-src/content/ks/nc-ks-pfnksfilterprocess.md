---
UID: NC:ks.PFNKSFILTERPROCESS
title: PFNKSFILTERPROCESS
author: windows-driver-content
description: An AVStream minidriver's AVStrMiniFilterProcess routine is called when the filter is meant to process frames. It is used to perform Filter-Centric Processing.
old-location: stream\avstrminifilterprocess.htm
old-project: stream
ms.assetid: f1998d68-1c9e-4527-a174-b22a8c301e63
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: AVStrMiniFilterProcess, AVStrMiniFilterProcess routine [Streaming Media Devices], PFNKSFILTERPROCESS, avstclbk_220bff5f-a966-460b-9157-b512cfc9c336.xml, ks/AVStrMiniFilterProcess, stream.avstrminifilterprocess
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
req.irql: "(See Remarks section)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ks.h
api_name:
-	AVStrMiniFilterProcess
product:
- Windows
targetos: Windows
req.typenames: SOUNDDETECTOR_PATTERNHEADER
---


# PFNKSFILTERPROCESS callback function
An AVStream minidriver's <i>AVStrMiniFilterProcess</i> routine is called when the filter is meant to process frames. It is used to perform <a href="https://msdn.microsoft.com/e56c5102-7ea6-4687-ae5e-1550db9500f0">Filter-Centric Processing</a>.

## Syntax

```
PFNKSFILTERPROCESS Pfnksfilterprocess;

NTSTATUS Pfnksfilterprocess(
  PKSFILTER Filter,
  PKSPROCESSPIN_INDEXENTRY Index
)
{...}
```

## Parameters

`Filter`

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562522">KSFILTER</a> structure that must process frames.

`Index`




## Return Value

Return STATUS_SUCCESS to continue processing. Return STATUS_PENDING to stop processing until the next triggering event. The minidriver may return an error code, but this will be treated as described for STATUS_PENDING.

## Remarks

The minidriver specifies this routine's address in the <b>Process</b> member of its <a href="https://msdn.microsoft.com/library/windows/hardware/ff562554">KSFILTER_DISPATCH</a> structure.

The routine is called at either IRQL = DISPATCH_LEVEL or PASSIVE_LEVEL depending on the preference expressed in the filter descriptor. Filter descriptors that specify KSFILTER_FLAG_DISPATCH_LEVEL_PROCESSING may have their process callback at DISPATCH_LEVEL; filter descriptors that do not specify this flag will have their process callback at PASSIVE_LEVEL.

For more information, see <a href="https://msdn.microsoft.com/e56c5102-7ea6-4687-ae5e-1550db9500f0">Filter-Centric Processing</a> and <a href="https://msdn.microsoft.com/f60d4dbd-61e6-4ae2-aa43-9edc8f36c3ff">Restarting Processing in AVStream</a>.

This routine is optional.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.  |
| **Target Platform** | Desktop |
| **Header** | ks.h (include Ks.h) |
| **IRQL** | "(See Remarks section)" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff562554">KSFILTER_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564260">KSPROCESSPIN_INDEXENTRY</a>