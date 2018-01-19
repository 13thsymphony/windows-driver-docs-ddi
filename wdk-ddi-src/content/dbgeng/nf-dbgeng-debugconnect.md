---
UID : NF:dbgeng.DebugConnect
title : DebugConnect function
author : windows-driver-content
description : The DebugConnect and DebugConnectWide functions create a new client object and return an interface pointer to it. The client object will be connected to a remote host.
old-location : debugger\debugconnect.htm
old-project : debugger
ms.assetid : 77dba83d-cc25-4609-905c-7a036cb7ced9
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : DebugConnect
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : dbgeng.h
req.include-header : Dbgeng.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : DebugConnect
req.alt-loc : dbgeng.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# DebugConnect function
The <b>DebugConnect</b> and <b>DebugConnectWide</b> functions create a new client object and return an interface pointer to it.  The client object will be connected to a remote host.

## Syntax

````
HRESULT DebugConnect(
  _In_  PCSTR  RemoteOptions,
  _In_  REFIID InterfaceId,
  _Out_ PVOID  *Interface
);
````

## Parameters

`RemoteOptions`

Specifies how the debugger engine will connect to the remote host.  These are the same options that get passed to the <b>-remote</b> option on the command line.  For details on the syntax of this string, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff537819">Activating a Debugging Client</a>.

`InterfaceId`

Specifies the interface identifier (IID) of the desired debugger engine client interface.  This is the type of the interface that will be returned in <i>Interface</i>. For information about the interface identifier, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560088">Using Client Objects</a>.

`Interface`

Receives an interface pointer for the new client.  The type of this interface is specified by <i>InterfaceId</i>.


## Return Value

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

## Remarks

As with <b>IUnknown::QueryInterface</b>, when the returned interface is no longer needed, its <b>IUnknown::Release</b> method should be called.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539140">Client Objects</a>
</dt>
<dt>Process Server and Smart Client</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20DebugConnect function%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>