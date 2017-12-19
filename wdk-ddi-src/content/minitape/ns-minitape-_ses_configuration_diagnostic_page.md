---
UID: NS.MINITAPE._SES_CONFIGURATION_DIAGNOSTIC_PAGE
title: _SES_CONFIGURATION_DIAGNOSTIC_PAGE
author: windows-driver-content
description: TBD.
old-location: storage\ses_configuration_diagnostic_page.htm
old-project: storage
ms.assetid: 0FD748D6-F598-44D1-A8D3-E63764CB90C6
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _SES_CONFIGURATION_DIAGNOSTIC_PAGE, PSES_CONFIGURATION_DIAGNOSTIC_PAGE, SES_CONFIGURATION_DIAGNOSTIC_PAGE, *PSES_CONFIGURATION_DIAGNOSTIC_PAGE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: minitape.h
req.include-header: Minitape.h, Storport.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 10, version 1709 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SES_CONFIGURATION_DIAGNOSTIC_PAGE
req.alt-loc: scsi.h
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

# _SES_CONFIGURATION_DIAGNOSTIC_PAGE structure



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

TBD



## -syntax

````
typedef struct _SES_CONFIGURATION_DIAGNOSTIC_PAGE {
  UCHAR                    PageCode;
  UCHAR                    NumberOfSecondarySubEnclosures;
  UCHAR                    PageLength[2];
  UCHAR                    GenerationCode[4];
  SES_ENCLOSURE_DESCRIPTOR Descriptors[ANYSIZE_ARRAY];
} SES_CONFIGURATION_DIAGNOSTIC_PAGE, *PSES_CONFIGURATION_DIAGNOSTIC_PAGE;
````


## -struct-fields

### -field PageCode

Specifies the diagnostic page being sent or requested based on the value. For a Microcode Control diagnostic page, the value should be 0x01.


### -field NumberOfSecondarySubEnclosures

Specifies the number of separate subenclosures included in
the enclosure descriptor list, not including the primary subenclosure. If this is set to zero, only the primary subenclosure exists.


### -field PageLength

Specifies the length of the diagnostic page, in bytes.


### -field GenerationCode

Specifies the value of the generation code.


### -field Descriptors

Specifies the enclosure descriptors for the primary and secondary enclosures. The primary enclosure is the first index.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows 10, version 1709 and later versions of Windows.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Scsi.h (include Minitape.h or Storport.h)</dt>
</dl>
</td>
</tr>
</table>