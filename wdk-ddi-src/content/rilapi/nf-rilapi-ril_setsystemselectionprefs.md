---
UID: NF:rilapi.RIL_SetSystemSelectionPrefs
title: RIL_SetSystemSelectionPrefs function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_setsystemselectionprefs.htm
old-project: netvista
ms.assetid: 57384690-9fe0-4fee-a578-5451e57cfc6b
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RIL_SetSystemSelectionPrefs
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
req.alt-api: RIL_SetSystemSelectionPrefs
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

# RIL_SetSystemSelectionPrefs function



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            



## -syntax

````
HRESULT  RIL_SetSystemSelectionPrefs(
   HRIL                           hRil,
   LPVOID                         lpContext,
   RILSETSYSTEMSELECTIONPREFSFLAG dwFlags,
   const RILSYSTEMSELECTIONPREFS  lpRilSystemSelectionPrefs
);
````


## -parameters

### -param hRil 


### -param lpContext 


### -param dwFlags 


### -param lpRilSystemSelectionPrefs 


## -returns
If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## -remarks
