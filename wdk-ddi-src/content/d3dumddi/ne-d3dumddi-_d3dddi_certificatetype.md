---
UID: NE:d3dumddi._D3DDDI_CERTIFICATETYPE
title: _D3DDDI_CERTIFICATETYPE
author: windows-driver-content
description: The D3DDDI_CERTIFICATETYPE enumeration contains values that identify certificate types.
old-location: display\d3dddi_certificatetype.htm
old-project: display
ms.assetid: 0e3835af-0ccf-4f41-96e3-beff5fdecd36
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DDDI_CERTIFICATETYPE, D3DDDI_CERTIFICATETYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDI_CERTIFICATETYPE is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDI_CERTIFICATETYPE
req.alt-loc: d3dumddi.h
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
req.typenames: D3DDDI_CERTIFICATETYPE
---

# _D3DDDI_CERTIFICATETYPE enumeration



## -description
The D3DDDI_CERTIFICATETYPE enumeration contains values that identify certificate types. 



## -syntax

````
typedef enum _D3DDDI_CERTIFICATETYPE { 
  D3DDDI_CERTTYPE_AUTHENTICATED_CHANNEL  = 1,
  D3DDDI_CERTTYPE_CRYPTOSESSION          = 2
} D3DDDI_CERTIFICATETYPE;
````


## -enum-fields

### -field D3DDDI_CERTTYPE_AUTHENTICATED_CHANNEL

The value specifies that the certificate type is an authenticated channel. 


### -field D3DDDI_CERTTYPE_CRYPTOSESSION

The value specifies that the certificate type is an encryption session. 


## -remarks
The user-mode display driver receives a D3DDDI_CERTIFICATETYPE-typed value in the <b>CertificateType</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_ddicertificateinfo.md">DDICERTIFICATEINFO</a> structure. The <b>pInfo</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_getcaps.md">D3DDDIARG_GETCAPS</a> structure points to DDICERTIFICATEINFO when the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a> function is called with the D3DDDICAPS_GETCERTIFICATE value set in the <b>Type</b> member of D3DDDIARG_GETCAPS. 


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
D3DDDI_CERTIFICATETYPE is supported beginning with the Windows 7 operating system.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_getcaps.md">D3DDDIARG_GETCAPS</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_ddicertificateinfo.md">DDICERTIFICATEINFO</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_CERTIFICATETYPE enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

