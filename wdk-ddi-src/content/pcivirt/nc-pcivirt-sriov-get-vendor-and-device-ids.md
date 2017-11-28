---
UID: NC.pcivirt.SRIOV_GET_VENDOR_AND_DEVICE_IDS
title: SRIOV_GET_VENDOR_AND_DEVICE_IDS
author: windows-driver-content
description: Supplies the Vendor and Device ID for a PCI Express SR-IOV Virtual Function (VF) to be used for generating a more generic Plug and Play ID for the VF. These IDs cannot be read directly from the VF’s configuration space.
old-location: pci\sriov_get_vendor_and_device_ids.htm
old-project: PCI
ms.assetid: d08bbaea-6f2b-49ef-bb8b-c1fe357e1c90
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: PARCLASS_INFORMATION, PARCLASS_INFORMATION, *PPARCLASS_INFORMATION
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
req.alt-api: *PSRIOV_GET_VENDOR_AND_DEVICE_IDS
req.alt-loc: Pcivirt.h
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
req.iface: 
---

# SRIOV_GET_VENDOR_AND_DEVICE_IDS callback



## -description
<p>Supplies the Vendor and Device ID for a PCI Express SR-IOV Virtual Function (VF) to be used for generating a more generic Plug and Play ID for the VF.  These IDs cannot be read directly from the VF’s configuration space.</p>


## -prototype

````
SRIOV_GET_VENDOR_AND_DEVICE_IDS SriovGetVendorAndDeviceIds;

NTSTATUS SriovGetVendorAndDeviceIds(
  _In_  PVOID   Context,
  _In_  USHORT  VfIndex,
  _Out_ PUSHORT VendorId,
  _Out_ PUSHORT DeviceId
)
{ ... }

typedef SRIOV_GET_VENDOR_AND_DEVICE_IDS *PSRIOV_GET_VENDOR_AND_DEVICE_IDS;
````


## -parameters
<dl>

### -param <i>Context</i> [in]

<dd>
<p>A pointer to a driver-defined context.
                    
                </p>
</dd>

### -param <i>VfIndex</i> [in]

<dd>
<p>A zero-based index of the VF to which this write operation applies.</p>
</dd>

### -param <i>VendorId</i> [out]

<dd>
<p>
                    
                A pointer to a USHORT variable that is filled with the vendor ID of the VF.</p>
</dd>

### -param <i>DeviceId</i> [out]

<dd>
<p>
                    
                A pointer to a USHORT variable that is filled with the device ID of the VF.</p>
</dd>
</dl>

## -returns
<p>
Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.</p>

## -remarks
<p>This callback function is implemented by the physical function (PF) driver. It is invoked  when the system wants to retrieve the vendor and device identifiers of the specified VF. </p>

<p>The PCI Express SR-IOV Specification requires that all VFs have the same Vendor and Device IDs.  This is a requirement of compliant hardware.  However, it’s possible to provision VFs such that their capabilities differ from each other, and it’s often useful to load different drivers on different hardware.  So Windows allows the  PF driver to supply separate Device and Vendor IDs (with different class codes, through the configuration space interfaces) such that each VF may appear with the Plug and Play IDs that are most appropriate for its use.</p>

<p>The PF driver registers its implementation by setting the <b>GetVendorAndDevice</b> member of the <a href="buses._sriov_device_interface_standard">SRIOV_DEVICE_INTERFACE_STANDARD</a>, configuring a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552439">WDF_QUERY_INTERFACE_CONFIG</a> structure, and calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff545870">WdfDeviceAddQueryInterface</a>.</p>

<p>Here is an example implementation of this callback function. </p>

<p>This callback function is implemented by the physical function (PF) driver. It is invoked  when the system wants to retrieve the vendor and device identifiers of the specified VF. </p>

<p>The PCI Express SR-IOV Specification requires that all VFs have the same Vendor and Device IDs.  This is a requirement of compliant hardware.  However, it’s possible to provision VFs such that their capabilities differ from each other, and it’s often useful to load different drivers on different hardware.  So Windows allows the  PF driver to supply separate Device and Vendor IDs (with different class codes, through the configuration space interfaces) such that each VF may appear with the Plug and Play IDs that are most appropriate for its use.</p>

<p>The PF driver registers its implementation by setting the <b>GetVendorAndDevice</b> member of the <a href="buses._sriov_device_interface_standard">SRIOV_DEVICE_INTERFACE_STANDARD</a>, configuring a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552439">WDF_QUERY_INTERFACE_CONFIG</a> structure, and calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff545870">WdfDeviceAddQueryInterface</a>.</p>

<p>Here is an example implementation of this callback function. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 10</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2016</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Pcivirt.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
</table>