---
UID : NF:wdm.TmGetTransactionId
title : TmGetTransactionId function
author : windows-driver-content
description : The TmGetTransactionId routine retrieves a transaction object's unit of work (UOW) identifier.
old-location : kernel\tmgettransactionid.htm
old-project : kernel
ms.assetid : 8ff4dd86-d828-4e1d-bde5-ab312187a8d7
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : ktm_ref_cbb12580-5399-4d81-ab6c-9d0235208681.xml, TmGetTransactionId routine [Kernel-Mode Driver Architecture], kernel.tmgettransactionid, TmGetTransactionId, wdm/TmGetTransactionId
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : Available in Windows Vista and later operating system versions.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : Any level
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# TmGetTransactionId function
The <b>TmGetTransactionId</b> routine retrieves a transaction object's <a href="https://msdn.microsoft.com/927a417b-35f5-49b8-85f3-7e6b1f5c0225">unit of work (UOW) identifier</a>.

## Syntax

````
VOID TmGetTransactionId(
  _In_  PKTRANSACTION Transaction,
  _Out_ PUOW          TransactionId
);
````

## Parameters

`Transaction`

A pointer to a <a href="https://msdn.microsoft.com/124105bd-70be-49b1-8ea4-af6ba1f3cf16">transaction object</a>. To obtain this pointer, your component must call <a href="..\wdm\nf-wdm-obreferenceobjectbyhandle.md">ObReferenceObjectByHandle</a> and supply the object handle that a previous call to <a href="..\wdm\nf-wdm-zwcreatetransaction.md">ZwCreateTransaction</a> or <a href="..\wdm\nf-wdm-zwopentransaction.md">ZwOpenTransaction</a> provided.

`TransactionId`

A pointer to a location that receives the transaction object's UOW identifier.


## Return Value

None

## Remarks

For information about when to use KTM's <b>Tm<i>Xxx</i></b> routines instead of <b>Zw<i>Xxx</i></b> routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565567">Using TmXxx Routines</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** |  |
| **IRQL** | Any level |
| **DDI compliance rules** |  |

## See Also

<a href="..\wdm\nf-wdm-zwopentransaction.md">ZwOpenTransaction</a>

<a href="..\wdm\nf-wdm-obreferenceobjectbyhandle.md">ObReferenceObjectByHandle</a>

<a href="..\wdm\nf-wdm-zwcreatetransaction.md">ZwCreateTransaction</a>

<a href="..\wdm\nf-wdm-zwqueryinformationtransaction.md">ZwQueryInformationTransaction</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20TmGetTransactionId routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>