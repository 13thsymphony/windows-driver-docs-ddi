---
UID: NF.dbgeng.IDebugControl4.ResetManagedStatus
title: IDebugControl4::ResetManagedStatus method
author: windows-driver-content
description: Clears and reinitializes the engine's managed code debugging support of the runtime debugging APIs provided by the common language runtime (CLR).
old-location: debugger\idebugcontrol4_resetmanagedstatus.htm
old-project: Debugger
ms.assetid: 6A9F8963-54F2-4AD7-AB98-C3215E1F7839
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IDebugControl4, IDebugControl4::ResetManagedStatus, ResetManagedStatus
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
req.alt-api: IDebugControl4.ResetManagedStatus
req.alt-loc: dbgeng.h
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
---

# IDebugControl4::ResetManagedStatus method



## -description
    Clears and reinitializes the engine's
    managed code debugging support of the runtime debugging APIs provided by the common language runtime (CLR).



## -syntax

````
HRESULT ResetManagedStatus(
  [in] ULONG Flags
);
````


## -parameters

### -param Flags [in]

Flags for the debugging API.


## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 

    Managed debugging support relies on debugging
    functionality provided by the CLR.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Dbgeng.h (include Dbgeng.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol4.md">IDebugControl4</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugControl4::ResetManagedStatus method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

