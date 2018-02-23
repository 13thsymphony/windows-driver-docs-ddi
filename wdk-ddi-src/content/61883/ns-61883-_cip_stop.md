---
UID: NS:61883._CIP_STOP
title: "_CIP_STOP"
author: windows-driver-content
description: This structure is used to stop transmission or reception.
old-location: ieee\cip_stop.htm
old-project: IEEE
ms.assetid: FE396C2C-B099-47F4-9C27-93D420D54103
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PCIP_STOP, 61883/CIP_STOP, CIP_STOP structure [Buses], _CIP_STOP, IEEE.cip_stop, PCIP_STOP, CIP_STOP, PCIP_STOP structure pointer [Buses], 61883/PCIP_STOP"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 61883.h
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
-	61883.h
apiname:
-	CIP_STOP
product: Windows
targetos: Windows
req.typenames: "*PCIP_STOP, CIP_STOP"
---

# _CIP_STOP structure
This structure is used to stop transmission or reception. The  request stops isochronous transmission or reception on the specified connection. This request will stop capturing CIP packets, whether there are any frames attached. If frames are attached and the stream is resumed, then processing of the frame is resumed on the next source packet within the frame. To resume the stream on the beginning of the frame, a driver must set <b>Flags</b> with CIP_RESET_FRAME_ON_DISCONTINUITY in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537045">CIP_FRAME</a> structure passed with AttachFrame request.

## Syntax
````
typedef struct _CIP_STOP {
  HANDLE hConnect;
} CIP_STOP, *PCIP_STOP;
````

## Members


`hConnect`

On input, a handle to the connection on which to stop isochronous transmission or reception.

## Remarks
If successful, the IEC-61883 protocol driver sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_SUCCESS. 

If an incorrect parameter is passed in, the protocol driver sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_INVALID_PARAMETER.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | 61883.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537008">AV_61883_REQUEST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20CIP_STOP structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>