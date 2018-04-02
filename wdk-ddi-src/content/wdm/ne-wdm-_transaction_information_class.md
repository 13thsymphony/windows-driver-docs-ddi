---
UID: NE:wdm._TRANSACTION_INFORMATION_CLASS
title: "_TRANSACTION_INFORMATION_CLASS"
author: windows-driver-content
description: The TRANSACTION_INFORMATION_CLASS enumeration specifies the type of information that ZwSetInformationTransaction can set and ZwQueryInformationTransaction can retrieve for a transaction manager object.
old-location: kernel\transaction_information_class.htm
old-project: kernel
ms.assetid: f3211114-8924-4e57-85a3-12471585652b
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: TRANSACTION_INFORMATION_CLASS, TRANSACTION_INFORMATION_CLASS enumeration [Kernel-Mode Driver Architecture], TransactionBasicInformation, TransactionEnlistmentInformation, TransactionPropertiesInformation, TransactionSuperiorEnlistmentInformation, _TRANSACTION_INFORMATION_CLASS, kernel.transaction_information_class, ktm_ref_b02f7265-fb29-402a-b0d3-79427735f354.xml, wdm/TRANSACTION_INFORMATION_CLASS, wdm/TransactionBasicInformation, wdm/TransactionEnlistmentInformation, wdm/TransactionPropertiesInformation, wdm/TransactionSuperiorEnlistmentInformation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
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
-	TRANSACTION_INFORMATION_CLASS
product: Windows
targetos: Windows
req.typenames: TRANSACTION_INFORMATION_CLASS
req.product: Windows 10 or later.
---

# _TRANSACTION_INFORMATION_CLASS Enumeration
The <b>TRANSACTION_INFORMATION_CLASS</b> enumeration specifies the type of information that <a href="https://msdn.microsoft.com/library/windows/hardware/ff567104">ZwSetInformationTransaction</a> can set and <a href="https://msdn.microsoft.com/library/windows/hardware/ff567057">ZwQueryInformationTransaction</a> can retrieve for a <a href="https://msdn.microsoft.com/af53cda4-e2ab-47df-9311-a4da2a2ee08d">transaction manager object</a>.

## Syntax
```
typedef enum _TRANSACTION_INFORMATION_CLASS {
  TransactionBasicInformation               ,
  TransactionPropertiesInformation          ,
  TransactionEnlistmentInformation          ,
  TransactionSuperiorEnlistmentInformation
} TRANSACTION_INFORMATION_CLASS;
```

## Constants

<table>
            
                <tr>
                    <td>TransactionBasicInformation</td>
                    <td>Information about a transaction manager object is stored in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564781">TRANSACTION_BASIC_INFORMATION</a> structure.</td>
                </tr>
            
                <tr>
                    <td>TransactionPropertiesInformation</td>
                    <td>Information about a transaction manager object is stored in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564844">TRANSACTION_PROPERTIES_INFORMATION</a> structure.</td>
                </tr>
            
                <tr>
                    <td>TransactionEnlistmentInformation</td>
                    <td>Information about a transaction manager object is stored in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564787">TRANSACTION_ENLISTMENTS_INFORMATION</a> structure.</td>
                </tr>
            
                <tr>
                    <td>TransactionSuperiorEnlistmentInformation</td>
                    <td>Information about a transaction manager object is stored in a <b>TRANSACTION_SUPERIOR_ENLISTMENT_INFORMATION</b> structure.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows Vista. Available starting with Windows Vista. |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567057">ZwQueryInformationTransaction</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567104">ZwSetInformationTransaction</a>