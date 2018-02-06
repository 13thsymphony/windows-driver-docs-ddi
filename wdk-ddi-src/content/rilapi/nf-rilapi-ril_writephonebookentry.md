---
UID: NF:rilapi.RIL_WritePhonebookEntry
title: RIL_WritePhonebookEntry function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_writephonebookentry.htm
old-project: netvista
ms.assetid: 03fc6240-ccc8-48de-87e0-b1ee5db3bac8
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ril_writephonebookentry, RIL_WritePhonebookEntry, RIL_WritePhonebookEntry method [Network Drivers Starting with Windows Vista], rilapi/RIL_WritePhonebookEntry
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
-	RIL_WritePhonebookEntry
product: Windows
targetos: Windows
req.typenames: "*PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER"
req.product: Windows 10 or later.
---


# RIL_WritePhonebookEntry function
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax

````
HRESULT  RIL_WritePhonebookEntry(
   HRIL                         hRil,
   LPVOID                       lpContext,
   HUICCAPP                     hUiccApp,
   RILPHONEENTRYSTORELOCATION   dwStoreLocation,
   const RILPHONEBOOKENTRY      lpEntry,
   const RILUICCLOCKCREDENTIAL  lpLockVerification
);
````

## Parameters

`hRil`



`lpContext`



`hUiccApp`



`dwStoreLocation`



`lpEntry`



`lpLockVerification`




## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Target Platform** | Windows |
| **Header** | rilapi.h |
| **Library** | NtosKrnl.exe |