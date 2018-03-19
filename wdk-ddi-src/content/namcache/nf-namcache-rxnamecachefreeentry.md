---
UID: NF:namcache.RxNameCacheFreeEntry
title: RxNameCacheFreeEntry function
author: windows-driver-content
description: RxNameCacheFreeEntry releases the storage for a NAME_CACHE entry and decrements the count of the NAME_CACHE cache entries associated with a NAME_CACHE_CONTROL structure.
old-location: ifsk\rxnamecachefreeentry.htm
old-project: ifsk
ms.assetid: c1adef80-b8f2-49bb-9254-b89c8d1af220
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RxNameCacheFreeEntry, RxNameCacheFreeEntry function [Installable File System Drivers], ifsk.rxnamecachefreeentry, namcache/RxNameCacheFreeEntry, rxref_ca0b7c99-59df-4a51-b28b-4c369b451741.xml
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	namcache.h
api_name:
-	RxNameCacheFreeEntry
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---


# RxNameCacheFreeEntry function
<b>RxNameCacheFreeEntry</b> releases the storage for a NAME_CACHE entry and decrements the count of the NAME_CACHE cache entries associated with a NAME_CACHE_CONTROL structure.

## Syntax

````
VOID RxNameCacheFreeEntry(
  _In_ PNAME_CACHE_CONTROL NameCacheCtl,
  _In_ PNAME_CACHE         NameCache
);
````

## Parameters

`NameCacheCtl`

A pointer to the NAME_CACHE_CONTROL structure for the name cache.

`NameCache`

A pointer to the NAME_CACHE structure to free.


## Return Value

None

## Remarks

The <b>RxNameCacheFreeEntry</b> routine assumes that the name cache entry is not on either the free or active list.

The <b>RxNameCacheFreeEntry</b> routine frees memory allocated for the name buffer if the name buffer for this name cache entry is not <b>NULL</b>. This routine will then free memory used for the NAME_CACHE entry. Then, the count of name cache entries on <i>NameCacheCtl</i> is decremented.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | namcache.h (include Namcache.h) |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\namcache\nf-namcache-rxnamecachefetchentry.md">RxNameCacheFetchEntry</a>



<a href="..\namcache\nf-namcache-rxnamecacheexpireentrywithshortname.md">RxNameCacheExpireEntryWithShortName</a>



<a href="..\namcache\nf-namcache-rxnamecachecreateentry.md">RxNameCacheCreateEntry</a>



<a href="..\namcache\nf-namcache-rxnamecacheinitialize.md">RxNameCacheInitialize</a>



<a href="..\namcache\nf-namcache-rxnamecacheexpireentry.md">RxNameCacheExpireEntry</a>



<a href="..\namcache\nf-namcache-rxnamecachecheckentry.md">RxNameCacheCheckEntry</a>



<a href="..\namcache\nf-namcache-rxnamecacheactivateentry.md">RxNameCacheActivateEntry</a>



<a href="..\namcache\nf-namcache-rxnamecachefinalize.md">RxNameCacheFinalize</a>