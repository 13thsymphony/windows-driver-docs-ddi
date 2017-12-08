---
UID: NC.drmk.PFNDRMFORWARDCONTENTTOFILEOBJECT
title: PFNDRMFORWARDCONTENTTOFILEOBJECT
author: windows-driver-content
description: This callback function is reserved for system use.
old-location: audio\pfndrmforwardcontenttofileobject.htm
old-project: audio
ms.assetid: 00ACCBFF-FEDE-4223-8503-4D75426E2BD6
ms.author: windowsdriverdev
ms.date: 12/6/2017
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
req.alt-api: DRMForwardContentToFileObject
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
---

# PFNDRMFORWARDCONTENTTOFILEOBJECT callback



## -description
This callback function is reserved for system use.


## -prototype

````
PFNDRMFORWARDCONTENTTOFILEOBJECT DRMForwardContentToFileObject;

NTSTATUS DRMForwardContentToFileObject(
  _In_ ULONG        ContentId,
  _In_ PFILE_OBJECT FileObject
)
{ ... }

typedef PFNDRMFORWARDCONTENTTOFILEOBJECT DRMForwardContentToFileObject;
````


## -parameters

### -param ContentId [in]

This parameter is reserved for system use.

### -param FileObject [in]

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