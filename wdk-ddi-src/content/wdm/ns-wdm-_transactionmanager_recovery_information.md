---
UID: NS.WDM._TRANSACTIONMANAGER_RECOVERY_INFORMATION
title: _TRANSACTIONMANAGER_RECOVERY_INFORMATION
author: windows-driver-content
description: The TRANSACTIONMANAGER_RECOVERY_INFORMATION structure contains information about a transaction manager object.
old-location: kernel\transactionmanager_recovery_information.htm
old-project: kernel
ms.assetid: 76701df3-8e7d-43fa-8caf-6cbf89504aad
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _TRANSACTIONMANAGER_RECOVERY_INFORMATION, TRANSACTIONMANAGER_RECOVERY_INFORMATION, *PTRANSACTIONMANAGER_RECOVERY_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later operating system versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: TRANSACTIONMANAGER_RECOVERY_INFORMATION
req.alt-loc: wdm.h
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
req.product: Windows 10 or later.
---

# _TRANSACTIONMANAGER_RECOVERY_INFORMATION structure



## -description
The TRANSACTIONMANAGER_RECOVERY_INFORMATION structure contains information about a <a href="https://msdn.microsoft.com/af53cda4-e2ab-47df-9311-a4da2a2ee08d">transaction manager object</a>.


## -syntax

````
typedef struct _TRANSACTIONMANAGER_RECOVERY_INFORMATION {
  ULONGLONG LastRecoveredLsn;
} TRANSACTIONMANAGER_RECOVERY_INFORMATION, *PTRANSACTIONMANAGER_RECOVERY_INFORMATION;
````


## -struct-fields

### -field LastRecoveredLsn

The last <a href="https://msdn.microsoft.com/4637fa0c-2f19-4f0c-bf13-f4ccac2e7284">log sequence number</a> of the last log record that KTM obtained from <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">CLFS</a> during the most recent recovery operation.

## -remarks
The TRANSACTIONMANAGER_RECOVERY_INFORMATION structure is used with the <a href="kernel.zwqueryinformationtransactionmanager">ZwQueryInformationTransactionManager</a> routine.

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
<dt>Wdm.h (include Wdm.h or Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.transactionmanager_information_class">TRANSACTIONMANAGER_INFORMATION_CLASS</a>
</dt>
<dt>
<a href="kernel.zwqueryinformationtransactionmanager">ZwQueryInformationTransactionManager</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20TRANSACTIONMANAGER_RECOVERY_INFORMATION structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
