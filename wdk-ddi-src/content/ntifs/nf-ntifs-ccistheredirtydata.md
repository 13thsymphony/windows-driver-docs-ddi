---
UID: NF:ntifs.CcIsThereDirtyData
title: CcIsThereDirtyData function
author: windows-driver-content
description: The CcIsThereDirtyData routine determines whether a mounted volume contains any files that have dirty data in the system cache.
old-location: ifsk\ccistheredirtydata.htm
old-project: ifsk
ms.assetid: 592c7f8d-0a39-45af-a9b8-14ddd55e2835
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: CcIsThereDirtyData, CcIsThereDirtyData routine [Installable File System Drivers], ccref_86c4a327-a13e-49b3-89d1-abf976973000.xml, ifsk.ccistheredirtydata, ntifs/CcIsThereDirtyData
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	CcIsThereDirtyData
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# CcIsThereDirtyData function
The <b>CcIsThereDirtyData</b> routine determines whether a mounted volume contains any files that have dirty data in the system cache.

## Syntax

````
BOOLEAN CcIsThereDirtyData(
  _In_ PVPB Vpb
);
````

## Parameters

`Vpb`

Pointer to a volume parameter block (VPB) for the volume.


## Return Value

<b>CcIsThereDirtyData</b> returns <b>TRUE</b> if the volume contains one or more cached files whose data has been modified in the cache but not yet flushed to disk, <b>FALSE</b> otherwise.

## Remarks

<b>CcIsThereDirtyData</b> ignores temporary files.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |

## See Also

<a href="..\ntifs\nf-ntifs-ccpurgecachesection.md">CcPurgeCacheSection</a>



<a href="..\ntifs\nf-ntifs-ccflushcache.md">CcFlushCache</a>