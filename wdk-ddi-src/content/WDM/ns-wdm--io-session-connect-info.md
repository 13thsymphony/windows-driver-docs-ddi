---
UID: NS.wdm._IO_SESSION_CONNECT_INFO
title: IO_SESSION_CONNECT_INFO
author: windows-driver-content
description: The IO_SESSION_CONNECT_INFO structure provides information about a user session.
old-location: kernel\io_session_connect_info.htm
ms.assetid: f9d7ffae-aa9e-44d6-b659-cb5a9068f1d7
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: kernel
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows 7 and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IO_SESSION_CONNECT_INFO
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
ms.keywords: IO_SESSION_CONNECT_INFO, IO_SESSION_CONNECT_INFO, *PIO_SESSION_CONNECT_INFO
req.iface: 
req.product: Windows 10 or later.
---

# IO_SESSION_CONNECT_INFO structure



## -description
<p>The <b>IO_SESSION_CONNECT_INFO</b> structure provides information about a user session. </p>


## -syntax

````
typedef struct _IO_SESSION_CONNECT_INFO {
  ULONG   SessionId;
  BOOLEAN LocalSession;
} IO_SESSION_CONNECT_INFO, *PIO_SESSION_CONNECT_INFO;
````


## -struct-fields
<dl>

### -field <b>SessionId</b>

<dd>
<p>Session ID. This member contains the <a href="http://go.microsoft.com/fwlink/p/?linkid=155045">Terminal Services</a> session identifier of the user session for which the driver is receiving this notification.</p>
</dd>

### -field <b>LocalSession</b>

<dd>
<p>Indicates whether the user session is a local session or a remote session. If <b>TRUE</b>, the user is logged on locally. If <b>FALSE</b>, the user is logged on remotely. </p>
</dd>
</dl>

## -remarks
<p>If a driver is registered to receive notifications of events in a user session, and if this session enters the <i>connected</i> state, the I/O manager calls the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff550626">IO_SESSION_NOTIFICATION_FUNCTION</a> function. For this call, the I/O manager sets the function's <i>Event</i> parameter to <b>IoSessionEventConnected</b>. Additionally, the I/O manager sets the function's <i>NotificationPayload</i> parameter to point to an <b>IO_SESSION_CONNECT_INFO</b> structure that contains information about the user session. For more information about <b>IoSessionEventConnected</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff550623">IO_SESSION_EVENT</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in Windows 7 and later versions of the Windows operating system.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, Ntifs.h, or Fltkernel.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550623">IO_SESSION_EVENT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550626">IO_SESSION_NOTIFICATION_FUNCTION</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IO_SESSION_CONNECT_INFO structure%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
