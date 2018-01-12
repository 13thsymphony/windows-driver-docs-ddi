---
UID: NN:dbgeng.IDebugSystemObjects4
title: IDebugSystemObjects4
author: windows-driver-content
description: IDebugSystemObjects4 interface
old-location: debugger\idebugsystemobjects4.htm
old-project: debugger
ms.assetid: 075143eb-03c4-41b2-b419-4618ed103843
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSystemObjects4, IDebugSystemObjects4::SetImplicitThreadDataOffset, SetImplicitThreadDataOffset
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugSystemObjects4,IDebugSystemObjects4.GetCurrentSystemServerNameWide
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
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# IDebugSystemObjects4 interface



## -description

## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugSystemObjects4</b> interface inherits from <a href="..\dbgeng\nn-dbgeng-idebugsystemobjects3.md">IDebugSystemObjects3</a>. <b>IDebugSystemObjects4</b> also has these types of members:

The <b>IDebugSystemObjects4</b> interface has these methods.

Returns the name of executable file loaded in the current process.



 


## -members
The <b>IDebugSystemObjects4</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545804">GetCurrentProcessExecutableNameWide</a>
</td>
<td align="left" width="63%">
Returns the name of executable file loaded in the current process.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>GetCurrentSystemServerNameWide</b></td>
<td align="left" width="63%">


</td>
</tr>
</table>Returns the name of executable file loaded in the current process.



 


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
<a href="..\dbgeng\nn-dbgeng-idebugsystemobjects.md">IDebugSystemObjects</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsystemobjects2.md">IDebugSystemObjects2</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsystemobjects3.md">IDebugSystemObjects3</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSystemObjects4 interface%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

