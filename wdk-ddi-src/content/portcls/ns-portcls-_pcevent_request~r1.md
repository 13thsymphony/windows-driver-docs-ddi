---
UID: NS.PORTCLS._PCEVENT_REQUEST~R1
title: _PCEVENT_REQUEST
author: windows-driver-content
description: The PCEVENT_REQUEST structure specifies an event request.
old-location: audio\pcevent_request.htm
old-project: audio
ms.assetid: b28bd1c2-9fbe-4427-a4ba-5b79a338e913
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _PCEVENT_REQUEST, PCEVENT_REQUEST, *PPCEVENT_REQUEST
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PCEVENT_REQUEST
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
---

# _PCEVENT_REQUEST structure



## -description
The <b>PCEVENT_REQUEST</b> structure specifies an event request.



## -syntax

````
typedef struct _PCEVENT_REQUEST {
  PUNKNOWN           MajorTarget;
  PUNKNOWN           MinorTarget;
  ULONG              Node;
  const PCEVENT_ITEM *EventItem;
  PKSEVENT_ENTRY     EventEntry;
  ULONG              Verb;
  PIRP               Irp;
} PCEVENT_REQUEST, *PPCEVENT_REQUEST;
````


## -struct-fields

### -field MajorTarget


<a href="com.iunknown">IUnknown</a> pointer to the main miniport object. This member contains the <i>UnknownMiniport</i> pointer that the adapter driver previously passed to the <a href="audio.iport_init">IPort::Init</a> method.


### -field MinorTarget


<a href="com.iunknown">IUnknown</a> pointer to a stream object that is associated with the <i>MajorTarget</i> miniport object. This member contains the stream-object pointer that the port driver previously retrieved from the IMiniport<i>Xxx</i>::NewStream method (for example, the <a href="audio.iminiportwavecyclic_newstream">IMiniportWaveCyclic::NewStream</a> method's <i>Stream</i> parameter).


### -field Node

Specifies a node ID. This member identifies the target node for the request. If the target is not a node, this member is set to ULONG(-1).


### -field EventItem

Pointer to the <a href="..\portcls\ns-portcls-__unnamed_struct_0c40_5.md">PCEVENT_ITEM</a> structure for this request


### -field EventEntry

Pointer to the <a href="stream.ksevent_entry">KSEVENT_ENTRY</a> structure for this request


### -field Verb

Specifies the type of event request. This member should be set to one of the values in the following table.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
PCEVENT_VERB_ADD

</td>
<td>
Indicates that a client wants to enable the specified event. After validating the event and target information, the <a href="..\portcls\nc-portcls-pcpfnevent_handler.md">EventHandler</a> routine adds the event by calling the <a href="audio.iportevents_addeventtoeventlist">IPortEvents::AddEventToEventList</a> method.

</td>
</tr>
<tr>
<td>
PCEVENT_VERB_REMOVE

</td>
<td>
Notifies the <a href="..\portcls\nc-portcls-pcpfnevent_handler.md">EventHandler</a> that an event is being disabled and removed from the list.

</td>
</tr>
<tr>
<td>
PCEVENT_VERB_SUPPORT

</td>
<td>
This request is a query for support. If the miniport driver supports the event for the target identified in the request, it should succeed this query. Otherwise, it should fail the query.

</td>
</tr>
<tr>
<td>
PCEVENT_VERB_NONE

</td>
<td>
No action is needed.

</td>
</tr>
</table>
 


### -field Irp

Pointer to the <a href="kernel.irp">IRP</a> containing the event request


## -remarks
This is the structure that the port driver passes to the miniport driver's <a href="..\portcls\nc-portcls-pcpfnevent_handler.md">EventHandler</a> routine. The <a href="..\portcls\ns-portcls-__unnamed_struct_0c40_5.md">PCEVENT_ITEM</a> structure contains a function pointer to an event handler that takes a <b>PCEVENT_REQUEST</b> pointer as its only call parameter. The port driver allocates a <b>PCEVENT_REQUEST</b> structure, extracts the relevant information from the original event request (which the <b>Irp</b> member points to), and loads the information into this structure before calling the handler.

In WDM audio, the target of an event request can be a pin instance but not a filter instance. The target can also include a node ID.

The <b>MajorTarget</b> and <b>MinorTarget</b> members are <a href="com.iunknown">IUnknown</a> pointers to the main miniport object and an associated stream object, respectively. The event handler can query these objects for their miniport and stream interfaces.

For example, if the target for the event request is a pin instance on a WaveCyclic filter:

The handler can call <a href="com.iunknown_queryinterface">QueryInterface</a> on the <b>MajorTarget</b> object's <a href="com.iunknown">IUnknown</a> interface to obtain a reference to the object's <a href="..\portcls\nn-portcls-iminiportwavecyclic.md">IMiniportWaveCyclic</a> interface.

The handler can call <a href="com.iunknown_queryinterface">QueryInterface</a> on the <b>MinorTarget</b> object's <a href="com.iunknown">IUnknown</a> interface to obtain a reference to the object's <a href="..\portcls\nn-portcls-iminiportwavecyclicstream.md">IMiniportWaveCyclicStream</a> interface.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Portcls.h (include Portcls.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537695">PCFILTER_NODE</a>
</dt>
<dt>
<a href="..\portcls\ns-portcls-__unnamed_struct_0c40_5.md">PCEVENT_ITEM</a>
</dt>
<dt>
<a href="stream.ksevent_entry">KSEVENT_ENTRY</a>
</dt>
<dt>
<a href="..\portcls\nc-portcls-pcpfnevent_handler.md">EventHandler</a>
</dt>
<dt>
<a href="audio.iportevents_addeventtoeventlist">IPortEvents::AddEventToEventList</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PCEVENT_REQUEST structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

