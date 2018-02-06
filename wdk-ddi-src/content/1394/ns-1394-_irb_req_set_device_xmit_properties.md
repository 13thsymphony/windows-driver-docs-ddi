---
UID: NS:1394._IRB_REQ_SET_DEVICE_XMIT_PROPERTIES
title: "_IRB_REQ_SET_DEVICE_XMIT_PROPERTIES"
author: windows-driver-content
description: This structure contains the fields necessary to carry out a SetDeviceXmitProperties request.
old-location: ieee\irb_req_set_device_xmit_properties.htm
old-project: IEEE
ms.assetid: 1E99F892-CD7C-411D-8832-08F988B9F2D7
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IRB_REQ_SET_DEVICE_XMIT_PROPERTIES, _IRB_REQ_SET_DEVICE_XMIT_PROPERTIES, 1394/IRB_REQ_SET_DEVICE_XMIT_PROPERTIES, IEEE.irb_req_set_device_xmit_properties, IRB_REQ_SET_DEVICE_XMIT_PROPERTIES structure [Buses]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 1394.h
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
-	1394.h
apiname:
-	IRB_REQ_SET_DEVICE_XMIT_PROPERTIES
product: Windows
targetos: Windows
req.typenames: IRB_REQ_SET_DEVICE_XMIT_PROPERTIES
---

# _IRB_REQ_SET_DEVICE_XMIT_PROPERTIES structure
This structure contains the fields necessary to carry out a SetDeviceXmitProperties request.

## Syntax
````
typedef struct _IRB_REQ_SET_DEVICE_XMIT_PROPERTIES {
  ULONG fulSpeed;
  ULONG fulPriority;
} IRB_REQ_SET_DEVICE_XMIT_PROPERTIES;
````

## Members


`fulPriority`

Specifies the priority.

`fulSpeed`

Specifies the maximum speed for transactions to the device. The possible speed values are SPEED_FLAGS_xxx, where xxx is the (approximate) transfer rate in megabits per second. Existing hardware supports transfer rates of 100, 200, and 400 Mb/sec.
<table>
<tr>
<th>Transfer Rate</th>
<th>Description</th>
</tr>
<tr>
<td>
SPEED_FLAGS_100

</td>
<td>
100 Mb/s

</td>
</tr>
<tr>
<td>
SPEED_FLAGS_200

</td>
<td>
200 Mb/s

</td>
</tr>
<tr>
<td>
SPEED_FLAGS_400

</td>
<td>
400 Mb/s

</td>
</tr>
</table> 

Reserved.
<div class="alert"><b>Note</b>  In Windows 7 and later versions of Windows, you can specify new values higher speed and  greater sized payloads. For more information, see <a href="https://msdn.microsoft.com/5473C6AC-284C-41B1-AA67-75696BE96C24">New Flags for Speed and Payload Size</a> and <a href="https://msdn.microsoft.com/5473C6AC-284C-41B1-AA67-75696BE96C24">IEEE 1394 IOCTL Changes</a> in Device Driver Interface (DDI) Changes in Windows 7.</div><div> </div>

## Remarks
By default, the maximum permitted transmission speed is the physical maximum. A driver should use this request to lower the maximum permitted speed.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | 1394.h |