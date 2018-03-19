---
UID: NS:1394._IRB_REQ_ASYNC_STREAM
title: "_IRB_REQ_ASYNC_STREAM"
author: windows-driver-content
description: This structure contains the fields necessary for the 1394 bus driver to carry out an asynchronous write request.
old-location: ieee\irb_req_async_stream.htm
old-project: IEEE
ms.assetid: 9E4958B0-066F-4485-AFF2-3AE499AF3E64
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: 1394/IRB_REQ_ASYNC_STREAM, IEEE.irb_req_async_stream, IRB_REQ_ASYNC_STREAM, IRB_REQ_ASYNC_STREAM structure [Buses], _IRB_REQ_ASYNC_STREAM
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	1394.h
api_name:
-	IRB_REQ_ASYNC_STREAM
product: Windows
targetos: Windows
req.typenames: IRB_REQ_ASYNC_STREAM
---

# _IRB_REQ_ASYNC_STREAM structure
This structure contains the fields necessary for the 1394 bus driver to carry out an asynchronous write request.

## Syntax
````
typedef struct _IRB_REQ_ASYNC_STREAM {
  ULONG nNumberOfBytesToStream;
  ULONG fulFlags;
  PMDL  Mdl;
  ULONG ulTag;
  ULONG nChannel;
  ULONG ulSynch;
  ULONG Reserved;
  UCHAR nSpeed;
} IRB_REQ_ASYNC_STREAM;
````

## Members


`nNumberOfBytesToStream`

Specifies the number of bytes to write.

`fulFlags`

Reserved. Drivers must set this to zero.

`Mdl`

Specifies the source buffer.

`ulTag`

Specifies the Tag field for any packets generated from this request.

`nChannel`

Specifies the channel to which the data will be written.

`ulSynch`

Specifies the Sy field for any packets generated from this request.

`Reserved`

Reserved. Drivers must set this to zero.

`nSpeed`

Specifies the transfer rate. The possible speed values are SPEED_FLAGS_xxx, where xxx is the (approximate) transfer rate in megabits per second. Existing hardware currently supports transfer rates of 100, 200, and 400 Mb/sec.

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
 

<div class="alert"><b>Note</b>  In Windows 7 and later versions of Windows, you can specify new values higher speed and  greater sized payloads. For more information, see <a href="https://msdn.microsoft.com/5473C6AC-284C-41B1-AA67-75696BE96C24">New Flags for Speed and Payload Size</a> and <a href="https://msdn.microsoft.com/5473C6AC-284C-41B1-AA67-75696BE96C24">IEEE 1394 IOCTL Changes</a> in Device Driver Interface (DDI) Changes in Windows 7.</div>
<div> </div>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | 1394.h |