---
UID: NF:rilapi.RIL_ReadPhonebookEntries
title: RIL_ReadPhonebookEntries function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_readphonebookentries.htm
old-project: netvista
ms.assetid: 3da05f28-a6de-4dad-a978-0439f3244bbb
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RIL_ReadPhonebookEntries
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
req.alt-api: RIL_ReadPhonebookEntries
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

# RIL_ReadPhonebookEntries function



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            



## -syntax

````
HRESULT  RIL_ReadPhonebookEntries(
   HRIL                       hRil,
   LPVOID                     lpContext,
   HUICCAPP                   hUiccApp,
   RILPHONEENTRYSTORELOCATION dwStoreLocation,
   DWORD                      dwStartIndex,
   DWORD                      dwEndIndex
);
````


## -parameters

### -param hRil 


### -param lpContext 


### -param hUiccApp 


### -param dwStoreLocation 


### -param dwStartIndex 


### -param dwEndIndex 


## -returns
If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## -remarks
