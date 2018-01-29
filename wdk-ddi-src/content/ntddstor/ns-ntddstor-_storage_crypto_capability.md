---
UID : NS:ntddstor._STORAGE_CRYPTO_CAPABILITY
title : _STORAGE_CRYPTO_CAPABILITY
author : windows-driver-content
description : Reserved for system use.
old-location : storage\storage_crypto_capability.htm
old-project : storage
ms.assetid : 9DFAB3C6-F833-487D-87FC-292B3AFAD767
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : storage.storage_crypto_capability, STORAGE_CRYPTO_CAPABILITY, STORAGE_CRYPTO_CAPABILITY structure [Storage Devices], PSTORAGE_CRYPTO_CAPABILITY, *PSTORAGE_CRYPTO_CAPABILITY, _STORAGE_CRYPTO_CAPABILITY, ntddstor/STORAGE_CRYPTO_CAPABILITY, PSTORAGE_CRYPTO_CAPABILITY structure pointer [Storage Devices], ntddstor/PSTORAGE_CRYPTO_CAPABILITY
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ntddstor.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PSTORAGE_CRYPTO_CAPABILITY, STORAGE_CRYPTO_CAPABILITY"
---

# _STORAGE_CRYPTO_CAPABILITY structure
Reserved for system use.

## Syntax
````
typedef struct _STORAGE_CRYPTO_CAPABILITY {
  ULONG                       Version;
  ULONG                       Size;
  ULONG                       CryptoCapabilityIndex;
  STORAGE_CRYPTO_ALGORITHM_ID AlgorithmId;
  STORAGE_CRYPTO_KEY_SIZE     KeySize;
  ULONG                       DataUnitSizeBitmask;
} STORAGE_CRYPTO_CAPABILITY, *PSTORAGE_CRYPTO_CAPABILITY;
````

## Members


`AlgorithmId`

Reserved for system use.

`CryptoCapabilityIndex`

Reserved for system use.

`DataUnitSizeBitmask`

Reserved for system use.

`KeySize`

Reserved for system use.

`Size`

Reserved for system use.

`Version`

Reserved for system use.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddstor.h |