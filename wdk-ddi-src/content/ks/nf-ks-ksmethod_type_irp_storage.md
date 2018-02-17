---
UID: NF:ks.KSMETHOD_TYPE_IRP_STORAGE
title: KSMETHOD_TYPE_IRP_STORAGE macro
author: windows-driver-content
description: This macro accesses the type of method as described in the KSMETHOD_ITEM. If the method will be processed asynchronously using KsDispatchSpecificMethod, this storage must be maintained intact.
old-location: stream\ksmethod_type_irp_storage.htm
old-project: stream
ms.assetid: f5327cbf-e71b-4c1c-94c0-0e27afb4d7cf
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.ksmethod_type_irp_storage, KSMETHOD_TYPE_IRP_STORAGE macro [Streaming Media Devices], KSMETHOD_TYPE_IRP_STORAGE, ks/KSMETHOD_TYPE_IRP_STORAGE, ksfunc_de99d882-5298-4972-9d16-fa4478d6229c.xml
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
req.lib: ks.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ks.h
apiname:
-	KSMETHOD_TYPE_IRP_STORAGE
product: Windows
targetos: Windows
req.typenames: 
---


# KSMETHOD_TYPE_IRP_STORAGE function
This macro accesses the type of method as described in the <a href="..\ks\ns-ks-ksmethod_item.md">KSMETHOD_ITEM</a>. If the method will be processed asynchronously using <a href="..\ks\nf-ks-ksdispatchspecificmethod.md">KsDispatchSpecificMethod</a>, this storage must be maintained intact.

## Syntax

````
VOID KSMETHOD_TYPE_IRP_STORAGE(
  [in] IRP Irp
);
````

## Parameters

`Irp`

Specifies the IRP passed to the handler routine.


## Return Value

None

## Remarks

The relevant KSMETHOD_ITEM structure is extracted from <b>Irp-&gt;Tail.Overlay.DriverContext</b>. Parameters in <b>DriverContext</b> are initialized by <a href="..\ks\nf-ks-ksmethodhandler.md">KsMethodHandler</a> and <a href="..\ks\nf-ks-ksmethodhandlerwithallocator.md">KsMethodHandlerWithAllocator</a>.

The macro is defined as follows:

<pre class="syntax" xml:space="preserve"><code>#define KSMETHOD_TYPE_IRP_STORAGE(Irp)      (*(ULONG_PTR*)(&amp;(Irp)-&gt;Tail.Overlay.DriverContext[2]))</code></pre>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ks.h (include Ks.h) |
| **Library** | ks.h |

## See Also

<a href="..\ks\nf-ks-ksmethodhandlerwithallocator.md">KsMethodHandlerWithAllocator</a>



<a href="..\ks\nf-ks-ksfastmethodhandler.md">KsFastMethodHandler</a>



<a href="..\ks\nf-ks-ikscontrol-ksmethod.md">KSMETHOD</a>



<a href="..\ks\ns-ks-ksmethod_set.md">KSMETHOD_SET</a>



<a href="..\ks\ns-ks-ksmethod_item.md">KSMETHOD_ITEM</a>



<a href="..\ks\nf-ks-ksmethodhandler.md">KsMethodHandler</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSMETHOD_TYPE_IRP_STORAGE macro%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>