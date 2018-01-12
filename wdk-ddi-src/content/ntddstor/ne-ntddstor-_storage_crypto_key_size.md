---
UID: NE:ntddstor._STORAGE_CRYPTO_KEY_SIZE
title: _STORAGE_CRYPTO_KEY_SIZE
author: windows-driver-content
description: The STORAGE_CRYPTO_KEY_SIZE enum returns the Size of the key in bits.
old-location: storage\storage_crypto_key_size.htm
old-project: storage
ms.assetid: C3E5CEC6-34A2-48DF-B963-677C69A97E0B
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _STORAGE_CRYPTO_KEY_SIZE, STORAGE_CRYPTO_KEY_SIZE, *PSTORAGE_CRYPTO_KEY_SIZE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddstor.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STORAGE_CRYPTO_KEY_SIZE, *PSTORAGE_CRYPTO_KEY_SIZE
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
req.typenames: STORAGE_CRYPTO_KEY_SIZE, *PSTORAGE_CRYPTO_KEY_SIZE
---

# _STORAGE_CRYPTO_KEY_SIZE enumeration



## -description
The <b>STORAGE_CRYPTO_KEY_SIZE</b> enum returns the Size of the key in bits.



## -syntax

````
typedef enum _STORAGE_CRYPTO_KEY_SIZE { 
  StorageCryptoKeySizeUnknown  = 0,
  StorageCryptoKeySize128Bits  = 1,
  StorageCryptoKeySize192Bits,
  StorageCryptoKeySize256Bits,
  StorageCryptoKeySize512Bits
} STORAGE_CRYPTO_KEY_SIZE, *PSTORAGE_CRYPTO_KEY_SIZE;
````


## -enum-fields

### -field StorageCryptoKeySizeUnknown

Reserved for system use.


### -field StorageCryptoKeySize128Bits

Reserved for system use.


### -field StorageCryptoKeySize192Bits

Reserved for system use.


### -field StorageCryptoKeySize256Bits

Reserved for system use.


### -field StorageCryptoKeySize512Bits

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