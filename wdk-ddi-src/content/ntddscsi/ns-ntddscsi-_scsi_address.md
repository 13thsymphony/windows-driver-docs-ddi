---
UID: NS:ntddscsi._SCSI_ADDRESS
title: _SCSI_ADDRESS
author: windows-driver-content
description: The SCSI_ADDRESS structure is used in conjunction with the IOCTL_SCSI_GET_ADDRESS request to retrieve the address information, such as the target ID (TID) and the logical unit number (LUN) of a particular SCSI target.
old-location: storage\scsi_address.htm
old-project: storage
ms.assetid: 2b3acd3d-b5da-4dd3-89f1-0b8a7d68e54c
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _SCSI_ADDRESS, *PSCSI_ADDRESS, SCSI_ADDRESS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddscsi.h
req.include-header: Ntddscsi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SCSI_ADDRESS
req.alt-loc: ntddscsi.h
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
req.typenames: *PSCSI_ADDRESS, SCSI_ADDRESS
---

# _SCSI_ADDRESS structure



## -description
The SCSI_ADDRESS structure is used in conjunction with the <a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_get_address.md">IOCTL_SCSI_GET_ADDRESS</a> request to retrieve the address information, such as the target ID (TID) and the logical unit number (LUN) of a particular SCSI target. 



## -syntax

````
typedef struct _SCSI_ADDRESS {
  ULONG Length;
  UCHAR PortNumber;
  UCHAR PathId;
  UCHAR TargetId;
  UCHAR Lun;
} SCSI_ADDRESS, *PSCSI_ADDRESS;
````


## -struct-fields

### -field Length

Contains the length of this structure in bytes. 


### -field PortNumber

Contains the number of the SCSI adapter.


### -field PathId

Contains the number of the bus. 


### -field TargetId

Contains the number of the target device. 


### -field Lun

Contains the logical unit number.


## -remarks
Legacy class drivers issue the <a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_get_address.md">IOCTL_SCSI_GET_ADDRESS</a> request to the port driver to obtain the address of their devices. 


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddscsi.h (include Ntddscsi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_get_address.md">IOCTL_SCSI_GET_ADDRESS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SCSI_ADDRESS structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

