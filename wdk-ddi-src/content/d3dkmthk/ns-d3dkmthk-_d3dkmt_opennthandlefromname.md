---
UID: NS:d3dkmthk._D3DKMT_OPENNTHANDLEFROMNAME
title: "_D3DKMT_OPENNTHANDLEFROMNAME"
author: windows-driver-content
description: Describes information that is required to open an NT handle to the process from a graphics adapter name.
old-location: display\d3dkmt_opennthandlefromname.htm
old-project: display
ms.assetid: 34f70519-7905-4a16-bd07-db3592b05890
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: D3DKMT_OPENNTHANDLEFROMNAME structure [Display Devices], D3DKMT_OPENNTHANDLEFROMNAME, _D3DKMT_OPENNTHANDLEFROMNAME, d3dkmthk/D3DKMT_OPENNTHANDLEFROMNAME, display.d3dkmt_opennthandlefromname
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3dkmthk.h
apiname:
-	D3DKMT_OPENNTHANDLEFROMNAME
product: Windows
targetos: Windows
req.typenames: D3DKMT_OPENNTHANDLEFROMNAME
---

# _D3DKMT_OPENNTHANDLEFROMNAME structure
Describes information that is required to open an NT handle to the process from a graphics adapter name.

## Syntax
````
typedef struct _D3DKMT_OPENNTHANDLEFROMNAME {
  DWORD             dwDesiredAccess;
  OBJECT_ATTRIBUTES *pObjAttrib;
  HANDLE            hNtHandle;
} D3DKMT_OPENNTHANDLEFROMNAME;
````

## Members


`dwDesiredAccess`

[in] Specifies read and write access for the resource.

`hNtHandle`

[out] An NT handle to the process.

`pObjAttrib`

[in] A pointer to an <a href="..\wudfwdm\ns-wudfwdm-_object_attributes.md">OBJECT_ATTRIBUTES</a> structure that specifies attributes of the adapter, including its name.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |