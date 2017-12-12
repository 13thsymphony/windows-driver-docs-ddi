---
UID: NF.wdm.NtRenameTransactionManager
title: NtRenameTransactionManager function
author: windows-driver-content
description: The NtRenameTransactionManager routine changes the identity of the transaction manager object that is stored in the CLFS log file stream contained in the log file name.
old-location: kernel\ntrenametransactionmanager.htm
old-project: kernel
ms.assetid: 53baa93a-bd71-4975-86cc-51eb31c2f430
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: NtRenameTransactionManager
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NtRenameTransactionManager
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
req.irql: <=APC_LEVEL
req.product: Windows 10 or later.
---

# NtRenameTransactionManager function



## -description
The <b>NtRenameTransactionManager</b> routine changes the identity of the transaction manager object that is stored in the <a href="https://msdn.microsoft.com/4da3cb49-dc20-4713-813b-ff458c99ab90">CLFS</a> log file stream contained in the log file name.



## -syntax

````
NTSTATUS NtRenameTransactionManager(
  _In_ PUNICODE_STRING LogFileName,
  _In_ LPGUID          ExistingTransactionManagerGuid
);
````


## -parameters

### -param LogFileName [in]


### -param ExistingTransactionManagerGuid [in]


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;=APC_LEVEL

</td>
</tr>
</table>