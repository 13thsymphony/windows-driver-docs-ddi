---
UID: NS:wdm._TRANSACTIONMANAGER_LOG_INFORMATION
title: "_TRANSACTIONMANAGER_LOG_INFORMATION"
author: windows-driver-content
description: The TRANSACTIONMANAGER_LOG_INFORMATION structure contains information about a transaction manager object.
old-location: kernel\transactionmanager_log_information.htm
old-project: kernel
ms.assetid: 7d0da54d-54a2-4440-910f-d99716660506
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PTRANSACTIONMANAGER_LOG_INFORMATION, PTRANSACTIONMANAGER_LOG_INFORMATION, PTRANSACTIONMANAGER_LOG_INFORMATION structure pointer [Kernel-Mode Driver Architecture], TRANSACTIONMANAGER_LOG_INFORMATION, TRANSACTIONMANAGER_LOG_INFORMATION structure [Kernel-Mode Driver Architecture], _TRANSACTIONMANAGER_LOG_INFORMATION, kernel.transactionmanager_log_information, ktm_ref_3cdc0767-5078-43dc-8a25-3e90a4a1483a.xml, wdm/PTRANSACTIONMANAGER_LOG_INFORMATION, wdm/TRANSACTIONMANAGER_LOG_INFORMATION"
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
-	TRANSACTIONMANAGER_LOG_INFORMATION
product: Windows
targetos: Windows
req.typenames: TRANSACTIONMANAGER_LOG_INFORMATION, *PTRANSACTIONMANAGER_LOG_INFORMATION
req.product: Windows 10 or later.
---

# _TRANSACTIONMANAGER_LOG_INFORMATION structure
The <b>TRANSACTIONMANAGER_LOG_INFORMATION</b> structure contains information about a <a href="https://msdn.microsoft.com/af53cda4-e2ab-47df-9311-a4da2a2ee08d">transaction manager object</a>.

## Syntax
````
typedef struct _TRANSACTIONMANAGER_LOG_INFORMATION {
  GUID LogIdentity;
} TRANSACTIONMANAGER_LOG_INFORMATION, *PTRANSACTIONMANAGER_LOG_INFORMATION;
````

## Members


`LogIdentity`

A GUID that KTM uses to identify restart records in a transaction manager object's log stream. For more information about restart records, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff566409">Writing Restart Records to a CLFS Stream</a>.

## Remarks
The <b>TRANSACTIONMANAGER_LOG_INFORMATION</b> structure is used with the <a href="..\wdm\nf-wdm-zwqueryinformationtransactionmanager.md">ZwQueryInformationTransactionManager</a> routine.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later operating system versions. Available in Windows Vista and later operating system versions. |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |

## See Also

<a href="..\wdm\ne-wdm-_transactionmanager_information_class.md">TRANSACTIONMANAGER_INFORMATION_CLASS</a>



<a href="..\wdm\nf-wdm-zwqueryinformationtransactionmanager.md">ZwQueryInformationTransactionManager</a>