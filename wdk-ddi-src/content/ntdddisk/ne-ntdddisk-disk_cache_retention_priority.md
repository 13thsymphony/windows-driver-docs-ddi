---
UID: NE.ntdddisk.DISK_CACHE_RETENTION_PRIORITY
title: DISK_CACHE_RETENTION_PRIORITY
author: windows-driver-content
description: The DISK_CACHE_RETENTION_PRIORITY enumeration is used in conjunction with the IOCTL_DISK_GET_CACHE_INFORMATION request and the structure DISK_CACHE_INFORMATION to indicate which kinds data are to be held in the cache on a preferential basis.
old-location: storage\disk_cache_retention_priority.htm
old-project: storage
ms.assetid: 238d0b22-bd35-4e8d-9bb5-283af2bbb75b
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: DISK_CACHE_RETENTION_PRIORITY, DISK_CACHE_RETENTION_PRIORITY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DISK_CACHE_RETENTION_PRIORITY
req.alt-loc: ntdddisk.h
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
---

# DISK_CACHE_RETENTION_PRIORITY enumeration



## -description
The DISK_CACHE_RETENTION_PRIORITY enumeration is used in conjunction with the <a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_get_cache_information.md">IOCTL_DISK_GET_CACHE_INFORMATION</a> request and the structure <a href="storage.disk_cache_information">DISK_CACHE_INFORMATION</a> to indicate which kinds data are to be held in the cache on a preferential basis. 


## -syntax

````
typedef enum  { 
  EqualPriority       = 0,
  KeepPrefetchedData  = 1,
  KeepReadData        = 2
} DISK_CACHE_RETENTION_PRIORITY;
````


## -enum-fields

### -field EqualPriority

Indicates that no data is held in the cache on a preferential basis. All types of data have equal access to cache memory. 

### -field KeepPrefetchedData

Indicates that a preference is to be given to prefetched data. 

### -field KeepReadData

Indicates that a preference is to be given to data cached from a READ operation.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntdddisk.h (include Ntdddisk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.disk_cache_information">DISK_CACHE_INFORMATION</a>
</dt>
<dt>
<a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_get_cache_information.md">IOCTL_DISK_GET_CACHE_INFORMATION</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DISK_CACHE_RETENTION_PRIORITY enumeration%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
