---
UID: NE:wdm._IO_ACCESS_MODE
title: "_IO_ACCESS_MODE"
author: windows-driver-content
description: Defines the types of access mode for Scheduled File I/O (SFIO).
old-location: kernel\io_access_mode.htm
old-project: kernel
ms.assetid: E48BDF14-5B56-45AF-9DD2-F019C8B7D7E5
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: IO_ACCESS_MODE, IO_ACCESS_MODE enumeration [Kernel-Mode Driver Architecture], RandomAccess, SequentialAccess, _IO_ACCESS_MODE, kernel.io_access_mode, wdm/IO_ACCESS_MODE, wdm/RandomAccess, wdm/SequentialAccess
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h, Ntddsfio.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	IO_ACCESS_MODE
product: Windows
targetos: Windows
req.typenames: IO_ACCESS_MODE
req.product: Windows 10 or later.
---

# _IO_ACCESS_MODE Enumeration
Defines the types of access mode for Scheduled File I/O (SFIO).

## Syntax
````
typedef enum _IO_ACCESS_MODE { 
  SequentialAccess,
  RandomAccess
} IO_ACCESS_MODE;
````

## Constants

<table>
            
                <tr>
                    <td>RandomAccess</td>
                    <td>Indicates that the input/output might not be in a predictable order.</td>
                </tr>
            
                <tr>
                    <td>SequentialAccess</td>
                    <td>Indicates that the input/output will be sent down in a sequential order.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wdm.h (include Wdm.h, Ntddsfio.h) |