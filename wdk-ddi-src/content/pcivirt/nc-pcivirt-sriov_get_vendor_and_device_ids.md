---
UID: NC:pcivirt.SRIOV_GET_VENDOR_AND_DEVICE_IDS
title: SRIOV_GET_VENDOR_AND_DEVICE_IDS
author: windows-driver-content
description: Supplies the Vendor and Device ID for a PCI Express SR-IOV Virtual Function (VF) to be used for generating a more generic Plug and Play ID for the VF. These IDs cannot be read directly from the VF’s configuration space.
old-location: pci\sriov_get_vendor_and_device_ids.htm
old-project: PCI
ms.assetid: d08bbaea-6f2b-49ef-bb8b-c1fe357e1c90
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: PCI.sriov_get_vendor_and_device_ids, SriovGetVendorAndDeviceIds callback function [Buses], SriovGetVendorAndDeviceIds, SRIOV_GET_VENDOR_AND_DEVICE_IDS, SRIOV_GET_VENDOR_AND_DEVICE_IDS, pcivirt/SriovGetVendorAndDeviceIds, *PSRIOV_GET_VENDOR_AND_DEVICE_IDS callback function pointer [Buses], *PSRIOV_GET_VENDOR_AND_DEVICE_IDS
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
-	Pcivirt.h
apiname:
-	*PSRIOV_GET_VENDOR_AND_DEVICE_IDS
product: Windows
targetos: Windows
req.typenames: PARCLASS_INFORMATION, *PPARCLASS_INFORMATION
---


# SRIOV_GET_VENDOR_AND_DEVICE_IDS function
Supplies the Vendor and Device ID for a PCI Express SR-IOV Virtual Function (VF) to be used for generating a more generic Plug and Play ID for the VF.  These IDs cannot be read directly from the VF’s configuration space.

## Syntax

```
SRIOV_GET_VENDOR_AND_DEVICE_IDS SriovGetVendorAndDeviceIds;

void SriovGetVendorAndDeviceIds(
  PVOID Context,
  USHORT VfIndex,
  PUSHORT VendorId,
  PUSHORT DeviceId
)
{...}
```

## Parameters

`Context`

A pointer to a driver-defined context.

`VfIndex`

A zero-based index of the VF to which this write operation applies.

`VendorId`

A pointer to a USHORT variable that is filled with the vendor ID of the VF.

`DeviceId`

A pointer to a USHORT variable that is filled with the device ID of the VF.


## Return Value

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.

## Remarks

This callback function is implemented by the physical function (PF) driver. It is invoked  when the system wants to retrieve the vendor and device identifiers of the specified VF. 

The PCI Express SR-IOV Specification requires that all VFs have the same Vendor and Device IDs.  This is a requirement of compliant hardware.  However, it’s possible to provision VFs such that their capabilities differ from each other, and it’s often useful to load different drivers on different hardware.  So Windows allows the  PF driver to supply separate Device and Vendor IDs (with different class codes, through the configuration space interfaces) such that each VF may appear with the Plug and Play IDs that are most appropriate for its use.

The PF driver registers its implementation by setting the <b>GetVendorAndDevice</b> member of the <a href="https://msdn.microsoft.com/c71add7d-9920-4b2f-a46a-4a09a94f3900">SRIOV_DEVICE_INTERFACE_STANDARD</a>, configuring a <a href="..\wdfqueryinterface\ns-wdfqueryinterface-_wdf_query_interface_config.md">WDF_QUERY_INTERFACE_CONFIG</a> structure, and calling <a href="..\wdfqueryinterface\nf-wdfqueryinterface-wdfdeviceaddqueryinterface.md">WdfDeviceAddQueryInterface</a>.

Here is an example implementation of this callback function. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
Virtualization_GetVendorAndDevice (
    _In_    PVOID           Context,
    _In_    USHORT          VfIndex,
    _Out_   PUSHORT         VendorId,
    _Out_   PUSHORT         DeviceId
    )
{
    PDEVICE_CONTEXT deviceContext;

    UNREFERENCED_PARAMETER(VfIndex);
    PAGED_CODE();

    deviceContext = (PDEVICE_CONTEXT)Context;

    *VendorId = deviceContext-&gt;VendorId;
    *DeviceId = deviceContext-&gt;DeviceId;

    return;
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