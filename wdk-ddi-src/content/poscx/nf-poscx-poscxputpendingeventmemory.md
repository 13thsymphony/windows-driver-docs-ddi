---
UID: NF.poscx.PosCxPutPendingEventMemory
title: PosCxPutPendingEventMemory
author: windows-driver-content
description: PosCxPutPendingEventMemory tries to delegate a memory object containing the event data to a waiting caller. If the target caller does not have a read request waiting, the new event is added to the designated event queue (control or data).
old-location: pos\poscxputpendingeventmemory.htm
old-project: pos
ms.assetid: DF9CA4A8-4B2A-4DED-9514-422AC5E0940D
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: PosCxPutPendingEventMemory
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
req.alt-api: PosCxPutPendingEventMemory
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
req.iface: 
req.product: Windows 10 or later.
---

# PosCxPutPendingEventMemory function



## -description
<p>PosCxPutPendingEventMemory tries to delegate a memory object containing the 
      event data to a waiting caller. 
      If the target caller does not have a read request waiting, the new event is added to 
      the designated event queue (control or data).</p>


## -syntax

````
NTSTATUS PosCxPutPendingEventMemory(
  _In_ WDFDEVICE               device,
  _In_ ULONG                   deviceInterfaceTag,
  _In_ WDFMEMORY               eventMemory,
  _In_ POS_CX_EVENT_ATTRIBUTES eventAttr
);
````


## -parameters
<dl>

### -param <i>device</i> [in]

<dd>
<p>A handle to a framework device object that represents the device.</p>
</dd>

### -param <i>deviceInterfaceTag</i> [in]

<dd>
<p>The device interface associated with the event.  By default, only
          file objects that have the same tag will receive this event.</p>
</dd>

### -param <i>eventMemory</i> [in]

<dd>
<p>The new event data memory object that contains both the point-of-service event header 
          and the data. PosCx will take over ownership of this passed in memory object.</p>
</dd>

### -param <i>eventAttr</i> [in]

<dd>
<p>The event attributes.</p>
</dd>
</dl>

## -returns
<p>Possible return values are:</p>

<p> </p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Product</p>
</th>
<td width="70%">
<p>Windows 10 or later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/mt593142">POS_CX_EVENT_ATTRIBUTES</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [pos\pos]:%20PosCxPutPendingEventMemory function%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
