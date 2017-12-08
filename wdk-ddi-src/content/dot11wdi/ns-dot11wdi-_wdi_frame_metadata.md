---
UID: NS.DOT11WDI._WDI_FRAME_METADATA
title: _WDI_FRAME_METADATA
author: windows-driver-content
description: The WDI_FRAME_METADATA structure defines the frame metadata.
old-location: netvista\wdi_frame_metadata.htm
old-project: netvista
ms.assetid: 34733e8f-cbe0-4fcd-abcf-6791e298282f
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _WDI_FRAME_METADATA, WDI_FRAME_METADATA, *PWDI_FRAME_METADATA
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
req.alt-api: WDI_FRAME_METADATA
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

# _WDI_FRAME_METADATA structure



## -description
The 
  WDI_FRAME_METADATA structure defines the frame metadata.


## -syntax

````
typedef struct _WDI_FRAME_METADATA {
  LIST_ENTRY       Linkage;
  PNET_BUFFER_LIST pNBL;
  WDI_FRAME_ID     FrameID;
  UINT16           wPad;
#ifdef _WIN64
  UINT32           dPad;
#endif 
  union {
    WDI_TX_METADATA txMetaData;
    WDI_RX_METADATA rxMetaData;
  } u;
} WDI_FRAME_METADATA, *PWDI_FRAME_METADATA;
````


## -struct-fields

### -field Linkage

Reserved for use by the Microsoft component.

### -field pNBL

Set by the LE on RX path and the UE on TX path when the metadata is associated with an NBL.

### -field FrameID

Filled in by the Microsoft component.

### -field wPad

Padding.

### -field dPad

Padding.

### -field u


### -field txMetaData

TX metadata.

### -field rxMetaData

RX metadata.
</dd>
</dl>

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

## -see-also
<dl>
<dt>
<a href="kernel.list_entry">LIST_ENTRY</a>
</dt>
<dt>
<a href="netvista.net_buffer_list">NET_BUFFER_LIST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt297642">WDI_FRAME_ID</a>
</dt>
<dt>
<a href="netvista.wdi_tx_metadata">WDI_TX_METADATA</a>
</dt>
<dt>
<a href="netvista.wdi_rx_metadata">WDI_RX_METADATA</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WDI_FRAME_METADATA structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
