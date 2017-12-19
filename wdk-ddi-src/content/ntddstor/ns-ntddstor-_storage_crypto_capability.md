---
UID: NS.NTDDSTOR._STORAGE_CRYPTO_CAPABILITY
title: _STORAGE_CRYPTO_CAPABILITY
author: windows-driver-content
description: Reserved for system use.
old-location: storage\storage_crypto_capability.htm
old-project: storage
ms.assetid: 9DFAB3C6-F833-487D-87FC-292B3AFAD767
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _STORAGE_CRYPTO_CAPABILITY, PSTORAGE_CRYPTO_CAPABILITY, STORAGE_CRYPTO_CAPABILITY, *PSTORAGE_CRYPTO_CAPABILITY
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
req.alt-api: STORAGE_CRYPTO_CAPABILITY
req.alt-loc: Ntddstor.h
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
---

# _STORAGE_CRYPTO_CAPABILITY structure



## -description
Reserved for system use.



## -syntax

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


## -struct-fields

### -field Version

Reserved for system use.


### -field Size

Reserved for system use.


### -field CryptoCapabilityIndex

Reserved for system use.


### -field AlgorithmId

Reserved for system use.


### -field KeySize

Reserved for system use.


### -field DataUnitSizeBitmask

Reserved for system use.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddstor.h</dt>
</dl>
</td>
</tr>
</table>