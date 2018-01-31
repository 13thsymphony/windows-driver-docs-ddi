---
UID : NF:ks.KsPinSubmitFrameMdl
title : KsPinSubmitFrameMdl function
author : windows-driver-content
description : If a pin has been placed into injection mode by a call to KsPinRegisterFrameReturnCallback, the KsPinSubmitFrameMdl function submits a frame directly into the transport circuit.
old-location : stream\kspinsubmitframemdl.htm
old-project : stream
ms.assetid : 8033c0a9-86dd-4d54-b93e-66c926cae952
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KsPinSubmitFrameMdl function [Streaming Media Devices], KsPinSubmitFrameMdl, avfunc_456aa5db-b749-4b95-8448-f024dbc2030b.xml, ks/KsPinSubmitFrameMdl, stream.kspinsubmitframemdl
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ks.h
req.include-header : Ks.h
req.target-type : Universal
req.target-min-winverclnt : Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
req.lib : Ks.lib
req.dll : 
req.irql : "<=DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : 
---


# KsPinSubmitFrameMdl function
If a pin has been placed into injection mode by a call to <a href="..\ks\nf-ks-kspinregisterframereturncallback.md">KsPinRegisterFrameReturnCallback</a>, the <b>KsPinSubmitFrameMdl</b> function submits a frame directly into the transport circuit.

## Syntax

````
NTSTATUS KsPinSubmitFrameMdl(
  _In_     PKSPIN           Pin,
  _In_opt_ PMDL             Mdl,
  _In_opt_ PKSSTREAM_HEADER StreamHeader,
  _In_opt_ PVOID            Context
);
````

## Parameters

`Pin`

A pointer to a <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> structure representing the pin on which to submit a frame.

`Mdl`

A pointer to a memory descriptor list describing the frame buffer. Optional.

`StreamHeader`

A pointer to a <a href="..\ks\ns-ks-ksstream_header.md">KSSTREAM_HEADER</a> structure. The stream header is copied if this parameter is supplied. Optional.

`Context`

A pointer to a caller-allocated buffer that is passed to the frame return callback registered through <a href="..\ks\nf-ks-kspinregisterframereturncallback.md">KsPinRegisterFrameReturnCallback</a>. This parameter is optional and is solely for the caller's use.


## Return Value

Returns STATUS_SUCCESS if frame submission is successful. Otherwise returns an appropriate error code.

## Remarks

The difference between this function and <a href="..\ks\nf-ks-kspinsubmitframe.md">KsPinSubmitFrame</a> is that this function will submit a frame using an <a href="https://msdn.microsoft.com/library/windows/hardware/ff554414">MDL</a> structure rather than a data and size argument.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h (include Ks.h) |
| **Library** |  |
| **IRQL** | "<=DISPATCH_LEVEL" |
| **DDI compliance rules** |  |

## See Also

<a href="..\ks\nf-ks-kspinregisterframereturncallback.md">KsPinRegisterFrameReturnCallback</a>

<a href="..\ks\nf-ks-kspinsubmitframe.md">KsPinSubmitFrame</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsPinSubmitFrameMdl function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>