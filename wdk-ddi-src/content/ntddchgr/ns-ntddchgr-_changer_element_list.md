---
UID: NS:ntddchgr._CHANGER_ELEMENT_LIST
title: "_CHANGER_ELEMENT_LIST"
author: windows-driver-content
description: The CHANGER_ELEMENT_LIST structure indicates a range of elements of a single type.
old-location: storage\changer_element_list.htm
old-project: storage
ms.assetid: 6e85eaa7-d622-4b05-9efd-c1b6b7789c03
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PCHANGER_ELEMENT_LIST, CHANGER_ELEMENT_LIST, CHANGER_ELEMENT_LIST structure [Storage Devices], PCHANGER_ELEMENT_LIST, PCHANGER_ELEMENT_LIST structure pointer [Storage Devices], _CHANGER_ELEMENT_LIST, ntddchgr/CHANGER_ELEMENT_LIST, ntddchgr/PCHANGER_ELEMENT_LIST, storage.changer_element_list, structs-changer_e1782d96-458d-49a5-9885-c853d835ba0a.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddchgr.h
req.include-header: 
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
-	ntddchgr.h
api_name:
-	CHANGER_ELEMENT_LIST
product: Windows
targetos: Windows
req.typenames: CHANGER_ELEMENT_LIST, *PCHANGER_ELEMENT_LIST
---

# _CHANGER_ELEMENT_LIST structure
The CHANGER_ELEMENT_LIST structure indicates a range of elements of a single type.

## Syntax
````
typedef struct _CHANGER_ELEMENT_LIST {
  CHANGER_ELEMENT Element;
  ULONG           NumberOfElements;
} CHANGER_ELEMENT_LIST, *PCHANGER_ELEMENT_LIST;
````

## Members


`Element`

Describes the first element of type <a href="..\ntddchgr\ns-ntddchgr-_changer_element.md">CHANGER_ELEMENT</a> in a range <b>NumberOfElements</b> long.

`NumberOfElements`

Specifies the number of elements in the range.

## Remarks
A changer class driver uses CHANGER_ELEMENT_LIST to indicate a range of elements of a single type, typically for an operation such as getting or initializing the status of multiple elements.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddchgr.h |

## See Also

<a href="..\ntddchgr\ns-ntddchgr-_changer_element.md">CHANGER_ELEMENT</a>



<a href="..\mcd\nf-mcd-changerinitializeelementstatus.md">ChangerInitializeElementStatus</a>



<a href="..\mcd\nf-mcd-changergetelementstatus.md">ChangerGetElementStatus</a>