---
UID: NS:d3dkmthk._D3DKMT_ADAPTERREGISTRYINFO
title: "_D3DKMT_ADAPTERREGISTRYINFO"
author: windows-driver-content
description: The D3DKMT_ADAPTERREGISTRYINFO structure contains registry information about the graphics adapter.
old-location: display\d3dkmt_adapterregistryinfo.htm
old-project: display
ms.assetid: b1bad6e8-8592-457a-8f66-40fc5040ae96
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMT_ADAPTERREGISTRYINFO, D3DKMT_ADAPTERREGISTRYINFO structure [Display Devices], OpenGL_Structs_0d97d602-7fc3-40a2-aa06-2966a6fc04f7.xml, _D3DKMT_ADAPTERREGISTRYINFO, d3dkmthk/D3DKMT_ADAPTERREGISTRYINFO, display.d3dkmt_adapterregistryinfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmthk.h
api_name:
-	D3DKMT_ADAPTERREGISTRYINFO
product: Windows
targetos: Windows
req.typenames: D3DKMT_ADAPTERREGISTRYINFO
---

# _D3DKMT_ADAPTERREGISTRYINFO structure
The D3DKMT_ADAPTERREGISTRYINFO structure contains registry information about the graphics adapter.

## Syntax
````
typedef struct _D3DKMT_ADAPTERREGISTRYINFO {
  WCHAR AdapterString[MAX_PATH];
  WCHAR BiosString[MAX_PATH];
  WCHAR DacType[MAX_PATH];
  WCHAR ChipType[MAX_PATH];
} D3DKMT_ADAPTERREGISTRYINFO;
````

## Members


`AdapterString`

[out] A string that contains the name of the graphics adapter.

`BiosString`

[out] A string that contains the name of the BIOS for the graphics adapter.

`DacType`

[out] A string that contains the DAC type for the graphics adapter.

`ChipType`

[out] A string that contains the chip type for the graphics adapter.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_queryadapterinfo.md">D3DKMT_QUERYADAPTERINFO</a>



<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtqueryadapterinfo.md">D3DKMTQueryAdapterInfo</a>