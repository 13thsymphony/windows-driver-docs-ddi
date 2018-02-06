---
UID: NE:nfcsedev._SECURE_ELEMENT_TYPE
title: "_SECURE_ELEMENT_TYPE"
author: windows-driver-content
description: Indicates the type of a secure element.
old-location: nfpdrivers\_secure_element_type.htm
old-project: nfpdrivers
ms.assetid: 118B63D1-713A-4F8C-B97A-53BB6D0B819E
ms.author: windowsdriverdev
ms.date: 12/18/2017
ms.keywords: nfcsedev/_SECURE_ELEMENT_TYPE, SECURE_ELEMENT_TYPE, *PSECURE_ELEMENT_TYPE, nfpdrivers._secure_element_type, _SECURE_ELEMENT_TYPE, SECURE_ELEMENT_TYPE, Integrated, nfcsedev/External, nfcsedev/DeviceHost, DeviceHost, External, nfcsedev/Integrated, *PSECURE_ELEMENT_TYPE, _SECURE_ELEMENT_TYPE enumeration [Near-Field Proximity Drivers], SECURE_ELEMENT_TYPE, *PSECURE_ELEMENT_TYPE enumeration [Near-Field Proximity Drivers]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: nfcsedev.h
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
-	nfcsedev.h
apiname:
-	SECURE_ELEMENT_TYPE, *PSECURE_ELEMENT_TYPE
product: Windows
targetos: Windows
req.typenames: "*PSECURE_ELEMENT_TYPE, SECURE_ELEMENT_TYPE"
---

# _SECURE_ELEMENT_TYPE Enumeration
Indicates the type of a secure element.

## Syntax
````
typedef enum _SECURE_ELEMENT_TYPE { 
  Integrated  = 0,
  External    = 1,
  DeviceHost  = 2
} SECURE_ELEMENT_TYPE, *PSECURE_ELEMENT_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>DeviceHost</td>
                    <td>Separate HCE-based secure element.</td>
                </tr>
            
                <tr>
                    <td>External</td>
                    <td>Separate UICC-based secure element.</td>
                </tr>
            
                <tr>
                    <td>Integrated</td>
                    <td>Integrated secure element.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | nfcsedev.h |