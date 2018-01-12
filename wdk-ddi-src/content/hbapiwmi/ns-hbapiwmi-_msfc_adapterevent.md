---
UID: NS:hbapiwmi._MSFC_AdapterEvent
title: _MSFC_AdapterEvent
author: windows-driver-content
description: The MSFC_AdapterEvent structure is used by HBA miniport drivers that support the T11 committee's Fibre Channel HBA API specification to report adapter events to WMI clients that have registered to be notified of these events.
old-location: storage\msfc_adapterevent.htm
old-project: storage
ms.assetid: 235300a1-3941-4f9c-8327-4ce174493f3e
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _MSFC_AdapterEvent, *PMSFC_AdapterEvent, MSFC_AdapterEvent
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
req.alt-api: MSFC_AdapterEvent
req.alt-loc: hbapiwmi.h
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
req.typenames: *PMSFC_AdapterEvent, MSFC_AdapterEvent
---

# _MSFC_AdapterEvent structure



## -description
The MSFC_AdapterEvent structure is used by HBA miniport drivers that support the T11 committee's <i>Fibre Channel HBA API</i> specification to report adapter events to WMI clients that have registered to be notified of these events. 



## -syntax

````
typedef struct _MSFC_AdapterEvent {
  ULONG EventType;
  UCHAR PortWWN[8];
} MSFC_AdapterEvent, *PMSFC_AdapterEvent;
````


## -struct-fields

### -field EventType

Indicates the type of the event. The values that can be assigned to this member are defined by the <a href="https://msdn.microsoft.com/528e5eaa-aaeb-4e5b-a4b2-0f518fcd79ee">EVENT_TYPE_QUALIFIERS</a> WMI class qualifier. 


### -field PortWWN

Contains the worldwide name of the port that generated the event. 


## -remarks
The WMI tool suite generates a declaration for this structure in <i>Hbapiwm.h </i>after compiling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562477">MSFC_AdapterEvent WMI Class</a>.

For more information about event types and worldwide names, see the T11 committee's <i>Fibre Channel HBA API</i> specification.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Hbapiwmi.h (include Hbapiwmi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/528e5eaa-aaeb-4e5b-a4b2-0f518fcd79ee">EVENT_TYPE_QUALIFIERS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562477">MSFC_AdapterEvent WMI Class</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MSFC_AdapterEvent structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

