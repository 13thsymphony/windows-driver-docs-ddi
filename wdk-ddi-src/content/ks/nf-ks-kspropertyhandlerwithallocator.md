---
UID: NF:ks.KsPropertyHandlerWithAllocator
title: KsPropertyHandlerWithAllocator function
author: windows-driver-content
description: The KsPropertyHandlerWithAllocator performs the same handling as KsPropertyHandler, with the same restrictions, but allows an optional allocator callback to be used to provide a buffer for the parameters.
old-location: stream\kspropertyhandlerwithallocator.htm
old-project: stream
ms.assetid: b7e52667-b4ef-4807-867c-37b80af03b6b
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsPropertyHandlerWithAllocator, KsPropertyHandlerWithAllocator function [Streaming Media Devices], ks/KsPropertyHandlerWithAllocator, ksfunc_bad2a764-641a-4f28-a7e6-7d9a03d300f3.xml, stream.kspropertyhandlerwithallocator
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: NtosKrnl.exe
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
-	KsPropertyHandlerWithAllocator
product: Windows
targetos: Windows
req.typenames: 
---


# KsPropertyHandlerWithAllocator function
The <b>KsPropertyHandlerWithAllocator </b>performs the same handling as <a href="..\ks\nf-ks-kspropertyhandler.md">KsPropertyHandler</a>, with the same restrictions, but allows an optional allocator callback to be used to provide a buffer for the parameters. If used, the filter may need to free the buffer in some nonconventional manner. IRP_BUFFERED_IO and IRP_DEALLOCATE_BUFFER flags are not set when using a custom allocator.

## Syntax

````
NTSTATUS KsPropertyHandlerWithAllocator(
  _In_           PIRP           Irp,
  _In_           ULONG          PropertySetsCount,
  _In_     const KSPROPERTY_SET *PropertySet,
  _In_opt_       PFNKSALLOCATOR Allocator,
  _In_opt_       ULONG          PropertyItemSize
);
````

## Parameters

`Irp`

Specifies the IRP with the property request being handled.

`PropertySetsCount`

Specifies the number of property sets being passed.

`PropertySet`

Specifies the pointer to an array of property set information.

`Allocator`

Optionally points to an allocation function used to allocate memory to store the property parameters.

`OPTIONAL`

TBD


## Return Value

The <b>KsPropertyHandler </b>function returns STATUS_SUCCESS if successful, or an error specific to the property being handled if unsuccessful. The function sets the Irp-&gt;IoStatus.Information member, either through setting it to zero because of an internal error, or through a property handler setting it. The function does not set the lrp-&gt;IoStatus.Status member nor does it complete the IRP.

On 64-bit platforms, if the <i>PropertyItemSize</i> parameter is not a multiple of 8, STATUS_INVALID_PARAMETER is returned, and the call fails.

## Remarks

<i>KsPropertyHandlerWithAllocator</i> places a pointer to the relevant KSPROPERTY_ITEM structure in the <b>Irp-&gt;Tail.Overlay.DriverContext</b> parameter in the IRP. The minidriver can use the KSPROPERTY_ITEM_IRP_STORAGE macro, defined in <i>ks.h</i>, to access this pointer.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | NtosKrnl.exe |

## See Also

<a href="..\ks\nf-ks-kspropertyhandler.md">KsPropertyHandler</a>



<a href="..\ks\nf-ks-ksfastpropertyhandler.md">KsFastPropertyHandler</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsPropertyHandlerWithAllocator function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>