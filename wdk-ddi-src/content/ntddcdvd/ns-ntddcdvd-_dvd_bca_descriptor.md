---
UID : NS:ntddcdvd._DVD_BCA_DESCRIPTOR
title : "_DVD_BCA_DESCRIPTOR"
author : windows-driver-content
description : The DVD_BCA_DESCRIPTOR structure is used in conjunction with the IOCTL_DVD_READ_STRUCTURE request to retrieve a DVD burst cutting area (BCA) descriptor.
old-location : storage\dvd_bca_descriptor.htm
old-project : storage
ms.assetid : a573beb8-7019-4605-ab37-5871f67c585d
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : PDVD_BCA_DESCRIPTOR, *PDVD_BCA_DESCRIPTOR, ntddcdvd/PDVD_BCA_DESCRIPTOR, storage.dvd_bca_descriptor, structs-DVD_4bbbd075-9b9f-40a6-b52d-e96b8ad7118b.xml, PDVD_BCA_DESCRIPTOR structure pointer [Storage Devices], ntddcdvd/DVD_BCA_DESCRIPTOR, DVD_BCA_DESCRIPTOR, DVD_BCA_DESCRIPTOR structure [Storage Devices], _DVD_BCA_DESCRIPTOR
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ntddcdvd.h
req.include-header : Ntddcdvd.h
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
req.typenames : "*PDVD_BCA_DESCRIPTOR, DVD_BCA_DESCRIPTOR"
---

# _DVD_BCA_DESCRIPTOR structure
The DVD_BCA_DESCRIPTOR structure is used in conjunction with the <a href="..\ntddcdvd\ni-ntddcdvd-ioctl_dvd_read_structure.md">IOCTL_DVD_READ_STRUCTURE</a> request to retrieve a DVD burst cutting area (BCA) descriptor.

## Syntax
````
typedef struct _DVD_BCA_DESCRIPTOR {
  UCHAR BCAInformation[];
} DVD_BCA_DESCRIPTOR, *PDVD_BCA_DESCRIPTOR;
````

## Members


`BCAInformation`

Contains an array that holds vendor-defined information retrieved from the burst cutting area.

## Remarks
The contents of the BCA region are specified by the media manufacturer.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddcdvd.h (include Ntddcdvd.h) |

## See Also

<a href="..\ntddcdvd\ni-ntddcdvd-ioctl_dvd_read_structure.md">IOCTL_DVD_READ_STRUCTURE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DVD_BCA_DESCRIPTOR structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>