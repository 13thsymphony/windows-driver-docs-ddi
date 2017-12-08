---
UID: NN.dbgeng.IDebugDataSpaces
title: IDebugDataSpaces
author: windows-driver-content
description: IDebugDataSpaces interface
old-location: debugger\idebugdataspaces.htm
old-project: debugger
ms.assetid: 9477821c-4f4f-4ea2-9968-d43f87c496b2
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: DebugCreateEx
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
req.alt-api: IDebugDataSpaces
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

# IDebugDataSpaces interface



## -description

## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugDataSpaces</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IDebugDataSpaces</b> also has these types of members:

The <b>IDebugDataSpaces</b> interface has these methods.

Checks for memory corruption in the low 4 GB of memory.

Reads data from a system bus.

Reads implementation-specific system data.

Returns information about the target that the debugger engine has queried or determined during the current session.

Reads from the system and bus I/O memory.

Reads a specified Model-Specific Register (MSR).

Reads the target's memory from the specified physical address.

 Reads pointers from the target's virtual address space.


Returns data about the specified processor.

Reads memory from the target's virtual address space.

Reads memory from the target's virtual address space.

Searches the target's virtual memory for a specified pattern of bytes.

Writes data to a system bus.

Writes implementation-specific system data.

Writes to the system and bus I/O memory.

Writes a value to the specified Model-Specific Register (MSR).

Writes data to the specified physical address in the target's memory.

Writes pointers to the target's virtual address space.

Writes data to the target's virtual address space.

Writes data to the target's virtual address space.

 

## -members
The <b>IDebugDataSpaces</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.checklowmemory">CheckLowMemory</a>
</td>
<td align="left" width="63%">
Checks for memory corruption in the low 4 GB of memory.
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.readbusdata">ReadBusData</a>
</td>
<td align="left" width="63%">
Reads data from a system bus.
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.readcontrol">ReadControl</a>
</td>
<td align="left" width="63%">
Reads implementation-specific system data.
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.readdebuggerdata">ReadDebuggerData</a>
</td>
<td align="left" width="63%">
Returns information about the target that the debugger engine has queried or determined during the current session.
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.readio">ReadIo</a>
</td>
<td align="left" width="63%">
Reads from the system and bus I/O memory.
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.readmsr">ReadMsr</a>
</td>
<td align="left" width="63%">
Reads a specified Model-Specific Register (MSR).
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.readphysical">ReadPhysical</a>
</td>
<td align="left" width="63%">
Reads the target's memory from the specified physical address.
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.readpointersvirtual">ReadPointersVirtual</a>
</td>
<td align="left" width="63%">
 Reads pointers from the target's virtual address space.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.readprocessorsystemdata">ReadProcessorSystemData</a>
</td>
<td align="left" width="63%">
Returns data about the specified processor.
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.readvirtual">ReadVirtual</a>
</td>
<td align="left" width="63%">
Reads memory from the target's virtual address space.
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.readvirtualuncached">ReadVirtualUncached</a>
</td>
<td align="left" width="63%">
Reads memory from the target's virtual address space.
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.searchvirtual">SearchVirtual</a>
</td>
<td align="left" width="63%">
Searches the target's virtual memory for a specified pattern of bytes.
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.writebusdata">WriteBusData</a>
</td>
<td align="left" width="63%">
Writes data to a system bus.
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.writecontrol">WriteControl</a>
</td>
<td align="left" width="63%">
Writes implementation-specific system data.
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.writeio">WriteIo</a>
</td>
<td align="left" width="63%">
Writes to the system and bus I/O memory.
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.writemsr">WriteMsr</a>
</td>
<td align="left" width="63%">
Writes a value to the specified Model-Specific Register (MSR).
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.writephysical">WritePhysical</a>
</td>
<td align="left" width="63%">
Writes data to the specified physical address in the target's memory.
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.writepointersvirtual">WritePointersVirtual</a>
</td>
<td align="left" width="63%">
Writes pointers to the target's virtual address space.
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.writevirtual">WriteVirtual</a>
</td>
<td align="left" width="63%">
Writes data to the target's virtual address space.
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.writevirtualuncached">WriteVirtualUncached</a>
</td>
<td align="left" width="63%">
Writes data to the target's virtual address space.
</td>
</tr>
</table>Checks for memory corruption in the low 4 GB of memory.

Reads data from a system bus.

Reads implementation-specific system data.

Returns information about the target that the debugger engine has queried or determined during the current session.

Reads from the system and bus I/O memory.

Reads a specified Model-Specific Register (MSR).

Reads the target's memory from the specified physical address.

 Reads pointers from the target's virtual address space.


Returns data about the specified processor.

Reads memory from the target's virtual address space.

Reads memory from the target's virtual address space.

Searches the target's virtual memory for a specified pattern of bytes.

Writes data to a system bus.

Writes implementation-specific system data.

Writes to the system and bus I/O memory.

Writes a value to the specified Model-Specific Register (MSR).

Writes data to the specified physical address in the target's memory.

Writes pointers to the target's virtual address space.

Writes data to the target's virtual address space.

Writes data to the target's virtual address space.

 

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
<a href="..\dbgeng\nn-dbgeng-idebugdataspaces2.md">IDebugDataSpaces2</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugdataspaces3.md">IDebugDataSpaces3</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugdataspaces4.md">IDebugDataSpaces4</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugDataSpaces interface%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
