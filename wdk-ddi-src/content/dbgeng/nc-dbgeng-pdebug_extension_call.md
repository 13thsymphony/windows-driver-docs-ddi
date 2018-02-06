---
UID: NC:dbgeng.PDEBUG_EXTENSION_CALL
title: PDEBUG_EXTENSION_CALL
author: windows-driver-content
description: Callback functions of the type PDEBUG_EXTENSION_CALL are called by the engine to execute extension commands. You can give these functions any name you want, as long as it contains no uppercase letters.
old-location: debugger\pdebug_extension_call.htm
old-project: debugger
ms.assetid: 325af2f4-9fb7-4fb3-9294-cd6d20d803c6
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: debugger.pdebug_extension_call, DebugExtensionCall, PDEBUG_EXTENSION_CALL function pointer [Windows Debugging], PDEBUG_EXTENSION_CALL, dbgeng/PDEBUG_EXTENSION_CALL, Extensions_Ref_fc621d91-0419-4ae3-8e53-71f4c522c318.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dbgeng.h
req.include-header: 
req.target-type: Desktop
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	dbgeng.h
apiname:
-	DebugExtensionCall
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# PDEBUG_EXTENSION_CALL callback function
Callback functions of the type <b>PDEBUG_EXTENSION_CALL</b> are called by the engine to execute <a href="https://msdn.microsoft.com/5131115b-b9a0-479b-9391-7ab384633d92">extension commands</a>. You can give these functions any name you want, as long as it contains no uppercase letters.

## Syntax

```
PDEBUG_EXTENSION_CALL PdebugExtensionCall;

HRESULT PdebugExtensionCall(
  PDEBUG_CLIENT Client,
  PCSTR Args
)
{...}
```

## Parameters

`Client`

Specifies an interface pointer to the client.  This can be used to interact with the engine.  Typically, this is the client through which the extension command was issued.

`Args`

Specifies the arguments passed to the extension command.  In particular, if the extension command was called from a command line, <i>Args</i> contains the rest of the command line.  It can be <b>NULL</b> or empty.


## Return Value

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The function was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>DEBUG_EXTENSION_CONTINUE_SEARCH</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the function cannot handle the command, or that other implementations of the same command in other extension DLLs should also run.  The engine should continue searching other extension DLLs for another function to handle the command. For example, this can be used to have all help functions run if each one returns CONTINUE_SEARCH.

</td>
</tr>
</table> 

All other return values are ignored by the engine.

## Remarks

The name of the function becomes the name of the extension command.  When executing an extension command, the engine searches through each of the loaded extension DLLs in turn, looking for an exported function that has the same name as the command.  For example, when executing the command <b>!stack</b>, the engine will look for an exported function named <b>stack</b> in each loaded extension DLL. For information about the order in which extension DLLs are searched, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560098">Using Debugger Extension Commands</a>.

The extension function should use the client that was passed to it in <i>Client</i> for all interaction with the engine, unless it has a specific reason to use another client.  The extension function should not maintain the pointer to the client object after it has finished.

DebugExtensionCall is called <b>PDEBUG_EXTENSION_CALL</b>   in the Dbgeng.h header file.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20PDEBUG_EXTENSION_CALL function pointer%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>