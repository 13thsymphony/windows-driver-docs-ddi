---
UID: NC.dispmprt.DXGKDDI_OPM_GET_CERTIFICATE
title: DXGKDDI_OPM_GET_CERTIFICATE
author: windows-driver-content
description: The DxgkDdiOPMGetCertificate function retrieves a certificate of the given type and size.
old-location: display\dxgkddiopmgetcertificate.htm
old-project: display
ms.assetid: 3c055598-5f07-46e1-830d-1df9a459f742
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _SYMBOL_INFO_EX, SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkDdiOPMGetCertificate
req.alt-loc: dispmprt.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
---

# DXGKDDI_OPM_GET_CERTIFICATE callback



## -description
The<i> DxgkDdiOPMGetCertificate</i> function retrieves a certificate of the given type and size.


## -prototype

````
DXGKDDI_OPM_GET_CERTIFICATE DxgkDdiOPMGetCertificate;

NTSTATUS DxgkDdiOPMGetCertificate(
  _In_  PVOID                    MiniportDeviceContext,
  _In_  DXGKMDT_CERTIFICATE_TYPE CertificateType,
  _In_  ULONG                    CertificateSize,
  _Out_ PVOID                    CertificateBuffer
)
{ ... }
````


## -parameters

### -param MiniportDeviceContext [in]

A handle to a context block associated with a display adapter. Previously, the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function provided this handle to the DirectX graphics kernel subsystem.

### -param CertificateType [in]

A <a href="display.dxgkmdt_certificate_type">DXGKMDT_CERTIFICATE_TYPE</a>-typed value that identifies the type of certificate to retrieve.

### -param CertificateSize [in]

The size, in bytes, of the certificate to retrieve. This size was returned by a call to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_certificate_size.md">DxgkDdiOPMGetCertificateSize</a> function.

### -param CertificateBuffer [out]

A pointer to a buffer that receives the requested certificate if <i>DxgkDdiOPMGetCertificate</i> returns successfully. If <i>DxgkDdiOPMGetCertificate</i> fails, the contents of the buffer are unchanged.

## -returns
<i>DxgkDdiOPMGetCertificate</i> returns one of the following values.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The function successfully retrieved the certificate.
<dl>
<dt><b>STATUS_GRAPHICS_OPM_NOT_SUPPORTED</b></dt>
</dl>The display miniport driver does not support OPM either because the hardware vender never signed the OPM license agreement or the miniport driver's graphics hardware does not comply with OPM rules. <i>DxgkDdiOPMGetCertificate</i> can also return this value if the display miniport driver detected tampering. 
<dl>
<dt><b>STATUS_GRAPHICS_COPP_NOT_SUPPORTED</b></dt>
</dl>The display miniport driver does not support COPP either because the hardware vender never signed the COPP license agreement or the miniport driver's graphics hardware does not comply with COPP rules. <i>DxgkDdiOPMGetCertificate</i> can also return this value if the display miniport driver detected tampering. 
<dl>
<dt><b>STATUS_GRAPHICS_UAB_NOT_SUPPORTED</b></dt>
</dl>The display miniport driver does not support UAB either because the hardware vender never signed the UAB license agreement or the miniport driver's graphics hardware does not comply with UAB rules. <i>DxgkDdiOPMGetCertificate</i> can also return this value if the display miniport driver detected tampering. 
<dl>
<dt><b>STATUS_GRAPHICS_PVP_HFS_FAILED</b></dt>
</dl>The display miniport driver's hardware functionality scan (HFS) failed or the display miniport driver detected tampering. A display miniport driver can optionally return this value. If <i>DxgkDdiOPMGetCertificate</i> does not return this value for tampering, it can return one of the previous error codes instead. 

 

This function might also return other error codes that are defined in Ntstatus.h.

## -remarks
<i>DxgkDdiOPMGetCertificate</i> can retrieve the display miniport driver's OPM certificate, User Accessible Bus (UAB) certificate, or Certified Output Protection Protocol (COPP) certificate. For information about these certificates, download the Output Content Protection document from the <a href="http://go.microsoft.com/fwlink/p/?linkid=204788">Output Content Protection and Windows Vista</a> website.

<i>DxgkDdiOPMGetCertificate</i> should be made pageable.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Dispmprt.h (include Dispmprt.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
PASSIVE_LEVEL (see Remarks section)
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_certificate_size.md">DxgkDdiOPMGetCertificateSize</a>
</dt>
<dt>
<a href="display.dxgkmdt_certificate_type">DXGKMDT_CERTIFICATE_TYPE</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_OPM_GET_CERTIFICATE callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
