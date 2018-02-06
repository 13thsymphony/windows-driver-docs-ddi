---
UID: NF:rilapi.RIL_ChangeUiccLockPassword
title: RIL_ChangeUiccLockPassword function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_changeuicclockpassword.htm
old-project: netvista
ms.assetid: 85f401bb-b8bd-4bb9-9953-08945ffc4d8b
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapi/RIL_ChangeUiccLockPassword, RIL_ChangeUiccLockPassword method [Network Drivers Starting with Windows Vista], RIL_ChangeUiccLockPassword, netvista.ril_changeuicclockpassword
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rilapi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapi.h
apiname:
-	RIL_ChangeUiccLockPassword
product: Windows
targetos: Windows
req.typenames: "*PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER"
req.product: Windows 10 or later.
---


# RIL_ChangeUiccLockPassword function
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax

````
HRESULT  RIL_ChangeUiccLockPassword(
   HRIL                         hRil,
   LPVOID                       lpContext,
   const RILUICCLOCKCREDENTIAL  lpLockCredential,
   LPCSTR                       lpszNewPassword
);
````

## Parameters

`hRil`



`lpContext`



`lpLockCredential`



`lpszNewPassword`




## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Target Platform** | Windows |
| **Header** | rilapi.h |
| **Library** | NtosKrnl.exe |