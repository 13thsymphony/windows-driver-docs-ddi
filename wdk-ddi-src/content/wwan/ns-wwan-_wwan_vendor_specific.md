---
UID: NS:wwan._WWAN_VENDOR_SPECIFIC
title: "_WWAN_VENDOR_SPECIFIC"
author: windows-driver-content
description: The WWAN_VENDOR_SPECIFIC structure represents vendor-specific data.
old-location: netvista\wwan_vendor_specific.htm
old-project: netvista
ms.assetid: e3f024d0-4543-4c28-958f-58a3072027ad
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PWWAN_VENDOR_SPECIFIC, PWWAN_VENDOR_SPECIFIC, PWWAN_VENDOR_SPECIFIC structure pointer [Network Drivers Starting with Windows Vista], WWAN_VENDOR_SPECIFIC, WWAN_VENDOR_SPECIFIC structure [Network Drivers Starting with Windows Vista], WwanRef_9261cb07-079e-4266-8358-fff73af8c31a.xml, _WWAN_VENDOR_SPECIFIC, netvista.wwan_vendor_specific, wwan/PWWAN_VENDOR_SPECIFIC, wwan/WWAN_VENDOR_SPECIFIC"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
req.target-min-winversvr: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wwan.h
api_name:
-	WWAN_VENDOR_SPECIFIC
product: Windows
targetos: Windows
req.typenames: WWAN_VENDOR_SPECIFIC, *PWWAN_VENDOR_SPECIFIC
req.product: Windows 10 or later.
---

# _WWAN_VENDOR_SPECIFIC structure
The WWAN_VENDOR_SPECIFIC structure represents vendor-specific data.

## Syntax
````
typedef struct _WWAN_VENDOR_SPECIFIC {
  ULONG uVendorSpecificBufferSize;
} WWAN_VENDOR_SPECIFIC, *PWWAN_VENDOR_SPECIFIC;
````

## Members


`uVendorSpecificBufferSize`

The size, in bytes, of the vendor-specific buffer that follows the structure instance in
     memory.

## Remarks
NDIS_WWAN_VENDOR_SPECIFIC should have the data following the 
    <b>uVendorSpecificBufferSize</b> member.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows. Available in Windows 7 and later versions of Windows. |
| **Header** | wwan.h (include Wwan.h) |

## See Also

<a href="..\ndiswwan\ns-ndiswwan-_ndis_wwan_vendor_specific.md">NDIS_WWAN_VENDOR_SPECIFIC</a>