---
UID : NS:d3d10umddi.D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_INPUT_DATA
title : D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_INPUT_DATA
author : windows-driver-content
description : D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_INPUT_DATA is used with D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_DATA in the implementation of Digital Rights Management (DRM).
old-location : display\d3dwddm2_0ddi_key_exchange_hw_protection_input_data.htm
old-project : display
ms.assetid : 9CF86E7B-B6EF-419C-97A9-424FFB08FF61
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_INPUT_DATA, display.d3dwddm2_0ddi_key_exchange_hw_protection_input_data, d3d10umddi/D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_INPUT_DATA, D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_INPUT_DATA structure [Display Devices]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3d10umddi.h
req.include-header : D3d10umddi.h
req.target-type : Windows
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : Windows Server 2016
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_INPUT_DATA
---

# D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_INPUT_DATA structure
<b>D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_INPUT_DATA</b> is used with <a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm2_0ddi_key_exchange_hw_protection_data.md">D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_DATA</a> in the implementation of Digital Rights Management (DRM).

## Syntax
````
typedef struct D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_INPUT_DATA {
  UINT PrivateDataSize;
  UINT HWProtectionDataSize;
  BYTE pbInput[4];
} D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_INPUT_DATA;
````

## Members


`HWProtectionDataSize`

Contains the size of the DRM command data.

`pbInput`

If <b>PrivateDataSize</b> is greater than 0, <b>pbInput</b>[0] – <b>pbInput</b>[<b>PrivateDataSize</b> - 1] is reserved for IHV use.



<b>pbInput</b>[<b>PrivateDataSize</b>] – <b>pbInput</b>[<b>HWProtectionDataSize</b> + <b>PrivateDataSize</b> - 1] contains the input data for the DRM command. The format and size of the DRM command is defined by the DRM specification.

`PrivateDataSize`

Contains the size of the private data reserved for IHV usage. This size is determined from the <b>pPrivateInputSize</b> member returned by <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm2_0ddi_getcryptosessionprivatedatasize.md">GetCryptoSessionPrivateDataSize</a>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm2_0ddi_getcryptosessionprivatedatasize.md">GetCryptoSessionPrivateDataSize</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_negotiatecryptosessionkeyeschange.md">NegotiateCryptoSessionKeyExchange</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm2_0ddi_key_exchange_hw_protection_data.md">D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_DATA</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_INPUT_DATA structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>