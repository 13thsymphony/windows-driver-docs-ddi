---
UID: NS.wsk._WSK_EXTENSION_CONTROL_OUT
title: WSK_EXTENSION_CONTROL_OUT
author: windows-driver-content
description: The WSK_EXTENSION_CONTROL_OUT structure specifies the WSK subsystem's implementation of an extension interface for a socket.
old-location: netvista\wsk_extension_control_out.htm
old-project: netvista
ms.assetid: aec44058-13ad-4093-91b1-e5dca6f2e295
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: WSK_EXTENSION_CONTROL_OUT, WSK_EXTENSION_CONTROL_OUT, *PWSK_EXTENSION_CONTROL_OUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating
   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WSK_EXTENSION_CONTROL_OUT
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
req.iface: 
req.product: Windows 10 or later.
---

# WSK_EXTENSION_CONTROL_OUT structure



## -description
<p>The WSK_EXTENSION_CONTROL_OUT structure specifies the WSK subsystem's implementation of an extension
  interface for a socket.</p>


## -syntax

````
typedef struct _WSK_EXTENSION_CONTROL_OUT {
  PVOID      ProviderContext;
  const VOID *ProviderDispatch;
} WSK_EXTENSION_CONTROL_OUT, *PWSK_EXTENSION_CONTROL_OUT;
````


## -struct-fields
<dl>

### -field <b>ProviderContext</b>

<dd>
<p>A pointer to a WSK subsystem-supplied context for the registration of the extension interface on a
     socket. The WSK subsystem uses this context to track the state of the extension interface registration
     for the socket. The contents of the WSK subsystem's registration context are opaque to the WSK
     application. The WSK application passes this pointer to the WSK subsystem whenever it calls any of the
     socket's extension interface functions that require the WSK subsystem's registration context.</p>
</dd>

### -field <b>ProviderDispatch</b>

<dd>
<p>A pointer to a structure that contains the WSK subsystem's dispatch table of functions for the
     extension interface. The contents of the structure are specific to the extension interface.</p>
</dd>
</dl>

## -remarks
<p>The WSK subsystem fills in the contents of the WSK_EXTENSION_CONTROL_OUT structure when a WSK
    application registers an extension interface. For more information about registering an extension
    interface, see 
    <a href="netvista.registering_an_extension_interface">Registering an Extension
    Interface</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later versions of the Windows operating
   systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff571127">WskControlSocket</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff570819">SIO_WSK_REGISTER_EXTENSION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff571167">WSK_EXTENSION_CONTROL_IN</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WSK_EXTENSION_CONTROL_OUT structure%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
