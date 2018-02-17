---
UID: NE:wdm._TRANSACTIONMANAGER_INFORMATION_CLASS
title: "_TRANSACTIONMANAGER_INFORMATION_CLASS"
author: windows-driver-content
description: The TRANSACTIONMANAGER_INFORMATION_CLASS enumeration specifies the type of information that the ZwQueryInformationTransactionManager routine can retrieve for a transaction manager object.
old-location: kernel\transactionmanager_information_class.htm
old-project: kernel
ms.assetid: 71d6db29-0a93-4793-92f4-3e85615e1b61
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/TRANSACTIONMANAGER_INFORMATION_CLASS, TransactionManagerLogPathInformation, wdm/TransactionManagerLogInformation, TRANSACTIONMANAGER_INFORMATION_CLASS enumeration [Kernel-Mode Driver Architecture], wdm/TransactionManagerLogPathInformation, TransactionManagerLogInformation, TransactionManagerBasicInformation, _TRANSACTIONMANAGER_INFORMATION_CLASS, kernel.transactionmanager_information_class, wdm/TransactionManagerRecoveryInformation, ktm_ref_55fd8dd4-e88d-40df-9091-1aecc4de38a7.xml, wdm/TransactionManagerBasicInformation, TRANSACTIONMANAGER_INFORMATION_CLASS, TransactionManagerRecoveryInformation
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	TRANSACTIONMANAGER_INFORMATION_CLASS
product: Windows
targetos: Windows
req.typenames: TRANSACTIONMANAGER_INFORMATION_CLASS
req.product: Windows 10 or later.
---

# _TRANSACTIONMANAGER_INFORMATION_CLASS Enumeration
The <b>TRANSACTIONMANAGER_INFORMATION_CLASS</b> enumeration specifies the type of information that the <a href="..\wdm\nf-wdm-zwqueryinformationtransactionmanager.md">ZwQueryInformationTransactionManager</a> routine can retrieve for a <a href="https://msdn.microsoft.com/af53cda4-e2ab-47df-9311-a4da2a2ee08d">transaction manager object</a>.

## Syntax
````
typedef enum _TRANSACTIONMANAGER_INFORMATION_CLASS { 
  TransactionManagerBasicInformation     = 0,
  TransactionManagerLogInformation       = 1,
  TransactionManagerLogPathInformation   = 2,
  TransactionManagerRecoveryInformation  = 4
} TRANSACTIONMANAGER_INFORMATION_CLASS;
````

## Constants

<table>
            
                <tr>
                    <td>TransactionManagerBasicInformation</td>
                    <td>Information about a transaction manager object is stored in a <a href="..\wdm\ns-wdm-_transactionmanager_basic_information.md">TRANSACTIONMANAGER_BASIC_INFORMATION</a> structure.</td>
                </tr>
            
                <tr>
                    <td>TransactionManagerLogInformation</td>
                    <td>Information about a transaction manager object is stored in a <a href="..\wdm\ns-wdm-_transactionmanager_log_information.md">TRANSACTIONMANAGER_LOG_INFORMATION</a> structure.</td>
                </tr>
            
                <tr>
                    <td>TransactionManagerLogPathInformation</td>
                    <td>Information about a transaction manager object is stored in a <a href="..\wdm\ns-wdm-_transactionmanager_logpath_information.md">TRANSACTIONMANAGER_LOGPATH_INFORMATION</a> structure.</td>
                </tr>
            
                <tr>
                    <td>TransactionManagerRecoveryInformation</td>
                    <td>Information about a transaction manager object is stored in a <a href="..\wdm\ns-wdm-_transactionmanager_recovery_information.md">TRANSACTIONMANAGER_RECOVERY_INFORMATION</a> structure.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later operating system versions. Available in Windows Vista and later operating system versions. |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |

    ## See Also

        <a href="..\wdm\ns-wdm-_transactionmanager_basic_information.md">TRANSACTIONMANAGER_BASIC_INFORMATION</a>



<a href="..\wdm\ns-wdm-_transactionmanager_logpath_information.md">TRANSACTIONMANAGER_LOGPATH_INFORMATION</a>



<a href="..\wdm\nf-wdm-zwqueryinformationtransactionmanager.md">ZwQueryInformationTransactionManager</a>



<a href="..\wdm\ns-wdm-_transactionmanager_log_information.md">TRANSACTIONMANAGER_LOG_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20TRANSACTIONMANAGER_INFORMATION_CLASS enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>