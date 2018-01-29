---
UID : NF:d3dkmthk.D3DKMTSetAllocationPriority
title : D3DKMTSetAllocationPriority function
author : windows-driver-content
description : The D3DKMTSetAllocationPriority function sets the priority level of a resource or list of allocations.
old-location : display\d3dkmtsetallocationpriority.htm
old-project : display
ms.assetid : d5ad6288-6123-4665-a48e-bbae856cc160
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : D3DKMTSetAllocationPriority function [Display Devices], display.d3dkmtsetallocationpriority, d3dkmthk/D3DKMTSetAllocationPriority, OpenGL_Functions_dc77467a-7ec3-4be9-96cd-8bedb5beb948.xml, D3DKMTSetAllocationPriority
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : d3dkmthk.h
req.include-header : D3dkmthk.h
req.target-type : Universal
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Gdi32.lib
req.dll : Gdi32.dll
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : D3DKMT_DRIVERVERSION
---


# D3DKMTSetAllocationPriority function
The <b>D3DKMTSetAllocationPriority</b> function sets the priority level of a resource or list of allocations.

## Syntax

````
NTSTATUS APIENTRY D3DKMTSetAllocationPriority(
  _In_ const D3DKMT_SETALLOCATIONPRIORITY *pData
);
````

## Parameters

`D3DKMT_SETALLOCATIONPRIORITY`

TBD


## Return Value

<b>D3DKMTSetAllocationPriority</b> returns one of the following values:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
Priority level for allocations was successfully set.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DEVICE_REMOVED</b></dt>
</dl>
</td>
<td width="60%">
The graphics adapter was stopped or the display device was reset.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Parameters were validated and determined to be incorrect.

</td>
</tr>
</table> 

This function might also return other NTSTATUS values.

## Remarks

The following code example demonstrates how an OpenGL ICD can use <b>D3DKMTSetAllocationPriority</b> to set the priority level of a resource (and therefore all of the allocations that are associated with the resource).
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID SetResourcePriority(D3DKMT_HANDLE hDevice, D3DKMT_HANDLE hResource, UINT uiPriority)
{
    D3DKMT_SETALLOCATIONPRIORITY SetAllocationPriorityData;

    SetAllocationPriorityData.hDevice = hDevice;
    SetAllocationPriorityData.hResource = hResource;
    SetAllocationPriorityData.phAllocationList = NULL;
    SetAllocationPriorityData.AllocationCount = 0;
    SetAllocationPriorityData.Priorities = &amp;uiPriority;    

    (*pfnKTSetAllocationPriority)(&amp;SetAllocationPriorityData);
}</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_setallocationpriority.md">D3DKMT_SETALLOCATIONPRIORITY</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTSetAllocationPriority function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>