---
UID: NE:rilapitypes.RIL3GPPTONE
title: RIL3GPPTONE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril3gpptone_2.htm
old-project: netvista
ms.assetid: 05981a37-ce5c-4214-82b7-c8705102bd6a
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ril3gpptone_2, RIL_3GPPTONE_BUSY, RIL_3GPPTONE_CONGESTION, RIL_3GPPTONE_NUMBERUNOBTAINABLE, RIL_3GPPTONE_MAX, RIL3GPPTONE enumeration [Network Drivers Starting with Windows Vista], RIL_3GPPTONE_CALLDROPPED, rilapitypes/RIL_3GPPTONE_BUSY, rilapitypes/RIL_3GPPTONE_CALLDROPPED, rilapitypes/RIL_3GPPTONE_RINGBACK, RIL3GPPTONE, rilapitypes/RIL_3GPPTONE_NUMBERUNOBTAINABLE, rilapitypes/RIL3GPPTONE, rilapitypes/RIL_3GPPTONE_MAX, RIL_3GPPTONE_AUTHENTICATIONFAILURE, RIL_3GPPTONE_RINGBACK, rilapitypes/RIL_3GPPTONE_CONGESTION, rilapitypes/RIL_3GPPTONE_AUTHENTICATIONFAILURE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapitypes.h
apiname:
-	RIL3GPPTONE
product: Windows
targetos: Windows
req.typenames: RIL3GPPTONE
req.product: Windows 10 or later.
---

# RIL3GPPTONE Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RIL3GPPTONE { 
  RIL_3GPPTONE_RINGBACK,
  RIL_3GPPTONE_BUSY,
  RIL_3GPPTONE_CONGESTION,
  RIL_3GPPTONE_AUTHENTICATIONFAILURE,
  RIL_3GPPTONE_NUMBERUNOBTAINABLE,
  RIL_3GPPTONE_CALLDROPPED,
  RIL_3GPPTONE_MAX
} RIL3GPPTONE;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_3GPPTONE_AUTHENTICATIONFAILURE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_3GPPTONE_BUSY</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_3GPPTONE_CALLDROPPED</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_3GPPTONE_CONGESTION</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_3GPPTONE_MAX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_3GPPTONE_NUMBERUNOBTAINABLE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_3GPPTONE_RINGBACK</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_3GPPTONE_TONEOFF</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |