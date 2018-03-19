---
UID: NC:ks.PFNKSPINFRAMERETURN
title: PFNKSPINFRAMERETURN
author: windows-driver-content
description: An AVStream minidriver's AVStrMiniFrameReturn routine is called when an injected frame has completed its trip around the circuit and is ready to be recycled or freed.
old-location: stream\avstrminiframereturn.htm
old-project: stream
ms.assetid: 842ed1ac-4043-41ce-90e5-94c9098e9da4
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: AVStrMiniFrameReturn, AVStrMiniFrameReturn routine [Streaming Media Devices], PFNKSPINFRAMERETURN, avstclbk_e7edb74a-8c38-4e7d-9978-849e5d88c153.xml, ks/AVStrMiniFrameReturn, stream.avstrminiframereturn
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ks.h
api_name:
-	AVStrMiniFrameReturn
product: Windows
targetos: Windows
req.typenames: SOUNDDETECTOR_PATTERNHEADER
---


# PFNKSPINFRAMERETURN callback function
An AVStream minidriver's <i>AVStrMiniFrameReturn</i> routine is called when an injected frame has completed its trip around the circuit and is ready to be recycled or freed.

## Syntax

```
PFNKSPINFRAMERETURN Pfnkspinframereturn;

void Pfnkspinframereturn(
  PKSPIN Pin,
  PVOID Data,
  ULONG Size OPTIONAL,
  PMDL Mdl,
  PVOID Context,
  NTSTATUS Status
)
{...}
```

## Parameters

`Pin`

Pointer to a <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> structure representing the pin on which the frame was injected.

`Data`

Pointer to the buffer originally specified in the call to <a href="..\ks\nf-ks-kspinsubmitframe.md">KsPinSubmitFrame</a>.

`OPTIONAL`



`Mdl`

Pointer to a memory descriptor list describing the injected frame as in the call to <a href="..\ks\nf-ks-kspinsubmitframemdl.md">KsPinSubmitFrameMdl</a><b>.</b>

`Context`

Pointer to the minidriver-supplied context buffer attached to the frame when the frame was injected into the circuit.

`Status`

Contains a copy of <i>Irp-&gt;IoStatus.Status</i> for the IRP to which the requested frame was attached.


## Return Value

None

## Remarks

The minidriver specifies this routine's address in the <i>FrameReturn</i> parameter of a call to <a href="..\ks\nf-ks-kspinregisterframereturncallback.md">KsPinRegisterFrameReturnCallback</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.  |
| **Target Platform** | Desktop |
| **Header** | ks.h (include Ks.h) |

## See Also

<a href="..\ks\nf-ks-kspinregisterframereturncallback.md">KsPinRegisterFrameReturnCallback</a>



<a href="..\ks\nf-ks-kspinsubmitframemdl.md">KsPinSubmitFrameMdl</a>