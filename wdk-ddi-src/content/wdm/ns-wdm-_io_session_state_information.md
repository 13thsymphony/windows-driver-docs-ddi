---
UID: NS:wdm._IO_SESSION_STATE_INFORMATION
title: "_IO_SESSION_STATE_INFORMATION"
author: windows-driver-content
description: The IO_SESSION_STATE_INFORMATION structure contains information about the state of a user session.
old-location: kernel\io_session_state_information.htm
old-project: kernel
ms.assetid: ef56da02-52ae-4f85-8820-fc310638bb89
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PIO_SESSION_STATE_INFORMATION, IO_SESSION_STATE_INFORMATION, IO_SESSION_STATE_INFORMATION structure [Kernel-Mode Driver Architecture], PIO_SESSION_STATE_INFORMATION, PIO_SESSION_STATE_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _IO_SESSION_STATE_INFORMATION, kernel.io_session_state_information, kstruct_b_1021e6f4-b82d-4f1d-8664-dbef116240d1.xml, wdm/IO_SESSION_STATE_INFORMATION, wdm/PIO_SESSION_STATE_INFORMATION"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	IO_SESSION_STATE_INFORMATION
product: Windows
targetos: Windows
req.typenames: IO_SESSION_STATE_INFORMATION, *PIO_SESSION_STATE_INFORMATION
req.product: Windows 10 or later.
---

# _IO_SESSION_STATE_INFORMATION structure
The <b>IO_SESSION_STATE_INFORMATION</b> structure contains information about the state of a user session.

## Syntax
````
typedef struct _IO_SESSION_STATE_INFORMATION {
  ULONG            SessionId;
  IO_SESSION_STATE SessionState;
  BOOLEAN          LocalSession;
} IO_SESSION_STATE_INFORMATION, *PIO_SESSION_STATE_INFORMATION;
````

## Members


`SessionId`

The session ID. This member contains the <a href="http://go.microsoft.com/fwlink/p/?linkid=155045">Terminal Services</a> session identifier of a user session. The <a href="..\wdm\nf-wdm-iogetcontainerinformation.md">IoGetContainerInformation</a> routine sets this member to the session ID of the session that is represented by the session object that the <i>ContainerObject</i> parameter of <b>IoGetContainerInformation</b> points to.

`SessionState`

The current state of the user session that is identified by <i>SessionId</i>. This member is set to one of the following <a href="..\wdm\ne-wdm-_io_session_state.md">IO_SESSION_STATE</a> enumeration constants:

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

`LocalSession`

Indicates whether the user session identified by <i>SessionId</i> is a local session. If <b>TRUE</b>, the user is logged on locally. If <b>FALSE</b>, the user is logged on remotely. This member is valid only if the session is connected. The following <b>IO_SESSION_STATE</b> enumeration constants represent session states in which the session is connected:

<ul>
<li><b>IoSessionStateConnected</b></li>
<li><b>IoSessionStateLoggedOn</b></li>
<li><b>IoSessionStateLoggedOff</b></li>
</ul>

## Remarks
To obtain information about a user session, a driver calls the <b>IoGetContainerInformation</b> routine. This routine's <i>Buffer</i> parameter points to an <b>IO_SESSION_STATE_INFORMATION</b> structure that contains information about the session state.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in Windows 7 and later versions of the Windows operating system. Supported in Windows 7 and later versions of the Windows operating system. |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h, Fltkernel.h) |

## See Also

<a href="..\wdm\nf-wdm-iogetcontainerinformation.md">IoGetContainerInformation</a>



<a href="..\wdm\ne-wdm-_io_session_state.md">IO_SESSION_STATE</a>