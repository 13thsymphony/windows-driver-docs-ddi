---
UID: NC.pcivirt.SRIOV_READ_CONFIG
title: SRIOV_READ_CONFIG
author: windows-driver-content
description: Reads data from the configuration space of the specified PCI Express SR-IOV Virtual Function (VF).
old-location: pci\sriov_read_config.htm
old-project: PCI
ms.assetid: 0fef9d53-b8af-4c9b-9914-982bcfc26517
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
req.alt-api: *PSRIOV_READ_CONFIG
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
---

# SRIOV_READ_CONFIG callback



## -description
Reads data from  the configuration space of the specified PCI Express SR-IOV Virtual Function (VF).


## -prototype

````
NTSTATUS  SRIOV_READ_CONFIG(
  _In_        PVOID  Context,
  _Out_ const VOID   *Data,
  _In_        USHORT VfIndex,
  _In_        ULONG  Offset,
  _In_        ULONG  Length
);

typedef SRIOV_READ_CONFIG *PSRIOV_READ_CONFIG;
````


## -parameters

### -param Context [in]

A pointer to a driver-defined context.
                    
                

### -param Data [out]

A pointer to buffer that contains the configuration information to be read from the VF's configuration space.

### -param VfIndex [in]

A zero-based index of the VF to which this read operation applies.

### -param Offset [in]

An offset in bytes to the start of the VF’s configuration space where the read begins.

### -param Length [in]

The length, in bytes, of the data to read from the configuration space.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.

## -remarks
This callback function is implemented by the physical function (PF) driver. It is invoked  when the system wants to read from the configuration space of a specific virtual function. 

The PF driver registers its implementation by setting the <b>ReadVfConfig</b> member of the <a href="buses._sriov_device_interface_standard">SRIOV_DEVICE_INTERFACE_STANDARD</a>, configuring a <a href="wdf.wdf_query_interface_config">WDF_QUERY_INTERFACE_CONFIG</a> structure, and calling <a href="wdf.wdfdeviceaddqueryinterface">WdfDeviceAddQueryInterface</a>.

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
PASSIVE_LEVEL
</td>
</tr>
</table>