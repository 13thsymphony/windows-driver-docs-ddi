---
UID: NF:knetpwrdepbroker.NpdBrokerAcquireWithTimeout
title: NpdBrokerAcquireWithTimeout function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\npdbrokeracquirewithtimeout.htm
old-project: netvista
ms.assetid: D2067A72-0FF5-4D77-A1F6-0A6984A1735A
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: knetpwrdepbroker/NpdBrokerAcquireWithTimeout, netvista.npdbrokeracquirewithtimeout, NpdBrokerAcquireWithTimeout function [Network Drivers Starting with Windows Vista], NpdBrokerAcquireWithTimeout
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
-	NpdBrokerAcquireWithTimeout
product: Windows
targetos: Windows
req.typenames: KEYWORDSELECTOR
---


# NpdBrokerAcquireWithTimeout function
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax

````
NTSTATUS NpdBrokerAcquireWithTimeout(
  _In_ HANDLE hBroker,
  _In_ LONG   lTimeoutMS
);
````

## Parameters

`hBroker`

Reserved.

`lTimeoutMS`

Reserved.


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1709 Windows 10, version 1709 |
| **Target Platform** | Windows |
| **Header** | knetpwrdepbroker.h (include KNetPwrDepBroker.h) |
| **Library** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |