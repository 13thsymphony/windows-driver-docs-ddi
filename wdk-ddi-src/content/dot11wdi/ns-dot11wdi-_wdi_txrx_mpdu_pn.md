---
UID: NS.DOT11WDI._WDI_TXRX_MPDU_PN
title: _WDI_TXRX_MPDU_PN
author: windows-driver-content
description: The WDI_TXRX_MPDU_PN union defines the parameters that are passed down to the TXRX component.
old-location: netvista\wdi_txrx_mpdu_pn.htm
old-project: netvista
ms.assetid: F03F5BE6-B2F2-4A9A-8D6D-1ACC9F08C890
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _WDI_TXRX_MPDU_PN, WDI_TXRX_MPDU_PN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dot11wdi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WDI_TXRX_MPDU_PN
req.alt-loc: dot11wdi.h
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
---

# _WDI_TXRX_MPDU_PN structure



## -description
The 
  WDI_TXRX_MPDU_PN union defines the parameters that are passed down to the TXRX component.


## -syntax

````
typedef union _WDI_TXRX_MPDU_PN {
  UINT32 Pn24;
  UINT64 Pn48;
  UINT64 Pn128[2];
} WDI_TXRX_MPDU_PN;
````


## -struct-fields

### -field Pn24

WEP: 24-bit PN

### -field Pn48

TKIP or CCMP: 48-bit PN

### -field Pn128

WAPI: 128-bit PN

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client
</th>
<td width="70%">
Windows 10
</td>
</tr>
<tr>
<th width="30%">
Minimum supported server
</th>
<td width="70%">
Windows Server 2016
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Dot11wdi.h</dt>
</dl>
</td>
</tr>
</table>