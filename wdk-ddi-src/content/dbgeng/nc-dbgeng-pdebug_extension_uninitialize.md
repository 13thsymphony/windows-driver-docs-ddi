---
UID : NC:dbgeng.PDEBUG_EXTENSION_UNINITIALIZE
title : PDEBUG_EXTENSION_UNINITIALIZE
author : windows-driver-content
description : The DebugExtensionUninitialize callback function is called by the engine to uninitialize the DbgEng extension DLL before it is unloaded.
old-location : debugger\debugextensionuninitialize.htm
old-project : debugger
ms.assetid : 34585815-d683-4702-bbfe-76d5d9fe244c
ms.author : windowsdriverdev
ms.date : 1/19/2018
ms.keywords : debugger.debugextensionuninitialize, DebugExtensionUninitialize, DebugExtensionUninitialize callback function [Windows Debugging], DebugExtensionUninitialize, PDEBUG_EXTENSION_UNINITIALIZE, PDEBUG_EXTENSION_UNINITIALIZE, dbgeng/DebugExtensionUninitialize, Extensions_Ref_76594e24-5f2d-495f-b8a9-6acec1f21ba4.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : dbgeng.h
req.include-header : 
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# PDEBUG_EXTENSION_UNINITIALIZE callback function
The <b>DebugExtensionUninitialize</b> callback function is called by the engine to uninitialize the DbgEng extension DLL before it is unloaded.
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre> CALLBACK* PDEBUG_EXTENSION_UNINITIALIZE DebugExtensionUninitialize;</pre>
</td>
</tr>
</table></span></div>

## Syntax

```
PDEBUG_EXTENSION_UNINITIALIZE PdebugExtensionUninitialize;

void PdebugExtensionUninitialize(
   void
)
{...}
```

## Parameters

`void`




## Return Value

This callback function does not return a value.

## Remarks

This function is optional.  A DbgEng extension DLL only needs to export <b>DebugExtensionUninitialize</b> if it needs to be notified before it is unloaded.  The engine looks for this function by name in the extension DLL.

This function can be used by the extension DLL to clean up before it is unloaded.

There may or may not be a session active when this function is called, so the extension should not assume that it is able to query session information.

DebugExtensionUninitialize is called <b>PDEBUG_EXTENSION_UNINITIALIZE</b> in the Dbgeng.h header file.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dbgeng.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\dbgeng\nc-dbgeng-pdebug_extension_initialize.md">DebugExtensionInitialize</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20PDEBUG_EXTENSION_UNINITIALIZE callback function%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>