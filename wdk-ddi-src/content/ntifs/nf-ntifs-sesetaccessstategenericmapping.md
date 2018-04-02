---
UID: NF:ntifs.SeSetAccessStateGenericMapping
title: SeSetAccessStateGenericMapping function
author: windows-driver-content
description: The SeSetAccessStateGenericMapping routine sets the generic mapping field of an ACCESS_STATE structure.
old-location: ifsk\sesetaccessstategenericmapping.htm
old-project: ifsk
ms.assetid: b9a5ca5c-2d1c-4974-bef8-6003a4d6e864
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: SeSetAccessStateGenericMapping, SeSetAccessStateGenericMapping routine [Installable File System Drivers], ifsk.sesetaccessstategenericmapping, ntifs/SeSetAccessStateGenericMapping, seref_41bfccdf-c133-4587-9d9e-a328eedbd28b.xml
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
-	SeSetAccessStateGenericMapping
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# SeSetAccessStateGenericMapping function
The <b>SeSetAccessStateGenericMapping</b> routine sets the generic mapping field of an ACCESS_STATE structure.

## Syntax

```
void SeSetAccessStateGenericMapping(
  PACCESS_STATE    AccessState,
  PGENERIC_MAPPING GenericMapping
);
```

## Parameters

`AccessState`

Pointer to the ACCESS_STATE structure to be modified.

`GenericMapping`

Pointer to a GENERIC<b>_</b>MAPPING structure to be copied into the ACCESS_STATE structure specified by <i>AccessState</i>.


## Return Value

None

## Remarks

<b>SeSetAccessStateGenericMapping</b> sets the <b>GenericMapping</b> field in the <b>AuxData</b> member of an ACCESS_STATE structure. If this field is not set when the ACCESS_STATE structure is created, <b>SeSetAccessStateGenericMapping</b> must be called to set this field before the structure is used to perform access validation.

The generic mapping structure defines the mapping of generic access rights to specific and standard access rights for an object. When a client requests generic access rights to an object, the desired access mask is mapped to one of the access masks defined in this structure.

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff538840">ACCESS_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546526">GENERIC_MAPPING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554762">SeAppendPrivileges</a>