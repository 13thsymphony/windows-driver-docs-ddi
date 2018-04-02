---
UID: NC:ks.PFNKSPINIRPCOMPLETION
title: PFNKSPINIRPCOMPLETION
author: windows-driver-content
description: An AVStream minidriver's AVStrMiniPinIrpCompletion routine is called when an IRP completes a pass around the circuit and the frame that is associated with the IRP is about to be recycled or retired.
old-location: stream\avstrminipinirpcompletion.htm
old-project: stream
ms.assetid: 46b29026-b3a9-49cc-8f3d-0318516526d2
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: AVStrMiniPinIrpCompletion, AVStrMiniPinIrpCompletion routine [Streaming Media Devices], PFNKSPINIRPCOMPLETION, avstclbk_fabf9c16-a37b-4101-9468-dc247545aea0.xml, ks/AVStrMiniPinIrpCompletion, stream.avstrminipinirpcompletion
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ks.h
api_name:
-	AVStrMiniPinIrpCompletion
product:
- Windows
targetos: Windows
req.typenames: SOUNDDETECTOR_PATTERNHEADER
---


# PFNKSPINIRPCOMPLETION callback function
An AVStream minidriver's <i>AVStrMiniPinIrpCompletion</i> routine is called when an IRP completes a pass around the circuit and the frame that is associated with the IRP is about to be recycled or retired.

## Syntax

```
PFNKSPINIRPCOMPLETION Pfnkspinirpcompletion;

void Pfnkspinirpcompletion(
  PKSPIN Pin,
  PIRP Irp
)
{...}
```

## Parameters

`Pin`

Points to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a> structure for which the callback is registered.

`Irp`

Points to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a> which originated from the circuit to which <i>Pin</i> belongs.


## Return Value

None

## Remarks

The minidriver specifies this routine's address in the <i>IrpCompletion</i> parameter of a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff563524">KsPinRegisterIrpCompletionCallback</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.  |
| **Target Platform** | Desktop |
| **Header** | ks.h (include Ks.h) |
| **IRQL** | "<=DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563524">KsPinRegisterIrpCompletionCallback</a>