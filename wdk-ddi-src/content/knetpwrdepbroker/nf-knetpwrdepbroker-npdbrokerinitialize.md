---
UID: NF:knetpwrdepbroker.NpdBrokerInitialize
title: NpdBrokerInitialize function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\npdbrokerinitialize.htm
old-project: netvista
ms.assetid: 7B23A6DF-2B78-48DF-BDD4-451A19521CAC
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: NpdBrokerInitialize, NpdBrokerInitialize function [Network Drivers Starting with Windows Vista], knetpwrdepbroker/NpdBrokerInitialize, netvista.npdbrokerinitialize
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	KNetPwrDepBroker.h
api_name:
-	NpdBrokerInitialize
product: Windows
targetos: Windows
req.typenames: SOUNDDETECTOR_PATTERNHEADER
---


# NpdBrokerInitialize function
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax

````
NTSTATUS NpdBrokerInitialize(
  _In_  ULONG   ulClientID,
  _Out_ PHANDLE phBroker
);
````

## Parameters

`ulClientID`

Reserved.

`phBroker`

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