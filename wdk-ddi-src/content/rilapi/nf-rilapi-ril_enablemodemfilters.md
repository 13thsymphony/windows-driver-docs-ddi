---
UID: NF:rilapi.RIL_EnableModemFilters
title: RIL_EnableModemFilters function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_enablemodemfilters.htm
old-project: netvista
ms.assetid: 11fc231e-4b65-4cbb-8c0f-58b1165c08dd
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: RIL_EnableModemFilters, RIL_EnableModemFilters method [Network Drivers Starting with Windows Vista], netvista.ril_enablemodemfilters, rilapi/RIL_EnableModemFilters
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
-	RIL_EnableModemFilters
product: Windows
targetos: Windows
req.typenames: PTP_VENDOR_DATA_OUT, *PPTP_VENDOR_DATA_OUT
req.product: Windows 10 or later.
---


# RIL_EnableModemFilters function
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax

```
HRESULT RIL_EnableModemFilters(
  HRIL   hRil,
  LPVOID lpContext,
  DWORD  filterID
);
```

## Parameters

`hRil`



`lpContext`



`filterID`




## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | rilapi.h |