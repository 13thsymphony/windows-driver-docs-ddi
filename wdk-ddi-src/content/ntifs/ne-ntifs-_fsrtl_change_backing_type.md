---
UID: NE:ntifs._FSRTL_CHANGE_BACKING_TYPE
title: "_FSRTL_CHANGE_BACKING_TYPE"
author: windows-driver-content
description: The FSRTL_CHANGE_BACKING_TYPE enumeration specifies the type of cache or control area that a file object designates.
old-location: ifsk\fsrtl_change_backing_type.htm
old-project: ifsk
ms.assetid: 952812f4-5d29-4d1d-ab81-dd3a76a5f04c
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PFSRTL_CHANGE_BACKING_TYPE, ChangeDataControlArea, ChangeImageControlArea, ChangeSharedCacheMap, FSRTL_CHANGE_BACKING_TYPE, FSRTL_CHANGE_BACKING_TYPE enumeration [Installable File System Drivers], PFSRTL_CHANGE_BACKING_TYPE, PFSRTL_CHANGE_BACKING_TYPE enumeration pointer [Installable File System Drivers], _FSRTL_CHANGE_BACKING_TYPE, contextstructures_f0bf2082-c88d-4f01-8e40-f7259e040ea6.xml, ifsk.fsrtl_change_backing_type, ntifs/ChangeDataControlArea, ntifs/ChangeImageControlArea, ntifs/ChangeSharedCacheMap, ntifs/FSRTL_CHANGE_BACKING_TYPE, ntifs/PFSRTL_CHANGE_BACKING_TYPE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntifs.h
req.include-header: Ntifs.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntifs.h
api_name:
-	FSRTL_CHANGE_BACKING_TYPE
product: Windows
targetos: Windows
req.typenames: FSRTL_CHANGE_BACKING_TYPE, *PFSRTL_CHANGE_BACKING_TYPE
---

# _FSRTL_CHANGE_BACKING_TYPE Enumeration
The FSRTL_CHANGE_BACKING_TYPE enumeration specifies the type of cache or control area that a file object designates.

## Syntax
```
typedef enum _FSRTL_CHANGE_BACKING_TYPE {
  ChangeDataControlArea   ,
  ChangeImageControlArea  ,
  ChangeSharedCacheMap
} *PFSRTL_CHANGE_BACKING_TYPE, FSRTL_CHANGE_BACKING_TYPE;
```

## Constants

<table>
            
                <tr>
                    <td>ChangeDataControlArea</td>
                    <td>The data control area of the memory manager.</td>
                </tr>
            
                <tr>
                    <td>ChangeImageControlArea</td>
                    <td>An image control area that belongs to the memory manager.</td>
                </tr>
            
                <tr>
                    <td>ChangeSharedCacheMap</td>
                    <td>The shared cache map of the cache manager.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntifs.h (include Ntifs.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545749">FsRtlChangeBackingFileObject</a>