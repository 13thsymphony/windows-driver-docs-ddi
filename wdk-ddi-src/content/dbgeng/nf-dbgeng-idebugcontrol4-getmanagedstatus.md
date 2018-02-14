---
UID: NF:dbgeng.IDebugControl4.GetManagedStatus
title: IDebugControl4::GetManagedStatus method
author: windows-driver-content
description: Provides feedback on the engine's use of the runtime debugging APIs provided by the common language runtime (CLR).
old-location: debugger\idebugcontrol4_getmanagedstatus.htm
old-project: debugger
ms.assetid: C2D32ABB-5ABE-4580-9577-1144569EA8E1
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: dbgeng/IDebugControl4::GetManagedStatus, GetManagedStatus method [Windows Debugging], IDebugControl4 interface [Windows Debugging], GetManagedStatus method, debugger.idebugcontrol4_getmanagedstatus, IDebugControl4, GetManagedStatus, GetManagedStatus method [Windows Debugging], IDebugControl4 interface, IDebugControl4::GetManagedStatus
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Windows
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
-	IDebugControl4.GetManagedStatus
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# GetManagedStatus method
Provides feedback on the engine's
    use of the runtime debugging APIs provided by the common language runtime (CLR).

## Syntax

````
HRESULT GetManagedStatus(
  [out, optional] PULONG                        Flags,
  [in]            ULONG                         WhichString,
  [out]           _writes_opt_(StringSize) PSTR String,
  [in]            ULONG                         StringSize,
  [out, optional] PULONG                        StringNeeded
);
````

## Parameters

`Flags`

A pointer to flags from the debugging APIs.

`WhichString`

A value that controls which string to use.

`String`

A pointer to a string from the debugging APIs.

`StringSize`

The size of the string.

`StringNeeded`

A pointer to an output string.


## Return Value

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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
 

    Managed debugging support relies on debugging
    functionality provided by the CLR.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugcontrol4.md">IDebugControl4</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl4::GetManagedStatus method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>