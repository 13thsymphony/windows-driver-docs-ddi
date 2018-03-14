---
UID: NS:d3d10umddi.D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_OUTPUT_DATA
title: D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_OUTPUT_DATA
author: windows-driver-content
description: D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_OUTPUT_DATA is used with D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_DATA in the implementation of Digital Rights Management (DRM).
old-location: display\d3dwddm2_0ddi_key_exchange_hw_protection_output_data.htm
old-project: display
ms.assetid: 4287B32C-FE40-4B24-801C-455610E4F627
ms.author: windowsdriverdev
ms.date: 2/26/2018
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
<b>D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_OUTPUT_DATA</b> is used with <a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm2_0ddi_key_exchange_hw_protection_data.md">D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_DATA</a> in the implementation of Digital Rights Management (DRM).

## Syntax
````
typedef struct D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_OUTPUT_DATA {
  UINT   PrivateDataSize;
  UINT   MaxHWProtectionDataSize;
  UINT   HWProtectionDataSize;
  UINT64 TransportTime;
  UINT64 ExecutionTime;
  BYTE   pbOutput[4];
} D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_OUTPUT_DATA;
````

## Members


`ExecutionTime`

Returns the number of 100 nanosecond units spent executing the content protection command.

`HWProtectionDataSize`

Returns the size of the output data written by the driver.

`MaxHWProtectionDataSize`

The maximum size of data that the driver can return in the output buffer. The last byte that it can write to is <b>pbOuput</b>[<b>PrivateDataSize</b> + <b>MaxHWProtectionDataSize</b> – 1].

`pbOutput`

If <b>PrivateDataSize</b> is greater than 0, <b>pbOutput</b>[0] – <b>pbOutput</b>[<b>PrivateDataSize</b> - 1] is reserved for IHV use.



<b>pbOutput</b>[<b>PrivateDataSize</b>] – <b>pbOutput</b>[<b>MaxHWProtectionDataSize</b> + <b>PrivateDataSize</b> - 1] contains the region into which the driver should return the output data from the DRM command. The format and size of the DRM command is defined by the DRM specification.

`PrivateDataSize`

Contains the size of the private data reserved for IHV usage. This size is determined from the <b>pPrivateInputSize</b> member returned by <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm2_0ddi_getcryptosessionprivatedatasize.md">GetCryptoSessionPrivateDataSize</a>.

`TransportTime`

Returns the number of 100 nanosecond units spent transporting the data.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm2_0ddi_getcryptosessionprivatedatasize.md">GetCryptoSessionPrivateDataSize</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_negotiatecryptosessionkeyeschange.md">NegotiateCryptoSessionKeyExchange</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm2_0ddi_key_exchange_hw_protection_data.md">D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_DATA</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_OUTPUT_DATA structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>