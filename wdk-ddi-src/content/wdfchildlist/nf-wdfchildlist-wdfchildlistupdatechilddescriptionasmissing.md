---
UID: NF:wdfchildlist.WdfChildListUpdateChildDescriptionAsMissing
title: WdfChildListUpdateChildDescriptionAsMissing function
author: windows-driver-content
description: The WdfChildListUpdateChildDescriptionAsMissing method informs the framework that a specified child device is currently unplugged or otherwise unavailable.
old-location: wdf\wdfchildlistupdatechilddescriptionasmissing.htm
old-project: wdf
ms.assetid: 21932a96-285c-490d-a1fb-a137aed57bbb
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectChildListRef_1a871104-3d76-4ecb-936e-c27c2a107f2e.xml, WdfChildListUpdateChildDescriptionAsMissing, WdfChildListUpdateChildDescriptionAsMissing method, kmdf.wdfchildlistupdatechilddescriptionasmissing, wdf.wdfchildlistupdatechilddescriptionasmissing, wdfchildlist/WdfChildListUpdateChildDescriptionAsMissing
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
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfChildListUpdateChildDescriptionAsMissing
product: Windows
targetos: Windows
req.typenames: WDF_RETRIEVE_CHILD_FLAGS
req.product: Windows 10 or later.
---


# WdfChildListUpdateChildDescriptionAsMissing function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfChildListUpdateChildDescriptionAsMissing</b> method informs the framework that a specified child device is currently unplugged or otherwise unavailable.

## Syntax

````
NTSTATUS WdfChildListUpdateChildDescriptionAsMissing(
  _In_ WDFCHILDLIST                                 ChildList,
  _In_ PWDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER IdentificationDescription
);
````

## Parameters

`ChildList`

A handle to a child list object.

`IdentificationDescription`

A pointer to a caller-allocated <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_identification_description_header.md">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a> structure that identifies a driver-supplied child <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dynamic-enumeration">identification description</a>.


## Return Value

<b>WdfChildListUpdateChildDescriptionAsMissing</b> returns STATUS_SUCCESS, or another status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS(status)</a> equals <b>TRUE</b>, if the operation succeeds. Otherwise, this method might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An input parameter was invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The size of the structure that <i>IdentificationDescription</i> points to was incorrect.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_SUCH_DEVICE</b></dt>
</dl>
</td>
<td width="60%">
The specified device was not found in the child list.

</td>
</tr>
</table>
 

This method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.



A system bug check occurs if the driver supplies an invalid object handle.

## Remarks

Your driver can report that a device is unavailable even if the driver never called <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistaddorupdatechilddescriptionaspresent.md">WdfChildListAddOrUpdateChildDescriptionAsPresent</a> to report that the device was present. In this case, the <b>WdfChildListUpdateChildDescriptionAsMissing</b> method just returns STATUS_NO_SUCH_DEVICE.

If you want to report that all devices in a child list are unavailable, your driver can simply call <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistbeginscan.md">WdfChildListBeginScan</a>, followed immediately by <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistendscan.md">WdfChildListEndScan</a>, instead of calling <b>WdfChildListUpdateChildDescriptionAsMissing</b> for each device.

For more information about child devices and child lists, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dynamic-enumeration">Dynamic Enumeration</a>.


#### Examples

The following code example informs the framework that a child device with a specified serial number is unavailable.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PDO_IDENTIFICATION_DESCRIPTION  description;
NTSTATUS  status;

WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT(
                                                 &amp;description.Header,
                                                 sizeof(description)
                                                 );

description.SerialNo = SerialNo;
status = WdfChildListUpdateChildDescriptionAsMissing(
                                                     list,
                                                     &amp;description.Header
                                                     );</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Header** | wdfchildlist.h (include Wdf.h) |
| **Library** | Wdf01000.sys (see Framework Library Versioning.) |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistaddorupdatechilddescriptionaspresent.md">WdfChildListAddOrUpdateChildDescriptionAsPresent</a>



<a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_identification_description_header.md">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a>



<a href="..\wdfchildlist\nf-wdfchildlist-wdf_child_identification_description_header_init.md">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT</a>