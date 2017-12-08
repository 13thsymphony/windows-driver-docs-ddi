---
UID: NC.dispmprt.DXGKDDI_OPM_CONFIGURE_PROTECTED_OUTPUT
title: DXGKDDI_OPM_CONFIGURE_PROTECTED_OUTPUT
author: windows-driver-content
description: The DxgkDdiOPMConfigureProtectedOutput function configures the given protected output object.
old-location: display\dxgkddiopmconfigureprotectedoutput.htm
old-project: display
ms.assetid: a7829587-c1e7-43ec-a0bb-92bca94b7c3d
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
req.alt-api: DxgkDdiOPMConfigureProtectedOutput
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

# DXGKDDI_OPM_CONFIGURE_PROTECTED_OUTPUT callback



## -description
The<i> DxgkDdiOPMConfigureProtectedOutput</i> function configures the given protected output object.


## -prototype

````
DXGKDDI_OPM_CONFIGURE_PROTECTED_OUTPUT DxgkDdiOPMConfigureProtectedOutput;

NTSTATUS DxgkDdiOPMConfigureProtectedOutput(
  _In_       PVOID                             MiniportDeviceContext,
  _In_       HANDLE                            ProtectedOutputHandle,
  _In_ const PDXGKMDT_OPM_CONFIGURE_PARAMETERS Parameters,
  _In_       ULONG                             AdditionalParametersSize,
  _In_ const PVOID                             AdditionalParameters
)
{ ... }
````


## -parameters

### -param MiniportDeviceContext [in]

A handle to a context block associated with a display adapter. The display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.

### -param ProtectedOutputHandle [in]

The handle to a protected output object. The <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_create_protected_output.md">DxgkDdiOPMCreateProtectedOutput</a> function creates the protected output object and returns the handle to the object.

### -param Parameters [in]

A pointer to a <a href="display.dxgkmdt_opm_configure_parameters">DXGKMDT_OPM_CONFIGURE_PARAMETERS</a> structure that contains parameters that are used to configure the protected output object whose handle is specified in the <i>ProtectedOutputHandle</i> parameter. 

### -param AdditionalParametersSize [in]

The size, in bytes, of the additional parameters in the buffer that is pointed to by <i>AdditionalParameters</i>. For Certified Output Protection Protocol (COPP) emulation, this is 0. 

### -param AdditionalParameters [in]

A pointer to a buffer that holds the additional parameters that are used to configure the protected output object whose handle is specified in the <i>ProtectedOutputHandle</i> parameter. For COPP emulation, this is <b>NULL</b>. If the <i>AdditionalParametersSize</i> parameter is set to 0, <i>AdditionalParameters</i> is always set to <b>NULL</b>. 

## -returns
<i>DxgkDdiOPMConfigureProtectedOutput</i> returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The function successfully configured the protected output object.
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl><i>DxgkDdiOPMConfigureProtectedOutput</i> cannot allocate memory required for it to complete. 

 

This function might also return other error codes that are defined in Ntstatus.h.

## -remarks
The DirectX graphics kernel subsystem calls <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_information.md">DxgkDdiOPMGetInformation</a> or <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md">DxgkDdiOPMGetCOPPCompatibleInformation</a> to retrieve information about the output and then calls <i>DxgkDdiOPMConfigureProtectedOutput</i> one or more times to configure the output.

<i>DxgkDdiOPMConfigureProtectedOutput</i> should be made pageable.

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
<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_create_protected_output.md">DxgkDdiOPMCreateProtectedOutput</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md">DxgkDdiOPMGetCOPPCompatibleInformation</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_information.md">DxgkDdiOPMGetInformation</a>
</dt>
<dt>
<a href="display.dxgkmdt_opm_configure_parameters">DXGKMDT_OPM_CONFIGURE_PARAMETERS</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_OPM_CONFIGURE_PROTECTED_OUTPUT callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
