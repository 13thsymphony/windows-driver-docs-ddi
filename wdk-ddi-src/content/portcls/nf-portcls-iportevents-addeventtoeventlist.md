---
UID: NF:portcls.IPortEvents.AddEventToEventList
title: IPortEvents::AddEventToEventList method
author: windows-driver-content
description: The AddEventToEventList method adds an event to the port driver's event list.
old-location: audio\iportevents_addeventtoeventlist.htm
old-project: audio
ms.assetid: 49b01942-3562-4fb2-907b-8863b2f09f8e
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IPortEvents, IPortEvents::AddEventToEventList, AddEventToEventList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPortEvents.AddEventToEventList
req.alt-loc: portcls.h
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
req.typenames: *PPC_EXIT_LATENCY, PC_EXIT_LATENCY
---

# IPortEvents::AddEventToEventList method



## -description
The <code>AddEventToEventList</code> method adds an event to the port driver's event list.



## -syntax

````
void AddEventToEventList(
  [in] PKSEVENT_ENTRY EventEntry
);
````


## -parameters

### -param EventEntry [in]

Pointer to the event entry that describes the event. This is an opaque system structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff561853">KSEVENT_ENTRY</a>.


## -returns
None


## -remarks
This method is used by a miniport driver's to add events to the event list that is maintained by the associated port object. The miniport driver's event handler typically calls this method in response to a PCEVENT_VERB_ADD request after the handler has validated support for the event being requested.


## -see-also
<dl>
<dt>
<a href="..\portcls\nn-portcls-iportevents.md">IPortEvents</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561853">KSEVENT_ENTRY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536889">IPortEvents::GenerateEventList</a>
</dt>
<dt>
<a href="..\portcls\nc-portcls-pcpfnevent_handler.md">EventHandler</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IPortEvents::AddEventToEventList method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

