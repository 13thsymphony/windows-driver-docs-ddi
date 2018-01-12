---
UID: NF:ks.KsPropertyHandlerWithAllocator
title: KsPropertyHandlerWithAllocator function
author: windows-driver-content
description: The KsPropertyHandlerWithAllocator performs the same handling as KsPropertyHandler, with the same restrictions, but allows an optional allocator callback to be used to provide a buffer for the parameters.
old-location: stream\kspropertyhandlerwithallocator.htm
old-project: stream
ms.assetid: b7e52667-b4ef-4807-867c-37b80af03b6b
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsPropertyHandlerWithAllocator
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
req.alt-api: KsPropertyHandlerWithAllocator
req.alt-loc: ks.h
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
req.typenames: 
---

# KsPropertyHandlerWithAllocator function



## -description
The <b>KsPropertyHandlerWithAllocator </b>performs the same handling as <a href="..\ks\nf-ks-kspropertyhandler.md">KsPropertyHandler</a>, with the same restrictions, but allows an optional allocator callback to be used to provide a buffer for the parameters. If used, the filter may need to free the buffer in some nonconventional manner. IRP_BUFFERED_IO and IRP_DEALLOCATE_BUFFER flags are not set when using a custom allocator.



## -syntax

````
NTSTATUS KsPropertyHandlerWithAllocator(
  _In_           PIRP           Irp,
  _In_           ULONG          PropertySetsCount,
  _In_     const KSPROPERTY_SET *PropertySet,
  _In_opt_       PFNKSALLOCATOR Allocator,
  _In_opt_       ULONG          PropertyItemSize
);
````


## -parameters

### -param Irp [in]

Specifies the IRP with the property request being handled.


### -param PropertySetsCount [in]

Specifies the number of property sets being passed.


### -param PropertySet [in]

Specifies the pointer to an array of property set information.


### -param Allocator [in, optional]

Optionally points to an allocation function used to allocate memory to store the property parameters.


### -param PropertyItemSize [in, optional]

Optionally contains the size of each KSPROPERTY_ITEM structure in the properties. The property item may be extended in order to store private information. If this parameter is zero, the structure size is assumed to be normal. If it is greater than or equal to a property item structure, the KSPROPERTY_ITEM_IRP_STORAGE macro can be used to return a pointer to the property item so the custom data can be retrieved. On 64-bit platforms, this parameter must be a multiple of 8.


## -returns
The <b>KsPropertyHandler </b>function returns STATUS_SUCCESS if successful, or an error specific to the property being handled if unsuccessful. The function sets the Irp-&gt;IoStatus.Information member, either through setting it to zero because of an internal error, or through a property handler setting it. The function does not set the lrp-&gt;IoStatus.Status member nor does it complete the IRP.

On 64-bit platforms, if the <i>PropertyItemSize</i> parameter is not a multiple of 8, STATUS_INVALID_PARAMETER is returned, and the call fails.




## -remarks
<i>KsPropertyHandlerWithAllocator</i> places a pointer to the relevant KSPROPERTY_ITEM structure in the <b>Irp-&gt;Tail.Overlay.DriverContext</b> parameter in the IRP. The minidriver can use the KSPROPERTY_ITEM_IRP_STORAGE macro, defined in <i>ks.h</i>, to access this pointer.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ks\nf-ks-ksfastpropertyhandler.md">KsFastPropertyHandler</a>
</dt>
<dt>
<a href="..\ks\nf-ks-kspropertyhandler.md">KsPropertyHandler</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsPropertyHandlerWithAllocator function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

