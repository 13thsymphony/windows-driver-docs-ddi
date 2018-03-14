---
UID: NF:ks.KSMETHOD_ITEM_IRP_STORAGE
title: KSMETHOD_ITEM_IRP_STORAGE macro
author: windows-driver-content
description: This macro accesses a pointer to the relevant KSMETHOD_ITEM. Note that this pointer is only set when using KsMethodHandlerWithAllocator.
old-location: stream\ksmethod_item_irp_storage.htm
old-project: stream
ms.assetid: 8c06da38-6f3b-4cd6-8331-c88758a7f00b
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KSMETHOD_ITEM_IRP_STORAGE, KSMETHOD_ITEM_IRP_STORAGE macro [Streaming Media Devices], ks/KSMETHOD_ITEM_IRP_STORAGE, ksfunc_f9a51af4-aa4e-432d-99e3-03052e99b902.xml, stream.ksmethod_item_irp_storage
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ks.h
api_name:
-	KSMETHOD_ITEM_IRP_STORAGE
product: Windows
targetos: Windows
req.typenames: 
---


# KSMETHOD_ITEM_IRP_STORAGE function
This macro accesses a pointer to the relevant <a href="..\ks\ns-ks-ksmethod_item.md">KSMETHOD_ITEM</a>. Note that this pointer is only set when using <a href="..\ks\nf-ks-ksmethodhandlerwithallocator.md">KsMethodHandlerWithAllocator</a>.

## Syntax

````
VOID KSMETHOD_ITEM_IRP_STORAGE(
  [in] IRP Irp
);
````

## Parameters

`Irp`

Specifies the IRP passed to the handler routine.


## Return Value

None

## Remarks

The pointer to a KSMETHOD_ITEM structure is extracted from <b>Irp-&gt;Tail.Overlay.DriverContext</b>. Parameters in <b>DriverContext</b> are initialized by <a href="..\ks\nf-ks-ksmethodhandler.md">KsMethodHandler</a> and <a href="..\ks\nf-ks-ksmethodhandlerwithallocator.md">KsMethodHandlerWithAllocator</a>.

The macro is defined as follows:

<pre class="syntax" xml:space="preserve"><code>#define KSMETHOD_ITEM_IRP_STORAGE(Irp)      (*(const KSMETHOD_ITEM**)&amp;(Irp)-&gt;Tail.Overlay.DriverContext[3])</code></pre>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ks.h (include Ks.h) |

## See Also

<a href="..\ks\ns-ks-ksmethod_set.md">KSMETHOD_SET</a>



<a href="..\ks\nf-ks-ksfastmethodhandler.md">KsFastMethodHandler</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563398">KSMETHOD</a>



<a href="..\ks\nf-ks-ksmethodhandlerwithallocator.md">KsMethodHandlerWithAllocator</a>



<a href="..\ks\nf-ks-ksmethodhandler.md">KsMethodHandler</a>



<a href="..\ks\ns-ks-ksmethod_item.md">KSMETHOD_ITEM</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSMETHOD_ITEM_IRP_STORAGE macro%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>