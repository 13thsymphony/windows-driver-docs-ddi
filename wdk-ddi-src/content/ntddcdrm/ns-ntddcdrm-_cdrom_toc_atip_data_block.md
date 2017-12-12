---
UID: NS.NTDDCDRM._CDROM_TOC_ATIP_DATA_BLOCK
title: _CDROM_TOC_ATIP_DATA_BLOCK
author: windows-driver-content
description: Device control IRPs with a control code of IOCTL_CDROM_READ_TOC_EX and a format of CDROM_READ_TOC_EX_FORMAT_ATIP return their output data in a header structure of type CDROM_TOC_ATIP_DATA followed by a series of ATIP data block descriptors defined by CDROM_TOC_ATIP_DATA_BLOCK.
old-location: storage\cdrom_toc_atip_data_block.htm
old-project: storage
ms.assetid: b98d0ba9-9c32-44ed-b6c3-db6de26a1663
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _CDROM_TOC_ATIP_DATA_BLOCK, CDROM_TOC_ATIP_DATA_BLOCK, *PCDROM_TOC_ATIP_DATA_BLOCK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddcdrm.h
req.include-header: Ntddcdrm.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CDROM_TOC_ATIP_DATA_BLOCK
req.alt-loc: ntddcdrm.h
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
---

# _CDROM_TOC_ATIP_DATA_BLOCK structure



## -description
Device control IRPs with a control code of <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_read_toc_ex.md">IOCTL_CDROM_READ_TOC_EX</a> and a format of CDROM_READ_TOC_EX_FORMAT_ATIP return their output data in a header structure of type <a href="storage.cdrom_toc_atip_data">CDROM_TOC_ATIP_DATA</a> followed by a series of ATIP data block descriptors defined by <b>CDROM_TOC_ATIP_DATA_BLOCK</b>.



## -syntax

````
typedef struct _CDROM_TOC_ATIP_DATA_BLOCK {
  UCHAR CdrwReferenceSpeed  :3;
  UCHAR Reserved3  :1;
  UCHAR WritePower  :3;
  UCHAR True1  :1;
  UCHAR Reserved4  :6;
  UCHAR UnrestrictedUse  :1;
  UCHAR Reserved5  :1;
  UCHAR A3Valid  :1;
  UCHAR A2Valid  :1;
  UCHAR A1Valid  :1;
  UCHAR DiscSubType  :3;
  UCHAR IsCdrw  :1;
  UCHAR True2  :1;
  UCHAR Reserved7;
  UCHAR LeadInMsf[3];
  UCHAR Reserved8;
  UCHAR LeadOutMsf[3];
  UCHAR Reserved9;
  UCHAR A1Values[3];
  UCHAR Reserved10;
  UCHAR A2Values[3];
  UCHAR Reserved11;
  UCHAR A3Values[3];
  UCHAR Reserved12;
} CDROM_TOC_ATIP_DATA_BLOCK, *PCDROM_TOC_ATIP_DATA_BLOCK;
````


## -struct-fields

### -field CdrwReferenceSpeed

Indicates the recommended write speed for the media. Values 0x00 to 0x01 are reserved. A value of 0x02 indicates a CD-ROM speed of 4X. A value of 0x03 indicates a CD-ROM speed of 8X. Values 0x04 to 0x07 are reserved. 


### -field Reserved3

Reserved. 


### -field WritePower

Indicates media's recommended initial laser power setting. The high order bit must be set to 1. The setting of the other bits varies between CD-R and CD-RW media. For an explanation of the values these bits can have, see the <i>SCSI Multimedia Commands - 3</i> (MMC-3) specification. 


### -field True1

Must be set to 1. 


### -field Reserved4

Reserved. 


### -field UnrestrictedUse

Indicates, when set to 1, that the mounted disc is defined for unrestricted use. When set to zero, indicates that the mounted disc is defined for restricted use. 


### -field Reserved5

Reserved. 


### -field A3Valid

Indicates that bytes 16-18 (bytes 12-14 of the ATIP descriptor) are valid when set to 1. When set to zero, indicates that bytes 16-18 are invalid. 


### -field A2Valid

Indicates that A2 values field is valid when set to 1. When set to zero, indicates that the A2 values field is invalid. 


### -field A1Valid

Indicates that A3 values field is valid when set to 1. When set to zero, indicates that the A3 values field is invalid. 


### -field DiscSubType

Must be set to zero. 


### -field IsCdrw

Indicates the media is rewritable (CD-RW) when set to 1. When set to zero, indicates the media is write-once (CD-R). 


### -field True2

Must be set to 1. 


### -field Reserved7

Reserved. 


### -field LeadInMsf

Indicates the ATIP start time of lead-in, in terms of minutes, seconds, and frames. Valid values of the first byte are from 0x50 to 0x63. For an explanation of the values that the second and third bytes can have, see the <i>SCSI Multimedia Commands - 3</i> (MMC-3) specification. 


### -field Reserved8

Reserved. 


### -field LeadOutMsf

Indicates the ATIP last possible start time of lead-out in terms of minutes, seconds, and frames. Valid values of the first byte are from 0x0 to 0x04F. For an explanation of the values that the second and third bytes can have, see the <i>SCSI Multimedia Commands - 3</i> (MMC-3) specification. 


### -field Reserved9

Reserved. 


### -field A1Values

See specification <i>T10/1363-D Revision-02A</i>, by National Committee for Information Technology Standards (NCITS) For information about the permissible values for this member. 


### -field Reserved10

Reserved. 


### -field A2Values

Reserved. 


### -field Reserved11

Reserved. 


### -field A3Values

Reserved. 


### -field Reserved12

Reserved. 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddcdrm.h (include Ntddcdrm.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_read_toc_ex.md">IOCTL_CDROM_READ_TOC_EX</a>
</dt>
<dt>
<a href="storage.cdrom_read_toc_ex">CDROM_READ_TOC_EX</a>
</dt>
<dt>
<a href="storage.cdrom_toc_atip_data">CDROM_TOC_ATIP_DATA</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CDROM_TOC_ATIP_DATA_BLOCK structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

