---
UID: NE:ntddscsi._MP_STORAGE_DIAGNOSTIC_LEVEL
title: "_MP_STORAGE_DIAGNOSTIC_LEVEL"
author: windows-driver-content
description: The MP_STORAGE_DIAGNOSTIC_LEVEL enumeration allows the caller to control what kinds of data the provider should return.
old-location: storage\mp_storage_diagnostic_level.htm
old-project: storage
ms.assetid: BB05D543-7B99-481E-8CDB-AE350CBCCA2A
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: PMP_STORAGE_DIAGNOSTIC_LEVEL, *PMP_STORAGE_DIAGNOSTIC_LEVEL, _MP_STORAGE_DIAGNOSTIC_LEVEL, ntddscsi/PMP_STORAGE_DIAGNOSTIC_LEVEL, StorageDiagnosticLevelMax, PMP_STORAGE_DIAGNOSTIC_LEVEL enumeration pointer [Storage Devices], ntddscsi/StorageDiagnosticLevelDefault, MP_STORAGE_DIAGNOSTIC_LEVEL, MP_STORAGE_DIAGNOSTIC_LEVEL enumeration [Storage Devices], StorageDiagnosticLevelDefault, ntddscsi/MP_STORAGE_DIAGNOSTIC_LEVEL, storage.mp_storage_diagnostic_level, ntddscsi/StorageDiagnosticLevelMax
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddscsi.h
apiname:
-	MP_STORAGE_DIAGNOSTIC_LEVEL
product: Windows
targetos: Windows
req.typenames: "*PMP_STORAGE_DIAGNOSTIC_LEVEL, MP_STORAGE_DIAGNOSTIC_LEVEL"
---

# _MP_STORAGE_DIAGNOSTIC_LEVEL Enumeration
The <b>MP_STORAGE_DIAGNOSTIC_LEVEL</b> enumeration allows the caller to control what kinds of data the provider should return.

## Syntax
````
typedef enum _MP_STORAGE_DIAGNOSTIC_LEVEL { 
  StorageDiagnosticLevelDefault  = 0,
  StorageDiagnosticLevelMax
} MP_STORAGE_DIAGNOSTIC_LEVEL, *PMP_STORAGE_DIAGNOSTIC_LEVEL;
````

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