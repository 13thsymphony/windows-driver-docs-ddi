---
UID: NF:ks.KsStreamPointerGetMdl
title: KsStreamPointerGetMdl function
author: windows-driver-content
description: The KsStreamPointerGetMdl function returns the MDL associated with the frame referenced by StreamPointer.
old-location: stream\ksstreampointergetmdl.htm
old-project: stream
ms.assetid: 05d37fbd-9bdc-478a-8772-6f63d1363c1c
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsStreamPointerGetMdl, KsStreamPointerGetMdl function [Streaming Media Devices], avfunc_94dcd1e0-4882-4703-b69a-9ca8b21d30a0.xml, ks/KsStreamPointerGetMdl, stream.ksstreampointergetmdl
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsStreamPointerGetMdl
product: Windows
targetos: Windows
req.typenames: 
---


# KsStreamPointerGetMdl function
The<b> KsStreamPointerGetMdl </b>function returns the MDL associated with the frame referenced by <i>StreamPointer</i>.

## Syntax

````
PMDL KsStreamPointerGetMdl(
  _In_ PKSSTREAM_POINTER StreamPointer
);
````

## Parameters

`StreamPointer`

A pointer to the <a href="..\ks\ns-ks-_ksstream_pointer.md">KSSTREAM_POINTER</a> structure that references the frame for which to return the associated MDL.


## Return Value

Returns either a pointer to the <a href="https://msdn.microsoft.com/a1ec4764-4e11-4fb2-b439-ad6b721eb504">memory descriptor list (MDL)</a> describing the frame referenced by <i>StreamPointer</i> or returns <b>NULL</b>. A <b>NULL</b> return value usually indicates that the given stream pointer was not locked at call-time.

## Remarks

The stream pointer <b>must</b> be locked in order for <b>KsStreamPointerGetMdl </b>to execute successfully.

Also see <a href="https://msdn.microsoft.com/4bac68a0-34d2-431a-9ed9-8a42751a736f">Stream Pointers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.  |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | Ks.lib |
| **IRQL** | "<=DISPATCH_LEVEL" |

## See Also

<a href="..\ks\nf-ks-ksstreampointergetirp.md">KsStreamPointerGetIrp</a>



<a href="..\ks\nf-ks-ksstreampointerlock.md">KsStreamPointerLock</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsStreamPointerGetMdl function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>