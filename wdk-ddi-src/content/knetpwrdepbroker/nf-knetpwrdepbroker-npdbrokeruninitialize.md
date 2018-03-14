---
UID: NF:knetpwrdepbroker.NpdBrokerUninitialize
title: NpdBrokerUninitialize function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\npdbrokeruninitialize.htm
old-project: netvista
ms.assetid: E1CC0E8D-B48E-4F02-AE26-82123A3722E6
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NpdBrokerUninitialize, NpdBrokerUninitialize function [Network Drivers Starting with Windows Vista], knetpwrdepbroker/NpdBrokerUninitialize, netvista.npdbrokeruninitialize
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
req.lib: 
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
-	NpdBrokerUninitialize
product: Windows
targetos: Windows
req.typenames: SOUNDDETECTOR_PATTERNHEADER
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
| **IRQL** | PASSIVE_LEVEL |