---
UID: NS:rilapitypes.RILRADIOSTATEGROUP
title: RILRADIOSTATEGROUP
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilradiostategroup_2.htm
old-project: netvista
ms.assetid: ce8cf743-4386-4afb-87d3-93f9a83bd632
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILRADIOSTATEGROUP, *LPRILRADIOSTATEGROUP, RILRADIOSTATEGROUP
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILRADIOSTATEGROUP
req.alt-loc: rilapitypes.h
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
req.typenames: *LPRILRADIOSTATEGROUP, RILRADIOSTATEGROUP
req.product: Windows 10 or later.
---

# RILRADIOSTATEGROUP structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILRADIOSTATEGROUP {
  DWORD                            dwGroupId;
  DWORD                            dwGroupType;
  DWORD                            dwGroupFlags;
  WCHAR [MAXLENGTH_RADIOGROUPTEXT] wszGroupText;
} RILRADIOSTATEGROUP, RILRADIOSTATEGROUP;
````


## -struct-fields

### -field dwGroupId


### -field dwGroupType


### -field dwGroupFlags


### -field wszGroupText


## -remarks
