---
UID: NS:hidpi._HIDP_UNKNOWN_TOKEN
title: "_HIDP_UNKNOWN_TOKEN"
author: windows-driver-content
description: The HIDP_UNKNOWN_TOKEN structure contains information about a global item that the HID parser did not recognize.
old-location: hid\hidp_unknown_token.htm
old-project: hid
ms.assetid: 6c9e0477-1698-41bf-9ce6-43e7e8741425
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: PHIDP_UNKNOWN_TOKEN, _HIDP_UNKNOWN_TOKEN, HIDP_UNKNOWN_TOKEN structure [Human Input Devices], hidstrct_646ea225-5fff-4430-9112-06bb4cf8c988.xml, hidpi/PHIDP_UNKNOWN_TOKEN, hidpi/HIDP_UNKNOWN_TOKEN, hid.hidp_unknown_token, PHIDP_UNKNOWN_TOKEN structure pointer [Human Input Devices], *PHIDP_UNKNOWN_TOKEN, HIDP_UNKNOWN_TOKEN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hidpi.h
req.include-header: Hidpi.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	hidpi.h
apiname:
-	HIDP_UNKNOWN_TOKEN
product: Windows
targetos: Windows
req.typenames: "*PHIDP_UNKNOWN_TOKEN, HIDP_UNKNOWN_TOKEN"
---

# _HIDP_UNKNOWN_TOKEN structure
The HIDP_UNKNOWN_TOKEN structure contains information about a global item that the HID parser did not recognize.

## Syntax
````
typedef struct _HIDP_UNKNOWN_TOKEN {
  UCHAR Token;
  UCHAR Reserved[3];
  ULONG BitField;
} HIDP_UNKNOWN_TOKEN, *PHIDP_UNKNOWN_TOKEN;
````

## Members


`BitField`

Specifies the data part of the global item.

`Reserved`

Reserved for internal system use.

`Token`

Specifies the one-byte prefix of a global item.

## Remarks
HIDP_UNKNOWN_TOKEN is designed to be used with the <a href="..\hidpi\ns-hidpi-_hidp_extended_attributes.md">HIDP_EXTENDED_ATTRIBUTES</a> structure. <a href="..\hidpi\nf-hidpi-hidp_getextendedattributes.md">HidP_GetExtendedAttributes</a> returns a HIDP_EXTENDED_ATTRIBUTES structure, which contains a variable length array of <b>HIDP_UNKNOWN_TOKEN</b> structures.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hidpi.h (include Hidpi.h) |

## See Also

<a href="..\hidpi\ns-hidpi-_hidp_extended_attributes.md">HIDP_EXTENDED_ATTRIBUTES</a>



<a href="..\hidpi\nf-hidpi-hidp_getextendedattributes.md">HidP_GetExtendedAttributes</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HIDP_UNKNOWN_TOKEN structure%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>