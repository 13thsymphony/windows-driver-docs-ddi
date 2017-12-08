---
UID: NS.STORPORT._STOR_SCATTER_GATHER_LIST
title: _STOR_SCATTER_GATHER_LIST
author: windows-driver-content
description: The STOR_SCATTER_GATHER_LIST structure is used in conjunction with the StorPortGetScatterGatherList routine to retrieve the scatter/gather list for a SCSI request block (SRB).
old-location: storage\stor_scatter_gather_list.htm
old-project: storage
ms.assetid: 9fbb8dea-67d3-4bb9-afc2-d623bea2ca8d
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: _STOR_SCATTER_GATHER_LIST, *PSTOR_SCATTER_GATHER_LIST, STOR_SCATTER_GATHER_LIST
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: storport.h
req.include-header: Storport.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STOR_SCATTER_GATHER_LIST
req.alt-loc: storport.h
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
req.product: Windows 10 or later.
---

# _STOR_SCATTER_GATHER_LIST structure



## -description
The STOR_SCATTER_GATHER_LIST structure is used in conjunction with the <a href="storage.storportgetscattergatherlist">StorPortGetScatterGatherList</a> routine to retrieve the scatter/gather list for a SCSI request block (SRB). 


## -syntax

````
typedef struct _STOR_SCATTER_GATHER_LIST {
  ULONG                       NumberOfElements;
  ULONG_PTR                   Reserved;
  STOR_SCATTER_GATHER_ELEMENT List[];
} STOR_SCATTER_GATHER_LIST, *PSTOR_SCATTER_GATHER_LIST;
````


## -struct-fields

### -field NumberOfElements

Contains the number of scatter/gather elements in the list. 

### -field Reserved

Reserved. 

### -field List

Contains the array of scatter/gather elements. 

## -remarks
Miniport drivers that work with the Storport driver call the Storport support routine, <a href="storage.storportgetscattergatherlist">StorPortGetScatterGatherList</a>, to retrieve the scatter gather list for an SRB. <b>StorPortGetScatterGatherList</b> returns a structure of type STOR_SCATTER_GATHER_LIST. Each scatter/gather element is of type <a href="storage.stor_scatter_gather_element">STOR_SCATTER_GATHER_ELEMENT</a>. 

## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Storport.h (include Storport.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.stor_scatter_gather_element">STOR_SCATTER_GATHER_ELEMENT</a>
</dt>
<dt>
<a href="storage.storportgetscattergatherlist">StorPortGetScatterGatherList</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STOR_SCATTER_GATHER_LIST structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
