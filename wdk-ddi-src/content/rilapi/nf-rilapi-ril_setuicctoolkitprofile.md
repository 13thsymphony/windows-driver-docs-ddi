---
UID: NF:rilapi.RIL_SetUiccToolkitProfile
title: RIL_SetUiccToolkitProfile function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_setuicctoolkitprofile.htm
old-project: netvista
ms.assetid: 123bf713-d238-491a-bc53-1f35dbb34feb
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RIL_SetUiccToolkitProfile, RIL_SetUiccToolkitProfile method [Network Drivers Starting with Windows Vista], netvista.ril_setuicctoolkitprofile, rilapi/RIL_SetUiccToolkitProfile
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
req.lib: NtosKrnl.exe
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
-	RIL_SetUiccToolkitProfile
product: Windows
targetos: Windows
req.typenames: RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, *PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
req.product: Windows 10 or later.
---


# RIL_SetUiccToolkitProfile function
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax

````
HRESULT  RIL_SetUiccToolkitProfile(
   HRIL                         hRil,
   LPVOID                       lpContext,
   const RILUICCTOOLKITPROFILE  lpToolkitProfile
);
````

## Parameters

`hRil`



`lpContext`



`lpToolkitProfile`




## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | rilapi.h |
| **Library** | NtosKrnl.exe |