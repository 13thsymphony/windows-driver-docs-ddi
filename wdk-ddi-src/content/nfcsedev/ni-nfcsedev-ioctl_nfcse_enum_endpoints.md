---
UID: NI:nfcsedev.IOCTL_NFCSE_ENUM_ENDPOINTS
title: IOCTL_NFCSE_ENUM_ENDPOINTS
author: windows-driver-content
description: Returns information regarding the list of all the secure elements attached to the NFC controller.
old-location: nfpdrivers\ioctl_nfcse_enum_endpoints.htm
old-project: nfpdrivers
ms.assetid: BDE62A2B-423E-4656-91CC-5EBDE50C6BB0
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: nfpdrivers.ioctl_nfcse_enum_endpoints, IOCTL_NFCSE_ENUM_ENDPOINTS, _IOCTL_NFCSE_ENUM_ENDPOINTS, IOCTL_NFCSE_ENUM_ENDPOINTS control code [Near-Field Proximity Drivers], IOCTL_NFCSE_ENUM_ENDPOINTS, nfcsedev/IOCTL_NFCSE_ENUM_ENDPOINTS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: nfcsedev.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	nfcsedev.h
apiname:
-	IOCTL_NFCSE_ENUM_ENDPOINTS
product: Windows
targetos: Windows
req.typenames: "*PSECURE_ELEMENT_TYPE, SECURE_ELEMENT_TYPE"
---

# IOCTL_NFCSE_ENUM_ENDPOINTS IOCTL
Returns information regarding the list of all the secure elements attached to the NFC controller. Note that the caller must allocate an output buffer large enough to hold information regarding all the secure elements that were enumerated by the driver i.e. Total number of SEs Enumerated x Size of the SE endpoint info otherwise the driver should return a STATUS_BUFFER_OVERFLOW error code to the client with the NumberOfEndpoints field containing the number of secure elements enumerated. The GUID identifying the secure element which maybe used to refer to a particular secure element.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
None

### Input Buffer Length
None

### Output Buffer
An <a href="..\nfcsedev\ns-nfcsedev-_secure_element_endpoint_list.md"> SECURE_ELEMENT_ENDPOINT_LIST</a> for each device enumerated.

### Output Buffer Length
<text></text>

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
<td><b>STATUS_INVALID_PARAMETER</b></td>
<td>This code is returned when the output buffer is non-zero.</td>
</tr>
<tr>
<td><b>STATUS_BUFFER_OVERFLOW</b></td>
<td>The buffer supplied was too small to receive the routing table configuration.</td>
</tr>
</table>

## Remarks
The following are requirements that the driver must adhere to.

<ul>
<li>In the case of integrated secure element the GUID shall be a unique identifier derived from the serial number and/or other unique identification of the secure element.

</li>
<li>For external secure elements, the GUID maybe a fixed constant and identifies only the “socket” into which the secure element is connected.</li>
<li>For device host secure element, the driver shall enumerate it as a SE end point only if it supports Host Card Emulation. The GUID used for DH maybe a fixed constant defined by the driver.</li>
<li>The caller is required to allocate an output buffer large enough to hold the information about all the secure elements that were enumerated by the driver. The buffer must be equal to the total number of SEs enumerated by the driver multiplied by the size of the SE endpoint information. If the appropriate buffer isn’t allocated, the driver returns a STATUS_BUFFER_OVERFLOW error code to the client with the NumberOfEndpoints field that contains the number of secure elements enumerated.</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | nfcsedev.h |