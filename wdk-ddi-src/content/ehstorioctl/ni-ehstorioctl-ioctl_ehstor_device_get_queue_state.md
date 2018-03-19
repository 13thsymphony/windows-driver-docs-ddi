---
UID: NI:ehstorioctl.IOCTL_EHSTOR_DEVICE_GET_QUEUE_STATE
title: IOCTL_EHSTOR_DEVICE_GET_QUEUE_STATE
author: windows-driver-content
description: The IOCTL_EHSTOR_DEVICE_GET_QUEUE_STATE request is sent by silo drivers and applications to determine the state of a storage device queue.
old-location: storage\ioctl_ehstor_device_get_queue_state.htm
old-project: storage
ms.assetid: 1BF7E7B3-26CF-41BB-B2E9-8EDC6872CF34
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_EHSTOR_DEVICE_GET_QUEUE_STATE, IOCTL_EHSTOR_DEVICE_GET_QUEUE_STATE control code [Storage Devices], ehstorioctl/IOCTL_EHSTOR_DEVICE_GET_QUEUE_STATE, storage.ioctl_ehstor_device_get_queue_state
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ehstorioctl.h
req.include-header: EhStorIoctl.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	EhStorIoctl.h
api_name:
-	IOCTL_EHSTOR_DEVICE_GET_QUEUE_STATE
product: Windows
targetos: Windows
req.typenames: PDO_TYPE
---

# IOCTL_EHSTOR_DEVICE_GET_QUEUE_STATE IOCTL
The <b>IOCTL_EHSTOR_DEVICE_GET_QUEUE_STATE</b> request is sent by silo drivers and applications to determine the state of a storage device queue. IO requests in the storage device queue are held when the device is temporarily unauthorized. A storage device may become temporarily unauthorized in low power states or when there is a policy that requires locking Enhanced Storage devices such as when the user session is locked.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
None.

### Input Buffer Length
None.

### Output Buffer
The output buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains an <b> ACT_QUEUE_STATE</b>  structure. <b>ACT_QUEUE_STATE</b> is declared in <i>ehstorioctl.h</i> as the following.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct tagACT_QUEUE_STATE
{
    BOOLEAN fFrozen;
} ACT_QUEUE_STATE;</pre>
</td>
</tr>
</table></span></div>

### Output Buffer Length
The length of an <b> ACT_QUEUE_STATE</b>  structure.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
One of the following values can be returned in the <b>Status</b> field.

<table>
<tr>
<th>Status Value</th>
<th>Description</th>
</tr>
<tr>
<td>STATUS_SUCCESS</td>
<td>The queue state was returned successfully.</td>
</tr>
<tr>
<td>STATUS_BUFFER_TOO_SMALL</td>
<td>The output buffer length is too small.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8 Available starting with Windows 8 |
| **Header** | ehstorioctl.h (include EhStorIoctl.h) |

## See Also

<a href="..\ehstorioctl\ni-ehstorioctl-ioctl_ehstor_device_set_queue_state.md">IOCTL_EHSTOR_DEVICE_SET_QUEUE_STATE</a>