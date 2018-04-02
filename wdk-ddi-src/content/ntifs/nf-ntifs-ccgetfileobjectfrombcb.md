---
UID: NF:ntifs.CcGetFileObjectFromBcb
title: CcGetFileObjectFromBcb function
author: windows-driver-content
description: Given a pointer to a pinned buffer control block (BCB) for a file, the CcGetFileObjectFromBcb routine returns a pointer to the file object that the cache manager is using for that file.
old-location: ifsk\ccgetfileobjectfrombcb.htm
old-project: ifsk
ms.assetid: d30a2ee4-4736-4127-95db-b86e782c3577
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: CcGetFileObjectFromBcb, CcGetFileObjectFromBcb routine [Installable File System Drivers], ccref_7fdf1d1e-a080-4322-a09c-be0a16543050.xml, ifsk.ccgetfileobjectfrombcb, ntifs/CcGetFileObjectFromBcb
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
-	CcGetFileObjectFromBcb
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# CcGetFileObjectFromBcb function
Given a pointer to a pinned buffer control block (BCB) for a file, the <b>CcGetFileObjectFromBcb</b> routine returns a pointer to the file object that the cache manager is using for that file.

## Syntax

```
NTKERNELAPI PFILE_OBJECT CcGetFileObjectFromBcb(
  PVOID Bcb
);
```

## Parameters

`Bcb`

Pointer to the pinned BCB.


## Return Value

Pointer to the file object, or <b>NULL</b> if the file is not cached or is no longer cached.

## Remarks

The file object pointer is guaranteed to remain valid as long as the BCB exists.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539155">CcMapData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539176">CcPinMappedData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539180">CcPinRead</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539183">CcPreparePinWrite</a>