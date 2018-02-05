---
UID : NI:nfcsedev.IOCTL_NFCSE_GET_ROUTING_TABLE
title : IOCTL_NFCSE_GET_ROUTING_TABLE
author : windows-driver-content
description : Returns information regarding the current configuration of listen mode routing table.
old-location : nfpdrivers\ioctl_nfcse_get_routing_table.htm
old-project : nfpdrivers
ms.assetid : 838D31E8-1835-47C7-8201-93910610F5EC
ms.author : windowsdriverdev
ms.date : 12/18/2017
ms.keywords : nfpdrivers.ioctl_nfcse_get_routing_table, IOCTL_NFCSE_GET_ROUTING_TABLE control code [Near-Field Proximity Drivers], IOCTL_NFCSE_GET_ROUTING_TABLE, nfcsedev/IOCTL_NFCSE_GET_ROUTING_TABLE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : nfcsedev.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
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
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PSECURE_ELEMENT_TYPE, SECURE_ELEMENT_TYPE"
---

# IOCTL_NFCSE_GET_ROUTING_TABLE IOCTL
Returns information regarding the current configuration of listen mode routing table. Note that the caller must allocate an output buffer large enough to hold information regarding all the entries that are present in the current listen mode routing table, i.e. Total number of routing entries x Size of routing table entry, otherwise the driver should return a STATUS_BUFFER_OVERFLOW error code to the client with NumberOfEntries field containing the number of routing table entries configured. The routing table entry is of type SECURE_ELEMENT_ROUTING_TABLE_ENTRY. Note: The driver shouldn’t return entry routing NFC-DEP to DH as part of the routing table returned in the output buffer even though the entry is present in the NFCC routing table.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
None

### Input Buffer Length
None

### Output Buffer
<a href="..\nfcsedev\ns-nfcsedev-_secure_element_routing_table.md"> SECURE_ELEMENT_ROUTING_TABLE</a> containing all currently configured routing entries.

### Output Buffer Length
sizeof(SECURE_ELEMENT_ROUTING_TABLE)

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
<b>Irp-&gt;IoStatus.Status</b> is set to <b>STATUS_SUCCESS</b> if the request is successful. Possible error codes are:
<table>
<tr>
<th>Return Code</th>
<th>Description</th>
</tr>
<tr>
<td><b>STATUS_BUFFER_OVERFLOW</b></td>
<td>The buffer supplied was too small to receive the routing table configuration.</td>
</tr>
<tr>
<td><b>STATUS_FEATURE_NOT_SUPPORTED</b></td>
<td>The NFCC does not support listen mode routing configuration.
</td>
</tr>
<tr>
<td><b>STATUS_INVALID_PARAMETER</b></td>
<td>This code is returned if the input buffer is non-zero.</td>
</tr>
<tr>
<td><b>STATUS_INVALID_DEVICE_STATE</b></td>
<td>This code is returned if the IOCTL is sent on a handle other than with relative name ‘SEManage’.
</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | nfcsedev.h |