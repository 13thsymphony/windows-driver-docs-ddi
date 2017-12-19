---
UID: NF.poscx.PosCxPutPendingEvent
title: PosCxPutPendingEvent function
author: windows-driver-content
description: PosCxPutPendingEvent creates a new event object, copies the event data to the new event object, and tries to delegate it to the waiting caller.
old-location: pos\poscxputpendingevent.htm
old-project: pos
ms.assetid: 4E2EA8F5-2D4A-4AEB-AF59-97D6C3FB09BC
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PosCxPutPendingEvent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: poscx.h
req.include-header: Poscx.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PosCxPutPendingEvent
req.alt-loc: poscx.h
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
req.product: Windows 10 or later.
---

# PosCxPutPendingEvent function



## -description
PosCxPutPendingEvent creates a new event object, copies the event data to the
      new event object, and tries to delegate it to the waiting caller. 
      If the target caller does not have a read request waiting, the new event is added to 
      the designated event queue (control or data).



## -syntax

````
NTSTATUS PosCxPutPendingEvent(
  _In_ WDFDEVICE                                  device,
  _In_ ULONG                                      deviceInterfaceTag,
  _In_ ULONG                                      eventType,
  _In_ size_t                                     rawEventDataSize,
       _In_reads_opt_(rawEventDataSize)
    PVOID rawEventDataPtr,
  _In_ POS_CX_EVENT_ATTRIBUTES                    eventAttr
);
````


## -parameters

### -param device [in]

A handle to a framework device object that represents the device.


### -param deviceInterfaceTag [in]

The device interface associated with the event.  By default, only
          file objects that have the same tag will receive this event.


### -param eventType [in]

The new event type.


### -param rawEventDataSize [in]

The raw event (without point-of-service header) buffer size in bytes.


### -param rawEventDataPtr 

The pointer to the raw (without point-of-service header) event data.
          The caller may reuse/release <i>rawEventDataPtr</i> after <b>PosCxPutPendingEvent</b> returns.


### -param eventAttr [in]

The event attributes.


## -returns
Possible return values are:

 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Product

</th>
<td width="70%">
Windows 10 or later.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Poscx.h (include Poscx.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="pos.pos_cx_event_attributes">POS_CX_EVENT_ATTRIBUTES</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [pos\pos]:%20PosCxPutPendingEvent function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

