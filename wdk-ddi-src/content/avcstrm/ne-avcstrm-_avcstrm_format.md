---
UID : NE:avcstrm._AVCSTRM_FORMAT
title : "_AVCSTRM_FORMAT"
author : windows-driver-content
description : The AVCSTRM_FUNCTION enumeration defines the AV/C subunit stream formats supported by avcstrm.sys.
old-location : stream\avcstrm_format.htm
old-project : stream
ms.assetid : 4481ec67-55b6-479e-b0b6-5f8ed56a5290
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : stream.avcstrm_format, avcstrm/AVCSTRM_FORMAT_MPEG2TS, avcstrm/AVCSTRM_FORMAT_SDLDV_NTSC, avcstrm/AVCSTRM_FORMAT_SDLDV_PAL, avcstrm/AVCSTRM_FORMAT_HDDV_NTSC, avcstrm/AVCSTRM_FORMAT_SDDV_NTSC, AVCSTRM_FORMAT_SDLDV_NTSC, avcstrm/AVCSTRM_FORMAT, AVCSTRM_FORMAT_SDDV_PAL, AVCSTRM_FORMAT_SDDV_NTSC, avcstrm/AVCSTRM_FORMAT_SDDV_PAL, _AVCSTRM_FORMAT, AVCSTRM_FORMAT_HDDV_NTSC, AVCSTRM_FORMAT_SDLDV_PAL, AVCSTRM_FORMAT enumeration [Streaming Media Devices], avcsref_489c2bf8-1e1f-4feb-91fb-0ba3666ba399.xml, AVCSTRM_FORMAT, AVCSTRM_FORMAT_HDDV_PAL, AVCSTRM_FORMAT_MPEG2TS, avcstrm/AVCSTRM_FORMAT_HDDV_PAL
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : avcstrm.h
req.include-header : Avcstrm.h
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
req.typenames : AVCSTRM_FORMAT
---

# _AVCSTRM_FORMAT Enumeration
The AVCSTRM_FUNCTION enumeration defines the AV/C subunit stream formats supported by <i>avcstrm.sys</i>.

## Syntax
````
typedef enum _AVCSTRM_FORMAT { 
  AVCSTRM_FORMAT_SDDV_NTSC   = 0,
  AVCSTRM_FORMAT_SDDV_PAL    = 1,
  AVCSTRM_FORMAT_MPEG2TS     = 2,
  AVCSTRM_FORMAT_HDDV_NTSC   = 3,
  AVCSTRM_FORMAT_HDDV_PAL    = 4,
  AVCSTRM_FORMAT_SDLDV_NTSC  = 5,
  AVCSTRM_FORMAT_SDLDV_PAL   = 6
} AVCSTRM_FORMAT;
````

## Constants

<table>

<tr>
<td>AVCSTRM_FORMAT_HDDV_NTSC</td>
<td>Specifies the 61883-3 specification for HD-DVCR data transmission, High Definition NTSC. This format is not supported.</td>
</tr>

<tr>
<td>AVCSTRM_FORMAT_HDDV_PAL</td>
<td>Specifies the 61883-3 specification for HD-DVCR data transmission, High Definition PAL. This format is not supported.</td>
</tr>

<tr>
<td>AVCSTRM_FORMAT_MPEG2TS</td>
<td>Specifies the 61883-4 specification for MPEG2-TS data transmission.</td>
</tr>

<tr>
<td>AVCSTRM_FORMAT_SDDV_NTSC</td>
<td>Specifies the 61883-2 specification for SD-DVCR data transmission, Standard Definition NTSC.</td>
</tr>

<tr>
<td>AVCSTRM_FORMAT_SDDV_PAL</td>
<td>Specifies the 61883-2 specification for SD-DVCR data transmission, Standard Definition PAL.</td>
</tr>

<tr>
<td>AVCSTRM_FORMAT_SDLDV_NTSC</td>
<td>Specifies the 61883-5 specification for SDL-DVCR data transmission. NTSC. This format is not supported.</td>
</tr>

<tr>
<td>AVCSTRM_FORMAT_SDLDV_PAL</td>
<td>Specifies the 61883-5 specification for SDL-DVCR data transmission. PAL. This format is not supported.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | avcstrm.h (include Avcstrm.h) |

## See Also

<a href="..\avcstrm\ns-avcstrm-_avcstrm_format_info.md">AVCSTRM_FORMAT_INFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20AVCSTRM_FORMAT enumeration%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>