---
UID: NC.dispmprt.DXGKDDI_OPM_GET_CERTIFICATE_SIZE
title: DXGKDDI_OPM_GET_CERTIFICATE_SIZE
author: windows-driver-content
description: The DxgkDdiOPMGetCertificateSize function retrieves the size of a certificate of the given type.
old-location: display\dxgkddiopmgetcertificatesize.htm
old-project: display
ms.assetid: fe4197ad-52a2-47b3-ad96-57ea73cd931f
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: SYMBOL_INFO_EX, SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
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
req.alt-api: DxgkDdiOPMGetCertificateSize
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
req.iface: IDebugSystemObjects4
---

# DXGKDDI_OPM_GET_CERTIFICATE_SIZE callback



## -description
<p>The<i> DxgkDdiOPMGetCertificateSize</i> function retrieves the size of a certificate of the given type.</p>


## -prototype

````
DXGKDDI_OPM_GET_CERTIFICATE_SIZE DxgkDdiOPMGetCertificateSize;

NTSTATUS DxgkDdiOPMGetCertificateSize(
  _In_  PVOID                    MiniportDeviceContext,
  _In_  DXGKMDT_CERTIFICATE_TYPE CertificateType,
  _Out_ PULONG                   CertificateSize
)
{ ... }
````


## -parameters
<dl>

### -param <i>MiniportDeviceContext</i> [in]

<dd>
<p>A handle to a context block that is associated with a display adapter. Previously, the display miniport driver's <a href="display.dxgkddiadddevice">DxgkDdiAddDevice</a> function provided this handle to the DirectX graphics kernel subsystem.</p>
</dd>

### -param <i>CertificateType</i> [in]

<dd>
<p>A <a href="https://msdn.microsoft.com/library/windows/hardware/ff560826">DXGKMDT_CERTIFICATE_TYPE</a>-typed value that identifies the type of certificate whose size <i> DxgkDdiOPMGetCertificateSize</i>  returns.</p>
</dd>

### -param <i>CertificateSize</i> [out]

<dd>
<p>A pointer to a variable that receives the size, in bytes, of the certificate whose type is identified by the value in the <i>CertificateType</i> parameter.</p>
</dd>
</dl>

## -returns
<p><i>DxgkDdiOPMGetCertificateSize</i> returns one of the following values:</p><dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl><p>The function successfully retrieved the certificate size.</p><dl>
<dt><b>STATUS_GRAPHICS_OPM_NOT_SUPPORTED</b></dt>
</dl><p>The display miniport driver does not support OPM either because the hardware vender never signed the OPM license agreement or the miniport driver's graphics hardware does not comply with OPM rules. <i>DxgkDdiOPMGetCertificateSize</i> can also return this value if the display miniport driver detected tampering. </p><dl>
<dt><b>STATUS_GRAPHICS_COPP_NOT_SUPPORTED</b></dt>
</dl><p>The display miniport driver does not support COPP either because the hardware vender never signed the COPP license agreement or the miniport driver's graphics hardware does not comply with COPP rules. <i>DxgkDdiOPMGetCertificateSize</i> can also return this value if the miniport driver detected tampering. </p><dl>
<dt><b>STATUS_GRAPHICS_UAB_NOT_SUPPORTED</b></dt>
</dl><p>The display miniport driver does not support UAB either because the hardware vender never signed the UAB license agreement or the miniport driver's graphics hardware does not comply with UAB rules. <i>DxgkDdiOPMGetCertificateSize</i> can also return this value if the display miniport driver detected tampering. </p><dl>
<dt><b>STATUS_GRAPHICS_PVP_HFS_FAILED</b></dt>
</dl><p>The display miniport driver's hardware functionality scan (HFS) failed or the display miniport driver detected tampering. A display miniport driver can optionally return this value. If <i>DxgkDdiOPMGetCertificateSize</i> does not return this value for tampering, it can return one of the previous error codes instead. </p>

<p> </p>

<p>This function might also return other error codes that are defined in Ntstatus.h.</p>

## -remarks
<p><i>DxgkDdiOPMGetCertificateSize</i> can retrieve the size of the display miniport driver's OPM certificate, User Accessible Bus (UAB) certificate, or Certified Output Protection Protocol (COPP) certificate. For information about these certificates, download the Output Content Protection document from the <a href="http://go.microsoft.com/fwlink/p/?linkid=204788">Output Content Protection and Windows Vista</a> website.</p>

<p><i>DxgkDdiOPMGetCertificateSize</i> should be made pageable.</p>

<p><i>DxgkDdiOPMGetCertificateSize</i> can retrieve the size of the display miniport driver's OPM certificate, User Accessible Bus (UAB) certificate, or Certified Output Protection Protocol (COPP) certificate. For information about these certificates, download the Output Content Protection document from the <a href="http://go.microsoft.com/fwlink/p/?linkid=204788">Output Content Protection and Windows Vista</a> website.</p>

<p><i>DxgkDdiOPMGetCertificateSize</i> should be made pageable.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Dispmprt.h (include Dispmprt.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL (see Remarks section)</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.dxgkddiadddevice">DxgkDdiAddDevice</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560826">DXGKMDT_CERTIFICATE_TYPE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_OPM_GET_CERTIFICATE_SIZE callback function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
