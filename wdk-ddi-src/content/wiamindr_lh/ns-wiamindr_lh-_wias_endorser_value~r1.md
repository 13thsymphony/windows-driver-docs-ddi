---
UID: NS.WIAMINDR_LH._WIAS_ENDORSER_VALUE~R1
title: _WIAS_ENDORSER_VALUE
author: windows-driver-content
description: The WIAS_ENDORSER_VALUE structure stores token/value pairs for endorser strings.
old-location: image\wias_endorser_value.htm
old-project: Image
ms.assetid: 54395899-c35d-4251-9e9d-ec2128b28c67
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _WIAS_ENDORSER_VALUE, *PWIAS_ENDORSER_VALUE, WIAS_ENDORSER_VALUE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wiamindr_lh.h
req.include-header: Wiamindr.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Me and in Windows XP and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WIAS_ENDORSER_VALUE
req.alt-loc: wiamindr_lh.h
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

# _WIAS_ENDORSER_VALUE structure



## -description
The WIAS_ENDORSER_VALUE structure stores token/value pairs for endorser strings.



## -syntax

````
typedef struct _WIAS_ENDORSER_VALUE {
  LPWSTR wszTokenName;
  LPWSTR wszValue;
} WIAS_ENDORSER_VALUE, *PWIAS_ENDORSER_VALUE;
````


## -struct-fields

### -field wszTokenName

Specifies a string value that represents the token name. Endorser token names begin and end with the $ character (for example, L"$MY_TOKEN_NAME$").


### -field wszValue

Specifies the value with which to replace the token.


## -remarks
This structure is used indirectly by the <a href="image.wiasparseendorserstring">wiasParseEndorserString</a> function. One of the parameters of this function is a <a href="image.wias_endorser_info">WIAS_ENDORSER_INFO</a> structure, which has a WIAS_ENDORSER_VALUE structure as one of its members.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Me and in Windows XP and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wiamindr_lh.h (include Wiamindr.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="image.wiasparseendorserstring">wiasParseEndorserString</a>
</dt>
<dt>
<a href="image.wias_endorser_info">WIAS_ENDORSER_INFO</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Image\image]:%20WIAS_ENDORSER_VALUE structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

