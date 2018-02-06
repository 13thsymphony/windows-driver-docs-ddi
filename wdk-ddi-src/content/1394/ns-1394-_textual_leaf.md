---
UID: NS:1394._TEXTUAL_LEAF
title: "_TEXTUAL_LEAF"
author: windows-driver-content
description: The TEXTUAL_LEAF structure describes the device description that can be stored in the Configuration ROM of devices that satisfy the PC 98 or PC 99 specifications.
old-location: ieee\textual_leaf.htm
old-project: IEEE
ms.assetid: 883c561c-0d1b-4a6c-946e-8ca567b12c9a
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IEEE.textual_leaf, TEXTUAL_LEAF structure [Buses], PTEXTUAL_LEAF structure pointer [Buses], PTEXTUAL_LEAF, _TEXTUAL_LEAF, 1394/TEXTUAL_LEAF, 1394/PTEXTUAL_LEAF, TEXTUAL_LEAF, *PTEXTUAL_LEAF, 1394stct_b63840e2-0a05-49e9-a533-9575f46af648.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 1394.h
req.include-header: 1394.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	1394.h
apiname:
-	TEXTUAL_LEAF
product: Windows
targetos: Windows
req.typenames: TEXTUAL_LEAF, *PTEXTUAL_LEAF
---

# _TEXTUAL_LEAF structure
The TEXTUAL_LEAF structure describes the device description that can be stored in the Configuration ROM of devices that satisfy the PC 98 or PC 99 specifications.

## Syntax
````
typedef struct _TEXTUAL_LEAF {
  USHORT TL_CRC;
  USHORT TL_Length;
  ULONG  TL_Spec_Id;
  ULONG  TL_Language_Id;
  UCHAR  TL_Data;
} TEXTUAL_LEAF, *PTEXTUAL_LEAF;
````

## Members


`TL_CRC`

Specifies the CRC of the text string.

`TL_Data`

Specifies a vendor-specified textual description of the device.

`TL_Language_Id`

Specifies the language of the <b>TL_Data</b> member.

`TL_Length`

Specifies the length of the text string, in bytes.

`TL_Spec_Id`

Specifies which specification describes the meaning of the <b>TL_Language_ID</b> member.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | 1394.h (include 1394.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537642">REQUEST_GET_CONFIGURATION_INFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20TEXTUAL_LEAF structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>