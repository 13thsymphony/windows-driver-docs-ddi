---
UID : NS:ntddpcm._TUPLE_REQUEST
title : "_TUPLE_REQUEST"
author : windows-driver-content
description : The TUPLE_REQUEST structure is used in conjunction with the IOCTL_GET_TUPLE_DATA request to retrieve tuple data from a PC Card's or CardBus card's attribute memory.
old-location : pcmcia\tuple_request.htm
old-project : PCMCIA
ms.assetid : c702d3aa-d586-4206-93be-30537c55edcf
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : ntddpcm/TUPLE_REQUEST, _TUPLE_REQUEST, TUPLE_REQUEST, PCMCIA.tuple_request, PTUPLE_REQUEST structure pointer [Buses], memcdref_9d88760a-943f-4537-ad46-738d5f41421e.xml, *PTUPLE_REQUEST, PTUPLE_REQUEST, ntddpcm/PTUPLE_REQUEST, TUPLE_REQUEST structure [Buses]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ntddpcm.h
req.include-header : Ntddpcm.h
req.target-type : Windows
req.target-min-winverclnt : 
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
req.typenames : TUPLE_REQUEST, *PTUPLE_REQUEST
---

# _TUPLE_REQUEST structure
The TUPLE_REQUEST structure is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537238">IOCTL_GET_TUPLE_DATA</a> request to retrieve tuple data from a PC Card's or CardBus card's attribute memory.

## Syntax
````
typedef struct _TUPLE_REQUEST {
  USHORT Socket;
} TUPLE_REQUEST, *PTUPLE_REQUEST;
````

## Members


`Socket`

Indicates the socket number.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddpcm.h (include Ntddpcm.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537238">IOCTL_GET_TUPLE_DATA</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCMCIA\buses]:%20TUPLE_REQUEST structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>