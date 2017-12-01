---
UID: NF.namcache.RxNameCacheFetchEntry
title: RxNameCacheFetchEntry
author: windows-driver-content
description: RxNameCacheFetchEntry looks for a match with a specified name string for a NAME_CACHE entry.
old-location: ifsk\rxnamecachefetchentry.htm
old-project: ifsk
ms.assetid: 1f4c50a8-2eee-46c6-8ca0-f5858d227922
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: RxNameCacheFetchEntry
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: namcache.h
req.include-header: Namcache.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RxNameCacheFetchEntry
req.alt-loc: namcache.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= APC_LEVEL
req.iface: 
---

# RxNameCacheFetchEntry function



## -description
<p><b>RxNameCacheFetchEntry</b> looks for a match with a specified name string for a NAME_CACHE entry.</p>


## -syntax

````
PNAME_CACHE RxNameCacheFetchEntry(
  _In_ PNAME_CACHE_CONTROL NameCacheCtl,
  _In_ PUNICODE_STRING     Name
);
````


## -parameters
<dl>

### -param <i>NameCacheCtl</i> [in]

<dd>
<p>A pointer to the NAME_CACHE_CONTROL structure to scan.</p>
</dd>

### -param <i>Name</i> [in]

<dd>
<p>A pointer to the Unicode string that contains the name to match.</p>
</dd>
</dl>

## -returns
<p><b>RxNameCacheFetchEntry </b>returns a pointer to the matching NAME_CACHE structure if a match was found, or <b>NULL</b> if the match failed. </p>

## -remarks
<p><b>RxNameCacheFetchEntry</b> looks for a match in the name cache active list for the specified <i>Name</i> parameter. If the name is found, the entry is removed from the name cache active list and a pointer to the NAME_CACHE structure is returned. Otherwise, <b>NULL</b> is returned.</p>

<p>The NAME_CACHE entry is removed from the active list to avoid possible problems with another thread that is trying to update the same entry, or observing that it expired and putting it on the free list. It is possible to get multiple entries with the same name by different threads, but eventually they will expire.</p>

<p>If a matching NAME_CACHE entry is found, no check is made for expiration. The caller must check for expiration because it might want to take some special action.</p>

<p>As a aside effect as the name cache active list is scanned, any non-matching entries that have expired are put on the free list. The name cache lock is acquired to protect this operation.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Namcache.h (include Namcache.h)</dt>
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
<a href="..\namcache\nf-namcache-rxnamecacheactivateentry.md">RxNameCacheActivateEntry</a>
</dt>
<dt>
<a href="..\namcache\nf-namcache-rxnamecachecheckentry.md">RxNameCacheCheckEntry</a>
</dt>
<dt>
<a href="..\namcache\nf-namcache-rxnamecachecreateentry.md">RxNameCacheCreateEntry</a>
</dt>
<dt>
<a href="..\namcache\nf-namcache-rxnamecacheexpireentry.md">RxNameCacheExpireEntry</a>
</dt>
<dt>
<a href="..\namcache\nf-namcache-rxnamecacheexpireentrywithshortname.md">RxNameCacheExpireEntryWithShortName</a>
</dt>
<dt>
<a href="..\namcache\nf-namcache-rxnamecachefinalize.md">RxNameCacheFinalize</a>
</dt>
<dt>
<a href="..\namcache\nf-namcache-rxnamecachefreeentry.md">RxNameCacheFreeEntry</a>
</dt>
<dt>
<a href="..\namcache\nf-namcache-rxnamecacheinitialize.md">RxNameCacheInitialize</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxNameCacheFetchEntry function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
