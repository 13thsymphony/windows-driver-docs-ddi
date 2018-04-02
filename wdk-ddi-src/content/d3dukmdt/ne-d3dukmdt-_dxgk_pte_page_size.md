---
UID: NE:d3dukmdt._DXGK_PTE_PAGE_SIZE
title: "_DXGK_PTE_PAGE_SIZE"
author: windows-driver-content
description: The DXGK_PTE_PAGE_SIZE enumeration is used by DXGK_PTE to indicate the size of lower page level pages.
old-location: display\dxgk_pte_page_size.htm
old-project: display
ms.assetid: 54ADAD37-C479-4F07-B0DD-CDF25AA4390C
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGK_PTE_PAGE_SIZE, DXGK_PTE_PAGE_SIZE enumeration [Display Devices], DXGK_PTE_PAGE_TABLE_PAGE_4KB, DXGK_PTE_PAGE_TABLE_PAGE_64KB, _DXGK_PTE_PAGE_SIZE, d3dukmdt/DXGK_PTE_PAGE_SIZE, d3dukmdt/DXGK_PTE_PAGE_TABLE_PAGE_4KB, d3dukmdt/DXGK_PTE_PAGE_TABLE_PAGE_64KB, display.dxgk_pte_page_size
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dukmdt.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dukmdt.h
api_name:
-	DXGK_PTE_PAGE_SIZE
product:
- Windows
targetos: Windows
req.typenames: DXGK_PTE_PAGE_SIZE
---

# _DXGK_PTE_PAGE_SIZE Enumeration
The <b>DXGK_PTE_PAGE_SIZE </b>enumeration is used by <a href="https://msdn.microsoft.com/library/windows/hardware/ff562008">DXGK_PTE</a> to indicate the size of lower page level pages.

## Syntax
```
typedef enum _DXGK_PTE_PAGE_SIZE {
  DXGK_PTE_PAGE_TABLE_PAGE_4KB   ,
  DXGK_PTE_PAGE_TABLE_PAGE_64KB
} DXGK_PTE_PAGE_SIZE;
```

## Constants

<table>
            
                <tr>
                    <td>DXGK_PTE_PAGE_TABLE_PAGE_4KB</td>
                    <td>Indicates the lower page table level uses 4 KB pages.</td>
                </tr>
            
                <tr>
                    <td>DXGK_PTE_PAGE_TABLE_PAGE_64KB</td>
                    <td>Indicates the lower page table level uses 64 KB pages.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | d3dukmdt.h (include D3dkmddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff562008">DXGK_PTE</a>