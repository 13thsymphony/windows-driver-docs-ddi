---
UID: NF:namcache.RxNameCacheExpireEntryWithShortName
title: RxNameCacheExpireEntryWithShortName function
author: windows-driver-content
description: RxNameCacheExpireEntryWithShortName expires all of the name cache entries whose name prefix matches the given short file name.
old-location: ifsk\rxnamecacheexpireentrywithshortname.htm
old-project: ifsk
ms.assetid: 4d842454-4a59-4f82-9aeb-3dfbe9d8cd8a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RxNameCacheExpireEntryWithShortName, RxNameCacheExpireEntryWithShortName function [Installable File System Drivers], ifsk.rxnamecacheexpireentrywithshortname, namcache/RxNameCacheExpireEntryWithShortName, rxref_fcde2e61-9855-4d66-8b81-a437921d5ec5.xml
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
-	RxNameCacheExpireEntryWithShortName
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---


# RxNameCacheExpireEntryWithShortName function
<b>RxNameCacheExpireEntryWithShortName</b> expires all of the name cache entries whose name prefix matches the given short file name.

## Syntax

````
VOID RxNameCacheExpireEntryWithShortName(
  _In_ PNAME_CACHE_CONTROL NameCacheCtl,
  _In_ PUNICODE_STRING     Name
);
````

## Parameters

`NameCacheCtl`

A pointer to the NAME_CACHE_CONTROL structure to scan.

`Name`

A pointer to the Unicode string that contains the name prefix to scan for name cache entry matches to expire.


## Return Value

None

## Remarks

The <b>RxNameCacheExpireEntryWithShortName</b> routine scans the active list and inserts any matching NAME_CACHE entries at the head of the free list. The <b>CaseInsensitive</b> member of the NAME_CACHE entry is used to determine whether the scan should ignore case sensitivity when matching the <i>Name</i> parameter.

Because the active list is scanned, the <b>RxNameCacheExpireEntryWithShortName</b> routine puts any non-matching entries that have expired on the free list. A <i>Name</i> value of zero length will match all entries and insert the entries on the free list.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | namcache.h (include Namcache.h) |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\namcache\nf-namcache-rxnamecachefetchentry.md">RxNameCacheFetchEntry</a>



<a href="..\namcache\nf-namcache-rxnamecachecreateentry.md">RxNameCacheCreateEntry</a>



<a href="..\namcache\nf-namcache-rxnamecacheinitialize.md">RxNameCacheInitialize</a>



<a href="..\namcache\nf-namcache-rxnamecacheexpireentry.md">RxNameCacheExpireEntry</a>



<a href="..\namcache\nf-namcache-rxnamecachecheckentry.md">RxNameCacheCheckEntry</a>



<a href="..\namcache\nf-namcache-rxnamecacheactivateentry.md">RxNameCacheActivateEntry</a>



<a href="..\namcache\nf-namcache-rxnamecachefinalize.md">RxNameCacheFinalize</a>



<a href="..\namcache\nf-namcache-rxnamecachefreeentry.md">RxNameCacheFreeEntry</a>