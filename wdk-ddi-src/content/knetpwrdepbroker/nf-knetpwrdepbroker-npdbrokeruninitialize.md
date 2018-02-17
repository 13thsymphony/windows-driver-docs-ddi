---
UID: NF:knetpwrdepbroker.NpdBrokerUninitialize
title: NpdBrokerUninitialize function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\npdbrokeruninitialize.htm
old-project: netvista
ms.assetid: E1CC0E8D-B48E-4F02-AE26-82123A3722E6
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: knetpwrdepbroker/NpdBrokerUninitialize, netvista.npdbrokeruninitialize, NpdBrokerUninitialize, NpdBrokerUninitialize function [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: knetpwrdepbroker.h
req.include-header: KNetPwrDepBroker.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	KNetPwrDepBroker.h
apiname:
-	NpdBrokerUninitialize
product: Windows
targetos: Windows
req.typenames: KEYWORDSELECTOR
---


# NpdBrokerUninitialize function
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax

````
NTSTATUS NpdBrokerUninitialize(
  _In_ HANDLE hBroker
);
````

## Parameters

`hBroker`

Reserved.


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1709  |
| **Target Platform** | Windows |
| **Header** | knetpwrdepbroker.h (include KNetPwrDepBroker.h) |
| **Library** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |