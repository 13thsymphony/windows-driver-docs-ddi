---
UID: NC.pcivirt.SRIOV_QUERY_VF_LUID
title: SRIOV_QUERY_VF_LUID
author: windows-driver-content
description: Gets the local unique identifier of the PCI Express SR-IOV Virtual Function (VF).
old-location: pci\sriov_query_vf_luid.htm
old-project: PCI
ms.assetid: 17fe6e28-59ce-4678-8268-b49cef09a3db
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _PARCLASS_INFORMATION, PARCLASS_INFORMATION, *PPARCLASS_INFORMATION
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
req.alt-api: *PSRIOV_QUERY_VF_LUID
req.alt-loc: pcivirt.h
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
---

# SRIOV_QUERY_VF_LUID callback



## -description
Gets the local unique identifier of the PCI Express SR-IOV Virtual Function (VF).



## -prototype

````
SRIOV_QUERY_VF_LUID SriovQueryVfLuid;

NTSTATUS SriovQueryVfLuid(
  _In_  PVOID  Context,
  _In_  USHORT VfIndex,
  _Out_ PLUID  Luid
)
{ ... }

typedef SRIOV_QUERY_VF_LUID *PSRIOV_QUERY_VF_LUID;
````


## -parameters

### -param Context [in]

A pointer to a driver-defined context.
                    
                


### -param VfIndex [in]

A zero-based index of the VF that is being queried.


### -param Luid [out]

A pointer to the local unique
identifier of the SR_IOV device implementing the interface.


## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.


## -remarks
This callback function is implemented by the physical function (PF) driver. It is invoked  when the system wants to get the identifier of a specific virtual function. 

The PF driver registers its implementation by setting the <b>QueryLuid</b> member of the SRIOV_DEVICE_INTERFACE_STANDARD_2, configuring a <a href="wdf.wdf_query_interface_config">WDF_QUERY_INTERFACE_CONFIG</a> structure, and calling <a href="wdf.wdfdeviceaddqueryinterface">WdfDeviceAddQueryInterface</a>.

Here is an example implementation of this callback function. The PF driver generates a unique identifier by calling <a href="kernel.zwallocatelocallyuniqueid">ZwAllocateLocallyUniqueId</a>  and stores it in the device context. 


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2016

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Pcivirt.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">


</td>
</tr>
</table>