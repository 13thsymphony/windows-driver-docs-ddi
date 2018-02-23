---
UID: NE:ntddstor._STORAGE_CRYPTO_ALGORITHM_ID
title: "_STORAGE_CRYPTO_ALGORITHM_ID"
author: windows-driver-content
description: The STORAGE_CRYPTO_ALGORITHM_ID enum provides an output buffer for StorageAdapterCryptoProperty and PropertyStandardQuery.
old-location: storage\storage_crypto_algorithm_id.htm
old-project: storage
ms.assetid: 5D1CCF3D-D677-47B0-9C7B-7E35C649A7D5
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "_STORAGE_CRYPTO_ALGORITHM_ID, StorageCryptoAlgorithmMax, STORAGE_CRYPTO_ALGORITHM_ID, *PSTORAGE_CRYPTO_ALGORITHM_ID enumeration [Storage Devices], ntddstor/StorageCryptoAlgorithmUnknown, StorageCryptoAlgorithmAESECB, ntddstor/STORAGE_CRYPTO_ALGORITHM_ID, StorageCryptoAlgorithmXTSAES, ntddstor/StorageCryptoAlgorithmBitlockerAESCBC, StorageCryptoAlgorithmESSIVAESCBC, ntddstor/StorageCryptoAlgorithmMax, STORAGE_CRYPTO_ALGORITHM_ID, storage.storage_crypto_algorithm_id, ntddstor/StorageCryptoAlgorithmXTSAES, *PSTORAGE_CRYPTO_ALGORITHM_ID, StorageCryptoAlgorithmBitlockerAESCBC, ntddstor/StorageCryptoAlgorithmESSIVAESCBC, ntddstor/StorageCryptoAlgorithmAESECB, STORAGE_CRYPTO_ALGORITHM_ID, *PSTORAGE_CRYPTO_ALGORITHM_ID, STORAGE_CRYPTO_ALGORITHM_ID enumeration [Storage Devices], StorageCryptoAlgorithmUnknown"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddstor.h
apiname:
-	STORAGE_CRYPTO_ALGORITHM_ID, *PSTORAGE_CRYPTO_ALGORITHM_ID
product: Windows
targetos: Windows
req.typenames: "*PSTORAGE_CRYPTO_ALGORITHM_ID, STORAGE_CRYPTO_ALGORITHM_ID"
---

# _STORAGE_CRYPTO_ALGORITHM_ID Enumeration
The <b>STORAGE_CRYPTO_ALGORITHM_ID</b> enum provides an output buffer for <b>StorageAdapterCryptoProperty</b> and <b>PropertyStandardQuery</b>.

## Syntax
````
typedef enum _STORAGE_CRYPTO_ALGORITHM_ID { 
  StorageCryptoAlgorithmUnknown          = 0,
  StorageCryptoAlgorithmXTSAES           = 1,
  StorageCryptoAlgorithmBitlockerAESCBC,
  StorageCryptoAlgorithmAESECB,
  StorageCryptoAlgorithmESSIVAESCBC,
  StorageCryptoAlgorithmMax
} STORAGE_CRYPTO_ALGORITHM_ID, *PSTORAGE_CRYPTO_ALGORITHM_ID;
````

## Constants

<table>
            
                <tr>
                    <td>StorageCryptoAlgorithmAESECB</td>
                    <td>Reserved for system use.</td>
                </tr>
            
                <tr>
                    <td>StorageCryptoAlgorithmBitlockerAESCBC</td>
                    <td>Reserved for system use.</td>
                </tr>
            
                <tr>
                    <td>StorageCryptoAlgorithmESSIVAESCBC</td>
                    <td>Reserved for system use.</td>
                </tr>
            
                <tr>
                    <td>StorageCryptoAlgorithmMax</td>
                    <td>Reserved for system use.</td>
                </tr>
            
                <tr>
                    <td>StorageCryptoAlgorithmUnknown</td>
                    <td>Reserved for system use.</td>
                </tr>
            
                <tr>
                    <td>StorageCryptoAlgorithmXTSAES</td>
                    <td>Reserved for system use.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddstor.h |