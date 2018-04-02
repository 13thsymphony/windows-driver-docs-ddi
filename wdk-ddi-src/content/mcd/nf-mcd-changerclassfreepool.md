---
UID: NF:mcd.ChangerClassFreePool
title: ChangerClassFreePool function
author: windows-driver-content
description: The ChangerClassFreePool routine frees pool memory previously allocated using ChangerClassAllocatePool.
old-location: storage\changerclassfreepool.htm
old-project: storage
ms.assetid: c20c39f9-ceee-47f0-849a-f8686fb05e6a
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: ChangerClassFreePool, ChangerClassFreePool routine [Storage Devices], chgrclas_3f5fb8a4-3c85-4dde-80c9-f8e001b7b3bd.xml, mcd/ChangerClassFreePool, storage.changerclassfreepool
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: mcd.h
req.include-header: Mcd.h, Ntddchgr.h
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
req.lib: Mcd.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Mcd.lib
-	Mcd.dll
api_name:
-	ChangerClassFreePool
product:
- Windows
targetos: Windows
req.typenames: LAMP_INTENSITY_WHITE
---


# ChangerClassFreePool function
The <b>ChangerClassFreePool</b> routine frees pool memory previously allocated using <a href="https://msdn.microsoft.com/library/windows/hardware/ff551402">ChangerClassAllocatePool</a>.

## Syntax

```
void ChangerClassFreePool(
  PVOID PoolToFree
);
```

## Parameters

`PoolToFree`

Pointer to the block of memory to be freed.


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | mcd.h (include Mcd.h, Ntddchgr.h) |
| **Library** | Mcd.lib |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551402">ChangerClassAllocatePool</a>