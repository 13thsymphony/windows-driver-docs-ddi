---
UID: NF.ks.KsDefaultAddEventHandler
title: KsDefaultAddEventHandler function
author: windows-driver-content
description: The KsDefaultAddEventHandler function is a default routine to handle event 'add' requests.
old-location: stream\ksdefaultaddeventhandler.htm
old-project: stream
ms.assetid: 8e429a48-4e86-4673-aa32-85b640e2f64f
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: KsDefaultAddEventHandler
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KsDefaultAddEventHandler
req.alt-loc: Ks.lib,Ks.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ks.lib
req.dll: 
req.irql: PASSIVE_LEVEL
---

# KsDefaultAddEventHandler function



## -description
The<b> KsDefaultAddEventHandler </b>function is a default routine to handle event 'add' requests.



## -syntax

````
NTSTATUS KsDefaultAddEventHandler(
  _In_    PIRP           Irp,
  _In_    PKSEVENTDATA   EventData,
  _Inout_ PKSEVENT_ENTRY EventEntry
);
````


## -parameters

### -param Irp [in]

The event <a href="kernel.irp">IRP</a>. This contains the object into which the event is inserted.


### -param EventData [in]

A pointer to a <a href="stream.kseventdata">KSEVENTDATA</a> structure that describes an event notification method.


### -param EventEntry [in, out]

The event entry that is to be inserted into the object's event list. The object is determined by <i>Irp</i>.


## -returns
Returns the success or failure of adding the event into the object's event list.


## -remarks
<b>KsDefaultAddEventHandler</b> determines the relevant object from <i>Irp</i> and adds the specified event to the object's event list.

This is functionally equivalent to <a href="stream.ksaddevent">KsAddEvent</a> (or <b>Ks</b><i>Xxx</i><b>AddEvent</b>, see below) for the object that is associated with <i>Irp</i>. Use <b>KsDefaultAddEventHandler</b> from a minidriver-specified <i>AddEvent</i> handler to insert the event into the object's event list.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Ks.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="stream.ksaddevent">KsAddEvent</a>
</dt>
<dt>
<a href="stream.ksfilteraddevent">KsFilterAddEvent</a>
</dt>
<dt>
<a href="stream.kspinaddevent">KsPinAddEvent</a>
</dt>
<dt>
<a href="stream.ksgenerateevents">KsGenerateEvents</a>
</dt>
<dt>
<a href="stream.ksevent_entry">KSEVENT_ENTRY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsDefaultAddEventHandler function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

