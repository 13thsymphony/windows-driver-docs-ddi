---
UID : NF:ks.KsStreamPointerGetIrp
title : KsStreamPointerGetIrp function
author : windows-driver-content
description : The KsStreamPointerGetIrp function returns the IRP associated with the frame that is referenced by the given stream pointer.
old-location : stream\ksstreampointergetirp.htm
old-project : stream
ms.assetid : 3ed4ed2f-66be-4429-b2d6-2d9d3f9bcf3e
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KsStreamPointerGetIrp, KsStreamPointerGetIrp function [Streaming Media Devices], stream.ksstreampointergetirp, avfunc_57ecd1af-c967-473c-b475-1d91bc42f2eb.xml, ks/KsStreamPointerGetIrp
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


# KsStreamPointerGetIrp function
The<b> KsStreamPointerGetIrp </b>function returns the IRP associated with the frame that is referenced by the given stream pointer.

## Syntax

````
PIRP KsStreamPointerGetIrp(
  _In_      PKSSTREAM_POINTER StreamPointer,
  _Out_opt_ PBOOLEAN          FirstFrameInIrp,
  _Out_opt_ PBOOLEAN          LastFrameInIrp
);
````

## Parameters

`StreamPointer`

A pointer to the <a href="..\ks\ns-ks-_ksstream_pointer.md">KSSTREAM_POINTER</a> structure that references the frame for which the associated IRP is returned.

`FirstFrameInIrp`

A pointer to a caller-supplied BOOLEAN value set to <b>TRUE</b> on return if the frame referenced by <i>StreamPointer</i> is the first frame in the returned IRP and <b>FALSE</b> if not. If <b>NULL</b>, AVStream does not test this condition.

`LastFrameInIrp`

A pointer to a caller-supplied BOOLEAN value set to <b>TRUE</b> if the frame referenced by the stream pointer is the last frame in the returned IRP and <b>FALSE</b> if not. If <b>NULL</b>, AVStream does not test this condition.


## Return Value

<b>KsStreamPointerGetIrp </b>returns either a pointer to the IRP associated with the frame that is referenced by the given stream pointer, or returns <b>NULL</b>. A return value of <b>NULL</b> indicates that the stream pointer is not locked.

## Remarks

<b>KsStreamPointerGetIrp </b>can also be used to determine if <i>StreamPointer</i> references the first and/or last frame contained in the returned IRP.

<i>StreamPointer</i> must be locked in order for <b>KsStreamPointerGetIrp </b>to execute successfully. Any attempt to call this function with an unlocked stream pointer results in a <b>NULL</b> return value.

<i>FirstFrameInIrp </i>and<i>/</i>or <i>LastFrameInIrp</i> must be non-<b>NULL</b> at call-time in order for AVStream to fill in these values.

Also see <a href="https://msdn.microsoft.com/4bac68a0-34d2-431a-9ed9-8a42751a736f">Stream Pointers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions. Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions. |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | Ks.lib |
| **IRQL** | "<=DISPATCH_LEVEL" |

## See Also

<a href="..\ks\nf-ks-ksstreampointergetmdl.md">KsStreamPointerGetMdl</a>

<a href="..\ks\nf-ks-ksstreampointerlock.md">KsStreamPointerLock</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsStreamPointerGetIrp function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>