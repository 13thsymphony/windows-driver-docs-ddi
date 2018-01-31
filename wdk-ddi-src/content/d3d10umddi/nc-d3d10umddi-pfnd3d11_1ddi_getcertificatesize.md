---
UID : NC:d3d10umddi.PFND3D11_1DDI_GETCERTIFICATESIZE
title : PFND3D11_1DDI_GETCERTIFICATESIZE
author : windows-driver-content
description : Queries the size in bytes of the certificate that the display miniport driver uses for either the cryptographic session certificate or authenticated channel.
old-location : display\getcertificatesize.htm
old-project : display
ms.assetid : 7f9a2a76-ee50-4f72-a588-d7b9145c14a6
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : display.getcertificatesize, pfnGetCertificateSize callback function [Display Devices], pfnGetCertificateSize, PFND3D11_1DDI_GETCERTIFICATESIZE, PFND3D11_1DDI_GETCERTIFICATESIZE, d3d10umddi/pfnGetCertificateSize
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : d3d10umddi.h
req.include-header : D3d10umddi.h
req.target-type : Desktop
req.target-min-winverclnt : Windows 8
req.target-min-winversvr : Windows Server 2012
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
req.typenames : SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3D11_1DDI_GETCERTIFICATESIZE callback function
Queries the size in bytes of the certificate that the display miniport driver uses for either the cryptographic  session certificate or authenticated channel.

## Syntax

```
PFND3D11_1DDI_GETCERTIFICATESIZE Pfnd3d111DdiGetcertificatesize;

void Pfnd3d111DdiGetcertificatesize(
  D3D10DDI_HDEVICE hDevice,
  CONST D3D11_1DDI_CERTIFICATE_INFO *pCertificateInfo,
  UINT *pCertificateSize
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*pCertificateInfo`



`*pCertificateSize`




## Return Value

This callback function does not return a value.

## Remarks

Based on the data in the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_certificate_info.md">D3D11_1DDI_CERTIFICATE_INFO</a> structure, the <b>GetCertificateSize</b> function returns the size in bytes of the certificate chain for either the cryptographic session or the authenticated channel. The driver uses this certificate to establish trust and perform key exchange for the session or channel.
<div class="alert"><b>Note</b>  The driver's certificate  can be queried by calling <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getcertificate.md">GetCertificate</a>.</div><div> </div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getcertificate.md">GetCertificate</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_certificate_info.md">D3D11_1DDI_CERTIFICATE_INFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_GETCERTIFICATESIZE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>