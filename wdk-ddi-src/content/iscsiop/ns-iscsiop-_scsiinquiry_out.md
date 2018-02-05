---
UID : NS:iscsiop._ScsiInquiry_OUT
title : "_ScsiInquiry_OUT"
author : windows-driver-content
description : The ScsiInquiry_OUT structure holds the output data for the ScsiInquiry method.
old-location : storage\scsiinquiry_out.htm
old-project : storage
ms.assetid : ac3ec079-61a5-42fe-a1c0-b7626e5f32d2
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : PScsiInquiry_OUT, storage.scsiinquiry_out, PScsiInquiry_OUT structure pointer [Storage Devices], *PScsiInquiry_OUT, ScsiInquiry_OUT, _ScsiInquiry_OUT, iscsiop/PScsiInquiry_OUT, ScsiInquiry_OUT structure [Storage Devices], iscsiop/ScsiInquiry_OUT, structs-iSCSI_0c90b572-8a05-4a75-86ce-5b12d82a1c2f.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : iscsiop.h
req.include-header : Iscsiop.h
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
req.typenames : ScsiInquiry_OUT, *PScsiInquiry_OUT
---

# _ScsiInquiry_OUT structure
The ScsiInquiry_OUT structure holds the output data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564585">ScsiInquiry</a> method.

## Syntax
````
typedef struct _ScsiInquiry_OUT {
  ULONG Status;
  ULONG ResponseBufferSize;
  UCHAR ScsiStatus;
  UCHAR SenseBuffer[18];
  UCHAR ResponseBuffer[1];
} ScsiInquiry_OUT, *PScsiInquiry_OUT;
````

## Members


`ResponseBuffer`

A buffer that holds the response data that the SCSI INQUIRY command received.

`ResponseBufferSize`

The response buffer size, in bytes<i>.</i>

`ScsiStatus`

The status of the SCSI INQUIRY command.

`SenseBuffer`

A buffer that holds the SCSI sense data that the SCSI INQUIRY command received.

`Status`

The status of the <b>ScsiInquiry</b> operation. This member will contain 0 if the INQUIRY operation succeeds and ISDSC_SCSI_REQUEST_FAILED if the operation fails. If the INQUIRY operation fails, <b>ScsiStatus</b> will contain the SCSI status of the SCSI command. SCSI status qualifiers are documented in the <i>SCSI Primary Commands</i> specification. For a list of status qualifiers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>.

## Remarks
You must implement this method.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iscsiop.h (include Iscsiop.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>

<a href="..\iscsiop\ns-iscsiop-_scsiinquiry_in.md">ScsiInquiry_IN</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564585">ScsiInquiry</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ScsiInquiry_OUT structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>