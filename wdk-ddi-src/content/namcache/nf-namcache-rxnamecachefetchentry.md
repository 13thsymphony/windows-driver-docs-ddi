---
UID : NF:namcache.RxNameCacheFetchEntry
title : RxNameCacheFetchEntry function
author : windows-driver-content
description : RxNameCacheFetchEntry looks for a match with a specified name string for a NAME_CACHE entry.
old-location : ifsk\rxnamecachefetchentry.htm
old-project : ifsk
ms.assetid : 1f4c50a8-2eee-46c6-8ca0-f5858d227922
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : RxNameCacheFetchEntry
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : namcache.h
req.include-header : Namcache.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : RxNameCacheFetchEntry
req.alt-loc : namcache.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : <= APC_LEVEL
req.typenames : VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---


# RxNameCacheFetchEntry function
<b>RxNameCacheFetchEntry</b> looks for a match with a specified name string for a NAME_CACHE entry.

## Syntax

````
PNAME_CACHE RxNameCacheFetchEntry(
  _In_ PNAME_CACHE_CONTROL NameCacheCtl,
  _In_ PUNICODE_STRING     Name
);
````

## Parameters

`NameCacheCtl`

A pointer to the NAME_CACHE_CONTROL structure to scan.

`Name`

A pointer to the Unicode string that contains the name to match.


## Return Value

<b>RxNameCacheFetchEntry </b>returns a pointer to the matching NAME_CACHE structure if a match was found, or <b>NULL</b> if the match failed.

## Remarks

<b>RxNameCacheFetchEntry</b> looks for a match in the name cache active list for the specified <i>Name</i> parameter. If the name is found, the entry is removed from the name cache active list and a pointer to the NAME_CACHE structure is returned. Otherwise, <b>NULL</b> is returned.

The NAME_CACHE entry is removed from the active list to avoid possible problems with another thread that is trying to update the same entry, or observing that it expired and putting it on the free list. It is possible to get multiple entries with the same name by different threads, but eventually they will expire.

If a matching NAME_CACHE entry is found, no check is made for expiration. The caller must check for expiration because it might want to take some special action.

As a aside effect as the name cache active list is scanned, any non-matching entries that have expired are put on the free list. The name cache lock is acquired to protect this operation.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | namcache.h (include Namcache.h) |
| **Library** |  |
| **IRQL** | <= APC_LEVEL |
| **DDI compliance rules** |  |

## See Also

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
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxNameCacheFetchEntry function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>