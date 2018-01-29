---
UID : NF:wdfresource.WdfIoResourceRequirementsListInsertIoResList
title : WdfIoResourceRequirementsListInsertIoResList function
author : windows-driver-content
description : The WdfIoResourceRequirementsListInsertIoResList method inserts a logical configuration into a resource requirements list.
old-location : wdf\wdfioresourcerequirementslistinsertioreslist.htm
old-project : wdf
ms.assetid : d70d9fed-22fd-4bcf-a4bf-fbd941559529
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : kmdf.wdfioresourcerequirementslistinsertioreslist, wdf.wdfioresourcerequirementslistinsertioreslist, PFN_WDFIORESOURCEREQUIREMENTSLISTINSERTIORESLIST, WdfIoResourceRequirementsListInsertIoResList, DFResourceObjectRef_193f75e1-39a1-4a93-947b-550e7ad99494.xml, wdfresource/WdfIoResourceRequirementsListInsertIoResList, WdfIoResourceRequirementsListInsertIoResList method
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
req.typenames : "*PWDF_REQUEST_SEND_OPTIONS, WDF_REQUEST_SEND_OPTIONS"
req.product : Windows 10 or later.
---


# WdfIoResourceRequirementsListInsertIoResList function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfIoResourceRequirementsListInsertIoResList</b> method inserts a <a href="https://msdn.microsoft.com/c7a6997b-34f9-4dd9-b384-2321a8b5ce54">logical configuration</a> into a resource requirements list.

## Syntax

````
NTSTATUS WdfIoResourceRequirementsListInsertIoResList(
  _In_ WDFIORESREQLIST RequirementsList,
  _In_ WDFIORESLIST    IoResList,
  _In_ ULONG           Index
);
````

## Parameters

`RequirementsList`

A handle to a framework resource-requirements-list object that represents a device's resource requirements list.

`IoResList`

A handle to a framework resource-range-list object that represents a logical configuration of hardware resources for a device.

`Index`

A zero-based value that is used as an index into the set of logical configurations that are already in the resource requirements list that <i>RequirementsList</i> specifies. To add a configuration to the end of the list, specify WDF_INSERT_AT_END or the return value from <a href="..\wdfresource\nf-wdfresource-wdfioresourcerequirementslistgetcount.md">WdfIoResourceRequirementsListGetCount</a>.


## Return Value

<b>WdfIoResourceRequirementsListInsertIoResList</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:
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
An invalid parameter as specified.

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
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ARRAY_BOUNDS_EXCEEDED</b></dt>
</dl>
</td>
<td width="60%">
The specified value for the <i>Index</i> parameter was too large.

</td>
</tr>
</table> 

A system bug check occurs if the driver supplies an invalid object handle.

## Remarks

The <b>WdfIoResourceRequirementsListInsertIoResList</b> method inserts the logical configuration that the <i>IoResList</i> parameter specifies into the resource requirements list that the <i>RequirementsList</i> parameter specifies, in front of the logical configuration that the <i>Index</i> value identifies. 

To add a logical configuration to the end of a resource requirements list, use WDF_INSERT_AT_END or the return value from <a href="..\wdfresource\nf-wdfresource-wdfioresourcerequirementslistgetcount.md">WdfIoResourceRequirementsListGetCount</a> as the <i>Index</i> value. Alternatively, use the <a href="..\wdfresource\nf-wdfresource-wdfioresourcerequirementslistappendioreslist.md">WdfIoResourceRequirementsListAppendIoResList</a> method.

For more information about resource requirements lists, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** |  |
| **Header** | wdfresource.h (include Wdf.h) |
| **Library** |  |
| **IRQL** | <=DISPATCH_LEVEL |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<a href="..\wdfresource\nf-wdfresource-wdfioresourcelistcreate.md">WdfIoResourceListCreate</a>

<a href="..\wdfresource\nf-wdfresource-wdfioresourcerequirementslistappendioreslist.md">WdfIoResourceRequirementsListAppendIoResList</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoResourceRequirementsListInsertIoResList method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>