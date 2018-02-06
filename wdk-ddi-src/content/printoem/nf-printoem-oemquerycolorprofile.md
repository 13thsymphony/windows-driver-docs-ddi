---
UID: NF:printoem.OEMQueryColorProfile
title: OEMQueryColorProfile function
author: windows-driver-content
description: OEMQueryColorProfile function
old-location: print\oemquerycolorprofile.htm
old-project: print
ms.assetid: a33a216d-f97e-44be-b9a5-bdadf1c422e1
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: OEMQueryColorProfile, print_obsoletefunctions_f21cf62d-45bd-4248-8b0c-a19cc982ad3c.xml, print.oemquerycolorprofile, OEMQueryColorProfile function [Print Devices], printoem/OEMQueryColorProfile
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: printoem.h
req.include-header: Printoem.h
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
-	printoem.h
apiname:
-	OEMQueryColorProfile
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---


# OEMQueryColorProfile function


## Syntax

````
BOOL APIENTRY OEMQueryColorProfile(
        HANDLE                               hPrinter,
        POEMUIOBJ                            poemuiobj,
        PDEVMODE                             pPublicDM,
        PVOID                                pOEMDM,
        ULONG                                ulQueryMode,
  _Out_ _writes_bytes_(*pcbProfileData) VOID *pvProfileData,
  _Out_ ULONG                                *pcbProfileData,
  _Out_ FLONG                                *pflProfileData
);
````

## Parameters

`hPrinter`



`poemuiobj`



`pPublicDM`



`pOEMDM`



`ulQueryMode`



`pvProfileData`



`pcbProfileData`



`pflProfileData`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | printoem.h (include Printoem.h) |
| **Library** | NtosKrnl.exe |