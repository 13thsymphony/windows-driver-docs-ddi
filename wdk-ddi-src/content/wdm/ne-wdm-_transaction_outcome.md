---
UID: NE:wdm._TRANSACTION_OUTCOME
title: "_TRANSACTION_OUTCOME"
author: windows-driver-content
description: The TRANSACTION_OUTCOME enumeration defines the outcomes (results) that KTM can assign to a transaction.
old-location: kernel\transaction_outcome.htm
old-project: kernel
ms.assetid: 1612e8d8-996b-45d2-93cc-df5b388596d4
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: TRANSACTION_OUTCOME, TRANSACTION_OUTCOME enumeration [Kernel-Mode Driver Architecture], TransactionOutcomeAborted, TransactionOutcomeCommitted, TransactionOutcomeUndetermined, _TRANSACTION_OUTCOME, kernel.transaction_outcome, ktm_ref_e1c01db3-bc06-43d4-a046-f94af84782e8.xml, wdm/TRANSACTION_OUTCOME, wdm/TransactionOutcomeAborted, wdm/TransactionOutcomeCommitted, wdm/TransactionOutcomeUndetermined
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	TRANSACTION_OUTCOME
product: Windows
targetos: Windows
req.typenames: TRANSACTION_OUTCOME
req.product: Windows 10 or later.
---

# _TRANSACTION_OUTCOME Enumeration
The <b>TRANSACTION_OUTCOME</b> enumeration defines the outcomes (results) that KTM can assign to a transaction.

## Syntax
````
typedef enum _TRANSACTION_OUTCOME { 
  TransactionOutcomeUndetermined  = 1,
  TransactionOutcomeCommitted     = 2,
  TransactionOutcomeAborted       = 3
} TRANSACTION_OUTCOME;
````

## Constants

<table>
            
                <tr>
                    <td>TransactionOutcomeUndetermined</td>
                    <td>The transaction has not yet been committed or rolled back.</td>
                </tr>
            
                <tr>
                    <td>TransactionOutcomeCommitted</td>
                    <td>The transaction has been committed.</td>
                </tr>
            
                <tr>
                    <td>TransactionOutcomeAborted</td>
                    <td>The transaction has been rolled back.</td>
                </tr>
</table>

## Remarks

The <b>TRANSACTION_OUTCOME</b> enumeration is used in the <a href="..\wdm\ns-wdm-_transaction_basic_information.md">TRANSACTION_BASIC_INFORMATION</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later operating system versions. Available in Windows Vista and later operating system versions. |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |

## See Also

<a href="..\wdm\ns-wdm-_transaction_basic_information.md">TRANSACTION_BASIC_INFORMATION</a>