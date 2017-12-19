---
UID: NS.WSK._WSK_EVENT_CALLBACK_CONTROL
title: _WSK_EVENT_CALLBACK_CONTROL
author: windows-driver-content
description: The WSK_EVENT_CALLBACK_CONTROL structure specifies the information for enabling and disabling a socket's event callback functions.
old-location: netvista\wsk_event_callback_control.htm
old-project: NetVista
ms.assetid: 152e142a-dda4-4540-b1a9-14625f4653bb
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _WSK_EVENT_CALLBACK_CONTROL, WSK_EVENT_CALLBACK_CONTROL, PWSK_EVENT_CALLBACK_CONTROL, *PWSK_EVENT_CALLBACK_CONTROL
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WSK_EVENT_CALLBACK_CONTROL
req.alt-loc: wsk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# _WSK_EVENT_CALLBACK_CONTROL structure



## -description
The WSK_EVENT_CALLBACK_CONTROL structure specifies the information for enabling and disabling a
  socket's event callback functions.



## -syntax

````
typedef struct _WSK_EVENT_CALLBACK_CONTROL {
  PNPIID NpiId;
  ULONG  EventMask;
} WSK_EVENT_CALLBACK_CONTROL, *PWSK_EVENT_CALLBACK_CONTROL;
````


## -struct-fields

### -field NpiId

A pointer to a 
     <a href="netvista.network_programming_interface">Network Programming Interface
     (NPI)</a> identifier that specifies the NPI for the event callback function that is being enabled or
     disabled. For enabling or disabling any of the standard WSK event callback functions, this member is a
     pointer to the WSK NPI identifier, NPI_WSK_INTERFACE_ID. For enabling or disabling any event callback
     functions for an extension interface, this member is a pointer to the NPI identifier for the extension
     interface.


### -field EventMask

A ULONG value that contains a bitwise OR of event flags for the event callback functions that are
     being enabled or disabled. For information about the event flags for the standard WSK event callback
     functions, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff570834">SO_WSK_EVENT_CALLBACK</a>.


## -remarks
A WSK application can enable any combination of event callback functions for a socket simultaneously
    by setting the 
    <b>EventMask</b> member to a bitwise OR of the event flags for all of the event callback functions that
    are being enabled. However, a WSK application must disable event callback functions individually by
    setting the 
    <b>EventMask</b> member to a bitwise OR of the event flag for the event callback function that is being
    disabled and the WSK_EVENT_DISABLE flag.

For more information about statically enabling certain event callback functions for all of the sockets
    that are created by a WSK application, see 
    <a href="netvista.wsk_set_static_event_callbacks">
    WSK_SET_STATIC_EVENT_CALLBACKS</a>.

For more information about enabling and disabling a socket's event callback functions, see 
    <a href="netvista.enabling_and_disabling_event_callback_functions">Enabling and
    Disabling Event Callback Functions</a>.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating
   systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wsk.h (include Wsk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wsk\nc-wsk-pfn_wsk_control_client.md">WskControlClient</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn_wsk_control_socket.md">WskControlSocket</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff570834">SO_WSK_EVENT_CALLBACK</a>
</dt>
<dt>
<a href="netvista.wsk_set_static_event_callbacks">
   WSK_SET_STATIC_EVENT_CALLBACKS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20WSK_EVENT_CALLBACK_CONTROL structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

