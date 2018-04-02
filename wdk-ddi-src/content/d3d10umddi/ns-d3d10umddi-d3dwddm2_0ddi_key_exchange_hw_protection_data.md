---
UID: NS:d3d10umddi.D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_DATA
title: D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_DATA
author: windows-driver-content
description: D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_DATA is used with NegotiateCryptoSessionKeyExchange in the implementation of Digital Rights Management (DRM).
old-location: display\d3dwddm2_0ddi_key_exchange_hw_protection_data.htm
old-project: display
ms.assetid: BAC7B5B9-FD89-4C60-B3C2-06251110CDF5
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_DATA, D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_DATA structure [Display Devices], d3d10umddi/D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_DATA, display.d3dwddm2_0ddi_key_exchange_hw_protection_data
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
-	D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_DATA
product:
- Windows
targetos: Windows
req.typenames: D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_DATA
---

# D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_DATA structure
<b>D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_DATA</b> is used with <a href="https://msdn.microsoft.com/a48dcbae-3236-4523-bc14-4be694da9a7b">NegotiateCryptoSessionKeyExchange</a> in the implementation of Digital Rights Management (DRM).

## Syntax
```
typedef struct D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_DATA {
  UINT                                                 HWProtectionFunctionID;
  D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_INPUT_DATA  *pInputData;
  D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_OUTPUT_DATA *pOutputData;
  HRESULT                                              Status;
};
```

## Members


`HWProtectionFunctionID`

Specifies the function ID of the DRM command. The values and meanings of the function ID are defined by each individual DRM component.

`pInputData`

Pointer to a buffer containing a <a href="https://msdn.microsoft.com/library/windows/hardware/dn894611">D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_INPUT_DATA</a> structure, reserved memory for IHV use, and the input data for the DRM command.

`pOutputData`

Pointer to a buffer containing a <a href="https://msdn.microsoft.com/library/windows/hardware/dn894612">D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_OUTPUT_DATA</a> structure, reserved memory for IHV use, and the output data for the DRM command.

`Status`

Returns the result of the hardware DRM command.

## Remarks
A pointer to this structure is passed in as the <i>pData</i> parameter of <a href="https://msdn.microsoft.com/a48dcbae-3236-4523-bc14-4be694da9a7b">NegotiateCryptoSessionKeyExchange</a> function when the <b>CryptoSession</b> object is creating using the <b>D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION</b> key exchange type.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn894611">D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_INPUT_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn894612">D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_OUTPUT_DATA</a>



<a href="https://msdn.microsoft.com/a48dcbae-3236-4523-bc14-4be694da9a7b">NegotiateCryptoSessionKeyExchange</a>