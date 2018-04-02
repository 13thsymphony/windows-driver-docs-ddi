---
UID: NE:ntddscsi._MP_STORAGE_DIAGNOSTIC_LEVEL
title: "_MP_STORAGE_DIAGNOSTIC_LEVEL"
author: windows-driver-content
description: The MP_STORAGE_DIAGNOSTIC_LEVEL enumeration allows the caller to control what kinds of data the provider should return.
old-location: storage\mp_storage_diagnostic_level.htm
old-project: storage
ms.assetid: BB05D543-7B99-481E-8CDB-AE350CBCCA2A
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PMP_STORAGE_DIAGNOSTIC_LEVEL, MP_STORAGE_DIAGNOSTIC_LEVEL, MP_STORAGE_DIAGNOSTIC_LEVEL enumeration [Storage Devices], PMP_STORAGE_DIAGNOSTIC_LEVEL, PMP_STORAGE_DIAGNOSTIC_LEVEL enumeration pointer [Storage Devices], StorageDiagnosticLevelDefault, StorageDiagnosticLevelMax, _MP_STORAGE_DIAGNOSTIC_LEVEL, ntddscsi/MP_STORAGE_DIAGNOSTIC_LEVEL, ntddscsi/PMP_STORAGE_DIAGNOSTIC_LEVEL, ntddscsi/StorageDiagnosticLevelDefault, ntddscsi/StorageDiagnosticLevelMax, storage.mp_storage_diagnostic_level"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddscsi.h
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
-	ntddscsi.h
api_name:
-	MP_STORAGE_DIAGNOSTIC_LEVEL
product:
- Windows
targetos: Windows
req.typenames: MP_STORAGE_DIAGNOSTIC_LEVEL, *PMP_STORAGE_DIAGNOSTIC_LEVEL
---

# _MP_STORAGE_DIAGNOSTIC_LEVEL Enumeration
The <b>MP_STORAGE_DIAGNOSTIC_LEVEL</b> enumeration allows the caller to control what kinds of data the provider should return.

## Syntax
```
typedef enum _MP_STORAGE_DIAGNOSTIC_LEVEL {
  MpStorageDiagnosticLevelDefault  ,
  MpStorageDiagnosticLevelMax
} *PMP_STORAGE_DIAGNOSTIC_LEVEL, MP_STORAGE_DIAGNOSTIC_LEVEL;
```

## Constants

<table>
            
                <tr>
                    <td>MpStorageDiagnosticLevelDefault</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>MpStorageDiagnosticLevelMax</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 10, version 1709. Available starting with Windows 10, version 1709. |
| **Header** | ntddscsi.h |