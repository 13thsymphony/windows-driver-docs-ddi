---
UID: NE:ehstorioctl._PDO_CAPS
title: "_PDO_CAPS"
author: windows-driver-content
description: This enumeration describes the capabilities of Physical Device Objects (PDOs).
old-location: storage\pdo_caps.htm
old-project: storage
ms.assetid: 78b6f3c7-bb42-4e93-8128-28b6f8e11dda
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PDO_CAPABILITY_INC512_CLEAR, PDO_CAPABILITY_INC512_SET, PDO_CAPABILITY_UNDEFINED, PDO_CAPS, PDO_CAPS enumeration [Storage Devices], _PDO_CAPS, ehstorioctl/PDO_CAPABILITY_INC512_CLEAR, ehstorioctl/PDO_CAPABILITY_INC512_SET, ehstorioctl/PDO_CAPABILITY_UNDEFINED, ehstorioctl/PDO_CAPS, storage.pdo_caps, structs-silo_bb81f7e7-c317-4937-87de-b38832944fe5.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ehstorioctl.h
req.include-header: EhStorIoctl.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	EhStorIoctl.h
api_name:
-	PDO_CAPS
product: Windows
targetos: Windows
req.typenames: PDO_CAPS
---

# _PDO_CAPS Enumeration
This enumeration describes the capabilities of Physical Device Objects (PDOs).

## Syntax
```
typedef enum _PDO_CAPS {
  PDO_CAPABILITY_UNDEFINED     ,
  PDO_CAPABILITY_INC512_SET    ,
  PDO_CAPABILITY_INC512_CLEAR
} PDO_CAPS;
```

## Constants

<table>
            
                <tr>
                    <td>PDO_CAPABILITY_UNDEFINED</td>
                    <td>Command data block size granularity is undefined.</td>
                </tr>
            
                <tr>
                    <td>PDO_CAPABILITY_INC512_SET</td>
                    <td>Command data block size granularity of 512 bytes is supported.</td>
                </tr>
            
                <tr>
                    <td>PDO_CAPABILITY_INC512_CLEAR</td>
                    <td>Command data block size granularity of 1 byte is supported.</td>
                </tr>
</table>

## Remarks

A silo must support either PDO_CAPABILITY_INC512_SET or PDO_CAPABILITY_INC512_CLEAR. It may also indicate that both values are supported by returning a logical OR of these two bits.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ehstorioctl.h (include EhStorIoctl.h) |