---
UID: NS:ntddstor._STORAGE_CRYPTO_CAPABILITY
title: "_STORAGE_CRYPTO_CAPABILITY"
author: windows-driver-content
description: Reserved for system use.
old-location: storage\storage_crypto_capability.htm
old-project: storage
ms.assetid: 9DFAB3C6-F833-487D-87FC-292B3AFAD767
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PSTORAGE_CRYPTO_CAPABILITY, PSTORAGE_CRYPTO_CAPABILITY, PSTORAGE_CRYPTO_CAPABILITY structure pointer [Storage Devices], STORAGE_CRYPTO_CAPABILITY, STORAGE_CRYPTO_CAPABILITY structure [Storage Devices], _STORAGE_CRYPTO_CAPABILITY, ntddstor/PSTORAGE_CRYPTO_CAPABILITY, ntddstor/STORAGE_CRYPTO_CAPABILITY, storage.storage_crypto_capability"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: 
req.target-type: Windows
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
-	Ntddstor.h
api_name:
-	STORAGE_CRYPTO_CAPABILITY
product:
- Windows
targetos: Windows
req.typenames: STORAGE_CRYPTO_CAPABILITY, *PSTORAGE_CRYPTO_CAPABILITY
---

# _STORAGE_CRYPTO_CAPABILITY structure
Reserved for system use.

## Syntax
```
typedef struct _STORAGE_CRYPTO_CAPABILITY {
  ULONG                       Version;
  ULONG                       Size;
  ULONG                       CryptoCapabilityIndex;
  STORAGE_CRYPTO_ALGORITHM_ID AlgorithmId;
  STORAGE_CRYPTO_KEY_SIZE     KeySize;
  ULONG                       DataUnitSizeBitmask;
} STORAGE_CRYPTO_CAPABILITY, *PSTORAGE_CRYPTO_CAPABILITY;
```

## Members


`Version`

Reserved for system use.

`Size`

Reserved for system use.

`CryptoCapabilityIndex`

Reserved for system use.

`AlgorithmId`

Reserved for system use.

`KeySize`

Reserved for system use.

`DataUnitSizeBitmask`

Reserved for system use.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddstor.h |