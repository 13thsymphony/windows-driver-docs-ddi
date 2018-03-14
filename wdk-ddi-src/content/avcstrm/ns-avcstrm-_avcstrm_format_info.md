---
UID: NS:avcstrm._AVCSTRM_FORMAT_INFO
title: "_AVCSTRM_FORMAT_INFO"
author: windows-driver-content
description: The AVCSTRM_FORMAT_INFO structure is used to describe a data stream.
old-location: stream\avcstrm_format_info.htm
old-project: stream
ms.assetid: de8e262b-bcb9-4549-94cc-0a73df45bddc
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PAVCSTRM_FORMAT_INFO, AVCSTRM_FORMAT_INFO, AVCSTRM_FORMAT_INFO structure [Streaming Media Devices], PAVCSTRM_FORMAT_INFO, PAVCSTRM_FORMAT_INFO structure pointer [Streaming Media Devices], _AVCSTRM_FORMAT_INFO, avcsref_e41f0bb0-8407-4338-9a68-46c00116ae92.xml, avcstrm/AVCSTRM_FORMAT_INFO, avcstrm/PAVCSTRM_FORMAT_INFO, stream.avcstrm_format_info"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: avcstrm.h
req.include-header: Avcstrm.h
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
-	avcstrm.h
api_name:
-	AVCSTRM_FORMAT_INFO
product: Windows
targetos: Windows
req.typenames: AVCSTRM_FORMAT_INFO, *PAVCSTRM_FORMAT_INFO
---

# _AVCSTRM_FORMAT_INFO structure
The AVCSTRM_FORMAT_INFO structure is used to describe a data stream.

## Syntax
````
typedef struct _AVCSTRM_FORMAT_INFO {
  ULONG          SizeOfThisBlock;
  AVCSTRM_FORMAT AVCStrmFormat;
  CIP_HDR1       cipHdr1;
  CIP_HDR2_SYT   cipHdr2;
  ULONG          SrcPacketsPerFrame;
  ULONG          FrameSize;
  ULONG          NumOfRcvBuffers;
  ULONG          NumOfXmtBuffers;
  DWORD          OptionFlags;
  ULONG          AvgTimePerFrame;
  ULONG          BlockPeriod;
  ULONG          Reserved[4];
} AVCSTRM_FORMAT_INFO, *PAVCSTRM_FORMAT_INFO;
````

## Members


`AVCStrmFormat`

Specifies one of the AV/C streaming subunit formats defined in <a href="..\avcstrm\ne-avcstrm-_avcstrm_format.md">AVCSTRM_FORMAT</a>.

`AvgTimePerFrame`

Specifies the average time per frame in 100 nanosecond units.

`BlockPeriod`

Specifies the block period. This is used for transmit only. It is calculated from 1/ BlockPerSecond * 1,000,000,000 picoseconds. For SDDV, it transmits one block per 1394 cycle. 1/(29.97 * 250) * 1,000,000,000,000 = 133,466,800 picoseconds.

`cipHdr1`

Specifies the definition of the first quadlet of the two quadlet CIP header.

`cipHdr2`

Specifies the definition of the second quadlet of the two quadlet CIP header.

`FrameSize`

Specifies the data buffer size.

`NumOfRcvBuffers`

Specifies the number of receiving buffers.

`NumOfXmtBuffers`

Specifies the number of transmitting buffers.

`OptionFlags`

Specifies any option flags. Currently, only one flag is defined:

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>


<dl>
<dt><a id="AVCSTRM_FORMAT_OPTION_STRIP_SPH"></a><a id="avcstrm_format_option_strip_sph"></a>AVCSTRM_FORMAT_OPTION_STRIP_SPH</dt>
<dd></dd>
</dl>
</td>
<td>
Strip the SPH (source packet header) from the 192-byte data packet for MPEG2TS.

</td>
</tr>
</table>

`Reserved`

Reserved. Do not use. Must be set to 0.

`SizeOfThisBlock`

Specifies the size of this data structure, in bytes.

`SrcPacketsPerFrame`

Specifies the number of source packets to fill a data frame.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | avcstrm.h (include Avcstrm.h) |

## See Also

<a href="..\avcstrm\ns-avcstrm-_cip_hdr2_fdf.md">CIP_HDR2_FDF</a>



<a href="..\avcstrm\ns-avcstrm-_cip_hdr2_syt.md">CIP_HDR2_SYT</a>



<a href="..\avcstrm\ne-avcstrm-_avcstrm_format.md">AVCSTRM_FORMAT</a>



<a href="..\avcstrm\ns-avcstrm-_cip_hdr2_mpegts.md">CIP_HDR2_MPEGTS</a>



<a href="..\avcstrm\ns-avcstrm-_cip_hdr1.md">CIP_HDR1</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20AVCSTRM_FORMAT_INFO structure%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>