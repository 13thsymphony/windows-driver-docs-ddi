---
UID: NF:poscx.PosCxPutPendingEventMemory
title: PosCxPutPendingEventMemory function
author: windows-driver-content
description: PosCxPutPendingEventMemory tries to delegate a memory object containing the event data to a waiting caller. If the target caller does not have a read request waiting, the new event is added to the designated event queue (control or data).
old-location: pos\poscxputpendingeventmemory.htm
old-project: pos
ms.assetid: DF9CA4A8-4B2A-4DED-9514-422AC5E0940D
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: PosCxPutPendingEventMemory, PosCxPutPendingEventMemory function, pos.poscxputpendingeventmemory, poscx/PosCxPutPendingEventMemory
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
-	PosCxPutPendingEventMemory
product: Windows
targetos: Windows
req.typenames: POS_CX_EVENT_PRIORITY
req.product: Windows 10 or later.
---


# PosCxPutPendingEventMemory function
PosCxPutPendingEventMemory tries to delegate a memory object containing the 
      event data to a waiting caller. 
      If the target caller does not have a read request waiting, the new event is added to 
      the designated event queue (control or data).

## Syntax

````
NTSTATUS PosCxPutPendingEventMemory(
  _In_ WDFDEVICE               device,
  _In_ ULONG                   deviceInterfaceTag,
  _In_ WDFMEMORY               eventMemory,
  _In_ POS_CX_EVENT_ATTRIBUTES eventAttr
);
````

## Parameters

`device`

A handle to a framework device object that represents the device.

`deviceInterfaceTag`

The device interface associated with the event.  By default, only
          file objects that have the same tag will receive this event.

`eventMemory`

The new event data memory object that contains both the point-of-service event header 
          and the data. PosCx will take over ownership of this passed in memory object.

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
<td><b>STATUS_DEVICE_NOT_READY</b></td>
<td>The PosCx library was not successfully initialized.</td>
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

<a href="..\poscx\ne-poscx-_pos_cx_event_attributes.md">POS_CX_EVENT_ATTRIBUTES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [pos\pos]:%20PosCxPutPendingEventMemory function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>