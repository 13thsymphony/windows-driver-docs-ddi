---
UID: NC.pcivirt.SRIOV_QUERY_PROBED_BARS
title: SRIOV_QUERY_PROBED_BARS
author: windows-driver-content
description: Queries the data read from the physical function's (PF) base address registers (BARs) if the value -1 were written to them first.
old-location: pci\sriov_query_probed_bars.htm
old-project: PCI
ms.assetid: 422a9212-7227-4508-8f06-0056349fa835
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
req.alt-api: *PSRIOV_QUERY_PROBED_BARS
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

# SRIOV_QUERY_PROBED_BARS callback



## -description

Queries the data read from
    the physical  function's (PF) base address registers (BARs) if the value -1 were written to them first.


## -prototype

````
SRIOV_QUERY_PROBED_BARS SriovQueryProbedBars;

NTSTATUS SriovQueryProbedBars(
  _In_  PVOID  Context,
  _Out_ PULONG BaseRegisterValues
)
{ ... }

typedef SRIOV_QUERY_PROBED_BARS *PSRIOV_QUERY_PROBED_BARS;
````


## -parameters

### -param Context [in]

A pointer to a driver-defined context.
                    
                

### -param BaseRegisterValues [out]

A pointer to an array of variables that is bounded by the number of BARs in a PCI device.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.

## -remarks
This callback function is implemented by the physical function (PF) driver. It is invoked  when the system wants to get base address register values. 

The PF driver registers its implementation by setting the <b>QueryProbedBars</b> member of the <a href="buses._sriov_device_interface_standard">SRIOV_DEVICE_INTERFACE_STANDARD</a>, configuring a <a href="wdf.wdf_query_interface_config">WDF_QUERY_INTERFACE_CONFIG</a> structure, and calling <a href="wdf.wdfdeviceaddqueryinterface">WdfDeviceAddQueryInterface</a>.

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