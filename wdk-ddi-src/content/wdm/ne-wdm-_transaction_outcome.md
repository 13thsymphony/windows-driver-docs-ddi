---
UID: NE.wdm._TRANSACTION_OUTCOME
title: _TRANSACTION_OUTCOME
author: windows-driver-content
description: The TRANSACTION_OUTCOME enumeration defines the outcomes (results) that KTM can assign to a transaction.
old-location: kernel\transaction_outcome.htm
old-project: kernel
ms.assetid: 1612e8d8-996b-45d2-93cc-df5b388596d4
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _TRANSACTION_OUTCOME, TRANSACTION_OUTCOME
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
req.alt-api: TRANSACTION_OUTCOME
req.alt-loc: Wdm.h
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
req.product: Windows 10 or later.
---

# _TRANSACTION_OUTCOME enumeration



## -description
The <b>TRANSACTION_OUTCOME</b> enumeration defines the outcomes (results) that KTM can assign to a transaction.


## -syntax

````
typedef enum _TRANSACTION_OUTCOME { 
  TransactionOutcomeUndetermined  = 1,
  TransactionOutcomeCommitted     = 2,
  TransactionOutcomeAborted       = 3
} TRANSACTION_OUTCOME;
````


## -enum-fields

### -field TransactionOutcomeUndetermined

The transaction has not yet been committed or rolled back.

### -field TransactionOutcomeCommitted

The transaction has been committed.

### -field TransactionOutcomeAborted

The transaction has been rolled back.

## -remarks
The <b>TRANSACTION_OUTCOME</b> enumeration is used in the <a href="kernel.transaction_basic_information">TRANSACTION_BASIC_INFORMATION</a> structure.

## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available in Windows Vista and later operating system versions.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.transaction_basic_information">TRANSACTION_BASIC_INFORMATION</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20TRANSACTION_OUTCOME enumeration%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
