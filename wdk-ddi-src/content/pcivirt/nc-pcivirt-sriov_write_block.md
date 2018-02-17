---
UID: NC:pcivirt.SRIOV_WRITE_BLOCK
title: SRIOV_WRITE_BLOCK
author: windows-driver-content
description: Writes data to the specified configuration block of a PCI Express SR-IOV Virtual Function (VF).
old-location: pci\sriov_write_block.htm
old-project: PCI
ms.assetid: da47d601-2fab-49bb-b669-909a2e5c95c0
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: PCI.sriov_write_block, SriovWriteBlock callback function [Buses], SriovWriteBlock, SRIOV_WRITE_BLOCK, SRIOV_WRITE_BLOCK, pcivirt/SriovWriteBlock, *PSRIOV_WRITE_BLOCK callback function pointer [Buses], *PSRIOV_WRITE_BLOCK
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
-	*PSRIOV_WRITE_BLOCK
product: Windows
targetos: Windows
req.typenames: "*PPARCLASS_INFORMATION, PARCLASS_INFORMATION"
---


# SRIOV_WRITE_BLOCK function
Writes data to the specified configuration block of a PCI Express SR-IOV Virtual Function (VF).

## Syntax

```
SRIOV_WRITE_BLOCK SriovWriteBlock;

NTSTATUS SriovWriteBlock(
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

A zero-based index of the VF to which this write operation applies.

`BlockId`

A number identifying the block to be written.  This is defined by the provider of the PF driver.

`Buffer`

A pointer to a buffer that contains the data to write to the VF's  configuration space.

`Length`

The length in bytes of this write operation.  Must not be greater than VPCI_MAX_READ_WRITE_BLOCK_SIZE defined in Pcivirt.h.


## Return Value

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.

## Remarks

This callback function is implemented by the physical function (PF) driver. It is invoked  when the system wants to read a configuration block for one of its VFs.

The PF driver registers its implementation by setting the <b>WriteVfConfigBlock</b> member of the <a href="https://msdn.microsoft.com/c71add7d-9920-4b2f-a46a-4a09a94f3900">SRIOV_DEVICE_INTERFACE_STANDARD</a>, configuring a <a href="..\wdfqueryinterface\ns-wdfqueryinterface-_wdf_query_interface_config.md">WDF_QUERY_INTERFACE_CONFIG</a> structure, and calling <a href="..\wdfqueryinterface\nf-wdfqueryinterface-wdfdeviceaddqueryinterface.md">WdfDeviceAddQueryInterface</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | pcivirt.h |
| **IRQL** | PASSIVE_LEVEL |