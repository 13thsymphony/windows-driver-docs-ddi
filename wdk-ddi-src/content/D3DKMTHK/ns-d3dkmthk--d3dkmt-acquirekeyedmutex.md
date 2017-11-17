---
UID: NS.d3dkmthk._D3DKMT_ACQUIREKEYEDMUTEX
title: D3DKMT_ACQUIREKEYEDMUTEX
author: windows-driver-content
description: The D3DKMT_ACQUIREKEYEDMUTEX structure describes a keyed mutex that the D3DKMTAcquireKeyedMutex function acquires.
old-location: display\d3dkmt_acquirekeyedmutex.htm
ms.assetid: de089f63-b2f4-4e8e-b653-15db3259a45e
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: display
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: D3DKMT_ACQUIREKEYEDMUTEX is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_ACQUIREKEYEDMUTEX
req.alt-loc: d3dkmthk.h
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
ms.keywords: D3DKMT_ACQUIREKEYEDMUTEX, D3DKMT_ACQUIREKEYEDMUTEX
req.iface: 
---

# D3DKMT_ACQUIREKEYEDMUTEX structure



## -description
<p>The D3DKMT_ACQUIREKEYEDMUTEX structure describes a keyed mutex that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546732">D3DKMTAcquireKeyedMutex</a> function acquires. </p>


## -syntax

````
typedef struct _D3DKMT_ACQUIREKEYEDMUTEX {
  D3DKMT_HANDLE  hKeyedMutex;
  UINT64         Key;
  PLARGE_INTEGER pTimeout;
  UINT64         FenceValue;
} D3DKMT_ACQUIREKEYEDMUTEX;
````


## -struct-fields
<dl>

### -field <b>hKeyedMutex</b>

<dd>
<p>[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the keyed mutex object to acquire. </p>
</dd>

### -field <b>Key</b>

<dd>
<p>[in] A 64-bit value that specifies the key value to acquire the mutex for. </p>
</dd>

### -field <b>pTimeout</b>

<dd>
<p>[in] A pointer to a time-out value that specifies the absolute or relative time, in 100-nanosecond units, at which acquiring the mutex is to be completed. </p>
<p>A positive value specifies an absolute time, relative to January 1, 1601. A negative value specifies an interval relative to the current time. Absolute expiration times track any changes in the system time; relative expiration times are not affected by system time changes. </p>
<p>If *<b>pTimeout</b> = 0, <a href="https://msdn.microsoft.com/library/windows/hardware/ff546732">D3DKMTAcquireKeyedMutex</a> returns without waiting. If the caller supplies a <b>NULL</b> pointer, <b>D3DKMTAcquireKeyedMutex</b> waits indefinitely until the mutex object is set to the signaled state. </p>
</dd>

### -field <b>FenceValue</b>

<dd>
<p>[out] A 64-bit value that specifies the current fence value of the GPU synchronization object. </p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>D3DKMT_ACQUIREKEYEDMUTEX is supported beginning with the Windows 7 operating system. </p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dkmthk.h (include D3dkmthk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546732">D3DKMTAcquireKeyedMutex</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_ACQUIREKEYEDMUTEX structure%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
