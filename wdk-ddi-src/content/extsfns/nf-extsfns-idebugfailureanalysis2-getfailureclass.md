---
UID : NF:extsfns.IDebugFailureAnalysis2.GetFailureClass
title : IDebugFailureAnalysis2::GetFailureClass method
author : windows-driver-content
description : The GetFailureClass method gets the failure class of a DebugFailureAnalysis object. The failure class indicates whether the debugging session that created the DebugFailureAnalysis object is a kernel mode session or a user mode session.
old-location : debugger\idebugfailureanalysis2_getfailureclass.htm
old-project : debugger
ms.assetid : 4840F881-E3CB-4C89-AE2D-88610790C221
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : IDebugFailureAnalysis2, IDebugFailureAnalysis2::GetFailureClass, GetFailureClass
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : extsfns.h
req.include-header : 
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IDebugFailureAnalysis2.GetFailureClass
req.alt-loc : extsfns.h
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
req.typenames : FA_EXTENSION_PLUGIN_PHASE
---


# GetFailureClass method
The <b>GetFailureClass</b> method gets the failure class of a <a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">DebugFailureAnalysis</a> object. The failure class indicates whether the debugging session  that created the <b>DebugFailureAnalysis</b> object is a kernel mode session or a user mode session.

## Syntax

````
ULONG GetFailureClass();
````

## Parameters

This function has no parameters.

## Return Value

<dl>
<dt><b>DEBUG_CLASS_UNINITIALIZED</b></dt>
<dt>0</dt>
</dl>The debug class has not been initialized.
<dl>
<dt><b>DEBUG_CLASS_KERNEL</b></dt>
<dt>1</dt>
</dl>The debugging session is a kernel-mode session.
<dl>
<dt><b>DEBUG_CLASS_USER_WINDOWS</b></dt>
<dt>2</dt>
</dl>The debugging session is a user-mode session.

 

These return values are defined in dbgeng.h.
<dl>
<dt><b>DEBUG_CLASS_UNINITIALIZED</b></dt>
<dt>0</dt>
</dl>The debug class has not been initialized.
<dl>
<dt><b>DEBUG_CLASS_KERNEL</b></dt>
<dt>1</dt>
</dl>The debugging session is a kernel-mode session.
<dl>
<dt><b>DEBUG_CLASS_USER_WINDOWS</b></dt>
<dt>2</dt>
</dl>The debugging session is a user-mode session.

 

These return values are defined in dbgeng.h.
<dl>
<dt><b>DEBUG_CLASS_UNINITIALIZED</b></dt>
<dt>0</dt>
</dl>The debug class has not been initialized.
<dl>
<dt><b>DEBUG_CLASS_KERNEL</b></dt>
<dt>1</dt>
</dl>The debugging session is a kernel-mode session.
<dl>
<dt><b>DEBUG_CLASS_USER_WINDOWS</b></dt>
<dt>2</dt>
</dl>The debugging session is a user-mode session.

 

These return values are defined in dbgeng.h.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | extsfns.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">IDebugFailureAnalysis2</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/jj983417">GetFailureType</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/jj983416">GetFailureCode</a>
</dt>
<dt>
<a href="..\extsfns\nc-extsfns-ext_analysis_plugin.md">_EFN_Analyze</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugFailureAnalysis2::GetFailureClass method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>