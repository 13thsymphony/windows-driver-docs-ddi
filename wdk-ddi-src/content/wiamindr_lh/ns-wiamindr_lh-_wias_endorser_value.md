---
UID: NS:wiamindr_lh._WIAS_ENDORSER_VALUE
title: "_WIAS_ENDORSER_VALUE"
author: windows-driver-content
description: The WIAS_ENDORSER_VALUE structure stores token/value pairs for endorser strings.
old-location: image\wias_endorser_value.htm
old-project: image
ms.assetid: 54395899-c35d-4251-9e9d-ec2128b28c67
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PWIAS_ENDORSER_VALUE, PWIAS_ENDORSER_VALUE, PWIAS_ENDORSER_VALUE structure pointer [Imaging Devices], WIAS_ENDORSER_VALUE, WIAS_ENDORSER_VALUE structure [Imaging Devices], _WIAS_ENDORSER_VALUE, image.wias_endorser_value, wiamindr_lh/PWIAS_ENDORSER_VALUE, wiamindr_lh/WIAS_ENDORSER_VALUE, wiastrct_b6e376e1-ecfd-4988-b752-3d81755cf990.xml"
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
-	wiamindr_lh.h
api_name:
-	WIAS_ENDORSER_VALUE
product: Windows
targetos: Windows
req.typenames: WIAS_ENDORSER_VALUE, *PWIAS_ENDORSER_VALUE
req.product: Windows 10 or later.
---

# _WIAS_ENDORSER_VALUE structure
The WIAS_ENDORSER_VALUE structure stores token/value pairs for endorser strings.

## Syntax
````
typedef struct _WIAS_ENDORSER_VALUE {
  LPWSTR wszTokenName;
  LPWSTR wszValue;
} WIAS_ENDORSER_VALUE, *PWIAS_ENDORSER_VALUE;
````

## Members


`wszTokenName`

Specifies a string value that represents the token name. Endorser token names begin and end with the $ character (for example, L"$MY_TOKEN_NAME$").

`wszValue`

Specifies the value with which to replace the token.

## Remarks
This structure is used indirectly by the <a href="..\wiamdef\nf-wiamdef-wiasparseendorserstring.md">wiasParseEndorserString</a> function. One of the parameters of this function is a <a href="..\wiamindr_lh\ns-wiamindr_lh-_wias_endorser_info.md">WIAS_ENDORSER_INFO</a> structure, which has a WIAS_ENDORSER_VALUE structure as one of its members.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Me and in Windows XP and later versions of the Windows operating systems. Available in Windows Me and in Windows XP and later versions of the Windows operating systems. |
| **Header** | wiamindr_lh.h (include Wiamindr.h) |

## See Also

<a href="..\wiamindr_lh\ns-wiamindr_lh-_wias_endorser_info.md">WIAS_ENDORSER_INFO</a>



<a href="..\wiamdef\nf-wiamdef-wiasparseendorserstring.md">wiasParseEndorserString</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20WIAS_ENDORSER_VALUE structure%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>