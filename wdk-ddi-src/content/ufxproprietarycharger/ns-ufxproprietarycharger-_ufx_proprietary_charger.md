---
UID: NS:ufxproprietarycharger._UFX_PROPRIETARY_CHARGER
title: _UFX_PROPRIETARY_CHARGER
author: windows-driver-content
description: Describes the proprietary charger's device power requirements.
old-location: buses\ufx_proprietary_charger.htm
old-project: usbref
ms.assetid: FAAEDAFE-69A8-4092-8301-DB159FD3583D
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _UFX_PROPRIETARY_CHARGER, UFX_PROPRIETARY_CHARGER, *PUFX_PROPRIETARY_CHARGER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ufxproprietarycharger.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UFX_PROPRIETARY_CHARGER
req.alt-loc: ufxproprietarycharger.h
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
req.typenames: UFX_PROPRIETARY_CHARGER, *PUFX_PROPRIETARY_CHARGER
req.product: Windows 10 or later.
---

# _UFX_PROPRIETARY_CHARGER structure



## -description
Describes the proprietary charger's device power requirements.



## -syntax

````
typedef struct _UFX_PROPRIETARY_CHARGER {
  GUID               ChargerId;
  DEVICE_POWER_STATE DxState;
} UFX_PROPRIETARY_CHARGER, *PUFX_PROPRIETARY_CHARGER;
````


## -struct-fields

### -field ChargerId

Charger identifier used to identify a specific type of charger.


### -field DxState

The minimum required device power state when it is connected, indicated by one of the <a href="..\wudfddi\ne-wudfddi-_device_power_state.md">DEVICE_POWER_STATE</a>-typed flags.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ufxproprietarycharger.h</dt>
</dl>
</td>
</tr>
</table>