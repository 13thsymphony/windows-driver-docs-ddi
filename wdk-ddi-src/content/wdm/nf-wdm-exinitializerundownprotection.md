---
UID: NF.wdm.ExInitializeRundownProtection
title: ExInitializeRundownProtection
author: windows-driver-content
description: The ExInitializeRundownProtection routine initializes run-down protection on a shared object.
old-location: kernel\exinitializerundownprotection.htm
old-project: kernel
ms.assetid: 59B9C222-1A03-4C04-9F29-D9EA47E5E298
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: ExInitializeRundownProtection
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ExInitializeRundownProtection
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# ExInitializeRundownProtection function



## -description
<p>The <b>ExInitializeRundownProtection</b> routine initializes run-down protection on a shared object.</p>


## -syntax

````
VOID ExInitializeRundownProtection(
  _Out_ PEX_RUNDOWN_REF RunRef
);
````


## -parameters
<dl>

### -param <i>RunRef</i> [out]

<dd>
<p>A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/jj569379">EX_RUNDOWN_REF</a> structure that is to be initialized. The allocation must be 4-byte aligned on 32-bit platforms, and 8-byte aligned on 64-bit platforms. For more information, see Remarks.</p>
</dd>
</dl>

## -returns
<p>None.</p>

## -remarks
<p>This routine is called by the driver that owns an object that resides in shared memory and is that accessed by other drivers.</p>

<p><b>ExInitializeRundownProtection</b> must be called to initialize an <b>EX_RUNDOWN_REF</b> structure before it is passed as a parameter to any other run-down protection routine.</p>

<p>The run-down protection routines use the <b>EX_RUNDOWN_REF</b> structure to track the run-down status of a shared object that is associated with the structure. This status information includes a count of instances of run-down protection that are currently in effect on the object. <b>ExInitializeRundownProtection</b> initializes this count to zero.</p>

<p>After an <b>EX_RUNDOWN_REF</b> structure is initialized, other drivers that access the associated object can call the <a href="https://msdn.microsoft.com/library/windows/hardware/jj569371">ExAcquireRundownProtection</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/jj569375">ExReleaseRundownProtection</a> routines to acquire and release run-down protection on the object.</p>

<p>For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/jj569382">Run-Down Protection</a>.</p>

<p>This routine is called by the driver that owns an object that resides in shared memory and is that accessed by other drivers.</p>

<p><b>ExInitializeRundownProtection</b> must be called to initialize an <b>EX_RUNDOWN_REF</b> structure before it is passed as a parameter to any other run-down protection routine.</p>

<p>The run-down protection routines use the <b>EX_RUNDOWN_REF</b> structure to track the run-down status of a shared object that is associated with the structure. This status information includes a count of instances of run-down protection that are currently in effect on the object. <b>ExInitializeRundownProtection</b> initializes this count to zero.</p>

<p>After an <b>EX_RUNDOWN_REF</b> structure is initialized, other drivers that access the associated object can call the <a href="https://msdn.microsoft.com/library/windows/hardware/jj569371">ExAcquireRundownProtection</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/jj569375">ExReleaseRundownProtection</a> routines to acquire and release run-down protection on the object.</p>

<p>For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/jj569382">Run-Down Protection</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with Windows XP.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= APC_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/jj569375">ExReleaseRundownProtection</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/jj569371">ExAcquireRundownProtection</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/jj569379">EX_RUNDOWN_REF</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExInitializeRundownProtection routine%20 RELEASE:%20(11/20/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
