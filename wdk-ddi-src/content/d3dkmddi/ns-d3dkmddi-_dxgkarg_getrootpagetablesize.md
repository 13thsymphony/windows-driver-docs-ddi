---
UID: NS:d3dkmddi._DXGKARG_GETROOTPAGETABLESIZE
title: "_DXGKARG_GETROOTPAGETABLESIZE"
author: windows-driver-content
description: DXGKARG_GETROOTPAGETABLESIZE is used with DxgkDdiGetRootPageTableSize.
old-location: display\dxgkarg_getrootpagetablesize.htm
old-project: display
ms.assetid: 31CB33F9-87E8-419D-AF35-E7F731661DD5
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.dxgkarg_getrootpagetablesize, *INOUT_PDXGKARG_GETROOTPAGETABLESIZE, d3dkmddi/DXGKARG_GETROOTPAGETABLESIZE, _DXGKARG_GETROOTPAGETABLESIZE, DXGKARG_GETROOTPAGETABLESIZE, DXGKARG_GETROOTPAGETABLESIZE structure [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGKARG_GETROOTPAGETABLESIZE
product: Windows
targetos: Windows
req.typenames: DXGKARG_GETROOTPAGETABLESIZE
---

# _DXGKARG_GETROOTPAGETABLESIZE structure
<b>DXGKARG_GETROOTPAGETABLESIZE</b> is used with <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_getrootpagetablesize.md">DxgkDdiGetRootPageTableSize</a>.

## Syntax
````
typedef struct _DXGKARG_GETROOTPAGETABLESIZE {
  UINT NumberOfPte;
  UINT PhysicalAdapterIndex;
} DXGKARG_GETROOTPAGETABLESIZE;
````

## Members


`NumberOfPte`

[in] A pointer to the number of page table entries which are required to be in the root page table.

[out] The actual number of page table entries in the page table with the returned size.

`PhysicalAdapterIndex`

Physical adapter index (zero for non-linked display adapter configurations).


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |

## See Also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_getrootpagetablesize.md">DxgkDdiGetRootPageTableSize</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_GETROOTPAGETABLESIZE structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>