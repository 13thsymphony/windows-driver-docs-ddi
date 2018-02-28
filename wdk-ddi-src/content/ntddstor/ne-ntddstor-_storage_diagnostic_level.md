---
UID: NE:ntddstor._STORAGE_DIAGNOSTIC_LEVEL
title: "_STORAGE_DIAGNOSTIC_LEVEL"
author: windows-driver-content
description: The STORAGE_DIAGNOSTIC_LEVEL enumeration specifies the target type of a storage diagnostic.
old-location: storage\storage_diagnostic_level.htm
old-project: storage
ms.assetid: 6D705DA8-7F45-4C7A-813F-5AE4F5A1D8ED
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PSTORAGE_DIAGNOSTIC_LEVEL, PSTORAGE_DIAGNOSTIC_LEVEL, PSTORAGE_DIAGNOSTIC_LEVEL enumeration pointer [Storage Devices], STORAGE_DIAGNOSTIC_LEVEL, STORAGE_DIAGNOSTIC_LEVEL enumeration [Storage Devices], StorageDiagnosticLevelDefault, StorageDiagnosticLevelMax, _STORAGE_DIAGNOSTIC_LEVEL, ntddstor/PSTORAGE_DIAGNOSTIC_LEVEL, ntddstor/STORAGE_DIAGNOSTIC_LEVEL, ntddstor/StorageDiagnosticLevelDefault, ntddstor/StorageDiagnosticLevelMax, storage.storage_diagnostic_level"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddstor.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10, version 1709.
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
-	ntddstor.h
api_name:
-	STORAGE_DIAGNOSTIC_LEVEL
product: Windows
targetos: Windows
req.typenames: STORAGE_DIAGNOSTIC_LEVEL, *PSTORAGE_DIAGNOSTIC_LEVEL
---

# _STORAGE_DIAGNOSTIC_LEVEL Enumeration
The <b>STORAGE_DIAGNOSTIC_LEVEL</b> enumeration specifies the target type of a storage diagnostic.

## Syntax
````
typedef enum _STORAGE_DIAGNOSTIC_LEVEL { 
  StorageDiagnosticLevelDefault  = 0,
  StorageDiagnosticLevelMax
} STORAGE_DIAGNOSTIC_LEVEL, *PSTORAGE_DIAGNOSTIC_LEVEL;
````

## Constants

<table>
            
                <tr>
                    <td>StorageDiagnosticLevelDefault</td>
                    <td>Specifies the default diagnostic level.</td>
                </tr>
            
                <tr>
                    <td>StorageDiagnosticLevelMax</td>
                    <td>Specifies the max diagnostic level.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 10, version 1709. Available starting with Windows 10, version 1709. |
| **Header** | ntddstor.h |