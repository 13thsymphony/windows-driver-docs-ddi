---
UID: NF.namcache.RxNameCacheCreateEntry
title: RxNameCacheCreateEntry function
author: windows-driver-content
description: RxNameCacheCreateEntry allocates and initializes a NAME_CACHE structure with the given name string.
old-location: ifsk\rxnamecachecreateentry.htm
old-project: ifsk
ms.assetid: 1cfe2d2d-99fa-4dc2-b517-5026fd72d5d4
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RxNameCacheCreateEntry
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
req.alt-api: RxNameCacheCreateEntry
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
---

# RxNameCacheCreateEntry function



## -description
<b>RxNameCacheCreateEntry</b> allocates and initializes a NAME_CACHE structure with the given name string. 


## -syntax

````
PNAME_CACHE RxNameCacheCreateEntry(
  _In_ PNAME_CACHE_CONTROL NameCacheCtl,
  _In_ PUNICODE_STRING     Name,
  _In_ BOOLEAN             CaseInsensitive
);
````


## -parameters

### -param NameCacheCtl [in]

A pointer to the NAME_CACHE_CONTROL structure from which to allocate the entry.

### -param Name [in]

A pointer to the Unicode name string with which to initialize the name cache entry.

### -param CaseInsensitive [in]

A Boolean value that indicates if case insensitive comparions should be used when comparing the <i>Name</i> parameter. 

## -returns
<b>RxNameCacheCreateEntry </b>returns a pointer to the newly allocated NAME_CACHE structure on success or a <b>NULL</b> pointer if the allocation fails.

## -remarks
A network mini-redirector calls <b>RxNameCacheCreateEntry</b> to allocate and initialize a NAME_CACHE structure with the given name string. It is expected that the caller will then initialize any additional network mini-redirector elements of the name cache context, set the lifetime (in seconds) and the <b>Context</b> member of the NAME_CACHE structure and then put the entry on the name cache active list by calling <b>RxNameCacheActivateEntry</b>.

<b>RxNameCacheCreateEntry</b> will first attempt to reuse a NAME_CACHE entry on the free list, if one is available, before allocating a new NAME_CACHE entry. 

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Namcache.h (include Namcache.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
&lt;= APC_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.rxnamecacheactivateentry">RxNameCacheActivateEntry</a>
</dt>
<dt>
<a href="ifsk.rxnamecachecheckentry">RxNameCacheCheckEntry</a>
</dt>
<dt>
<a href="ifsk.rxnamecacheexpireentry">RxNameCacheExpireEntry</a>
</dt>
<dt>
<a href="ifsk.rxnamecacheexpireentrywithshortname">RxNameCacheExpireEntryWithShortName</a>
</dt>
<dt>
<a href="ifsk.rxnamecachefetchentry">RxNameCacheFetchEntry</a>
</dt>
<dt>
<a href="ifsk.rxnamecachefinalize">RxNameCacheFinalize</a>
</dt>
<dt>
<a href="ifsk.rxnamecachefreeentry">RxNameCacheFreeEntry</a>
</dt>
<dt>
<a href="ifsk.rxnamecacheinitialize">RxNameCacheInitialize</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxNameCacheCreateEntry function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
