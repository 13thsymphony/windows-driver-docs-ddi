---
UID: NF:aux_klib.AuxKlibGetBugCheckData
title: AuxKlibGetBugCheckData function
author: windows-driver-content
description: The AuxKlibGetBugCheckData routine retrieves information about a bug check that has just occurred.
old-location: kernel\auxklibgetbugcheckdata.htm
old-project: kernel
ms.assetid: d41d0eba-14e3-48ff-874d-e52589cf716c
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: AuxKlibGetBugCheckData, AuxKlibGetBugCheckData routine [Kernel-Mode Driver Architecture], aux_klib/AuxKlibGetBugCheckData, aux_klib_3cb977df-feb6-4b52-afa1-b5e3038fc287.xml, kernel.auxklibgetbugcheckdata
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: aux_klib.h
req.include-header: Aux_klib.h
req.target-type: Universal
req.target-min-winverclnt: Supported starting with Windows 2000.
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
req.lib: Aux_Klib.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Aux_Klib.lib
-	Aux_Klib.dll
api_name:
-	AuxKlibGetBugCheckData
product: Windows
targetos: Windows
req.typenames: REPORT_ZONES_EXT_DATA, *PREPORT_ZONES_EXT_DATA
---


# AuxKlibGetBugCheckData function
The <b>AuxKlibGetBugCheckData</b> routine retrieves information about a bug check that has just occurred.

## Syntax

````
NTSTATUS AuxKlibGetBugCheckData(
  _Out_ PKBUGCHECK_DATA BugCheckData
);
````

## Parameters

`BugCheckData`

A pointer to a <a href="..\aux_klib\ns-aux_klib-_kbugcheck_data.md">KBUGCHECK_DATA</a> structure that contains information about the bug check. The <i>BugCheckData</i> size of this structure should be set equal to the size, in bytes, of the <b>KBUGCHECK_DATA</b> structure.


## Return Value

<b>AuxKlibGetBugCheckData</b> returns STATUS_SUCCESS if the operation succeeds. The routine returns STATUS_INFO_LENGTH_MISMATCH if the <b>KBUGCHECK_DATA</b> structure's size is incorrect.

## Remarks

The <b>AuxKlibGetBugCheckData</b> routine can be called only from a <a href="..\wdm\nc-wdm-kbugcheck_callback_routine.md">BugCheckCallback</a> routine.

Drivers must call <a href="..\aux_klib\nf-aux_klib-auxklibinitialize.md">AuxKlibInitialize</a> before calling <b>AuxKlibGetBugCheckData</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | aux_klib.h (include Aux_klib.h) |
| **Library** | Aux_Klib.lib |

## See Also

<a href="..\aux_klib\nf-aux_klib-auxklibinitialize.md">AuxKlibInitialize</a>



<a href="..\aux_klib\ns-aux_klib-_kbugcheck_data.md">KBUGCHECK_DATA</a>



<a href="..\wdm\nc-wdm-kbugcheck_callback_routine.md">BugCheckCallback</a>