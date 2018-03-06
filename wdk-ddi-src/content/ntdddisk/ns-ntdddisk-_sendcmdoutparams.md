---
UID: NS:ntdddisk._SENDCMDOUTPARAMS
title: "_SENDCMDOUTPARAMS"
author: windows-driver-content
description: The SENDCMDOUTPARAMS structure is used in conjunction with the SMART_SEND_DRIVE_COMMAND request to retrieve data returned by a Self-Monitoring Analysis and Reporting Technology (SMART) command.
old-location: storage\sendcmdoutparams.htm
old-project: storage
ms.assetid: e9fb6d5c-258c-46eb-ba3a-3f10008fdf68
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPSENDCMDOUTPARAMS, *PSENDCMDOUTPARAMS, LPSENDCMDOUTPARAMS, LPSENDCMDOUTPARAMS structure pointer [Storage Devices], PSENDCMDOUTPARAMS, PSENDCMDOUTPARAMS structure pointer [Storage Devices], SENDCMDOUTPARAMS, SENDCMDOUTPARAMS structure [Storage Devices], _SENDCMDOUTPARAMS, ntdddisk/LPSENDCMDOUTPARAMS, ntdddisk/PSENDCMDOUTPARAMS, ntdddisk/SENDCMDOUTPARAMS, storage.sendcmdoutparams, structs-IDE_d1a70016-0e77-465a-9368-665975369bdc.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
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
-	ntdddisk.h
api_name:
-	SENDCMDOUTPARAMS
product: Windows
targetos: Windows
req.typenames: SENDCMDOUTPARAMS, *PSENDCMDOUTPARAMS, *LPSENDCMDOUTPARAMS
---

# _SENDCMDOUTPARAMS structure
The SENDCMDOUTPARAMS structure is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566206">SMART_SEND_DRIVE_COMMAND</a> request to retrieve data returned by a Self-Monitoring Analysis and Reporting Technology (SMART) command.

## Syntax
````
typedef struct _SENDCMDOUTPARAMS {
  ULONG        cBufferSize;
  DRIVERSTATUS DriverStatus;
  UCHAR        bBuffer[1];
} SENDCMDOUTPARAMS, *PSENDCMDOUTPARAMS, *LPSENDCMDOUTPARAMS;
````

## Members


`bBuffer`

Pointer to a buffer in which to store the data read from the drive.

`cBufferSize`

Contains the size in bytes of the buffer pointed to by <b>bBuffer</b>.

`DriverStatus`

Contains a <a href="..\ntdddisk\ns-ntdddisk-_driverstatus.md">DRIVERSTATUS</a> structure that indicates the driver status.

## Remarks
The <a href="https://msdn.microsoft.com/library/windows/hardware/ff566206">SMART_SEND_DRIVE_COMMAND</a> is used to send SMART commands to a device. 

The SENDCMDOUTPARAMS structure is also used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566204">SMART_RCV_DRIVE_DATA</a> request.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntdddisk.h (include Ntdddisk.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566204">SMART_RCV_DRIVE_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566206">SMART_SEND_DRIVE_COMMAND</a>



<a href="..\ntdddisk\ns-ntdddisk-_sendcmdinparams.md">SENDCMDINPARAMS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SENDCMDOUTPARAMS structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>