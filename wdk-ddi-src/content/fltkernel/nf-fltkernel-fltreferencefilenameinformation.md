---
UID: NF:fltkernel.FltReferenceFileNameInformation
title: FltReferenceFileNameInformation function
author: windows-driver-content
description: FltReferenceFileNameInformation increments the reference count on a file name information structure.
old-location: ifsk\fltreferencefilenameinformation.htm
old-project: ifsk
ms.assetid: d2df37f3-78f7-4e44-9139-2c2e569bb48d
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FltApiRef_p_to_z_c6cfa7ad-ac72-45ad-9750-c466dd6ede6e.xml, FltReferenceFileNameInformation, FltReferenceFileNameInformation function [Installable File System Drivers], fltkernel/FltReferenceFileNameInformation, ifsk.fltreferencefilenameinformation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltReferenceFileNameInformation
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# FltReferenceFileNameInformation function
<b>FltReferenceFileNameInformation</b> increments the reference count on a file name information structure.

## Syntax

```
VOID FLTAPI FltReferenceFileNameInformation(
  PFLT_FILE_NAME_INFORMATION FileNameInformation
);
```

## Parameters

`FileNameInformation`

Pointer to the file name information (<a href="https://msdn.microsoft.com/library/windows/hardware/ff544633">FLT_FILE_NAME_INFORMATION</a>) structure. This parameter is required and cannot be <b>NULL</b>.


## Return Value

None

## Remarks

<b>FltReferenceFileNameInformation</b> increments the reference count on a file name information (<a href="https://msdn.microsoft.com/library/windows/hardware/ff544633">FLT_FILE_NAME_INFORMATION</a>) structure returned by a previous call to a file name query routine such as <a href="https://msdn.microsoft.com/library/windows/hardware/ff543032">FltGetFileNameInformation</a>. 

After a successful call to <b>FltReferenceFileNameInformation</b>, the caller is responsible for decrementing the reference count on the file name information structure by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff544320">FltReleaseFileNameInformation</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** | FltMgr.lib |
| **DLL** | Fltmgr.sys |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544633">FLT_FILE_NAME_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543003">FltGetDestinationFileNameInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543032">FltGetFileNameInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543035">FltGetFileNameInformationUnsafe</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543177">FltGetTunneledName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544320">FltReleaseFileNameInformation</a>