---
UID : NS:ntddcdrm._CDROM_TOC_FULL_TOC_DATA_BLOCK
title : _CDROM_TOC_FULL_TOC_DATA_BLOCK
author : windows-driver-content
description : The CDROM_TOC_FULL_TOC_DATA_BLOCK structure contains track descriptor data used in conjunction with the data from the CDROM_TOC_FULL_TOC_DATA structure.
old-location : storage\cdrom_toc_full_toc_data_block.htm
old-project : storage
ms.assetid : 8d6d1283-b64e-4c3b-8a45-376cfe76a19d
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : _CDROM_TOC_FULL_TOC_DATA_BLOCK, CDROM_TOC_FULL_TOC_DATA_BLOCK, *PCDROM_TOC_FULL_TOC_DATA_BLOCK
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
req.alt-api : CDROM_TOC_FULL_TOC_DATA_BLOCK
req.alt-loc : ntddcdrm.h
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
req.typenames : CDROM_TOC_FULL_TOC_DATA_BLOCK, *PCDROM_TOC_FULL_TOC_DATA_BLOCK
---

# _CDROM_TOC_FULL_TOC_DATA_BLOCK structure
The CDROM_TOC_FULL_TOC_DATA_BLOCK structure contains track descriptor data used in conjunction with the data from the <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_toc_full_toc_data.md">CDROM_TOC_FULL_TOC_DATA</a> structure.

## Syntax
````
typedef struct _CDROM_TOC_FULL_TOC_DATA_BLOCK {
  UCHAR SessionNumber;
  UCHAR Control  :4;
  UCHAR Adr  :4;
  UCHAR Reserved1;
  UCHAR Point;
  UCHAR MsfExtra[3];
  UCHAR Zero;
  UCHAR Msf[3];
} CDROM_TOC_FULL_TOC_DATA_BLOCK, *PCDROM_TOC_FULL_TOC_DATA_BLOCK;
````

## Members

        
            `Adr`

            Indicates the type of information encoded in the Q subchannel of the block where this table of contents entry was found.
        
            `Control`

            Indicates the attributes of the track.
        
            `Msf`

            Contains the minute, second, and frame. Msf[0] contains the minutes field. Msf[1] contains the seconds field, and Msf[2] contains the frames field. MSF is a format similar to logical block addressing.
        
            `MsfExtra`

            See specification <i>T10/1363-D Revision-02A</i>, by National Committee for Information Technology Standards (NCITS) For information about the permissible values for this member.
        
            `Point`

            Defines various types of information within the table of contents lead-in area. For information about the permissible values for this member, see specification <i>T10/1363-D Revision-02A</i>, by National Committee for Information Technology Standards (NCITS).
        
            `Reserved1`

            Reserved.
        
            `SessionNumber`

            Contains the number of the session that the track belongs to.
        
            `Zero`

            Contains the value of the zero bit.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddcdrm.h (include Ntddcdrm.h) |

    ## See Also

        <dl>
<dt>
<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_read_toc_ex.md">IOCTL_CDROM_READ_TOC_EX</a>
</dt>
<dt>
<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_read_toc_ex.md">CDROM_READ_TOC_EX</a>
</dt>
<dt>
<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_toc_full_toc_data.md">CDROM_TOC_FULL_TOC_DATA</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CDROM_TOC_FULL_TOC_DATA_BLOCK structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>