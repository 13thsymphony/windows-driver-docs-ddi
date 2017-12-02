---
UID: NF.wdm.ExNotifyCallback
title: ExNotifyCallback
author: windows-driver-content
description: The ExNotifyCallback routine causes all callback routines registered for the given object to be called.
old-location: kernel\exnotifycallback.htm
old-project: kernel
ms.assetid: 5c126639-494d-45b4-81c2-1af6dc773db6
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: ExNotifyCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ExNotifyCallback
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
req.irql: <= DISPATCH_LEVEL (see Remarks section)
req.iface: 
req.product: Windows 10 or later.
---

# ExNotifyCallback function



## -description
<p>The <b>ExNotifyCallback</b> routine causes all callback routines registered for the given object to be called.</p>


## -syntax

````
VOID ExNotifyCallback(
  _In_     PVOID CallbackObject,
  _In_opt_ PVOID Argument1,
  _In_opt_ PVOID Argument2
);
````


## -parameters
<dl>

### -param CallbackObject [in]

<dd>
<p>A pointer to the callback object for which all registered callback routines will be called.</p>
</dd>

### -param Argument1 [in, optional]

<dd>
<p>Specifies the parameter that is passed as <i>Argument1</i> of the callback routine.</p>
</dd>

### -param Argument2 [in, optional]

<dd>
<p>Specifies the parameter that is passed as <i>Argument2</i> of the callback routine. </p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>Driver writers <u>must not</u> call <b>ExNotifyCallback</b> for any of the system-defined callback objects listed in <b>ExCreateCallback</b>.</p>

<p>The system calls callback routines in order of their registration.</p>

<p>For more information about callback objects, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540718">Callback Objects</a>.</p>

<p>Callers of this routine must be running at IRQL &lt;= DISPATCH_LEVEL. The system calls all registered callback routines at the caller's IRQL.</p>

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
<p>Available starting with Windows 2000.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
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
<p>&lt;= DISPATCH_LEVEL (see Remarks section)</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-excreatecallback.md">ExCreateCallback</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-exregistercallback.md">ExRegisterCallback</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExNotifyCallback routine%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
