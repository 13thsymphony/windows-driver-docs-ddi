---
UID : NS:ntddchgr._CHANGER_ELEMENT_LIST
title : _CHANGER_ELEMENT_LIST
author : windows-driver-content
description : The CHANGER_ELEMENT_LIST structure indicates a range of elements of a single type.
old-location : storage\changer_element_list.htm
old-project : storage
ms.assetid : 6e85eaa7-d622-4b05-9efd-c1b6b7789c03
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : _CHANGER_ELEMENT_LIST, *PCHANGER_ELEMENT_LIST, CHANGER_ELEMENT_LIST
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ntddchgr.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : CHANGER_ELEMENT_LIST
req.alt-loc : ntddchgr.h
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
req.typenames : "*PCHANGER_ELEMENT_LIST, CHANGER_ELEMENT_LIST"
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
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddchgr.h |

    ## See Also

        <dl>
<dt>
<a href="..\ntddchgr\ns-ntddchgr-_changer_element.md">CHANGER_ELEMENT</a>
</dt>
<dt>
<a href="..\mcd\nf-mcd-changergetelementstatus.md">ChangerGetElementStatus</a>
</dt>
<dt>
<a href="..\mcd\nf-mcd-changerinitializeelementstatus.md">ChangerInitializeElementStatus</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CHANGER_ELEMENT_LIST structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>