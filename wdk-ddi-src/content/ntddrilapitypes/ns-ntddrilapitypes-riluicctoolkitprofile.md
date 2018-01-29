---
UID : NS:ntddrilapitypes.RILUICCTOOLKITPROFILE
title : RILUICCTOOLKITPROFILE
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\riluicctoolkitprofile.htm
old-project : netvista
ms.assetid : ff1f5839-78be-48ab-9c26-f8fee6788d51
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : netvista.riluicctoolkitprofile, ntddrilapitypes/RILUICCTOOLKITPROFILE, RILUICCTOOLKITPROFILE, RILUICCTOOLKITPROFILE structure [Network Drivers Starting with Windows Vista], *LPRILUICCTOOLKITPROFILE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ntddrilapitypes.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*LPRILUICCTOOLKITPROFILE, RILUICCTOOLKITPROFILE"
---

# RILUICCTOOLKITPROFILE structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILUICCTOOLKITPROFILE {
  DWORD    cbSize;
  DWORD    dwProfileSize;
  BYTE [1] bProfile;
} RILUICCTOOLKITPROFILE, RILUICCTOOLKITPROFILE;
````

## Members


`bProfile`



`cbSize`



`dwProfileSize`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddrilapitypes.h |