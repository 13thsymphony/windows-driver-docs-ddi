---
UID : NC:pcivirt.SRIOV_READ_BLOCK
title : SRIOV_READ_BLOCK
author : windows-driver-content
description : Reads data from the specified configuration block of a PCI Express SR-IOV Virtual Function (VF).
old-location : pci\sriov_read_block.htm
old-project : PCI
ms.assetid : af0d3465-2854-47d9-a6a4-06f510229a59
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _PARCLASS_INFORMATION, PARCLASS_INFORMATION, *PPARCLASS_INFORMATION
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : pcivirt.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : Windows Server 2016
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : "*PSRIOV_READ_BLOCK"
req.alt-loc : Pcivirt.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : PARCLASS_INFORMATION, *PPARCLASS_INFORMATION
---


# SRIOV_READ_BLOCK function
Reads data from the specified configuration block of a PCI Express SR-IOV Virtual Function (VF).

## Syntax

```
SRIOV_READ_BLOCK SriovReadBlock;

NTSTATUS SriovReadBlock(
  PVOID Context,
  USHORT VfIndex,
  ULONG BlockId,
  PVOID Buffer,
  ULONG Length
)
{...}
```

## Parameters

`Context`

A pointer to a driver-defined context.

`VfIndex`

A zero-based index of the VF to which this read operation applies.

`BlockId`

A number identifying the block to be read.  This is defined by the provider of the PF driver.

`Buffer`

A pointer to a buffer that receives the data read from the VF's  configuration space.

`Length`

The length in bytes of this read operation.  Must not be greater than VPCI_MAX_READ_WRITE_BLOCK_SIZE defined in Pcivirt.h.


## Return Value

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.

## Remarks

This callback function is implemented by the physical function (PF) driver. It is invoked  when the system wants to read a configuration block for one of its VFs.

The PF driver registers its implementation by setting the <b>ReadVfConfigBlock</b> member of the <a href="https://msdn.microsoft.com/c71add7d-9920-4b2f-a46a-4a09a94f3900">SRIOV_DEVICE_INTERFACE_STANDARD</a>, configuring a <a href="..\wdfqueryinterface\ns-wdfqueryinterface-_wdf_query_interface_config.md">WDF_QUERY_INTERFACE_CONFIG</a> structure, and calling <a href="..\wdfqueryinterface\nf-wdfqueryinterface-wdfdeviceaddqueryinterface.md">WdfDeviceAddQueryInterface</a>.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | pcivirt.h |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |