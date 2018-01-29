---
UID : NI:bthxddi.IOCTL_BTHX_GET_VERSION
title : IOCTL_BTHX_GET_VERSION
author : windows-driver-content
description : Profile drivers use IOCTL_BTHX_GET_VERSION to get the version supported by the transport driver.
old-location : bltooth\ioctl_bthx_get_version.htm
old-project : bltooth
ms.assetid : F4FD760B-551C-4738-A13D-444E08215D59
ms.author : windowsdriverdev
ms.date : 12/21/2017
ms.keywords : bltooth.ioctl_bthx_get_version, IOCTL_BTHX_GET_VERSION control code [Bluetooth Devices], IOCTL_BTHX_GET_VERSION, bthxddi/IOCTL_BTHX_GET_VERSION
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : bthxddi.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Supported starting with  Windows 8.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : "<= PASSIVE_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PBTHX_SCO_SUPPORT, BTHX_SCO_SUPPORT"
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
Profile drivers should use KMDF and its <a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveoutputmemory.md">WdfRequestRetrieveOutputMemory</a> method to retrieve output parameters.  For example, to get the output buffer:

<code>Status = WdfRequestRetrieveOutputMemory(_Request, &amp;ReqOutMemory);</code>

The buffer describes a <a href="..\bthxddi\ns-bthxddi-_bthx_version.md">BTHX_VERSION</a> structure. 

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
| **Windows Driver kit version** |  |
| **Header** | bthxddi.h |
| **IRQL** | <= PASSIVE_LEVEL |