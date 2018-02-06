---
UID: NC:d3d10umddi.PFND3D11_1DDI_GETCERTIFICATE
title: PFND3D11_1DDI_GETCERTIFICATE
author: windows-driver-content
description: Returns a certificate that the display miniport driver uses for either the cryptographic session certificate or authenticated channel.
old-location: display\getcertificate.htm
old-project: display
ms.assetid: b2ceaa6e-a952-4c2f-9594-289ebe24c62d
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.getcertificate, pfnGetCertificate callback function [Display Devices], pfnGetCertificate, PFND3D11_1DDI_GETCERTIFICATE, PFND3D11_1DDI_GETCERTIFICATE, d3d10umddi/pfnGetCertificate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	UserDefined
apilocation:
-	D3d10umddi.h
apiname:
-	pfnGetCertificate
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---


# PFND3D11_1DDI_GETCERTIFICATE callback function
Returns a certificate that the display miniport driver uses for either the cryptographic  session certificate or authenticated channel.

## Syntax

```
PFND3D11_1DDI_GETCERTIFICATE Pfnd3d111DdiGetcertificate;

void Pfnd3d111DdiGetcertificate(
  D3D10DDI_HDEVICE hDevice,
  CONST D3D11_1DDI_CERTIFICATE_INFO *pCertificateInfo,
  UINT CertificateSize,
  BYTE *pCertificate
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*pCertificateInfo`

A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_certificate_info.md">D3D11_1DDI_CERTIFICATE_INFO</a> structure that specifies the cryptographic  session certificate or authenticated channel to return.

`CertificateSize`

The size, in bytes, of the buffer that is referenced by the <i>pCertificate</i> parameter.

`*pCertificate`

A pointer to a byte array that receives the driver's certificate chain.


## Return Value

This callback function does not return a value.

## Remarks

Based on the data in the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_certificate_info.md">D3D11_1DDI_CERTIFICATE_INFO</a> structure, <b>GetCertificate</b> returns the certificate for either the cryptographic session or the authenticated channel. The driver uses this certificate to establish trust and perform key exchange for the session or channel.
<div class="alert"><b>Note</b>  The size, in bytes, of a driver's certificate chain can be queried by calling <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getcertificatesize.md">GetCertificateSize</a>.</div><div> </div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_certificate_info.md">D3D11_1DDI_CERTIFICATE_INFO</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getcertificatesize.md">GetCertificateSize</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_GETCERTIFICATE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>