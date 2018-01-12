---
UID: NS:ucmtcpciglobals._UCMTCPCI_DRIVER_GLOBALS
title: _UCMTCPCI_DRIVER_GLOBALS
author: windows-driver-content
description: The global structure for the USB Type-C Port Controller Interface framework extension (UcmTcpciCx).
old-location: buses\ucmtcpci_driver_globals.htm
old-project: usbref
ms.assetid: 75a0e9ef-0791-4465-b671-36c86dc9116a
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _UCMTCPCI_DRIVER_GLOBALS, UCMTCPCI_DRIVER_GLOBALS, *PUCMTCPCI_DRIVER_GLOBALS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucmtcpciglobals.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UCMTCPCI_DRIVER_GLOBALS
req.alt-loc: Ucmtcpciglobals.h
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
req.typenames: UCMTCPCI_DRIVER_GLOBALS, *PUCMTCPCI_DRIVER_GLOBALS
req.product: Windows 10 or later.
---

# _UCMTCPCI_DRIVER_GLOBALS structure



## -description

             The global structure for the  USB Type-C Port Controller Interface framework extension (UcmTcpciCx).
         



## -syntax

````
typedef struct _UCMTCPCI_DRIVER_GLOBALS {
  ULONG Reserved;
} UCMTCPCI_DRIVER_GLOBALS, *UCMTCPCI_DRIVER_GLOBALS;
````


## -struct-fields

### -field Reserved


                     Reserved.
                 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ucmtcpciglobals.h</dt>
</dl>
</td>
</tr>
</table>