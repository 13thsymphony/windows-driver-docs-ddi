---
UID: NF:wdm.TmRenameTransactionManager
title: TmRenameTransactionManager function
author: windows-driver-content
description: The TmRenameTransactionManager routine changes the identity of the transaction manager object that is stored in the CLFS log file stream contained in the log file name.
old-location: kernel\tmrenametransactionmanager_.htm
old-project: kernel
ms.assetid: B4124FF4-50CC-474A-B42F-17BCF698AB59
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/TmRenameTransactionManager, TmRenameTransactionManager routine [Kernel-Mode Driver Architecture], kernel.tmrenametransactionmanager_, TmRenameTransactionManager
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: 
req.target-type: Universal
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Wdm.h
-	Ext-MS-Win-ntos-tm-l1-1-0.dll
-	tm.sys
apiname:
-	TmRenameTransactionManager
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# TmRenameTransactionManager function
The <b>TmRenameTransactionManager</b> routine changes the identity of the transaction manager object that is stored in the <a href="https://msdn.microsoft.com/4da3cb49-dc20-4713-813b-ff458c99ab90">CLFS</a> log file stream contained in the log file name.
<div class="alert"><b>Warning</b>  Changing the identity of the transaction manger object might break any cross-log transactional links that may exist.</div><div> </div>

## Syntax

````
NTSTATUS TmRenameTransactionManager (
  _In_ PUNICODE_STRING  LogFileName,
  _In_ LPGUID           ExistingTransactionManagerGuid
);
````

## Parameters

`LogFileName`

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains the path and file name of a <a href="https://msdn.microsoft.com/4da3cb49-dc20-4713-813b-ff458c99ab90">CLFS</a> log file stream to be associated with the transaction manager object.

`ExistingTransactionManagerGuid`

A pointer to a GUID structure that represents the current name of the transaction manager object.


## Return Value

The <b>TmRenameTransactionManager</b> routine returns an NTSTATUS value. If the routine fails, it returns one of the following error codes:


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows Vista. Available starting with Windows Vista. |
| **Target Platform** | Universal |
| **Header** | wdm.h |
| **Library** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |