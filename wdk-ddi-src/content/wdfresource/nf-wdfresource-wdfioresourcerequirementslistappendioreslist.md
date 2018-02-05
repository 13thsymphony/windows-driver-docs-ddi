---
UID : NF:wdfresource.WdfIoResourceRequirementsListAppendIoResList
title : WdfIoResourceRequirementsListAppendIoResList function
author : windows-driver-content
description : The WdfIoResourceRequirementsListAppendIoResList method adds a logical configuration to the end of a resource requirements list.
old-location : wdf\wdfioresourcerequirementslistappendioreslist.htm
old-project : wdf
ms.assetid : efb3617d-86be-4380-ad1a-0a333d248168
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : wdf.wdfioresourcerequirementslistappendioreslist, DFResourceObjectRef_1d064295-4660-4112-9512-9c5ff7196485.xml, wdfresource/WdfIoResourceRequirementsListAppendIoResList, WdfIoResourceRequirementsListAppendIoResList method, PFN_WDFIORESOURCEREQUIREMENTSLISTAPPENDIORESLIST, WdfIoResourceRequirementsListAppendIoResList, kmdf.wdfioresourcerequirementslistappendioreslist
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdfresource.h
req.include-header : Wdf.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 
req.ddi-compliance : DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Wdf01000.sys (see Framework Library Versioning.)
req.dll : 
req.irql : "<=DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WDF_REQUEST_SEND_OPTIONS, *PWDF_REQUEST_SEND_OPTIONS
req.product : Windows 10 or later.
---


# WdfIoResourceRequirementsListAppendIoResList function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfIoResourceRequirementsListAppendIoResList</b> method adds a <a href="https://msdn.microsoft.com/c7a6997b-34f9-4dd9-b384-2321a8b5ce54">logical configuration</a> to the end of a resource requirements list.

## Syntax

````
NTSTATUS WdfIoResourceRequirementsListAppendIoResList(
  _In_ WDFIORESREQLIST RequirementsList,
  _In_ WDFIORESLIST    IoResList
);
````

## Parameters

`RequirementsList`

A handle to a framework resource-requirements-list object that represents a device's resource requirements list.

`IoResList`

A handle to a framework resource-range-list object that represents a logical configuration of hardware resources for a device.


## Return Value

<b>WdfIoResourceRequirementsListAppendIoResList</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:
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
An invalid parameter was specified.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The specified resource-requirements-list object does not own the specified resource-range-list object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The framework could not allocate space to store the resource-range-list object.

</td>
</tr>
</table> 

A system bug check occurs if the driver supplies an invalid object handle.

## Remarks

For more information about resource requirements lists, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.

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

<a href="..\wdfresource\nf-wdfresource-wdfioresourcerequirementslistinsertioreslist.md">WdfIoResourceRequirementsListInsertIoResList</a>

<a href="..\wdfresource\nf-wdfresource-wdfioresourcelistcreate.md">WdfIoResourceListCreate</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoResourceRequirementsListAppendIoResList method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>