---
UID: NF:rilapi.RIL_ReadMsg
title: RIL_ReadMsg function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_readmsg.htm
old-project: netvista
ms.assetid: a38c089b-a5f4-4fd2-ab94-ead53228c5e9
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: RIL_ReadMsg, RIL_ReadMsg method [Network Drivers Starting with Windows Vista], netvista.ril_readmsg, rilapi/RIL_ReadMsg
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
-	RIL_ReadMsg
product:
- Windows
targetos: Windows
req.typenames: PTP_VENDOR_DATA_OUT, *PPTP_VENDOR_DATA_OUT
req.product: Windows 10 or later.
---


# RIL_ReadMsg function
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax

```
HRESULT RIL_ReadMsg(
  HRIL     hRil,
  LPVOID   lpContext,
  HUICCAPP hUiccApp,
  DWORD    dwIndex
);
```

## Parameters

`hRil`



`lpContext`



`hUiccApp`



`dwIndex`




## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | rilapi.h |