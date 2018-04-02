---
UID: NI:bthxddi.IOCTL_BTHX_GET_VERSION
title: IOCTL_BTHX_GET_VERSION
author: windows-driver-content
description: Profile drivers use IOCTL_BTHX_GET_VERSION to get the version supported by the transport driver.
old-location: bltooth\ioctl_bthx_get_version.htm
old-project: bltooth
ms.assetid: F4FD760B-551C-4738-A13D-444E08215D59
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_BTHX_GET_VERSION, IOCTL_BTHX_GET_VERSION control code [Bluetooth Devices], bltooth.ioctl_bthx_get_version, bthxddi/IOCTL_BTHX_GET_VERSION
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
req.irql: "<= PASSIVE_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	BthXDDI.h
api_name:
-	IOCTL_BTHX_GET_VERSION
product: Windows
targetos: Windows
req.typenames: BTHX_SCO_SUPPORT, *PBTHX_SCO_SUPPORT
---

# IOCTL_BTHX_GET_VERSION IOCTL
Profile drivers use IOCTL_BTHX_GET_VERSION to get the version supported by the transport driver.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
None.

### Input Buffer Length
None.

### Output Buffer
Profile drivers should use KMDF and its <a href="https://msdn.microsoft.com/library/windows/hardware/ff550019">WdfRequestRetrieveOutputMemory</a> method to retrieve output parameters.  For example, to get the output buffer:

<code>Status = WdfRequestRetrieveOutputMemory(_Request, &amp;ReqOutMemory);</code>

The buffer describes a <a href="https://msdn.microsoft.com/library/windows/hardware/hh450838">BTHX_VERSION</a> structure. 

Refer to the WDK Bluetooth samples for more information.

### Output Buffer Length
The length of the buffer is the size of the <b>BTHX_VERSION</b> structure.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The 
      <b>Information</b> member of the STATUS_BLOCK structure is set to the size, in bytes, of the buffer that holds the BTHX_VERSION structure.

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
 

Any unsuccessful NT status code prevents the driver from loading.

## Remarks
IOCTL_BTHX_GET_VERSION is a synchronous operation.

A transport driver can return one or more versions that it supports in BTHX_VERSION structure.  If no version is set,  Windows unloads the Bluetooth stack.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with  Windows 8. Supported starting with  Windows 8. |
| **Header** | bthxddi.h |
| **IRQL** | "<= PASSIVE_LEVEL" |