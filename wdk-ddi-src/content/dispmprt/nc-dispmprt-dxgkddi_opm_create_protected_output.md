---
UID: NC.dispmprt.DXGKDDI_OPM_CREATE_PROTECTED_OUTPUT
title: DXGKDDI_OPM_CREATE_PROTECTED_OUTPUT
author: windows-driver-content
description: The DxgkDdiOPMCreateProtectedOutput function creates a new protected output object with Certified Output Protection Protocol (COPP) or OPM semantics.
old-location: display\dxgkddiopmcreateprotectedoutput.htm
old-project: display
ms.assetid: 8143732e-cef6-49f1-9b20-db6b6ee073e6
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
req.alt-api: DxgkDdiOPMCreateProtectedOutput
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

# DXGKDDI_OPM_CREATE_PROTECTED_OUTPUT callback



## -description
The<i> DxgkDdiOPMCreateProtectedOutput</i> function creates a new protected output object with Certified Output Protection Protocol (COPP) or OPM semantics.


## -prototype

````
DXGKDDI_OPM_CREATE_PROTECTED_OUTPUT DxgkDdiOPMCreateProtectedOutput;

NTSTATUS DxgkDdiOPMCreateProtectedOutput(
  _In_  PVOID                              MiniportDeviceContext,
  _In_  D3DDDI_VIDEO_PRESENT_TARGET_ID     VidPnTargetId,
  _In_  DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS NewVideoOutputSemantics,
  _Out_ PHANDLE                            NewProtectedOutputHandle
)
{ ... }
````


## -parameters

### -param MiniportDeviceContext [in]

A handle to a context block associated with a display adapter. Previously, the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function provided this handle to the DirectX graphics kernel subsystem.

### -param VidPnTargetId [in]

An integer that uniquely identifies the video present target that corresponds to the new protected output object. Each video present target must correspond to one physical monitor connector. If <i>VidPnTargetId</i> corresponds to multiple physical monitor connectors, <i>DxgkDdiOPMCreateProtectedOutput</i> should return the STATUS_GRAPHICS_OPM_SPANNING_MODE_ENABLED or STATUS_GRAPHICS_OPM_THEATER_MODE_ENABLED error code. 

### -param NewVideoOutputSemantics [in]

A <a href="display.dxgkmdt_opm_video_output_semantics">DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS</a>-typed value that determines whether the new protected output has COPP or OPM semantics.

### -param NewProtectedOutputHandle [out]

A pointer to a variable that receives the handle to the new protected output object if <i>DxgkDdiOPMCreateProtectedOutput</i> returns successfully. The DirectX graphics kernel subsystem passes this handle in calls to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_random_number.md">DxgkDdiOPMGetRandomNumber</a>, <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_set_signing_key_and_sequence_numbers.md">DxgkDdiOPMSetSigningKeyAndSequenceNumbers</a>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_information.md">DxgkDdiOPMGetInformation</a>, <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md">DxgkDdiOPMGetCOPPCompatibleInformation</a>, <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_configure_protected_output.md">DxgkDdiOPMConfigureProtectedOutput</a>, and <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_destroy_protected_output.md">DxgkDdiOPMDestroyProtectedOutput</a>.
If <i>DxgkDdiOPMCreateProtectedOutput</i> fails, the value of the variable is unchanged.

## -returns
<i>DxgkDdiOPMCreateProtectedOutput</i> returns one of the following values.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The function successfully created a new protected output object.
<dl>
<dt><b>STATUS_GRAPHICS_OPM_NOT_SUPPORTED</b></dt>
</dl>The display miniport driver does not support OPM either because the hardware vender never signed the OPM license agreement or the miniport driver's graphics hardware does not comply with OPM rules. 
<dl>
<dt><b>STATUS_GRAPHICS_COPP_NOT_SUPPORTED</b></dt>
</dl>The display miniport driver does not support COPP either because the hardware vender never signed the COPP license agreement or the miniport driver's graphics hardware does not comply with COPP rules. 
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl><i>DxgkDdiOPMCreateProtectedOutput</i> cannot allocate memory required for it to complete. 
<dl>
<dt><b>STATUS_GRAPHICS_OPM_SPANNING_MODE_ENABLED</b></dt>
</dl><i>DxgkDdiOPMCreateProtectedOutput</i> could not create a protected output because the video present target is in spanning mode. When the video present target is in spanning mode, it corresponds to multiple physical monitor connectors and each connector displays a separate part of the frame buffer. For a diagram of how the display miniport driver typically implements spanning mode, see the Remarks section. 

The display miniport driver informs the operating system on how the frame buffer corresponds to a particular monitor. The left half of the frame buffer is displayed on one monitor, and the right half of the frame buffer is displayed on the other monitor. 
<dl>
<dt><b>STATUS_GRAPHICS_OPM_THEATER_MODE_ENABLED</b></dt>
</dl><i>DxgkDdiOPMCreateProtectedOutput</i> could not create a protected output because the video present target is in theater mode. When the video present target is in theater mode, it corresponds to two physical monitor connectors; one connector displays the entire frame buffer and the other connector displays only part of the frame buffer. Theater mode is also known as mirror mode. For a diagram of how the display miniport driver typically implements theater mode, see the Remarks section. 

The display miniport driver informs the operating system on how the frame buffer corresponds to a particular monitor. The entire frame buffer is displayed on one monitor, and only part of the frame buffer is displayed on the other monitor. 

 

This function might also return other error codes that are defined in Ntstatus.h.

## -remarks
The following figure shows how the display miniport driver typically implements spanning mode.

The following figure shows how the display miniport driver typically implements theater mode.

<i>DxgkDdiOPMCreateProtectedOutput</i> should be made pageable.

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
<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_random_number.md">DxgkDdiOPMGetRandomNumber</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_set_signing_key_and_sequence_numbers.md">DxgkDdiOPMSetSigningKeyAndSequenceNumbers</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_information.md">DxgkDdiOPMGetInformation</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md">DxgkDdiOPMGetCOPPCompatibleInformation</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_configure_protected_output.md">DxgkDdiOPMConfigureProtectedOutput</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_destroy_protected_output.md">DxgkDdiOPMDestroyProtectedOutput</a>
</dt>
<dt>
<a href="display.dxgkmdt_opm_video_output_semantics">DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_OPM_CREATE_PROTECTED_OUTPUT callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
