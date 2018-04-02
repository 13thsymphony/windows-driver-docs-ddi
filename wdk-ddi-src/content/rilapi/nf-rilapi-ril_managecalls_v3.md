---
UID: NF:rilapi.RIL_ManageCalls_V3
title: RIL_ManageCalls_V3 function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_managecalls_v3.htm
old-project: netvista
ms.assetid: 4c301656-8918-46f2-8f8f-3ceff2af8e94
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: RIL_ManageCalls_V3, RIL_ManageCalls_V3 method [Network Drivers Starting with Windows Vista], netvista.ril_managecalls_v3, rilapi/RIL_ManageCalls_V3
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapi.h
api_name:
-	RIL_ManageCalls_V3
product:
- Windows
targetos: Windows
req.typenames: PTP_VENDOR_DATA_OUT, *PPTP_VENDOR_DATA_OUT
req.product: Windows 10 or later.
---


# RIL_ManageCalls_V3 function
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax

```
HRESULT RIL_ManageCalls_V3(
  HRIL                               hRil,
  LPVOID                             lpContext,
  DWORD                              dwExecutor,
  RILMANAGECALLPARAMSCOMMAND         dwCommand,
  DWORD                              dwID,
  const LPRILCALLMEDIAOFFERANSWERSET lprcmOfferAnswer,
  const LPRILADDRESS                 lpraAddress
);
```

## Parameters

`hRil`



`lpContext`



`dwExecutor`



`dwCommand`



`dwID`



`lprcmOfferAnswer`



`lpraAddress`




## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | rilapi.h |