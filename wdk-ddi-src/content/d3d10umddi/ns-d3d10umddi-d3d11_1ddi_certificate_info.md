---
UID : NS:d3d10umddi.D3D11_1DDI_CERTIFICATE_INFO
title : D3D11_1DDI_CERTIFICATE_INFO
author : windows-driver-content
description : Specifies a cryptographic session certificate or authenticated channel.
old-location : display\d3d11_1ddi_certificate_info.htm
old-project : display
ms.assetid : 9a687c45-2201-483c-b1ad-958b9f651e54
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : D3D11_1DDI_CERTIFICATE_INFO, D3D11_1DDI_CERTIFICATE_INFO
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3d10umddi.h
req.include-header : D3d10umddi.h
req.target-type : Windows
req.target-min-winverclnt : Windows 8
req.target-min-winversvr : Windows Server 2012
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : D3D11_1DDI_CERTIFICATE_INFO
req.alt-loc : D3d10umddi.h
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
req.typenames : D3D11_1DDI_CERTIFICATE_INFO
---

# D3D11_1DDI_CERTIFICATE_INFO structure
Specifies a cryptographic  session certificate or authenticated channel.

## Syntax
````
typedef struct D3D11_1DDI_CERTIFICATE_INFO {
  D3D11_1DDI_CERTIFICATE_TYPE CertificateType;
  union {
    D3D11_1DDI_AUTHENTICATED_CHANNEL_TYPE ChannelType;
    GUID                                  CryptoSessionType;
  };
} D3D11_1DDI_CERTIFICATE_INFO;
````

## Members

        
            `CertificateType`

            A <a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_certificate_type.md">D3D11_1DDI_CERTIFICATE_TYPE</a> value that specifies the type of authenticated certificate that is used to establish trust and perform a key exchange.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

    ## See Also

        <dl>
<dt>
<a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_authenticated_channel_type.md">D3D11_1DDI_AUTHENTICATED_CHANNEL_TYPE</a>
</dt>
<dt>
<a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_certificate_type.md">D3D11_1DDI_CERTIFICATE_TYPE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_1DDI_CERTIFICATE_INFO structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>