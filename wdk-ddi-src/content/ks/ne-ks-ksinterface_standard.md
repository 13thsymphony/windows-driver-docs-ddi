---
UID: NE:ks.KSINTERFACE_STANDARD
title: KSINTERFACE_STANDARD
author: windows-driver-content
description: "."
old-location: stream\ksinterface_standard.htm
old-project: stream
ms.assetid: B000E3BD-28FA-454E-A598-3670B5FCD3DD
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: KSINTERFACE_STANDARD_LOOPED_STREAMING, ks/KSINTERFACE_STANDARD_LOOPED_STREAMING, ks/KSINTERFACE_STANDARD_CONTROL, KSINTERFACE_STANDARD enumeration [Streaming Media Devices], ks/KSINTERFACE_STANDARD, stream.ksinterface_standard, KSINTERFACE_STANDARD_STREAMING, KSINTERFACE_STANDARD_CONTROL, KSINTERFACE_STANDARD, ks/KSINTERFACE_STANDARD_STREAMING
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ks.h
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
-	Ks.h
apiname:
-	KSINTERFACE_STANDARD
product: Windows
targetos: Windows
req.typenames: KSINTERFACE_STANDARD
---

# KSINTERFACE_STANDARD Enumeration


## Syntax
````
typedef enum  { 
  KSINTERFACE_STANDARD_STREAMING,
  KSINTERFACE_STANDARD_LOOPED_STREAMING,
  KSINTERFACE_STANDARD_CONTROL
} KSINTERFACE_STANDARD;
````

## Constants

<table>
            
                <tr>
                    <td>KSINTERFACE_STANDARD_CONTROL</td>
                    <td>Reserved for system use.</td>
                </tr>
            
                <tr>
                    <td>KSINTERFACE_STANDARD_LOOPED_STREAMING</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>KSINTERFACE_STANDARD_STREAMING</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ks.h |