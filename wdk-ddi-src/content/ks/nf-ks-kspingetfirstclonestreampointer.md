---
UID : NF:ks.KsPinGetFirstCloneStreamPointer
title : KsPinGetFirstCloneStreamPointer function
author : windows-driver-content
description : The KsPinGetFirstCloneStreamPointer function returns the first cloned stream pointer on Pin.
old-location : stream\kspingetfirstclonestreampointer.htm
old-project : stream
ms.assetid : 9b4880af-d748-4a4e-92ec-8081138d4e27
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KsPinGetFirstCloneStreamPointer function [Streaming Media Devices], avfunc_2a3d17ef-c1b8-4b22-af1e-7f9bb01c1183.xml, ks/KsPinGetFirstCloneStreamPointer, stream.kspingetfirstclonestreampointer, KsPinGetFirstCloneStreamPointer
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


# KsPinGetFirstCloneStreamPointer function
The<b> KsPinGetFirstCloneStreamPointer</b> function returns the first cloned stream pointer on <i>Pin</i>.

## Syntax

````
PKSSTREAM_POINTER KsPinGetFirstCloneStreamPointer(
  _In_ PKSPIN Pin
);
````

## Parameters

`Pin`

A pointer to the <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> structure on which to return the first clone stream pointer.


## Return Value

<b>KsPinGetFirstCloneStreamPointer</b> returns a pointer to a <a href="..\ks\ns-ks-_ksstream_pointer.md">KSSTREAM_POINTER</a> structure. This pointer points to the first cloned stream pointer on <i>Pin</i>. If no clone stream pointers exist for <i>Pin</i>, <b>KsPinGetFirstCloneStreamPointer</b> returns <b>NULL</b>.

## Remarks

<b>KsPinGetFirstCloneStreamPointer</b>, along with <a href="..\ks\nf-ks-ksstreampointergetnextclone.md">KsStreamPointerGetNextClone</a> can be used to enumerate all clone stream pointers on a given pin in the order in which they were cloned. Also see <a href="https://msdn.microsoft.com/4bac68a0-34d2-431a-9ed9-8a42751a736f">Stream Pointers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h (include Ks.h) |
| **Library** |  |
| **IRQL** | <=DISPATCH_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\ks\ns-ks-_ksstream_pointer.md">KSSTREAM_POINTER</a>

<a href="..\ks\nf-ks-ksstreampointergetnextclone.md">KsStreamPointerGetNextClone</a>

<a href="..\ks\nf-ks-ksstreampointerclone.md">KsStreamPointerClone</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsPinGetFirstCloneStreamPointer function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>