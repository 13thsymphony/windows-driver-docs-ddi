---
UID : NS:hbapiwmi._MSFC_EventBuffer
title : _MSFC_EventBuffer
author : windows-driver-content
description : The MSFC_EventBuffer structure is used in conjunction with the GetEventBuffer method to retrieve the next events in the HBA's event queue.
old-location : storage\msfc_eventbuffer.htm
old-project : storage
ms.assetid : 7d41c092-251e-4f93-b5be-ff989b37196b
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : MSFC_EventBuffer, PMSFC_EventBuffer structure pointer [Storage Devices], storage.msfc_eventbuffer, structs-Fibre_d89430e7-c05b-4314-946e-fd8e70d938ac.xml, hbapiwmi/PMSFC_EventBuffer, MSFC_EventBuffer structure [Storage Devices], hbapiwmi/MSFC_EventBuffer, _MSFC_EventBuffer, *PMSFC_EventBuffer, PMSFC_EventBuffer
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : hbapiwmi.h
req.include-header : Hbapiwmi.h
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
req.typenames : MSFC_EventBuffer, *PMSFC_EventBuffer
---

# _MSFC_EventBuffer structure
The MSFC_EventBuffer structure is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553935">GetEventBuffer</a> method to retrieve the next events in the HBA's event queue.

## Syntax
````
typedef struct _MSFC_EventBuffer {
  ULONG EventType;
  ULONG EventInfo[4];
} MSFC_EventBuffer, *PMSFC_EventBuffer;
````

## Members


`EventInfo`

Contains a structure of type <a href="..\hbaapi\ns-hbaapi-hba_eventinfo.md">HBA_EventInfo</a> that holds information about the events that were retrieved.

`EventType`

Indicates the type of the event. The values that can be assigned to this member are defined by the <a href="https://msdn.microsoft.com/528e5eaa-aaeb-4e5b-a4b2-0f518fcd79ee">EVENT_TYPE_QUALIFIERS</a> WMI class qualifier.

## Remarks
The WMI tool suite generates a declaration for this structure in <i>hbapiwm.h </i>after compiling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562483">MSFC_EventBuffer WMI Class</a>. 

The <a href="..\hbaapi\ns-hbaapi-hba_eventinfo.md">HBA_EventInfo</a> structure is declared in <i>hbaapi.h</i>. You must include <i>hbaapi.h</i> to reference this structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | hbapiwmi.h (include Hbapiwmi.h) |

## See Also

<a href="https://msdn.microsoft.com/528e5eaa-aaeb-4e5b-a4b2-0f518fcd79ee">EVENT_TYPE_QUALIFIERS</a>

<a href="..\hbaapi\ns-hbaapi-hba_eventinfo.md">HBA_EventInfo</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553935">GetEventBuffer</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MSFC_EventBuffer structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>