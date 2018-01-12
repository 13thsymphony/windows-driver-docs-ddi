---
UID: NC:drmk.PFNDRMGETCONTENTRIGHTS
title: PFNDRMGETCONTENTRIGHTS
author: windows-driver-content
description: This callback function is reserved for system use.
old-location: audio\pfndrmgetcontentrights.htm
old-project: audio
ms.assetid: 1230C71C-9C1A-4F1F-8AA7-C814249675B5
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _WDI_TX_METADATA, *PWDI_TX_METADATA, WDI_TX_METADATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: drmk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DRMGetContentRights
req.alt-loc: Drmk.h
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
req.typenames: *PWDI_TX_METADATA, WDI_TX_METADATA
---

# PFNDRMGETCONTENTRIGHTS callback



## -description
This callback function is reserved for system use.



## -prototype

````
PFNDRMGETCONTENTRIGHTS DRMGetContentRights;

NTSTATUS DRMGetContentRights(
  _In_  ULONG      ContentId,
  _Out_ PDRMRIGHTS DrmRights
)
{ ... }

typedef PFNDRMGETCONTENTRIGHTS DRMGetContentRights;
````


## -parameters

### -param ContentId [in]

This parameter is reserved for system use.


### -param DrmRights [out]

This parameter is reserved for system use.


## -returns
This return value is reserved for system use.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Drmk.h</dt>
</dl>
</td>
</tr>
</table>