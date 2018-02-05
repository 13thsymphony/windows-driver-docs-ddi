---
UID : NS:ntddcdrm._SUB_Q_MEDIA_CATALOG_NUMBER
title : "_SUB_Q_MEDIA_CATALOG_NUMBER"
author : windows-driver-content
description : The SUB_Q_MEDIA_CATALOG_NUMBER structure contains position information and is used in conjunction with the SUB_Q_CHANNEL_DATA structure.
old-location : storage\sub_q_media_catalog_number.htm
old-project : storage
ms.assetid : 14b0aed7-1602-41a3-bc55-59da40650860
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : PSUB_Q_MEDIA_CATALOG_NUMBER structure pointer [Storage Devices], *PSUB_Q_MEDIA_CATALOG_NUMBER, ntddcdrm/PSUB_Q_MEDIA_CATALOG_NUMBER, SUB_Q_MEDIA_CATALOG_NUMBER, ntddcdrm/SUB_Q_MEDIA_CATALOG_NUMBER, _SUB_Q_MEDIA_CATALOG_NUMBER, PSUB_Q_MEDIA_CATALOG_NUMBER, storage.sub_q_media_catalog_number, structs-CD-ROM_d4acf54e-b837-4064-a654-4fa2ebbe7425.xml, SUB_Q_MEDIA_CATALOG_NUMBER structure [Storage Devices]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ntddcdrm.h
req.include-header : Ntddcdrm.h
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
req.typenames : "*PSUB_Q_MEDIA_CATALOG_NUMBER, SUB_Q_MEDIA_CATALOG_NUMBER"
---

# _SUB_Q_MEDIA_CATALOG_NUMBER structure
The SUB_Q_MEDIA_CATALOG_NUMBER structure contains position information and is used in conjunction with the <a href="..\ntddcdrm\ns-ntddcdrm-_sub_q_channel_data.md">SUB_Q_CHANNEL_DATA</a> structure.

## Syntax
````
typedef struct _SUB_Q_MEDIA_CATALOG_NUMBER {
  SUB_Q_HEADER Header;
  UCHAR        FormatCode;
  UCHAR        Reserved[3];
  UCHAR        Reserved1  :7;
  UCHAR        Mcval  :1;
  UCHAR        MediaCatalog[15];
} SUB_Q_MEDIA_CATALOG_NUMBER, *PSUB_Q_MEDIA_CATALOG_NUMBER;
````

## Members


`FormatCode`

Should have a value of IOCTL_CDROM_MEDIA_CATALOG.

`Header`

Indicates, among other things, the length of the Q subchannel data that was retrieved. See <a href="..\ntddcdrm\ns-ntddcdrm-_sub_q_header.md">SUB_Q_HEADER</a> for further details.

`Mcval`

Indicates that the media catalog number (MCN) data is valid if set to 1; set to zero otherwise.

`MediaCatalog`

Contains the catalog number if <b>Mcval</b> is set to 1.

`Reserved`

Reserved.

`Reserved1`

Reserved.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddcdrm.h (include Ntddcdrm.h) |

## See Also

<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_read_q_channel.md">IOCTL_CDROM_READ_Q_CHANNEL</a>

<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_sub_q_data_format.md">CDROM_SUB_Q_DATA_FORMAT</a>

<a href="..\ntddcdrm\ns-ntddcdrm-_sub_q_channel_data.md">SUB_Q_CHANNEL_DATA</a>

<a href="..\ntddcdrm\ns-ntddcdrm-_sub_q_header.md">SUB_Q_HEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SUB_Q_MEDIA_CATALOG_NUMBER structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>