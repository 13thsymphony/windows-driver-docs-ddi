---
UID: NF:dbgeng.IDebugControl2.RemoveExtension
title: IDebugControl2::RemoveExtension method
author: windows-driver-content
description: The RemoveExtension method unloads an extension library.
old-location: debugger\removeextension.htm
old-project: Debugger
ms.assetid: ba4a87cc-2412-4769-9694-d6eefd750c4b
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IDebugControl3::RemoveExtension, dbgeng/IDebugControl3::RemoveExtension, IDebugControl, IDebugControl2, RemoveExtension method [Windows Debugging], IDebugControl2 interface, IDebugControl2::RemoveExtension, dbgeng/IDebugControl2::RemoveExtension, debugger.removeextension, IDebugControl interface [Windows Debugging], RemoveExtension method, IDebugControl::RemoveExtension, IDebugControl2 interface [Windows Debugging], RemoveExtension method, RemoveExtension method [Windows Debugging], IDebugControl3 interface, RemoveExtension method [Windows Debugging], IDebugControl interface, dbgeng/IDebugControl::RemoveExtension, IDebugControl_c762281b-f49c-4837-a524-e2f04edb3b0c.xml, RemoveExtension, IDebugControl3 interface [Windows Debugging], RemoveExtension method, RemoveExtension method [Windows Debugging]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
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
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugControl.RemoveExtension
-	IDebugControl2.RemoveExtension
-	IDebugControl3.RemoveExtension
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# RemoveExtension method
The <b>RemoveExtension</b> method unloads an extension library.

## Syntax

````
HRESULT RemoveExtension(
  [in] ULONG64 Handle
);
````

## Parameters

`Handle`

Specifies the handle of the extension library to unload.  This is the handle returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff537892">AddExtension</a>.


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
The method was successful.

</td>
</tr>
</table>
 

This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

## Remarks

For more information on using extension libraries, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539033">Calling Extensions and Extension Functions</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537892">AddExtension</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugControl::RemoveExtension method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>