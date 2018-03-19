---
UID: NF:ntifs.CcUnpinDataForThread
title: CcUnpinDataForThread function
author: windows-driver-content
description: The CcUnpinDataForThread routine releases pages of a cached file whose buffer control block (BCB) was modified by an earlier call to CcSetBcbOwnerPointer.
old-location: ifsk\ccunpindataforthread.htm
old-project: ifsk
ms.assetid: 9c29689c-ce5e-4b29-a17b-32d96f8f87e7
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: CcUnpinDataForThread, CcUnpinDataForThread routine [Installable File System Drivers], ccref_71102887-ef3b-44b1-8b1f-e2b07dea3392.xml, ifsk.ccunpindataforthread, ntifs/CcUnpinDataForThread
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	CcUnpinDataForThread
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# CcUnpinDataForThread function
The <b>CcUnpinDataForThread</b> routine releases pages of a cached file whose buffer control block (BCB) was modified by an earlier call to <a href="..\ntifs\nf-ntifs-ccsetbcbownerpointer.md">CcSetBcbOwnerPointer</a>.

## Syntax

````
VOID CcUnpinDataForThread(
  _In_ PVOID            Bcb,
  _In_ ERESOURCE_THREAD ResourceThreadId
);
````

## Parameters

`Bcb`

Pointer to the BCB for the pages to be released.

`ResourceThreadId`

Identifies the thread that originally acquired the BCB. Must match the owner pointer used in the call to <a href="..\ntifs\nf-ntifs-ccsetbcbownerpointer.md">CcSetBcbOwnerPointer</a>.


## Return Value

None

## Remarks

<b>CcUnpinDataForThread</b> releases the BCB for the indicated thread and performs any other necessary cleanup.

Each call to <a href="..\ntifs\nf-ntifs-ccsetbcbownerpointer.md">CcSetBcbOwnerPointer</a> must be matched by a subsequent call to <b>CcUnpinDataForThread</b>.

<b>CcUnpinDataForThread</b> is functionally equivalent to <a href="..\ntifs\nf-ntifs-ccunpindata.md">CcUnpinData</a>, except that it also releases the BCB resource for the indicated thread.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\ntifs\nf-ntifs-ccunpindata.md">CcUnpinData</a>



<a href="..\ntifs\nf-ntifs-ccsetbcbownerpointer.md">CcSetBcbOwnerPointer</a>