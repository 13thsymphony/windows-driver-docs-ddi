---
UID : NF:dbgeng.IDebugClient5.StartServerWide
title : IDebugClient5::StartServerWide method
author : windows-driver-content
description : The StartServerWide method starts a debugging server.
old-location : debugger\startserverwide.htm
old-project : debugger
ms.assetid : 7a36f278-45eb-4ee9-9bdf-370c546245c0
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : IDebugClient5, IDebugClient5::StartServerWide, StartServerWide
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : dbgeng.h
req.include-header : Dbgeng.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IDebugClient5.StartServerWide
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


# StartServerWide method
The <b>StartServerWide</b> method starts a debugging server.

## Syntax

````
HRESULT StartServerWide(
  [in] PCSTR Options
);
````

## Parameters

`Options`

Specifies the connections options for this server.  These are the same options given to the <b>.server</b> debugger command or the WinDbg and CDB <b>-server</b> command-line option.  For details on the syntax of this string, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff537823">Activating a Debugging Server</a>.


## Return Value

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

## Remarks

The server that is started will be accessible by other <a href="https://msdn.microsoft.com/13F9D82A-4C04-425A-A063-B349DB5C8E08">debuggers</a> through the transport specified in the <i>Options</i> parameter.

For more information about debugging servers, see Debugging Server and Debugging Client.

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
<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>
</dt>
<dt>
<a href="..\dbgeng\nf-dbgeng-debugconnect.md">DebugConnect</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558810">StartProcessServer</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553247">OutputServers</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient5::StartServerWide method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>