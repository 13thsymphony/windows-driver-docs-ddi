---
UID: NS:portcls.__unnamed_struct_0c40_5
title: PCEVENT_ITEM
author: windows-driver-content
description: The PCEVENT_ITEM structure is used to describe an event that is supported by a particular filter, pin, or node.
old-location: audio\pcevent_item.htm
old-project: audio
ms.assetid: b91a7582-e146-4ded-a6b7-cb77850bfd2c
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PCEVENT_ITEM, PCEVENT_ITEM, *PPCEVENT_ITEM
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
req.alt-api: PCEVENT_ITEM
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
req.typenames: PCEVENT_ITEM, *PPCEVENT_ITEM
---

# PCEVENT_ITEM structure



## -description
The <b>PCEVENT_ITEM</b> structure is used to describe an event that is supported by a particular filter, pin, or node.



## -syntax

````
typedef struct {
  const GUID         *Set;
  ULONG              Id;
  ULONG              Flags;
  PCPFNEVENT_HANDLER Handler;
} PCEVENT_ITEM, *PPCEVENT_ITEM;
````


## -struct-fields

### -field Set

Specifies the event set. This member is a pointer to a GUID that uniquely identifies the event set. See the list of event-set GUIDs in <a href="https://msdn.microsoft.com/library/windows/hardware/ff536195">Audio Drivers Event Sets</a>.


### -field Id

Specifies the event ID. This member identifies an event item within the event set. If the event set contains N items, valid event IDs are integers in the range 0 to N-1.


### -field Flags

Specifies the type of event. This member is set to one of the following values:




### -field PCEVENT_ITEM_FLAG_ENABLE

Indicates the event notification should be enabled for this event type. The driver should continue event notification until the client explicitly disables it.


### -field PCEVENT_ITEM_FLAG_ONESHOT

Indicates that the event notification should be enabled for the next occurrence of this event only. The client does not (and should not) disable the event once it has occurred.


### -field PCEVENT_ITEM_FLAG_BASICSUPPORT

If the client specifies this flag, the driver returns STATUS_SUCCESS if it supports the event and an error code if it does not.

</dd>
</dl>

### -field Handler

Pointer to the miniport driver's event-handler routine. This member is a function pointer of type PCPFNEVENT_HANDLER, which is defined as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>  typedef NTSTATUS (*PCPFNEVENT_HANDLER)
  (
      IN PPCEVENT_REQUEST  EventRequest
  );</pre>
</td>
</tr>
</table></span></div>
When calling the <b>Handler</b> routine, the caller passes in a single call parameter, which is a pointer to a caller-allocated <a href="..\portcls\ns-portcls-_pcevent_request.md">PCEVENT_REQUEST</a> structure.


## -remarks
The <b>PCEVENT_ITEM</b> structure specifies a particular event item in an automation table. The <a href="..\portcls\ns-portcls-__unnamed_struct_0c40_6.md">PCAUTOMATION_TABLE</a> structure points to an array of <b>PCEVENT_ITEM</b> structures.

In WDM audio, the target for an event request is either a pin instance or a node on a pin. A filter instance cannot be the target of an event request.


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
<a href="..\portcls\ns-portcls-_pcevent_request.md">PCEVENT_REQUEST</a>
</dt>
<dt>
<a href="..\portcls\ns-portcls-__unnamed_struct_0c40_6.md">PCAUTOMATION_TABLE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PCEVENT_ITEM structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

