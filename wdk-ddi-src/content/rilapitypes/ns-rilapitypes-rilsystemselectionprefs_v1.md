---
UID: NS:rilapitypes.RILSYSTEMSELECTIONPREFS_V1
title: RILSYSTEMSELECTIONPREFS_V1
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsystemselectionprefs_v1_2.htm
old-project: netvista
ms.assetid: 19af0039-a2dd-49a4-ad93-1858288d00cd
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILSYSTEMSELECTIONPREFS_V1, RILSYSTEMSELECTIONPREFS_V1, *LPRILSYSTEMSELECTIONPREFS_V1
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
req.alt-api: RILSYSTEMSELECTIONPREFS_V1
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
req.typenames: RILSYSTEMSELECTIONPREFS_V1, *LPRILSYSTEMSELECTIONPREFS_V1
req.product: Windows 10 or later.
---

# RILSYSTEMSELECTIONPREFS_V1 structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILSYSTEMSELECTIONPREFS_V1 {
  DWORD                               cbSize;
  DWORD                               dwParams;
  DWORD                               dwExecutor;
  DWORD                               dwSystemTypes;
  RILSYSTEMSELECTIONPREFSMODE         dwMode;
  RILOPERATORNAMES                    plmnInfo;
  RILSYSTEMSELECTIONPREFSROAMINGMODE  dwRoamingMode;
} RILSYSTEMSELECTIONPREFS_V1, RILSYSTEMSELECTIONPREFS_V1;
````


## -struct-fields

### -field cbSize


### -field dwParams


### -field dwExecutor


### -field dwSystemTypes


### -field dwMode


### -field plmnInfo


### -field dwRoamingMode


## -remarks
