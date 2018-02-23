---
UID: NI:bthxddi.IOCTL_BTHX_QUERY_CAPABILITIES
title: IOCTL_BTHX_QUERY_CAPABILITIES
author: windows-driver-content
description: IOCTL_BTHX_QUERY_CAPABILITIES is used to query the capabilities of the transport driver.
old-location: bltooth\ioctl_bthx_query_capabilities.htm
old-project: bltooth
ms.assetid: 199C93EC-AB91-47F1-914A-F44BFF1796A6
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: bltooth.ioctl_bthx_query_capabilities, IOCTL_BTHX_QUERY_CAPABILITIES control code [Bluetooth Devices], IOCTL_BTHX_QUERY_CAPABILITIES, bthxddi/IOCTL_BTHX_QUERY_CAPABILITIES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: bthxddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 8.
req.target-min-winversvr: 
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	BthXDDI.h
apiname:
-	IOCTL_BTHX_QUERY_CAPABILITIES
product: Windows
targetos: Windows
req.typenames: "*PBTHX_SCO_SUPPORT, BTHX_SCO_SUPPORT"
---

# IOCTL_BTHX_QUERY_CAPABILITIES IOCTL
IOCTL_BTHX_QUERY_CAPABILITIES is used to query the capabilities of the transport driver.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
None.

### Input Buffer Length
None.

### Output Buffer
The <b>AssociatedIrp.SystemBuffer</b> member points to a buffer that holds a <a href="..\bthxddi\ns-bthxddi-_bthx_capabilities.md">BTHX_CAPABILITIES</a> structure.

### Output Buffer Length
The length of the buffer is the size of the <b>BTHX_CAPABILITIES</b> structure.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The 
      <b>Information</b> member of the STATUS_BLOCK structure is set to the size of the structure.

The 
      <b>Status</b> member is set to one of the values in the following table.

<table>
<tr>
<th>Status value</th>
<th>Description</th>
</tr>
<tr>
<td>
STATUS_SUCCESS

</td>
<td>
The IOCTL completed successfully.

</td>
</tr>
</table>

## Remarks
During startup, the Bluetooth stack sends IOCTL_BTHX_QUERY_CAPABILITIES to query the capabilities of the transport driver.

This is a synchrononous call and failure of this IOCTL prevents Windows from loading the Bluetooth stack.

The output buffer of this IOCTL is defined by the BTHX_CAPABILITIES structure.

The <b>MaxScoChannels</b> member must be set to 1. The <b>ScoSupport</b> member must be set to <b>ScoSupportHCIBypass</b>. Failure to do so prevents the stack from being loaded.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with  Windows 8. Supported starting with  Windows 8. |
| **Header** | bthxddi.h |
| **IRQL** | "<= DISPATCH_LEVEL" |