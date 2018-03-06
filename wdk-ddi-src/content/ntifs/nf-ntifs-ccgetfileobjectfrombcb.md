---
UID: NF:ntifs.CcGetFileObjectFromBcb
title: CcGetFileObjectFromBcb function
author: windows-driver-content
description: Given a pointer to a pinned buffer control block (BCB) for a file, the CcGetFileObjectFromBcb routine returns a pointer to the file object that the cache manager is using for that file.
old-location: ifsk\ccgetfileobjectfrombcb.htm
old-project: ifsk
ms.assetid: d30a2ee4-4736-4127-95db-b86e782c3577
ms.author: windowsdriverdev
ms.date: 2/16/2018
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

````
PFILE_OBJECT CcGetFileObjectFromBcb(
  _In_ PVOID Bcb
);
````

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

<a href="..\ntifs\nf-ntifs-ccpinread.md">CcPinRead</a>



<a href="..\ntifs\nf-ntifs-ccpinmappeddata.md">CcPinMappedData</a>



<a href="..\ntifs\nf-ntifs-ccpreparepinwrite.md">CcPreparePinWrite</a>



<a href="..\ntifs\nf-ntifs-ccmapdata.md">CcMapData</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcGetFileObjectFromBcb routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>