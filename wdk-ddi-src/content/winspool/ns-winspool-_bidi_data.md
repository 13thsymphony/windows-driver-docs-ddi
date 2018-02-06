---
UID: NS:winspool._BIDI_DATA
title: "_BIDI_DATA"
author: windows-driver-content
description: The BIDI_DATA structure is used to store the values of a bidi schema.
old-location: print\bidi_data.htm
old-project: print
ms.assetid: 9e0f3044-01c0-4dec-b34c-0f33ccfe3300
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: winspool/PBIDI_DATA, BIDI_DATA structure [Print Devices], PBIDI_DATA structure pointer [Print Devices], LPBIDI_DATA structure pointer [Print Devices], *LPBIDI_DATA, spoolfnc_6e6c0bc2-88f6-43ab-8183-42ee1a91e593.xml, winspool/LPBIDI_DATA, _BIDI_DATA, PBIDI_DATA, BIDI_DATA, *PBIDI_DATA, winspool/BIDI_DATA, LPBIDI_DATA, print.bidi_data
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: winspool.h
req.include-header: Winspool.h
req.target-type: Windows
req.target-min-winverclnt: This structure is available in Windows XP and later.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	winspool.h
apiname:
-	BIDI_DATA
product: Windows
targetos: Windows
req.typenames: "*PBIDI_DATA, *LPBIDI_DATA, BIDI_DATA"
req.product: Windows 10 or later.
---

# _BIDI_DATA structure
The BIDI_DATA structure is used to store the values of a bidi schema.

## Syntax
````
typedef struct _BIDI_DATA {
  DWORD dwBidiType;
  union {
    BOOL             bData;
    LONG             iData;
    LPWSTR           sData;
    FLOAT            fData;
    BINARY_CONTAINER biData;
  } u;
} BIDI_DATA, *PBIDI_DATA, *LPBIDI_DATA;
````

## Members


`dwBidiType`

Specifies the type of data in a bidi request as one of the values listed in the <a href="..\winspool\ne-winspool-bidi_type.md">BIDI_TYPE</a> enumeration. The value of this member determines which one of the following five union members is valid.

`u`



## Remarks
The <a href="..\winspool\ns-winspool-_bidi_request_data.md">BIDI_REQUEST_DATA</a> and <a href="..\winspool\ns-winspool-_bidi_response_data.md">BIDI_RESPONSE_DATA</a> structures each have a member of this type, which holds the bidi data for the request or response.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | This structure is available in Windows XP and later. This structure is available in Windows XP and later. |
| **Header** | winspool.h (include Winspool.h) |

## See Also

<a href="..\winspool\ne-winspool-bidi_type.md">BIDI_TYPE</a>

<a href="..\winspool\ns-winspool-_bidi_response_data.md">BIDI_RESPONSE_DATA</a>

<a href="..\winspool\ns-winspool-_binary_container.md">BINARY_CONTAINER</a>

<a href="..\winspool\ns-winspool-_bidi_request_data.md">BIDI_REQUEST_DATA</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20BIDI_DATA structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>