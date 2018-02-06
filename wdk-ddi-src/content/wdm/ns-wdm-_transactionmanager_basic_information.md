---
UID: NS:wdm._TRANSACTIONMANAGER_BASIC_INFORMATION
title: "_TRANSACTIONMANAGER_BASIC_INFORMATION"
author: windows-driver-content
description: The TRANSACTIONMANAGER_BASIC_INFORMATION structure contains information about a transaction manager object.
old-location: kernel\transactionmanager_basic_information.htm
old-project: kernel
ms.assetid: bffa1bd2-143c-4d32-a886-0a2e82320dc8
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PTRANSACTIONMANAGER_BASIC_INFORMATION structure pointer [Kernel-Mode Driver Architecture], *PTRANSACTIONMANAGER_BASIC_INFORMATION, wdm/PTRANSACTIONMANAGER_BASIC_INFORMATION, PTRANSACTIONMANAGER_BASIC_INFORMATION, TRANSACTIONMANAGER_BASIC_INFORMATION structure [Kernel-Mode Driver Architecture], ktm_ref_0b404d6e-efa9-4f37-a14f-4e8fcdc2c6e5.xml, kernel.transactionmanager_basic_information, TRANSACTIONMANAGER_BASIC_INFORMATION, wdm/TRANSACTIONMANAGER_BASIC_INFORMATION, _TRANSACTIONMANAGER_BASIC_INFORMATION
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	TRANSACTIONMANAGER_BASIC_INFORMATION
product: Windows
targetos: Windows
req.typenames: "*PTRANSACTIONMANAGER_BASIC_INFORMATION, TRANSACTIONMANAGER_BASIC_INFORMATION"
req.product: Windows 10 or later.
---

# _TRANSACTIONMANAGER_BASIC_INFORMATION structure
The <b>TRANSACTIONMANAGER_BASIC_INFORMATION</b> structure contains information about a <a href="https://msdn.microsoft.com/af53cda4-e2ab-47df-9311-a4da2a2ee08d">transaction manager object</a>.

## Syntax
````
typedef struct _TRANSACTIONMANAGER_BASIC_INFORMATION {
  GUID          TmIdentity;
  LARGE_INTEGER VirtualClock;
} TRANSACTIONMANAGER_BASIC_INFORMATION, *PTRANSACTIONMANAGER_BASIC_INFORMATION;
````

## Members


`TmIdentity`

A GUID that KTM has assigned to a transaction manager object.

`VirtualClock`

The <a href="https://msdn.microsoft.com/de01b0f1-86b1-4e7d-af22-84dbbe3a3f83">virtual clock value</a> that is currently associated with a transaction manager object.

## Remarks
The <b>TRANSACTIONMANAGER_BASIC_INFORMATION</b> structure is used with the <a href="..\wdm\nf-wdm-zwqueryinformationtransactionmanager.md">ZwQueryInformationTransactionManager</a> routine.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later operating system versions. Available in Windows Vista and later operating system versions. |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |

## See Also

<a href="..\wdm\ne-wdm-_transactionmanager_information_class.md">TRANSACTIONMANAGER_INFORMATION_CLASS</a>

<a href="..\wdm\nf-wdm-zwqueryinformationtransactionmanager.md">ZwQueryInformationTransactionManager</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20TRANSACTIONMANAGER_BASIC_INFORMATION structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>