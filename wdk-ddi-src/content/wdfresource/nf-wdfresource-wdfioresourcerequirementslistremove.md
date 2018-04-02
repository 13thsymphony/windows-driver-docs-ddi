---
UID: NF:wdfresource.WdfIoResourceRequirementsListRemove
title: WdfIoResourceRequirementsListRemove function
author: windows-driver-content
description: The WdfIoResourceRequirementsListRemove method removes a logical configuration from a resource requirements list.
old-location: wdf\wdfioresourcerequirementslistremove.htm
old-project: wdf
ms.assetid: 3668aa5a-1cb4-4ee1-91bd-bf2f3fa30622
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFResourceObjectRef_7f7c29e8-231a-48ec-b4e3-01989ad994b0.xml, WdfIoResourceRequirementsListRemove, WdfIoResourceRequirementsListRemove method, kmdf.wdfioresourcerequirementslistremove, wdf.wdfioresourcerequirementslistremove, wdfresource/WdfIoResourceRequirementsListRemove
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
-	WdfIoResourceRequirementsListRemove
product:
- Windows
targetos: Windows
req.typenames: WDF_REQUEST_SEND_OPTIONS, *PWDF_REQUEST_SEND_OPTIONS
req.product: Windows 10 or later.
---


# WdfIoResourceRequirementsListRemove function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfIoResourceRequirementsListRemove</b> method removes a <a href="https://msdn.microsoft.com/c7a6997b-34f9-4dd9-b384-2321a8b5ce54">logical configuration</a> from a resource requirements list.

## Syntax

```
void WdfIoResourceRequirementsListRemove(
  WDFIORESREQLIST RequirementsList,
  ULONG           Index
);
```

## Parameters

`RequirementsList`

A handle to a framework resource-requirements-list object that represents a device's resource requirements list.

`Index`

A zero-based value that is used as an index into the resource requirements list that <i>RequirementsList</i> specifies.


## Return Value

None.

A system bug check occurs if the driver supplies an invalid object handle.

## Remarks

The <b>WdfIoResourceRequirementsListRemove</b> method removes the logical configuration that is associated with the index value that the <i>Index</i> parameter specifies.

When <b>WdfIoResourceRequirementsListRemove</b> removes the logical configuration that has the index value <i>n</i>, the index value of the next logical configuration changes from <i>n</i>+1 to <i>n</i>.

For more information about resource requirements lists, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.


#### Examples

The following code example removes the second logical configuration from a resource requirements list.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
Example_EvtDeviceFilterRemoveResourceRequirements(
    IN WDFDEVICE Device,
    IN WDFIORESREQLIST RequirementsList
    )
{
...
    WdfIoResourceRequirementsListRemove(
                                        RequirementsList,
                                        1
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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548575">WdfIoResourceRequirementsListRemoveByIoResList</a>