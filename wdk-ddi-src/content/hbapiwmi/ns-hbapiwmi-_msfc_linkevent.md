---
UID: NS:hbapiwmi._MSFC_LinkEvent
title: "_MSFC_LinkEvent"
author: windows-driver-content
description: A WMI provider uses the MSFC_LinkEvent structure to report link events for the indicated adapter.
old-location: storage\msfc_linkevent.htm
old-project: storage
ms.assetid: 35fb3397-2e45-4d32-8cb1-1050199b2209
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PMSFC_LinkEvent, MSFC_LinkEvent, MSFC_LinkEvent structure [Storage Devices], PMSFC_LinkEvent, PMSFC_LinkEvent structure pointer [Storage Devices], _MSFC_LinkEvent, hbapiwmi/MSFC_LinkEvent, hbapiwmi/PMSFC_LinkEvent, storage.msfc_linkevent, structs-Fibre_cbf79af7-ccf4-4996-b14d-bca141dece0e.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
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
-	hbapiwmi.h
api_name:
-	MSFC_LinkEvent
product: Windows
targetos: Windows
req.typenames: MSFC_LinkEvent, *PMSFC_LinkEvent
---

# _MSFC_LinkEvent structure
A WMI provider uses the MSFC_LinkEvent structure to report link events for the indicated adapter.

## Syntax
````
typedef struct _MSFC_LinkEvent {
  ULONG EventType;
  UCHAR AdapterWWN[8];
  ULONG RLIRBufferSize;
  UCHAR RLIRBuffer[1];
} MSFC_LinkEvent, *PMSFC_LinkEvent;
````

## Members


`AdapterWWN`

Contains a worldwide name that indicates the adapter for which the event occurred.

`EventType`

Indicates the type of the event. The values that can be assigned to this member are defined by the <a href="https://msdn.microsoft.com/528e5eaa-aaeb-4e5b-a4b2-0f518fcd79ee">EVENT_TYPE_QUALIFIERS</a> WMI class qualifier.

`RLIRBuffer`

Contains the data associated with a register link incident request (RLIR).

`RLIRBufferSize`

Indicates the size of the buffer at <b>RLIRBuffer</b>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hbapiwmi.h (include Hbapiwmi.h) |

## See Also

<a href="https://msdn.microsoft.com/528e5eaa-aaeb-4e5b-a4b2-0f518fcd79ee">EVENT_TYPE_QUALIFIERS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MSFC_LinkEvent structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>