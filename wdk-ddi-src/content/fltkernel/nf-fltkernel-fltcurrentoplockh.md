---
UID: NF:fltkernel.FltCurrentOplockH
title: FltCurrentOplockH function
author: windows-driver-content
description: A minifilter driver calls the FltCurrentOplockH routine to determine whether there are any CACHE_HANDLE_LEVEL opportunistic locks (oplocks) on a file.
old-location: ifsk\fltcurrentoplockh.htm
old-project: ifsk
ms.assetid: ee066013-99fb-4a43-82f9-edbad7b5a8e9
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FltApiRef_a_to_d_0abdd89d-fe36-4546-a3bd-87d7d132f73e.xml, FltCurrentOplockH, FltCurrentOplockH routine [Installable File System Drivers], fltkernel/FltCurrentOplockH, ifsk.fltcurrentoplockh
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: The FltCurrentOplockH routine is available starting with Windows 7.
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
req.lib: FltMgr.lib
req.dll: 
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	FltMgr.lib
-	FltMgr.dll
api_name:
-	FltCurrentOplockH
product:
- Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# FltCurrentOplockH function
A minifilter driver calls the <b>FltCurrentOplockH</b> routine to determine whether there are any CACHE_HANDLE_LEVEL opportunistic locks (oplocks) on a file.

## Syntax

```
BOOLEAN FLTAPI FltCurrentOplockH(
  POPLOCK Oplock
);
```

## Parameters

`Oplock`

An opaque oplock pointer for the file. This pointer must have been initialized by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543289">FltInitializeOplock</a>.


## Return Value

<b>FltCurrentOplockH</b> returns <b>TRUE</b> if there are CACHE_HANDLE_LEVEL oplocks that are currently being held. Otherwise, it returns <b>FALSE</b>.

## Remarks

<b>FltCurrentOplockH</b> returns <b>FALSE</b> if no CACHE_HANDLE_LEVEL opportunistic locks are currently held.

For more information about opportunistic locks, see the Microsoft Windows SDK documentation.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | The FltCurrentOplockH routine is available starting with Windows 7.  |
| **Target Platform** | Universal |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** | FltMgr.lib |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543289">FltInitializeOplock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545837">FsRtlCurrentOplockH</a>