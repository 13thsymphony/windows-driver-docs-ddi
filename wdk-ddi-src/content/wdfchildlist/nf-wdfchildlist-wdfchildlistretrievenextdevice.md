---
UID: NF:wdfchildlist.WdfChildListRetrieveNextDevice
title: WdfChildListRetrieveNextDevice function
author: windows-driver-content
description: The WdfChildListRetrieveNextDevice method traverses a specified child list and retrieves the next child device that matches specified criteria.
old-location: wdf\wdfchildlistretrievenextdevice.htm
old-project: wdf
ms.assetid: 925807ff-e445-4ccf-ace6-fd913439799b
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: WdfChildListRetrieveNextDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfchildlist.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfChildListRetrieveNextDevice
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: WDF_RETRIEVE_CHILD_FLAGS
req.product: Windows 10 or later.
---

# WdfChildListRetrieveNextDevice function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfChildListRetrieveNextDevice</b> method traverses a specified child list and retrieves the next child device that matches specified criteria.



## -syntax

````
NTSTATUS WdfChildListRetrieveNextDevice(
  _In_    WDFCHILDLIST             ChildList,
  _In_    PWDF_CHILD_LIST_ITERATOR Iterator,
  _Out_   WDFDEVICE                *Device,
  _Inout_ PWDF_CHILD_RETRIEVE_INFO Info
);
````


## -parameters

### -param ChildList [in]

A handle to a framework child-list object.


### -param Iterator [in]

A pointer to the same caller-allocated <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_list_iterator.md">WDF_CHILD_LIST_ITERATOR</a> structure that the driver previously supplied to <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistbeginiteration.md">WdfChildListBeginIteration</a>.


### -param Device [out]

A pointer to a location that receives a handle to a framework device object. The received value is <b>NULL</b> if the <i>Iterator</i> parameter specifies the <a href="..\wdfchildlist\ne-wdfchildlist-_wdf_retrieve_child_flags.md">WdfRetrievePendingChildren</a> flag.


### -param Info [in, out]

A pointer to a caller-allocated <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_retrieve_info.md">WDF_CHILD_RETRIEVE_INFO</a> structure. This pointer is optional and can be <b>NULL</b>.


## -returns
<b>WdfChildListRetrieveNextDevice</b> returns STATUS_SUCCESS, or another status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS(status)</a> equals <b>TRUE</b>, if the operation succeeds. Otherwise, this method might return one of the following values:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An input parameter was invalid.
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>The size of the <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_list_iterator.md">WDF_CHILD_LIST_ITERATOR</a> structure that <i>Iterator</i> specified was incorrect
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>An address description was specified but the child list did not contain address descriptions.
<dl>
<dt><b>STATUS_NO_MORE_ENTRIES</b></dt>
</dl>The framework reached the end of the child list.
<dl>
<dt><b>STATUS_INVALID_DEVICE_STATE</b></dt>
</dl>The driver has not called <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistbeginiteration.md">WdfChildListBeginIteration</a>.

 

This method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.



A system bug check occurs if the driver supplies an invalid object handle.



## -remarks
Before calling <b>WdfChildListRetrieveNextDevice</b>, your driver must call <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistbeginiteration.md">WdfChildListBeginIteration</a>. After the driver has finished traversing the child list, it must call <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistenditeration.md">WdfChildListEndIteration</a>. The framework then informs the Plug and Play (PnP) manager of any changes that were made to the child list.

Each time the driver calls <b>WdfChildListRetrieveNextDevice</b>, the method retrieves the next child that matches the following search criteria:

The child's type must correspond to <a href="..\wdfchildlist\ne-wdfchildlist-_wdf_retrieve_child_flags.md">WDF_RETRIEVE_CHILD_FLAGS</a>-typed flags in the driver's <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_list_iterator.md">WDF_CHILD_LIST_ITERATOR</a> structure.

If the driver provides a pointer to an <a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_identification_description_compare.md">EvtChildListIdentificationDescriptionCompare</a> callback function in its <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_retrieve_info.md">WDF_CHILD_RETRIEVE_INFO</a> structure, the callback function must return <b>TRUE</b>.

If the driver provides an <a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_identification_description_compare.md">EvtChildListIdentificationDescriptionCompare</a> callback function, it must also provide an <a href="wdf.dynamic_enumeration#dynamic_child_descriptions#dynamic_child_descriptions">identification description</a> in the WDF_CHILD_RETRIEVE_INFO structure. The framework uses the callback function to compare the passed-in identification descriptor with a child's description in the child list, if the WDF_RETRIEVE_CHILD_FLAGS-typed flags indicate that the child is a match candidate. If the callback function returns <b>TRUE</b>, the match is successful. If the callback function returns <b>FALSE</b>, the framework looks for another candidate.

When <b>WdfChildListRetrieveNextDevice</b> finds a match, it copies the child's identification description and address description into the driver's <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_retrieve_info.md">WDF_CHILD_RETRIEVE_INFO</a> structure, if the pointer that the <i>Info</i> parameter specifies is not <b>NULL</b>. (Note that this operation overwrites the driver's input identification description.) The method also places a handle to the child's device object in the location that the <i>Device</i> parameter identifies.

For more information about child lists, see <a href="https://msdn.microsoft.com/6e46b456-7d2d-4c6e-8692-7f310366387d">Dynamic Enumeration</a>.

The following code example informs the framework that all of a parent device's children are being ejected. The example obtains a device's default child list and walks through the list. It obtains each child's identification descriptor, and it passes each identification descriptor to <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistrequestchildeject.md">WdfChildListRequestChildEject</a>.


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
Minimum KMDF version

</th>
<td width="70%">
1.0

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdfchildlist.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (see <a href="https://msdn.microsoft.com/51db6f3c-45cb-46a7-9dd4-2bab67893fea">Framework Library Versioning</a>.)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= DISPATCH_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544957">DriverCreate</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff548167">KmdfIrql</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975091">KmdfIrql2</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_list_iterator.md">WDF_CHILD_LIST_ITERATOR</a>
</dt>
<dt>
<a href="..\wdfchildlist\nf-wdfchildlist-wdf_child_list_iterator_init.md">WDF_CHILD_LIST_ITERATOR_INIT</a>
</dt>
<dt>
<a href="..\wdfchildlist\nf-wdfchildlist-wdf_child_identification_description_header_init.md">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT</a>
</dt>
<dt>
<a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_retrieve_info.md">WDF_CHILD_RETRIEVE_INFO</a>
</dt>
<dt>
<a href="..\wdfchildlist\ne-wdfchildlist-_wdf_retrieve_child_flags.md">WDF_RETRIEVE_CHILD_FLAGS</a>
</dt>
<dt>
<a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_identification_description_compare.md">EvtChildListIdentificationDescriptionCompare</a>
</dt>
<dt>
<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistbeginscan.md">WdfChildListBeginScan</a>
</dt>
<dt>
<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistrequestchildeject.md">WdfChildListRequestChildEject</a>
</dt>
<dt>
<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistretrievenextdevice.md">WdfChildListRetrieveNextDevice</a>
</dt>
<dt>
<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistbeginiteration.md">WdfChildListBeginIteration</a>
</dt>
<dt>
<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistenditeration.md">WdfChildListEndIteration</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfChildListRetrieveNextDevice method%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

