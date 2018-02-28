---
UID: NF:wdfresource.WdfCmResourceListRemove
title: WdfCmResourceListRemove function
author: windows-driver-content
description: The WdfCmResourceListRemove method removes a resource descriptor from a specified resource list.
old-location: wdf\wdfcmresourcelistremove.htm
old-project: wdf
ms.assetid: f636d85d-f7bb-4ebe-b03f-3b9c3c17bacd
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DFResourceObjectRef_5b1c7fce-45d2-454e-9d21-3f8d460ba99f.xml, WdfCmResourceListRemove, WdfCmResourceListRemove method, kmdf.wdfcmresourcelistremove, wdf.wdfcmresourcelistremove, wdfresource/WdfCmResourceListRemove
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfresource.h
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfCmResourceListRemove
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_SEND_OPTIONS, *PWDF_REQUEST_SEND_OPTIONS
req.product: Windows 10 or later.
---


# WdfCmResourceListRemove function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfCmResourceListRemove</b> method removes a resource descriptor from a specified resource list.

## Syntax

````
VOID WdfCmResourceListRemove(
  _In_ WDFCMRESLIST List,
  _In_ ULONG        Index
);
````

## Parameters

`List`

A handle to a framework resource-list object that represents a list of hardware resources for a device.

`Index`

A zero-based value that is used as an index into the resource list that <i>List</i> specifies.


## Return Value

None.

A system bug check occurs if the driver supplies an invalid object handle.

## Remarks

The <b>WdfCmResourceListRemove</b> method removes the resource descriptor that is associated with the index value that the <i>Index</i> parameter specifies.

When <b>WdfCmResourceListRemove</b> removes the resource descriptor that has the index value <i>n</i>, the index value of the next resource descriptor changes from <i>n</i>+1 to <i>n</i>.

For more information about resource lists, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.


#### Examples

The following code example removes the third resource descriptor from the raw and translated lists of hardware resources that an <a href="..\wdffdo\nc-wdffdo-evt_wdf_device_remove_added_resources.md">EvtDeviceRemoveAddedResources</a> callback function receives.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
MyEvtDeviceRemoveAddedResources(
    WDFDEVICE Device,
    WDFCMRESLIST ResourcesRaw,
    WDFCMRESLIST ResourcesTranslated
    )
{
...
    WdfCmResourceListRemove(
                            ResourcesRaw,
                            2
                            );
    WdfCmResourceListRemove(
                            ResourcesTranslated,
                            2
                            );
...

}</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Header** | wdfresource.h (include Wdf.h) |
| **Library** | Wdf01000.sys (see Framework Library Versioning.) |
| **IRQL** | "<=DISPATCH_LEVEL" |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<a href="..\wdfresource\nf-wdfresource-wdfcmresourcelistremovebydescriptor.md">WdfCmResourceListRemoveByDescriptor</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfCmResourceListRemove method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>