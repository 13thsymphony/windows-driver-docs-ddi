---
UID: NS.WDM._IO_SESSION_STATE_INFORMATION
title: _IO_SESSION_STATE_INFORMATION
author: windows-driver-content
description: The IO_SESSION_STATE_INFORMATION structure contains information about the state of a user session.
old-location: kernel\io_session_state_information.htm
old-project: kernel
ms.assetid: ef56da02-52ae-4f85-8820-fc310638bb89
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _IO_SESSION_STATE_INFORMATION, IO_SESSION_STATE_INFORMATION, *PIO_SESSION_STATE_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows 7 and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IO_SESSION_STATE_INFORMATION
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
req.product: Windows 10 or later.
---

# _IO_SESSION_STATE_INFORMATION structure



## -description
The <b>IO_SESSION_STATE_INFORMATION</b> structure contains information about the state of a user session.


## -syntax

````
typedef struct _IO_SESSION_STATE_INFORMATION {
  ULONG            SessionId;
  IO_SESSION_STATE SessionState;
  BOOLEAN          LocalSession;
} IO_SESSION_STATE_INFORMATION, *PIO_SESSION_STATE_INFORMATION;
````


## -struct-fields

### -field SessionId


      The session ID. This member contains the <a href="http://go.microsoft.com/fwlink/p/?linkid=155045">Terminal Services</a> session identifier of a user session. The <a href="kernel.iogetcontainerinformation">IoGetContainerInformation</a> routine sets this member to the session ID of the session that is represented by the session object that the <i>ContainerObject</i> parameter of <b>IoGetContainerInformation</b> points to.

### -field SessionState

The current state of the user session that is identified by <i>SessionId</i>. This member is set to one of the following <a href="kernel.io_session_state">IO_SESSION_STATE</a> enumeration constants:
<ul>
<li><b>IoSessionStateCreated</b></li>
<li><b>IoSessionStateInitialized</b></li>
<li><b>IoSessionStateConnected</b></li>
<li><b>IoSessionStateDisconnected</b></li>
<li><b>IoSessionStateDisconnectedLoggedOn</b></li>
<li><b>IoSessionStateLoggedOn</b></li>
<li><b>IoSessionStateLoggedOff</b></li>
<li><b>IoSessionStateTerminated</b></li>
</ul>

### -field LocalSession

Indicates whether the user session identified by <i>SessionId</i> is a local session. If <b>TRUE</b>, the user is logged on locally. If <b>FALSE</b>, the user is logged on remotely. This member is valid only if the session is connected. The following <b>IO_SESSION_STATE</b> enumeration constants represent session states in which the session is connected:
<ul>
<li><b>IoSessionStateConnected</b></li>
<li><b>IoSessionStateLoggedOn</b></li>
<li><b>IoSessionStateLoggedOff</b></li>
</ul>

## -remarks
To obtain information about a user session, a driver calls the <b>IoGetContainerInformation</b> routine. This routine's <i>Buffer</i> parameter points to an <b>IO_SESSION_STATE_INFORMATION</b> structure that contains information about the session state.

## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Supported in Windows 7 and later versions of the Windows operating system.
</td>
</tr>
<tr>
<th width="30%">
Header
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
<a href="kernel.iogetcontainerinformation">IoGetContainerInformation</a>
</dt>
<dt>
<a href="kernel.io_session_state">IO_SESSION_STATE</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IO_SESSION_STATE_INFORMATION structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
