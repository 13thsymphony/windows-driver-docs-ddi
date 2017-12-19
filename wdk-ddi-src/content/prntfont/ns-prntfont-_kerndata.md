---
UID: NS.PRNTFONT._KERNDATA
title: _KERNDATA
author: windows-driver-content
description: The KERNDATA structure is used for describing printer kerning pairs.
old-location: print\kerndata.htm
old-project: print
ms.assetid: b3f68c08-7097-46e7-ad47-6e5e1f2cb8b2
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _KERNDATA, PKERNDATA, KERNDATA, *PKERNDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: prntfont.h
req.include-header: Prntfont.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KERNDATA
req.alt-loc: prntfont.h
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
req.product: Windows 10 or later.
---

# _KERNDATA structure



## -description
The KERNDATA structure is used for describing printer kerning pairs.



## -syntax

````
typedef struct _KERNDATA {
  DWORD          dwSize;
  DWORD          dwKernPairNum;
  FD_KERNINGPAIR KernPair[1];
} KERNDATA, *PKERNDATA;
````


## -struct-fields

### -field dwSize

Specifies the size, in bytes, of KERNDATA structure, including the <b>KernPair</b> array.


### -field dwKernPairNum

Specifies the number of elements in the <b>KernPair</b> array.


### -field KernPair

Is an array of <a href="display.fd_kerningpair">FD_KERNINGPAIR</a> structures.


## -remarks
A .ufm file's KERNDATA structures are accessed by a pointer in the file's <a href="print.unifm_hdr">UNIFM_HDR</a> structure.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Prntfont.h (include Prntfont.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.fd_kerningpair">FD_KERNINGPAIR</a>
</dt>
<dt>
<a href="print.unifm_hdr">UNIFM_HDR</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20KERNDATA structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

