---
UID: NC:d3dumddi.PFND3DDDI_EVICTCB
title: PFND3DDDI_EVICTCB
author: windows-driver-content
description: pfnEvictCb is used to instruct the OS to decrement the residency reference count. Once this count reaches zero, it will remove the allocation from the device residency list.
old-location: display\pfnevictcb.htm
old-project: display
ms.assetid: 5E66A522-BC1C-4E7C-8732-87D40F99BBDA
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3DDDI_EVICTCB, d3dumddi/pfnEvictCb, display.pfnevictcb, pfnEvictCb, pfnEvictCb callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	pfnEvictCb
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_EVICTCB callback function
<b>pfnEvictCb</b> is used to instruct the OS to decrement the residency reference count. Once this count reaches zero, it will remove the allocation from the device residency list.

## Syntax

```
PFND3DDDI_EVICTCB Pfnd3dddiEvictcb;

HRESULT Pfnd3dddiEvictcb(
  HANDLE hDevice,
  D3DDDICB_EVICT *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device.

`*`




## Return Value

If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

## Remarks

Once the eviction request is queued, it is illegal to access the underlying allocation as the allocation may be evicted at anytime from there on at the operating system discretion.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn906762">D3DDDICB_EVICT</a>