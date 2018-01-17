---
UID: NF:rilapi.RIL_GetExecutorConfig
title: RIL_GetExecutorConfig function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_getexecutorconfig.htm
old-project: netvista
ms.assetid: 71931187-14f1-459f-9c1a-cc3463178af9
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RIL_GetExecutorConfig
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
req.alt-api: RIL_GetExecutorConfig
req.alt-loc: rilapi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.typenames: PTP_VENDOR_DATA_OUT, *PPTP_VENDOR_DATA_OUT
req.product: Windows 10 or later.
---

# RIL_GetExecutorConfig function



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            



## -syntax

````
HRESULT  RIL_GetExecutorConfig(
   HRIL   hRil,
   LPVOID lpContext,
   DWORD  dwExecutor
);
````


## -parameters

### -param hRil 


### -param lpContext 


### -param dwExecutor 


## -returns
If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## -remarks
