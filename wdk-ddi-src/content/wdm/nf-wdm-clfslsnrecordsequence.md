---
UID: NF:wdm.ClfsLsnRecordSequence
title: ClfsLsnRecordSequence function
author: windows-driver-content
description: The ClfsLsnRecordSequence routine returns the record sequence number contained in a specified LSN.
old-location: kernel\clfslsnrecordsequence.htm
old-project: kernel
ms.assetid: 407675de-4a06-49f7-9b43-c48b4c84ac7e
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: ClfsLsnRecordSequence, ClfsLsnRecordSequence routine [Kernel-Mode Driver Architecture], Clfs_a78f7923-d295-408c-9a52-16e5cc38ca31.xml, kernel.clfslsnrecordsequence, wdm/ClfsLsnRecordSequence
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.
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
req.lib: Clfs.lib
req.dll: Clfs.sys
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Clfs.sys
-	Ext-MS-Win-fs-clfs-l1-1-0.dll
api_name:
-	ClfsLsnRecordSequence
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# ClfsLsnRecordSequence function
The <b>ClfsLsnRecordSequence</b> routine returns the record sequence number contained in a specified LSN.

## Syntax

```
CLFSUSER_API ULONG ClfsLsnRecordSequence(
  const CLFS_LSN *plsn
);
```

## Parameters

`plsn`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541824">CLFS_LSN</a> structure from which the record sequence number is retrieved.


## Return Value

<b>ClfsLsnRecordSequence</b> returns the record sequence number contained in the LSN that is supplied by the caller.

## Remarks

For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.  |
| **Target Platform** | Desktop |
| **Header** | wdm.h (include Wdm.h) |
| **Library** | Clfs.lib |
| **DLL** | Clfs.sys |
| **IRQL** | Any level |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541569">ClfsLsnBlockOffset</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541573">ClfsLsnContainer</a>