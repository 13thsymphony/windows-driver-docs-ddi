---
UID : NS:61883._CIP_NOTIFY_INFO
title : _CIP_NOTIFY_INFO
author : windows-driver-content
description : The CIP_NOTIFY_INFO structure contains information about the frame.
old-location : ieee\cip_notify_info.htm
old-project : IEEE
ms.assetid : 60b0d44b-0178-43ce-a1ad-7f5825bed3ba
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : 61883/PCIP_NOTIFY_INFO, CIP_NOTIFY_INFO structure [Buses], *PCIP_NOTIFY_INFO, _CIP_NOTIFY_INFO, 61883/CIP_NOTIFY_INFO, CIP_NOTIFY_INFO, PCIP_NOTIFY_INFO, 61883_structures_383bc74c-1168-4478-8284-b2724f9ec654.xml, IEEE.cip_notify_info, PCIP_NOTIFY_INFO structure pointer [Buses]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : 61883.h
req.include-header : 61883.h
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
req.typenames : "*PCIP_NOTIFY_INFO, CIP_NOTIFY_INFO"
---

# _CIP_NOTIFY_INFO structure
The CIP_NOTIFY_INFO structure contains information about the frame.

## Syntax
````
typedef struct _CIP_NOTIFY_INFO {
  HANDLE     hConnect;
  PVOID      Context;
  PCIP_FRAME Frame;
} CIP_NOTIFY_INFO, *PCIP_NOTIFY_INFO;
````

## Members


`Context`

Points to the context provided by the caller at <b>NotifyContext</b> in the input CIP_FRAME structure.

`Frame`

Points to the completed frame.

`hConnect`

A handle to the connection.

## Remarks
The IEC-61883 protocol driver allocates and initializes this structure from the input CIP_FRAME structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | 61883.h (include 61883.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537045">CIP_FRAME</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20CIP_NOTIFY_INFO structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>