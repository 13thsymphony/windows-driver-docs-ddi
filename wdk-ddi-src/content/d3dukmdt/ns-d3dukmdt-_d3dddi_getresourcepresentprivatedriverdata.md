---
UID: NS:d3dukmdt._D3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATA
title: "_D3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATA"
author: windows-driver-content
description: D3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATA is used with pfnGetResourcePresentPrivateDriverDataCb to query the resource private data, which is associated with the resource during Present.
old-location: display\d3dddi_getresourcepresentprivatedriverdata.htm
old-project: display
ms.assetid: 4473E808-D22E-47C4-8619-7427C8BA682E
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3dddi_getresourcepresentprivatedriverdata, _D3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATA, D3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATA structure [Display Devices], D3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATA, d3dukmdt/D3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	d3dukmdt.h
apiname:
-	D3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATA
product: Windows
targetos: Windows
req.typenames: D3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATA
---

# _D3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATA structure
<b>D3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATA</b> is used with <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getresourcepresentprivatedriverdatacb.md">pfnGetResourcePresentPrivateDriverDataCb</a> to query the resource private data, which is associated with the resource during Present.

## Syntax
````
typedef struct _D3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATA {
  D3DKMT_HANDLE hResource;
  UINT          PrivateDriverDataSize;
  PVOID         *pPrivateDriverData;
} D3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATA;
````

## Members


`hResource`

[in] A DirectX graphics kernel resource handle.

`pPrivateDriverData`

[in, out] The buffer where the private data will be written to.

`PrivateDriverDataSize`

[in, out] The size of the <b>pPrivateDriverData</b> buffer in bytes. When zero or when there is insufficient space, the size of the required buffer is returned back to the caller along with a <b>STATUS_INVALID_BUFFER_SIZE</b><b>HRESULT</b> value from the calling method. 
<div class="alert"><b>Note</b>  By the time another call is made with the new buffer size, the resource could be associated with a different sized buffer.</div><div> </div>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | d3dukmdt.h (include D3dumddi.h, D3dkmddi.h) |

## See Also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getresourcepresentprivatedriverdatacb.md">pfnGetResourcePresentPrivateDriverDataCb</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATA structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>