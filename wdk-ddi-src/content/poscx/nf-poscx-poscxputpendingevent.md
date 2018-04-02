---
UID: NF:poscx.PosCxPutPendingEvent
title: PosCxPutPendingEvent function
author: windows-driver-content
description: PosCxPutPendingEvent creates a new event object, copies the event data to the new event object, and tries to delegate it to the waiting caller.
old-location: pos\poscxputpendingevent.htm
old-project: pos
ms.assetid: 4E2EA8F5-2D4A-4AEB-AF59-97D6C3FB09BC
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: PosCxPutPendingEvent, PosCxPutPendingEvent function, pos.poscxputpendingevent, poscx/PosCxPutPendingEvent
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
-	poscx.h
api_name:
-	PosCxPutPendingEvent
product:
- Windows
targetos: Windows
req.typenames: POS_CX_EVENT_PRIORITY
req.product: Windows 10 or later.
---


# PosCxPutPendingEvent function
PosCxPutPendingEvent creates a new event object, copies the event data to the
      new event object, and tries to delegate it to the waiting caller. 
      If the target caller does not have a read request waiting, the new event is added to 
      the designated event queue (control or data).

## Syntax

```
NTSTATUS PosCxPutPendingEvent(
  WDFDEVICE               device,
  ULONG                   deviceInterfaceTag,
  ULONG                   eventType,
  size_t                  rawEventDataSize,
  PVOID                   rawEventDataPtr,
  POS_CX_EVENT_ATTRIBUTES eventAttr
);
```

## Parameters

`device`

A handle to a framework device object that represents the device.

`deviceInterfaceTag`

The device interface associated with the event.  By default, only
          file objects that have the same tag will receive this event.

`eventType`

The new event type.

`rawEventDataSize`

The raw event (without point-of-service header) buffer size in bytes.

`rawEventDataPtr`

The pointer to the raw (without point-of-service header) event data.
          The caller may reuse/release <i>rawEventDataPtr</i> after <b>PosCxPutPendingEvent</b> returns.

`eventAttr`

The event attributes.


## Return Value

Possible return values are:

<table>
<tr>
<td><b>STATUS_SUCCESS</b></td>
<td>The event was created and delegated to a waiting caller,
          or the event was discarded because there is no device owner.
</td>
</tr>
<tr>
<td><b>STATUS_PENDING</b></td>
<td>The event was queued because no caller is currently waiting.</td>
</tr>
<tr>
<td>Other errors</td>
<td>Other appropriate failure error codes.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | poscx.h (include Poscx.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt593142">POS_CX_EVENT_ATTRIBUTES</a>