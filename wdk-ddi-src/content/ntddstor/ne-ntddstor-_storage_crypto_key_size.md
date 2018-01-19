---
UID : NE:ntddstor._STORAGE_CRYPTO_KEY_SIZE
title : _STORAGE_CRYPTO_KEY_SIZE
author : windows-driver-content
description : The STORAGE_CRYPTO_KEY_SIZE enum returns the Size of the key in bits.
old-location : storage\storage_crypto_key_size.htm
old-project : storage
ms.assetid : C3E5CEC6-34A2-48DF-B963-677C69A97E0B
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : _STORAGE_CRYPTO_KEY_SIZE, STORAGE_CRYPTO_KEY_SIZE, *PSTORAGE_CRYPTO_KEY_SIZE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : ntddstor.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : STORAGE_CRYPTO_KEY_SIZE, *PSTORAGE_CRYPTO_KEY_SIZE
req.alt-loc : Ntddstor.h
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
req.typenames : STORAGE_CRYPTO_KEY_SIZE, *PSTORAGE_CRYPTO_KEY_SIZE
---

# _STORAGE_CRYPTO_KEY_SIZE Enumeration
The <b>STORAGE_CRYPTO_KEY_SIZE</b> enum returns the Size of the key in bits.

## Syntax
````
typedef enum _STORAGE_CRYPTO_KEY_SIZE { 
  StorageCryptoKeySizeUnknown  = 0,
  StorageCryptoKeySize128Bits  = 1,
  StorageCryptoKeySize192Bits,
  StorageCryptoKeySize256Bits,
  StorageCryptoKeySize512Bits
} STORAGE_CRYPTO_KEY_SIZE, *PSTORAGE_CRYPTO_KEY_SIZE;
````

## Constants

<table>

<tr>
<td>StorageCryptoKeySize128Bits</td>
<td>Reserved for system use.</td>
</tr>

<tr>
<td>StorageCryptoKeySize192Bits</td>
<td>Reserved for system use.</td>
</tr>

<tr>
<td>StorageCryptoKeySize256Bits</td>
<td>Reserved for system use.</td>
</tr>

<tr>
<td>StorageCryptoKeySize512Bits</td>
<td>Reserved for system use.</td>
</tr>

<tr>
<td>StorageCryptoKeySizeUnknown</td>
<td>Reserved for system use.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddstor.h |