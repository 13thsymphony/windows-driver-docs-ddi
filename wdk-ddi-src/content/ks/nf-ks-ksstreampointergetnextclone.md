---
UID : NF:ks.KsStreamPointerGetNextClone
title : KsStreamPointerGetNextClone function
author : windows-driver-content
description : The KsStreamPointerGetNextClone function returns the clone stream pointer that was cloned immediately after the specified clone.
old-location : stream\ksstreampointergetnextclone.htm
old-project : stream
ms.assetid : b7f34d42-6044-43c6-85c8-ca3a6177c057
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : avfunc_946c362b-9246-4d06-afce-e4597a16a91b.xml, KsStreamPointerGetNextClone, KsStreamPointerGetNextClone function [Streaming Media Devices], ks/KsStreamPointerGetNextClone, stream.ksstreampointergetnextclone
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


# KsStreamPointerGetNextClone function
The<b> KsStreamPointerGetNextClone </b>function returns the clone stream pointer that was cloned immediately after the specified clone.

## Syntax

````
PKSSTREAM_POINTER KsStreamPointerGetNextClone(
  _In_ PKSSTREAM_POINTER StreamPointer
);
````

## Parameters

`StreamPointer`

A pointer to a <a href="..\ks\ns-ks-_ksstream_pointer.md">KSSTREAM_POINTER</a> structure representing the clone stream pointer for which the clone stream pointer cloned immediately after it on the same pin is returned.


## Return Value

<b>KsStreamPointerGetNextClone </b>returns a pointer to a <a href="..\ks\ns-ks-_ksstream_pointer.md">KSSTREAM_POINTER</a> structure representing the clone stream pointer that was cloned immediately after <i>StreamPointer</i> on the same pin. Alternatively, it returns <b>NULL</b> indicating that either <i>StreamPointer</i> is the last clone on the pin or that <i>StreamPointer</i> is not a clone. If not a clone, <i>StreamPointer</i> is either the leading or trailing edge stream pointer.

## Remarks

The returned pointer always refers to the same pin as <i>StreamPointer</i>. <b>KsStreamPointerGetNextClone</b>, in conjunction with <a href="..\ks\nf-ks-kspingetfirstclonestreampointer.md">KsPinGetFirstCloneStreamPointer</a>,<b></b>can be used to enumerate all clone stream pointers on a given pin in the order in which they were cloned.

Also see <a href="https://msdn.microsoft.com/4bac68a0-34d2-431a-9ed9-8a42751a736f">Stream Pointers</a>.

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

<a href="..\ks\nf-ks-kspingetfirstclonestreampointer.md">KsPinGetFirstCloneStreamPointer</a>

<a href="..\ks\nf-ks-ksstreampointerdelete.md">KsStreamPointerDelete</a>

<a href="..\ks\nf-ks-ksstreampointerclone.md">KsStreamPointerClone</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsStreamPointerGetNextClone function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>