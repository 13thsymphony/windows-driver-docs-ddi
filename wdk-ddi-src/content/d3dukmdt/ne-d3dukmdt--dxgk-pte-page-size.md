---
UID: NE.d3dukmdt._DXGK_PTE_PAGE_SIZE
title: DXGK_PTE_PAGE_SIZE
author: windows-driver-content
description: The DXGK_PTE_PAGE_SIZE enumeration is used by DXGK_PTE to indicate the size of lower page level pages.
old-location: display\dxgk_pte_page_size.htm
old-project: display
ms.assetid: 54ADAD37-C479-4F07-B0DD-CDF25AA4390C
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DKMT_PRESENT_MULTIPLANE_OVERLAY, D3DKMT_PRESENT_MULTIPLANE_OVERLAY
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
req.alt-api: DXGK_PTE_PAGE_SIZE
req.alt-loc: d3dukmdt.h
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
req.iface: 
---

# DXGK_PTE_PAGE_SIZE enumeration



## -description
<p>The <b>DXGK_PTE_PAGE_SIZE </b>enumeration is used by <a href="..\d3dukmdt\ns-d3dukmdt--dxgk-pte.md">DXGK_PTE</a> to indicate the size of lower page level pages. </p>


## -syntax

````
typedef enum _DXGK_PTE_PAGE_SIZE { 
  DXGK_PTE_PAGE_TABLE_PAGE_4KB   = 0,
  DXGK_PTE_PAGE_TABLE_PAGE_64KB  = 1
} DXGK_PTE_PAGE_SIZE;
````


## -enum-fields
<dl>

### -field <a id="DXGK_PTE_PAGE_TABLE_PAGE_4KB"></a><a id="dxgk_pte_page_table_page_4kb"></a><b>DXGK_PTE_PAGE_TABLE_PAGE_4KB</b>

<dd>
<p>Indicates the lower page table level uses 4 KB pages. </p>
</dd>

### -field <a id="DXGK_PTE_PAGE_TABLE_PAGE_64KB"></a><a id="dxgk_pte_page_table_page_64kb"></a><b>DXGK_PTE_PAGE_TABLE_PAGE_64KB</b>

<dd>
<p>Indicates the lower page table level uses 64 KB pages. </p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 10</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2016</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dukmdt.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dukmdt\ns-d3dukmdt--dxgk-pte.md">DXGK_PTE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_PTE_PAGE_SIZE enumeration%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
