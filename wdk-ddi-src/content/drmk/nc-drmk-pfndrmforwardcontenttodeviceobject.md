---
UID: NC:drmk.PFNDRMFORWARDCONTENTTODEVICEOBJECT
title: PFNDRMFORWARDCONTENTTODEVICEOBJECT
author: windows-driver-content
description: This callback function is reserved for system use.
old-location: audio\pfndrmforwardcontenttodeviceobject.htm
old-project: audio
ms.assetid: A6256D6D-A952-4E10-B8E7-A28E3D8D9585
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
req.alt-api: DRMForwardContentToDeviceObject
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

# PFNDRMFORWARDCONTENTTODEVICEOBJECT callback



## -description
This callback function is reserved for system use.



## -prototype

````
PFNDRMFORWARDCONTENTTODEVICEOBJECT DRMForwardContentToDeviceObject;

NTSTATUS DRMForwardContentToDeviceObject(
  _In_ ULONG        ContentId,
  _In_ PVOID        Reserved,
  _In_ PCDRMFORWARD DrmForward
)
{ ... }

typedef PFNDRMFORWARDCONTENTTODEVICEOBJECT DRMForwardContentToDeviceObject;
````


## -parameters

### -param ContentId [in]

This parameter is reserved for system use.


### -param Reserved [in]

This parameter is reserved for system use.


### -param DrmForward [in]

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