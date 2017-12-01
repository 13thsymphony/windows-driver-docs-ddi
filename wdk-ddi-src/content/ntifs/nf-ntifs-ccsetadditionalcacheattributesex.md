---
UID: NF.ntifs.CcSetAdditionalCacheAttributesEx
title: CcSetAdditionalCacheAttributesEx
author: windows-driver-content
description: Call the CcSetAdditionalCacheAttributesEx routine to enable extended cache behavior on a cached file.
old-location: ifsk\ccsetadditionalcacheattributesex.htm
old-project: ifsk
ms.assetid: 187719CD-5F0C-4AFD-BC00-ECD3C29A118F
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: CcSetAdditionalCacheAttributesEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CcSetAdditionalCacheAttributesEx
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
---

# CcSetAdditionalCacheAttributesEx function



## -description
<p>Call the <b>CcSetAdditionalCacheAttributesEx</b> routine to enable extended cache behavior on a cached file.</p>


## -syntax

````
VOID CcSetAdditionalCacheAttributesEx(
  _In_ PFILE_OBJECT FileObject,
  _In_ ULONG        Flags
);
````


## -parameters
<dl>

### -param <i>FileObject</i> [in]

<dd>
<p>Pointer to a file object for the cached file.</p>
</dd>

### -param <i>Flags</i> [in]

<dd>
<p>Behavior flags to set for <i>FileObject</i>. Currently, only the  <b>AGGRESSIVE_UNMAP_BEHIND</b> flag is available. Setting this flag will allow the cache manager to optimize memory usage when modified writes are disabled for a file object.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p><b>CcSetAdditionalCacheAttributesEx</b> can be called any time after calling <a href="..\ntifs\nf-ntifs-ccinitializecachemap.md">CcInitializeCacheMap</a>. </p>

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
<p>Available starting with Windows 8.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h)</dt>
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
<a href="..\ntifs\nf-ntifs-ccsetadditionalcacheattributes.md">CcSetAdditionalCacheAttributes</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-ccinitializecachemap.md">CcInitializeCacheMap</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcSetAdditionalCacheAttributesEx routine%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
