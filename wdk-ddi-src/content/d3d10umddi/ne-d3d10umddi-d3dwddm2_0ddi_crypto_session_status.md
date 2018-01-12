---
UID: NE:d3d10umddi.D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS
title: D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS
author: windows-driver-content
description: Provides status information for an existing CryptoSession object.
old-location: display\d3dwddm2_0ddi_crypto_session_status.htm
old-project: display
ms.assetid: DBAFEAE2-66B6-4F2F-801D-21B7792BCA60
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS, D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS
req.alt-loc: D3d10umddi.h
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
req.typenames: D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS
---

# D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS enumeration



## -description
Provides status information for an existing <i>CryptoSession</i> object.



## -syntax

````
typedef enum _D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS { 
  D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS_OK                    = 0,
  D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS_KEY_LOST              = 1,
  D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS_KEY_AND_CONTENT_LOST  = 2
} D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS;
````


## -enum-fields

### -field D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS_OK

The <i>CryptoSession</i> object is in a functional state.


### -field D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS_KEY_LOST

The underlying hardware key for the specified <i>CryptoSession</i> has become lost. 


### -field D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS_KEY_AND_CONTENT_LOST

The underlying hardware key for the specified <i>CryptoSession</i> has become lost and protected content has become corrupted. 


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
<dt>D3d10umddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>