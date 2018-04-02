---
UID: NE:wwan._WWAN_COMPRESSION
title: "_WWAN_COMPRESSION"
author: windows-driver-content
description: The WWAN_COMPRESSION enumeration lists the different compression options that are supported by the MB device.
old-location: netvista\wwan_compression.htm
old-project: netvista
ms.assetid: a22bcf4e-f460-4f32-9e1e-4ae952fc87d0
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PWWAN_COMPRESSION, PWWAN_COMPRESSION, PWWAN_COMPRESSION enumeration pointer [Network Drivers Starting with Windows Vista], WWAN_COMPRESSION, WWAN_COMPRESSION enumeration [Network Drivers Starting with Windows Vista], WwanCompressionEnable, WwanCompressionMax, WwanCompressionNone, WwanRef_ee5377b4-3352-4daf-96a4-296ad130a6f5.xml, _WWAN_COMPRESSION, netvista.wwan_compression, wwan/PWWAN_COMPRESSION, wwan/WWAN_COMPRESSION, wwan/WwanCompressionEnable, wwan/WwanCompressionMax, wwan/WwanCompressionNone"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	WWAN_COMPRESSION
product: Windows
targetos: Windows
req.typenames: WWAN_COMPRESSION, *PWWAN_COMPRESSION
req.product: Windows 10 or later.
---

# _WWAN_COMPRESSION Enumeration
The WWAN_COMPRESSION enumeration lists the different compression options that are supported by the MB
  device.

## Syntax
```
typedef enum _WWAN_COMPRESSION {
  WwanCompressionNone    ,
  WwanCompressionEnable  ,
  WwanCompressionMax
} WWAN_COMPRESSION, *PWWAN_COMPRESSION;
```

## Constants

<table>
            
                <tr>
                    <td>WwanCompressionNone</td>
                    <td>No compression is applied.</td>
                </tr>
            
                <tr>
                    <td>WwanCompressionEnable</td>
                    <td>Enable header and data compression.</td>
                </tr>
            
                <tr>
                    <td>WwanCompressionMax</td>
                    <td>The total number of supported compression options.</td>
                </tr>
</table>

## Remarks

This enumeration applies only to GSM devices. The MB Service specifies 
    <b>WwanCompressionNone</b> as the compression type for CDMA-based devices.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows. Available in Windows 7 and later versions of Windows. |
| **Header** | wwan.h (include Wwan.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff571201">WWAN_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571235">WWAN_SET_CONTEXT_STATE</a>