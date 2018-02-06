---
UID: NF:ntifs.CcIsThereDirtyDataEx
title: CcIsThereDirtyDataEx function
author: windows-driver-content
description: The CcIsThereDirtyDataEx routine determines whether a volume contains any files that have dirty data in the system cache.
old-location: ifsk\ccistheredirtydataex.htm
old-project: ifsk
ms.assetid: 88378f82-2975-4b53-9dde-53ab81df3c53
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ntifs/CcIsThereDirtyDataEx, ifsk.ccistheredirtydataex, CcIsThereDirtyDataEx routine [Installable File System Drivers], CcIsThereDirtyDataEx, ccref_13ae1f3e-b2ea-4bc6-a1cb-0101afd58d04.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	CcIsThereDirtyDataEx
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# CcIsThereDirtyDataEx function
The <b>CcIsThereDirtyDataEx</b> routine determines whether a volume contains any files that have dirty data in the system cache.

## Syntax

````
BOOLEAN CcIsThereDirtyDataEx(
  _In_     PVPB   Vpb,
  _In_opt_ PULONG NumberOfDirtyPages
);
````

## Parameters

`Vpb`

A pointer to a volume parameter block (VPB) for the volume.

`NumberOfDirtyPages`

An optional pointer to an unsigned long buffer that receives the number of dirty pages on the volume (associated with the Vpb parameter).


## Return Value

The <b>CcIsThereDirtyDataEx</b> routine returns <b>TRUE</b> if the volume contains one or more cached files whose data has been modified in the cache, but not yet flushed to disk. Otherwise, this routine returns <b>FALSE</b>.

## Remarks

This routine will return <b>TRUE</b> if any dirty pages exist including temporary files (<a href="..\ntifs\nf-ntifs-ccistheredirtydata.md">CcIsThereDirtyData</a> ignores temporary files).  It will also return <b>TRUE</b> if there is any data currently queued to the volume.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of Windows. Available in Windows Vista and later versions of Windows. |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h, FltKernel.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\ntifs\nf-ntifs-ccistheredirtydata.md">CcIsThereDirtyData</a>

<a href="..\ntifs\nf-ntifs-ccpurgecachesection.md">CcPurgeCacheSection</a>

<a href="..\ntifs\nf-ntifs-ccflushcache.md">CcFlushCache</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcIsThereDirtyDataEx routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>