---
UID: NS:wsk._WSK_EXTENSION_CONTROL_IN
title: _WSK_EXTENSION_CONTROL_IN
author: windows-driver-content
description: The WSK_EXTENSION_CONTROL_IN structure specifies a WSK application's implementation of an extension interface for a socket.
old-location: netvista\wsk_extension_control_in.htm
old-project: netvista
ms.assetid: d04f4c24-15a5-490a-aada-af1050f727d4
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: _WSK_EXTENSION_CONTROL_IN, *PWSK_EXTENSION_CONTROL_IN, WSK_EXTENSION_CONTROL_IN
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
req.alt-api: WSK_EXTENSION_CONTROL_IN
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
req.typenames: *PWSK_EXTENSION_CONTROL_IN, WSK_EXTENSION_CONTROL_IN
req.product: Windows 10 or later.
---

# _WSK_EXTENSION_CONTROL_IN structure



## -description
The WSK_EXTENSION_CONTROL_IN structure specifies a WSK application's implementation of an extension
  interface for a socket.



## -syntax

````
typedef struct _WSK_EXTENSION_CONTROL_IN {
  PNPIID     NpiId;
  PVOID      ClientContext;
  const VOID *ClientDispatch;
} WSK_EXTENSION_CONTROL_IN, *PWSK_EXTENSION_CONTROL_IN;
````


## -struct-fields

### -field NpiId

A pointer to the 
     <a href="netvista.network_programming_interface">Network Programming Interface
     (NPI)</a> identifier that identifies the extension interface.


### -field ClientContext

A pointer to a WSK application-supplied context for the registration of the extension interface on
     a socket. A WSK application uses this context to track the state of the extension interface registration
     for the socket. The contents of the WSK application's registration context are opaque to the WSK
     subsystem. The WSK subsystem passes this pointer to the WSK application whenever it calls any of the
     socket's extension interface event callback functions that require the WSK application's registration
     context.


### -field ClientDispatch

A pointer to a structure that contains the WSK application's dispatch table of event callback
     functions for the extension interface. The contents of the structure are specific to the extension
     interface.


## -remarks
A WSK application passes a pointer to a WSK_EXTENSION_CONTROL_IN structure to the WSK subsystem when
    registering an extension interface. For more information about registering an extension interface, see 
    <a href="netvista.registering_an_extension_interface">Registering an Extension
    Interface</a>.


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
<a href="..\wsk\nc-wsk-pfn_wsk_control_socket.md">WskControlSocket</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff570819">SIO_WSK_REGISTER_EXTENSION</a>
</dt>
<dt>
<a href="..\wsk\ns-wsk-_wsk_extension_control_out.md">WSK_EXTENSION_CONTROL_OUT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WSK_EXTENSION_CONTROL_IN structure%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

