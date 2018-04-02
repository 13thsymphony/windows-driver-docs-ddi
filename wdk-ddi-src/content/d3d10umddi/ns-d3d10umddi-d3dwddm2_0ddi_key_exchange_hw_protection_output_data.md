---
UID: NS:d3d10umddi.D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_OUTPUT_DATA
title: D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_OUTPUT_DATA
author: windows-driver-content
description: D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_OUTPUT_DATA is used with D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_DATA in the implementation of Digital Rights Management (DRM).
old-location: display\d3dwddm2_0ddi_key_exchange_hw_protection_output_data.htm
old-project: display
ms.assetid: 4287B32C-FE40-4B24-801C-455610E4F627
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_OUTPUT_DATA, D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_OUTPUT_DATA structure [Display Devices], d3d10umddi/D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_OUTPUT_DATA, display.d3dwddm2_0ddi_key_exchange_hw_protection_output_data
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d10umddi.h
api_name:
-	D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_OUTPUT_DATA
product: Windows
targetos: Windows
req.typenames: D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_OUTPUT_DATA
---

# D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_OUTPUT_DATA structure
<b>D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_OUTPUT_DATA</b> is used with <a href="https://msdn.microsoft.com/library/windows/hardware/dn894610">D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_DATA</a> in the implementation of Digital Rights Management (DRM).

## Syntax
```
typedef struct D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_OUTPUT_DATA {
  UINT   PrivateDataSize;
  UINT   MaxHWProtectionDataSize;
  UINT   HWProtectionDataSize;
  UINT64 TransportTime;
  UINT64 ExecutionTime;
  BYTE   pbOutput[4];
};
```

## Members


`PrivateDataSize`

Contains the size of the private data reserved for IHV usage. This size is determined from the <b>pPrivateInputSize</b> member returned by <a href="https://msdn.microsoft.com/library/windows/hardware/dn906349">GetCryptoSessionPrivateDataSize</a>.

`MaxHWProtectionDataSize`

The maximum size of data that the driver can return in the output buffer. The last byte that it can write to is <b>pbOuput</b>[<b>PrivateDataSize</b> + <b>MaxHWProtectionDataSize</b> – 1].

`HWProtectionDataSize`

Returns the size of the output data written by the driver.

`TransportTime`

Returns the number of 100 nanosecond units spent transporting the data.

`ExecutionTime`

Returns the number of 100 nanosecond units spent executing the content protection command.

`pbOutput`

If <b>PrivateDataSize</b> is greater than 0, <b>pbOutput</b>[0] – <b>pbOutput</b>[<b>PrivateDataSize</b> - 1] is reserved for IHV use.



<b>pbOutput</b>[<b>PrivateDataSize</b>] – <b>pbOutput</b>[<b>MaxHWProtectionDataSize</b> + <b>PrivateDataSize</b> - 1] contains the region into which the driver should return the output data from the DRM command. The format and size of the DRM command is defined by the DRM specification.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn894610">D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn906349">GetCryptoSessionPrivateDataSize</a>



<a href="https://msdn.microsoft.com/a48dcbae-3236-4523-bc14-4be694da9a7b">NegotiateCryptoSessionKeyExchange</a>