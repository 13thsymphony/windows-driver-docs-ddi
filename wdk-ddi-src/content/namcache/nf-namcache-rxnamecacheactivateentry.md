---
UID: NF:namcache.RxNameCacheActivateEntry
title: RxNameCacheActivateEntry function
author: windows-driver-content
description: RxNameCacheActivateEntry takes a name cache entry and updates the expiration time and the network mini-redirector context. It then puts the name cache entry on the active list.
old-location: ifsk\rxnamecacheactivateentry.htm
old-project: ifsk
ms.assetid: 6ebd4b00-ec25-4383-beba-0478b3241f09
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RxNameCacheActivateEntry, RxNameCacheActivateEntry function [Installable File System Drivers], ifsk.rxnamecacheactivateentry, namcache/RxNameCacheActivateEntry, rxref_f8bd601f-32b7-4164-beb5-c020f3670fe7.xml
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
-	RxNameCacheActivateEntry
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---


# RxNameCacheActivateEntry function
<b>RxNameCacheActivateEntry</b> takes a name cache entry and updates the expiration time and the network mini-redirector context. It then puts the name cache entry on the active list.

## Syntax

````
VOID RxNameCacheActivateEntry(
  _In_ PNAME_CACHE_CONTROL NameCacheCtl,
  _In_ PNAME_CACHE         NameCache,
  _In_ ULONG               LifeTime,
  _In_ ULONG               MRxContext
);
````

## Parameters

`NameCacheCtl`

A pointer to the NAME_CACHE_CONTROL structure on which to activate the entry.

`NameCache`

A pointer to the NAME_CACHE structure to activate.

`LifeTime`

A value that indicates the valid lifetime in seconds of the cache entry. A value of 0 means to leave the current value unchanged. A value of 0 is used for reactivations after a match where you want the original lifetime preserved.

`MRxContext`

A value of context supplied by the network mini-redirector for equality checking when making a valid entry check. An <i>MRxContext</i> value of 0 means to leave the current value unchanged. A value of 0 is used for reactivations after a match where you want the original <i>MRxContext</i> preserved.


## Return Value

None

## Remarks

The <b>RxNameCacheActivateEntry</b> routine is normally called after a network mini-redirector calls <b>RxNameCacheCreateEntry</b> to allocate and initialize a NAME_CACHE structure with the given name string. It is expected that the caller will then initialize any additional network mini-redirector elements of the name cache context, such as <i>Lifetime</i> (in seconds) and <i>MRxContext</i>, and then put the entry on the name cache active list by calling <b>RxNameCacheActivateEntry</b>.

The <b>RxNameCacheActivateEntry</b> routine assumes that the name cache entry is not on either the free or active list.

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



<a href="..\namcache\nf-namcache-rxnamecachefinalize.md">RxNameCacheFinalize</a>



<a href="..\namcache\nf-namcache-rxnamecachefreeentry.md">RxNameCacheFreeEntry</a>