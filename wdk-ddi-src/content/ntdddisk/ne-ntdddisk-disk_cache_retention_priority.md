---
UID: NE:ntdddisk.DISK_CACHE_RETENTION_PRIORITY
title: DISK_CACHE_RETENTION_PRIORITY
author: windows-driver-content
description: The DISK_CACHE_RETENTION_PRIORITY enumeration is used in conjunction with the IOCTL_DISK_GET_CACHE_INFORMATION request and the structure DISK_CACHE_INFORMATION to indicate which kinds data are to be held in the cache on a preferential basis.
old-location: storage\disk_cache_retention_priority.htm
old-project: storage
ms.assetid: 238d0b22-bd35-4e8d-9bb5-283af2bbb75b
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DISK_CACHE_RETENTION_PRIORITY, DISK_CACHE_RETENTION_PRIORITY enumeration [Storage Devices], EqualPriority, KeepPrefetchedData, KeepReadData, ntdddisk/DISK_CACHE_RETENTION_PRIORITY, ntdddisk/EqualPriority, ntdddisk/KeepPrefetchedData, ntdddisk/KeepReadData, storage.disk_cache_retention_priority, structs-disk_19939b68-659e-4546-8419-7e1e141b8291.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntdddisk.h
api_name:
-	DISK_CACHE_RETENTION_PRIORITY
product:
- Windows
targetos: Windows
req.typenames: DISK_CACHE_RETENTION_PRIORITY
---

# DISK_CACHE_RETENTION_PRIORITY Enumeration
The DISK_CACHE_RETENTION_PRIORITY enumeration is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559451">IOCTL_DISK_GET_CACHE_INFORMATION</a> request and the structure <a href="https://msdn.microsoft.com/library/windows/hardware/ff552580">DISK_CACHE_INFORMATION</a> to indicate which kinds data are to be held in the cache on a preferential basis.

## Syntax
```
typedef enum DISK_CACHE_RETENTION_PRIORITY {
  EqualPriority       ,
  KeepPrefetchedData  ,
  KeepReadData
} ;
```

## Constants

<table>
            
                <tr>
                    <td>EqualPriority</td>
                    <td>Indicates that no data is held in the cache on a preferential basis. All types of data have equal access to cache memory.</td>
                </tr>
            
                <tr>
                    <td>KeepPrefetchedData</td>
                    <td>Indicates that a preference is to be given to prefetched data.</td>
                </tr>
            
                <tr>
                    <td>KeepReadData</td>
                    <td>Indicates that a preference is to be given to data cached from a READ operation.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntdddisk.h (include Ntdddisk.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552580">DISK_CACHE_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559451">IOCTL_DISK_GET_CACHE_INFORMATION</a>