---
UID: NF:rilapi.RIL_SetDMProfileConfigInfo
title: RIL_SetDMProfileConfigInfo function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_setdmprofileconfiginfo.htm
old-project: netvista
ms.assetid: 4d2ab950-a045-4b5a-be9b-0b80c442e63d
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: RIL_SetDMProfileConfigInfo, RIL_SetDMProfileConfigInfo method [Network Drivers Starting with Windows Vista], netvista.ril_setdmprofileconfiginfo, rilapi/RIL_SetDMProfileConfigInfo
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
-	RIL_SetDMProfileConfigInfo
product: Windows
targetos: Windows
req.typenames: PTP_VENDOR_DATA_OUT, *PPTP_VENDOR_DATA_OUT
req.product: Windows 10 or later.
---


# RIL_SetDMProfileConfigInfo function
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax

```
HRESULT RIL_SetDMProfileConfigInfo(
  HRIL                       hRil,
  LPVOID                     lpContext,
  DWORD                      dwExecutor,
  DWORD                      dwConfigItem,
  const RILDMCONFIGINFOVALUE *rciValue
);
```

## Parameters

`hRil`



`lpContext`



`dwExecutor`



`dwConfigItem`



`rciValue`




## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | rilapi.h |