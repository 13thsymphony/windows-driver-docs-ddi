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
ms.keywords: D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS_KEY_LOST, D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS_OK, D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS, d3d10umddi/D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS_KEY_LOST, display.d3dwddm2_0ddi_crypto_session_status, D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS enumeration [Display Devices], d3d10umddi/D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS, d3d10umddi/D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS_OK, d3d10umddi/D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS_KEY_AND_CONTENT_LOST, D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS_KEY_AND_CONTENT_LOST
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3d10umddi.h
apiname:
-	D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS
product: Windows
targetos: Windows
req.typenames: D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS
---

# D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS Enumeration
Provides status information for an existing <i>CryptoSession</i> object.

## Syntax
````
typedef enum _D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS { 
  D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS_OK                    = 0,
  D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS_KEY_LOST              = 1,
  D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS_KEY_AND_CONTENT_LOST  = 2
} D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS;
````

## Constants

<table>
            
                <tr>
                    <td>D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS_KEY_AND_CONTENT_LOST</td>
                    <td>The underlying hardware key for the specified <i>CryptoSession</i> has become lost and protected content has become corrupted.</td>
                </tr>
            
                <tr>
                    <td>D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS_KEY_LOST</td>
                    <td>The underlying hardware key for the specified <i>CryptoSession</i> has become lost.</td>
                </tr>
            
                <tr>
                    <td>D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS_OK</td>
                    <td>The <i>CryptoSession</i> object is in a functional state.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |