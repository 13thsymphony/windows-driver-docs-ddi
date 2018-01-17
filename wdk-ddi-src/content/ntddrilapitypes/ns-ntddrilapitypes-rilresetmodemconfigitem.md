---
UID: NS:ntddrilapitypes.RILRESETMODEMCONFIGITEM
title: RILRESETMODEMCONFIGITEM
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilresetmodemconfigitem.htm
old-project: netvista
ms.assetid: 4e823f87-662c-491f-b368-f853f381e4b8
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILRESETMODEMCONFIGITEM, *LPRILRESETMODEMCONFIGITEM, RILRESETMODEMCONFIGITEM
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILRESETMODEMCONFIGITEM
req.alt-loc: ntddrilapitypes.h
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
req.typenames: *LPRILRESETMODEMCONFIGITEM, RILRESETMODEMCONFIGITEM
---

# RILRESETMODEMCONFIGITEM structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILRESETMODEMCONFIGITEM {
  DWORD                     dwModemConfigItem;
  RILRESETMODEMCONFIGVALUE  rrmcValue;
} RILRESETMODEMCONFIGITEM, RILRESETMODEMCONFIGITEM;
````


## -struct-fields

### -field dwModemConfigItem


### -field rrmcValue


## -remarks
