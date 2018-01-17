---
UID: NS:ntddrilapitypes.RILSYSTEMSELECTIONPREFS_V1
title: RILSYSTEMSELECTIONPREFS_V1
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsystemselectionprefs_v1.htm
old-project: netvista
ms.assetid: a2ba47e6-9dec-46b4-ac8b-a863345f228f
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILSYSTEMSELECTIONPREFS_V1, RILSYSTEMSELECTIONPREFS_V1, *LPRILSYSTEMSELECTIONPREFS_V1
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
req.alt-api: RILSYSTEMSELECTIONPREFS_V1
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
req.typenames: RILSYSTEMSELECTIONPREFS_V1, *LPRILSYSTEMSELECTIONPREFS_V1
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
