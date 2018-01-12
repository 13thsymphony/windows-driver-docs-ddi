---
UID: NE:winsplp._NOTIFICATION_CONFIG_FLAGS
title: _NOTIFICATION_CONFIG_FLAGS
author: windows-driver-content
description: .
old-location: print\notification_config_flags.htm
old-project: print
ms.assetid: B53AB706-D780-4E29-A531-51D3A9041D24
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: _NOTIFICATION_CONFIG_FLAGS, NOTIFICATION_CONFIG_FLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: winsplp.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NOTIFICATION_CONFIG_FLAGS
req.alt-loc: Winsplp.h
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
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---

# _NOTIFICATION_CONFIG_FLAGS enumeration



## -description




## -syntax

````
typedef enum _NOTIFICATION_CONFIG_FLAGS { 
  NOTIFICATION_CONFIG_CREATE_EVENT       = 1 << 0,
  NOTIFICATION_CONFIG_REGISTER_CALLBACK  = 1 << 1,
  NOTIFICATION_CONFIG_EVENT_TRIGGER      = 1 << 2,
  NOTIFICATION_CONFIG_ASYNC_CHANNEL      = 1 << 3
} NOTIFICATION_CONFIG_FLAGS;
````


## -enum-fields

### -field NOTIFICATION_CONFIG_CREATE_EVENT


### -field NOTIFICATION_CONFIG_REGISTER_CALLBACK


### -field NOTIFICATION_CONFIG_EVENT_TRIGGER


### -field NOTIFICATION_CONFIG_ASYNC_CHANNEL


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Winsplp.h</dt>
</dl>
</td>
</tr>
</table>