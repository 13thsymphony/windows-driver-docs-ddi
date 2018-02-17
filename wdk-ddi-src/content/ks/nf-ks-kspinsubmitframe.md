---
UID: NF:ks.KsPinSubmitFrame
title: KsPinSubmitFrame function
author: windows-driver-content
description: If a pin has been placed into injection mode by a call to KsPinRegisterFrameReturnCallback, the KsPinSubmitFrame function submits a frame directly into the transport circuit.
old-location: stream\kspinsubmitframe.htm
old-project: stream
ms.assetid: 3fdb83b2-85b7-4f86-9a59-a42138000214
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsPinSubmitFrame function [Streaming Media Devices], ks/KsPinSubmitFrame, avfunc_ce7c4c71-c404-4061-a2e5-b9f4c15df4a2.xml, stream.kspinsubmitframe, KsPinSubmitFrame
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsPinSubmitFrame
product: Windows
targetos: Windows
req.typenames: 
---


# KsPinSubmitFrame function
If a pin has been placed into injection mode by a call to <a href="..\ks\nf-ks-kspinregisterframereturncallback.md">KsPinRegisterFrameReturnCallback</a>, the <b>KsPinSubmitFrame</b> function submits a frame directly into the transport circuit.

## Syntax

````
NTSTATUS KsPinSubmitFrame(
  _In_     PKSPIN           Pin,
  _In_opt_ PVOID            Data,
  _In_opt_ ULONG            Size,
  _In_opt_ PKSSTREAM_HEADER StreamHeader,
  _In_opt_ PVOID            Context
);
````

## Parameters

`Pin`

A pointer to the <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> structure on which to submit a frame.

`Data`

A pointer to a frame buffer. This should be <b>NULL</b> if and only if <i>Size</i> is equal to 0. Optional.

`OPTIONAL`

TBD

`StreamHeader`

A pointer to a <a href="..\ks\ns-ks-ksstream_header.md">KSSTREAM_HEADER</a> structure. The stream header is copied if this parameter is supplied. Optional.

`Context`

A pointer to a caller-allocated buffer. AVStream provides this pointer to the frame return callback registered through a call to <a href="..\ks\nf-ks-kspinregisterframereturncallback.md">KsPinRegisterFrameReturnCallback</a>. Optional.


## Return Value

Returns STATUS_SUCCESS if frame submission is successful. Otherwise returns an appropriate error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.  |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | Ks.lib |
| **IRQL** | "<=DISPATCH_LEVEL" |

## See Also

<a href="..\ks\nf-ks-kspinregisterframereturncallback.md">KsPinRegisterFrameReturnCallback</a>



<a href="..\ks\nf-ks-kspinsubmitframemdl.md">KsPinSubmitFrameMdl</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsPinSubmitFrame function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>