---
UID: NS:rilapitypes.RILCAPSLOCKINGPWDLENGTH
title: RILCAPSLOCKINGPWDLENGTH
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcapslockingpwdlength_2.htm
old-project: netvista
ms.assetid: 7ab6ea03-cfe6-4679-91ff-e52aae7a5200
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILCAPSLOCKINGPWDLENGTH, *LPRILCAPSLOCKINGPWDLENGTH, RILCAPSLOCKINGPWDLENGTH
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
req.alt-api: RILCAPSLOCKINGPWDLENGTH
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
req.typenames: *LPRILCAPSLOCKINGPWDLENGTH, RILCAPSLOCKINGPWDLENGTH
req.product: Windows 10 or later.
---

# RILCAPSLOCKINGPWDLENGTH structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILCAPSLOCKINGPWDLENGTH {
  DWORD  cbSize;
  DWORD  dwParams;
  DWORD  dwPersoFeature;
  DWORD  dwPasswordLength;
} RILCAPSLOCKINGPWDLENGTH, RILCAPSLOCKINGPWDLENGTH;
````


## -struct-fields

### -field cbSize


### -field dwParams


### -field dwPersoFeature


### -field dwPasswordLength


## -remarks
