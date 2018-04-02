---
UID: NS:wdm._TRANSACTION_ENLISTMENT_PAIR
title: "_TRANSACTION_ENLISTMENT_PAIR"
author: windows-driver-content
description: The TRANSACTION_ENLISTMENT_PAIR structure contains information about an enlistment that is associated with a transaction object.
old-location: kernel\transaction_enlistment_pair.htm
old-project: kernel
ms.assetid: f8d49d61-f15e-4972-bcd2-d20f1be5786c
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PTRANSACTION_ENLISTMENT_PAIR, PTRANSACTION_ENLISTMENT_PAIR, PTRANSACTION_ENLISTMENT_PAIR structure pointer [Kernel-Mode Driver Architecture], TRANSACTION_ENLISTMENT_PAIR, TRANSACTION_ENLISTMENT_PAIR structure [Kernel-Mode Driver Architecture], _TRANSACTION_ENLISTMENT_PAIR, kernel.transaction_enlistment_pair, ktm_ref_5f4d1426-1829-4c3d-836f-8655b41d9c0c.xml, wdm/PTRANSACTION_ENLISTMENT_PAIR, wdm/TRANSACTION_ENLISTMENT_PAIR"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later operating system versions.
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	TRANSACTION_ENLISTMENT_PAIR
product: Windows
targetos: Windows
req.typenames: TRANSACTION_ENLISTMENT_PAIR, *PTRANSACTION_ENLISTMENT_PAIR
req.product: Windows 10 or later.
---

# _TRANSACTION_ENLISTMENT_PAIR structure
The <b>TRANSACTION_ENLISTMENT_PAIR</b> structure contains information about an enlistment that is associated with a <a href="https://msdn.microsoft.com/124105bd-70be-49b1-8ea4-af6ba1f3cf16">transaction object</a>.

## Syntax
```
typedef struct _TRANSACTION_ENLISTMENT_PAIR {
  GUID EnlistmentId;
  GUID ResourceManagerId;
} *PTRANSACTION_ENLISTMENT_PAIR, TRANSACTION_ENLISTMENT_PAIR;
```

## Members


`EnlistmentId`

A GUID that KTM has assigned to the enlistment.

`ResourceManagerId`

A GUID that KTM has assigned to the resource manager that created the enlistment.

## Remarks
The <b>TRANSACTION_ENLISTMENT_PAIR</b> structure is used as a member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564787">TRANSACTION_ENLISTMENTS_INFORMATION</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later operating system versions. Available in Windows Vista and later operating system versions. |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564787">TRANSACTION_ENLISTMENTS_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567057">ZwQueryInformationTransaction</a>