---
UID: NF:nfccx.NFC_CX_CLIENT_CONFIG_INIT
title: NFC_CX_CLIENT_CONFIG_INIT function
author: windows-driver-content
description: The NFC_CX_CLIENT_CONFIG_INIT function initializes the NFC_CX_CLIENT_CONFIG structure.
old-location: nfpdrivers\nfc_cx_client_config_init.htm
old-project: nfpdrivers
ms.assetid: 0679406E-091D-4E66-956A-54E3A517BF4C
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: NFC_CX_CLIENT_CONFIG_INIT, NFC_CX_CLIENT_CONFIG_INIT function [Near-Field Proximity Drivers], nfccx/NFC_CX_CLIENT_CONFIG_INIT, nfpdrivers.nfc_cx_client_config_init
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: nfccx.h
req.include-header: Ncidef.h
req.target-type: Desktop
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
req.lib: Nfccxstub.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	nfccxstub.lib
-	nfccxstub.dll
api_name:
-	NFC_CX_CLIENT_CONFIG_INIT
product: Windows
targetos: Windows
req.typenames: NFC_CX_TRANSPORT_TYPE, *PNFC_CX_TRANSPORT_TYPE
---


# NFC_CX_CLIENT_CONFIG_INIT function
The <b>NFC_CX_CLIENT_CONFIG_INIT</b> function initializes the <a href="https://msdn.microsoft.com/library/windows/hardware/dn905540">NFC_CX_CLIENT_CONFIG</a> structure.

## Syntax

```
void NFC_CX_CLIENT_CONFIG_INIT(
  PNFC_CX_CLIENT_CONFIG Config,
  NFC_CX_TRANSPORT_TYPE BusType
);
```

## Parameters

`Config`

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/dn905540">NFC_CX_CLIENT_CONFIG</a> structure.

`BusType`

An <a href="https://msdn.microsoft.com/library/windows/hardware/dn905564">NFC_CX_TRANSPORT_TYPE</a> enumeration.


## Return Value

This function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | nfccx.h (include Ncidef.h) |
| **Library** | Nfccxstub.lib |

## See Also

<a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>



<a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>