---
UID : NS:winspool._BINARY_CONTAINER
title : "_BINARY_CONTAINER"
author : windows-driver-content
description : The BINARY_CONTAINER structure is a container for binary data.
old-location : print\binary_container.htm
old-project : print
ms.assetid : bac960c5-7c29-4550-9b82-5adb6a0cc243
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : PBINARY_CONTAINER structure pointer [Print Devices], winspool/BINARY_CONTAINER, _BINARY_CONTAINER, winspool/PBINARY_CONTAINER, BINARY_CONTAINER structure [Print Devices], PBINARY_CONTAINER, spoolfnc_a034cd3e-8afb-4a15-9640-06d693fd150c.xml, *PBINARY_CONTAINER, BINARY_CONTAINER, print.binary_container
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : winspool.h
req.include-header : Winspool.h
req.target-type : Windows
req.target-min-winverclnt : This structure is available in Windows XP and later operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : BINARY_CONTAINER, *PBINARY_CONTAINER
req.product : Windows 10 or later.
---

# _BINARY_CONTAINER structure
The BINARY_CONTAINER structure is a container for binary data.

## Syntax
````
typedef struct _BINARY_CONTAINER {
  DWORD  cbBuf;
  LPBYTE pData;
} BINARY_CONTAINER, *PBINARY_CONTAINER;
````

## Members


`cbBuf`

Specifies the number of bytes of binary data in the <b>pData</b> member.

`pData`

Pointer to a buffer that contains the binary data.

## Remarks
The BINARY_CONTAINER structure is used in a <a href="..\winspool\ns-winspool-_bidi_data.md">BIDI_DATA</a> structure when the bidi data consists of binary data, as opposed to integer, float, or string data.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | winspool.h (include Winspool.h) |

## See Also

<a href="..\winspool\ns-winspool-_bidi_data.md">BIDI_DATA</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20BINARY_CONTAINER structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>