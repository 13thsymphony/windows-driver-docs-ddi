---
UID: NE:ntddstor._STORAGE_DIAGNOSTIC_TARGET_TYPE
title: "_STORAGE_DIAGNOSTIC_TARGET_TYPE"
author: windows-driver-content
description: The STORAGE_DIAGNOSTIC_TARGET_TYPE enumeration specifies the target type of a storage diagnostic.
old-location: storage\storage_diagnostic_target_type.htm
old-project: storage
ms.assetid: 8BC338FB-7C76-49D3-96E5-0F20C4A250CE
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PSTORAGE_DIAGNOSTIC_TARGET_TYPE, PSTORAGE_DIAGNOSTIC_TARGET_TYPE, PSTORAGE_DIAGNOSTIC_TARGET_TYPE enumeration pointer [Storage Devices], STORAGE_DIAGNOSTIC_TARGET_TYPE, STORAGE_DIAGNOSTIC_TARGET_TYPE enumeration [Storage Devices], StorageDiagnosticTargetTypeHbaFirmware, StorageDiagnosticTargetTypeMax, StorageDiagnosticTargetTypeMiniport, StorageDiagnosticTargetTypePort, StorageDiagnosticTargetTypeUndefined, _STORAGE_DIAGNOSTIC_TARGET_TYPE, ntddstor/PSTORAGE_DIAGNOSTIC_TARGET_TYPE, ntddstor/STORAGE_DIAGNOSTIC_TARGET_TYPE, ntddstor/StorageDiagnosticTargetTypeHbaFirmware, ntddstor/StorageDiagnosticTargetTypeMax, ntddstor/StorageDiagnosticTargetTypeMiniport, ntddstor/StorageDiagnosticTargetTypePort, ntddstor/StorageDiagnosticTargetTypeUndefined, storage.storage_diagnostic_target_type"
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
-	STORAGE_DIAGNOSTIC_TARGET_TYPE
product: Windows
targetos: Windows
req.typenames: STORAGE_DIAGNOSTIC_TARGET_TYPE, *PSTORAGE_DIAGNOSTIC_TARGET_TYPE
---

# _STORAGE_DIAGNOSTIC_TARGET_TYPE Enumeration
The <b>STORAGE_DIAGNOSTIC_TARGET_TYPE</b> enumeration specifies the target type of a storage diagnostic.

## Syntax
````
typedef enum _STORAGE_DIAGNOSTIC_TARGET_TYPE { 
  StorageDiagnosticTargetTypeUndefined    = 0,
  StorageDiagnosticTargetTypePort,
  StorageDiagnosticTargetTypeMiniport,
  StorageDiagnosticTargetTypeHbaFirmware,
  StorageDiagnosticTargetTypeMax
} STORAGE_DIAGNOSTIC_TARGET_TYPE, *PSTORAGE_DIAGNOSTIC_TARGET_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>StorageDiagnosticTargetTypeHbaFirmware</td>
                    <td>Specifies the target type is a Hba Firmware driver.</td>
                </tr>
            
                <tr>
                    <td>StorageDiagnosticTargetTypeMax</td>
                    <td>Specifies the target type is a Max driver.</td>
                </tr>
            
                <tr>
                    <td>StorageDiagnosticTargetTypeMiniport</td>
                    <td>Specifies the target type is a Miniport driver.</td>
                </tr>
            
                <tr>
                    <td>StorageDiagnosticTargetTypePort</td>
                    <td>Specifies the target type is a port driver.</td>
                </tr>
            
                <tr>
                    <td>StorageDiagnosticTargetTypeUndefined</td>
                    <td>Specifies the target type is undefined.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 10, version 1709. Available starting with Windows 10, version 1709. |
| **Header** | ntddstor.h |