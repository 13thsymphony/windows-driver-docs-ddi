---
UID: NC:pcivirt.SRIOV_GET_RESOURCE_FOR_BAR
title: SRIOV_GET_RESOURCE_FOR_BAR
author: windows-driver-content
description: Gets the translated resource for a specific Base Address Register (BAR).
old-location: pci\sriov_get_resource_for_bar.htm
old-project: PCI
ms.assetid: b52bafee-d541-4396-be0a-06956d07fb2b
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: PCI.sriov_get_resource_for_bar, SriovGetResourceForBar callback function [Buses], SriovGetResourceForBar, SRIOV_GET_RESOURCE_FOR_BAR, SRIOV_GET_RESOURCE_FOR_BAR, pcivirt/SriovGetResourceForBar, *PSRIOV_GET_RESOURCE_FOR_BAR callback function pointer [Buses], *PSRIOV_GET_RESOURCE_FOR_BAR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: pcivirt.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	pcivirt.h
apiname:
-	*PSRIOV_GET_RESOURCE_FOR_BAR
product: Windows
targetos: Windows
req.typenames: PARCLASS_INFORMATION, *PPARCLASS_INFORMATION
---


# SRIOV_GET_RESOURCE_FOR_BAR function
Gets the translated resource for a specific Base Address Register (BAR)

## Syntax

```
SRIOV_GET_RESOURCE_FOR_BAR SriovGetResourceForBar;

NTSTATUS SriovGetResourceForBar(
  PVOID Context,
  USHORT VfIndex,
  USHORT BarIndex,
  PCM_PARTIAL_RESOURCE_DESCRIPTOR Resource
)
{...}
```

## Parameters

`Context`

A pointer to a driver-defined context.

`VfIndex`

A zero-based index of the VF that is being queried.

`BarIndex`

The index of the BAR (between 0 and 5).

`Resource`

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure that is filled with the translated hardware resources for the specified BAR.


## Return Value

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.

## Remarks

This callback function is implemented by the physical function (PF) driver. It is invoked  when the system wants to access  the translated hardware resources of a particular BAR of a virtual function.

The PF driver registers its implementation by setting the <b>GetResourceForBar</b> member of the SRIOV_DEVICE_INTERFACE_STANDARD, configuring a <a href="..\wdfqueryinterface\ns-wdfqueryinterface-_wdf_query_interface_config.md">WDF_QUERY_INTERFACE_CONFIG</a> structure, and calling <a href="..\wdfqueryinterface\nf-wdfqueryinterface-wdfdeviceaddqueryinterface.md">WdfDeviceAddQueryInterface</a>.

Here is an example implementation of this callback function. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
NTSTATUS
Virtualization_GetResourceForBar(
    __inout     PVOID             Context,
    __in        USHORT            VfIndex,
    __in        USHORT            BarIndex,
    __out       PCM_PARTIAL_RESOURCE_DESCRIPTOR Resource
    )

{
    PDEVICE_CONTEXT  deviceContext;
    
    PAGED_CODE();

    deviceContext = (PDEVICE_CONTEXT)Context;
    
    TraceEvents(TRACE_LEVEL_VERBOSE, DBG_INTERFACE,
        "Virtualization_GetResourceForBar received with"
        "VFIndex = %d, BarIndex = %d\n",
        VfIndex, BarIndex);

    NT_ASSERT(BarIndex &lt; PCI_TYPE0_BAR_COUNT);
    
    if(VfIndex &gt;= deviceContext-&gt;NumVFs)
    {
        NT_ASSERT(FALSE);
        return STATUS_INVALID_DEVICE_REQUEST;
    }

    //
    // Copy the descriptor for all VFs at the given Bar index
    // to the output descriptor.
    //
    
    *Resource = deviceContext-&gt;AssignedVfBarResources[BarIndex];

    if(Resource-&gt;Type == CmResourceTypeMemory ||
       Resource-&gt;Type == CmResourceTypeMemoryLarge)
    {
        NT_ASSERT((Resource-&gt;u.Memory.Length % deviceContext-&gt;NumVFs) == 0);
        Resource-&gt;u.Memory.Length /= deviceContext-&gt;NumVFs;
        Resource-&gt;u.Memory.Start.QuadPart += (Resource-&gt;u.Memory.Length * VfIndex);
    }

    return STATUS_SUCCESS;
}

</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | pcivirt.h |
| **IRQL** | PASSIVE_LEVEL |