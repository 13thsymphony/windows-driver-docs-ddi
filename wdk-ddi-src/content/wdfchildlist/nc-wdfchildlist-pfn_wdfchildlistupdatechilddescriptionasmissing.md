---
UID: NC:wdfchildlist.PFN_WDFCHILDLISTUPDATECHILDDESCRIPTIONASMISSING
title: PFN_WDFCHILDLISTUPDATECHILDDESCRIPTIONASMISSING function
author: windows-driver-content
description: The WdfChildListUpdateChildDescriptionAsMissing method informs the framework that a specified child device is currently unplugged or otherwise unavailable.
old-location: wdf\wdfchildlistupdatechilddescriptionasmissing.htm
old-project: wdf
ms.assetid: 21932a96-285c-490d-a1fb-a137aed57bbb
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: PFN_WDFCHILDLISTUPDATECHILDDESCRIPTIONASMISSING
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
req.alt-api: WdfChildListUpdateChildDescriptionAsMissing
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
req.typenames: WDBGEXTS_THREAD_OS_INFO, *PWDBGEXTS_THREAD_OS_INFO
req.product: Windows 10 or later.
---

# PFN_WDFCHILDLISTUPDATECHILDDESCRIPTIONASMISSING function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfChildListUpdateChildDescriptionAsMissing</b> method informs the framework that a specified child device is currently unplugged or otherwise unavailable.



## -syntax

````
NTSTATUS WdfChildListUpdateChildDescriptionAsMissing(
  _In_ WDFCHILDLIST                                 ChildList,
  _In_ PWDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER IdentificationDescription
);
````


## -parameters

### -param ChildList [in]

A handle to a child list object.


### -param IdentificationDescription [in]

A pointer to a caller-allocated <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_identification_description_header.md">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a> structure that identifies a driver-supplied child <a href="wdf.dynamic_enumeration#dynamic_child_descriptions#dynamic_child_descriptions">identification description</a>.


## -returns
<b>WdfChildListUpdateChildDescriptionAsMissing</b> returns STATUS_SUCCESS, or another status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS(status)</a> equals <b>TRUE</b>, if the operation succeeds. Otherwise, this method might return one of the following values:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An input parameter was invalid.
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>The size of the structure that <i>IdentificationDescription</i> points to was incorrect.
<dl>
<dt><b>STATUS_NO_SUCH_DEVICE</b></dt>
</dl>The specified device was not found in the child list.

 

This method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.



A system bug check occurs if the driver supplies an invalid object handle.



## -remarks
Your driver can report that a device is unavailable even if the driver never called <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistaddorupdatechilddescriptionaspresent.md">WdfChildListAddOrUpdateChildDescriptionAsPresent</a> to report that the device was present. In this case, the <b>WdfChildListUpdateChildDescriptionAsMissing</b> method just returns STATUS_NO_SUCH_DEVICE.

If you want to report that all devices in a child list are unavailable, your driver can simply call <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistbeginscan.md">WdfChildListBeginScan</a>, followed immediately by <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistendscan.md">WdfChildListEndScan</a>, instead of calling <b>WdfChildListUpdateChildDescriptionAsMissing</b> for each device.

For more information about child devices and child lists, see <a href="https://msdn.microsoft.com/6e46b456-7d2d-4c6e-8692-7f310366387d">Dynamic Enumeration</a>.

The following code example informs the framework that a child device with a specified serial number is unavailable.


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
<a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_identification_description_header.md">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a>
</dt>
<dt>
<a href="..\wdfchildlist\nf-wdfchildlist-wdf_child_identification_description_header_init.md">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT</a>
</dt>
<dt>
<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistaddorupdatechilddescriptionaspresent.md">WdfChildListAddOrUpdateChildDescriptionAsPresent</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfChildListUpdateChildDescriptionAsMissing method%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

