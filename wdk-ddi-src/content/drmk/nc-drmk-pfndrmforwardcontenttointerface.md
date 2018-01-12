---
UID: NC:drmk.PFNDRMFORWARDCONTENTTOINTERFACE
title: PFNDRMFORWARDCONTENTTOINTERFACE
author: windows-driver-content
description: This callback function is reserved for system use.
old-location: audio\pfndrmforwardcontenttointerface.htm
old-project: audio
ms.assetid: DFD077B7-307B-439B-828D-DC225FC5AAA0
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
req.alt-api: DRMForwardContentToInterface
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

# PFNDRMFORWARDCONTENTTOINTERFACE callback



## -description
This callback function is reserved for system use.



## -prototype

````
PFNDRMFORWARDCONTENTTOINTERFACE DRMForwardContentToInterface;

NTSTATUS DRMForwardContentToInterface(
  _In_ ULONG     ContentId,
  _In_ PUNKNOWN  pUnknown,
  _In_ ULONG     NumMethods
)
{ ... }

typedef PFNDRMFORWARDCONTENTTOINTERFACE DRMForwardContentToInterface;
````


## -parameters

### -param ContentId [in]

This parameter is reserved for system use.


### -param pUnknown [in]

This parameter is reserved for system use.


### -param NumMethods [in]

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