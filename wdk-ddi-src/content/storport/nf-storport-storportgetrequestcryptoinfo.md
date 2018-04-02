---
UID: NF:storport.StorPortGetRequestCryptoInfo
title: StorPortGetRequestCryptoInfo function
author: windows-driver-content
description: Reserved for system use.
old-location: storage\storportgetrequestcryptoinfo.htm
old-project: storage
ms.assetid: B8D1E882-FBFA-4CB1-83D3-CB817F111F20
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: StorPortGetRequestCryptoInfo, StorPortGetRequestCryptoInfo routine [Storage Devices], storage.storportgetrequestcryptoinfo, storport/StorPortGetRequestCryptoInfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: 
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Storport.h
api_name:
-	StorPortGetRequestCryptoInfo
product:
- Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---


# StorPortGetRequestCryptoInfo function
Reserved for system use.

## Syntax

```
ULONG StorPortGetRequestCryptoInfo(
  PVOID                 HwDeviceExtension,
  PSCSI_REQUEST_BLOCK   Srb,
  PSTOR_CRYPTO_KEY_INFO CryptoKeyInfo
);
```

## Parameters

`HwDeviceExtension`

TBD

`Srb`

TBD

`CryptoKeyInfo`

TBD


## Return Value

Reserved for system use.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | storport.h |