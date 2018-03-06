---
UID: NS:d3d10umddi.D3D10DDI_CORELAYER_DEVICECALLBACKS
title: D3D10DDI_CORELAYER_DEVICECALLBACKS
author: windows-driver-content
description: The D3D10DDI_CORELAYER_DEVICECALLBACKS structure contains Microsoft Direct3D 10 runtime callback functions that the user-mode display driver can use.
old-location: display\d3d10ddi_corelayer_devicecallbacks.htm
old-project: display
ms.assetid: cced2221-7e8c-432a-9963-3b1de67037a3
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D10DDI_CORELAYER_DEVICECALLBACKS, D3D10DDI_CORELAYER_DEVICECALLBACKS structure [Display Devices], UMDisplayDriver_Dx10param_Structs_4c7782a0-4963-4f18-802e-98c8eb39c1a1.xml, d3d10umddi/D3D10DDI_CORELAYER_DEVICECALLBACKS, display.d3d10ddi_corelayer_devicecallbacks
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
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
-	d3d10umddi.h
api_name:
-	D3D10DDI_CORELAYER_DEVICECALLBACKS
product: Windows
targetos: Windows
req.typenames: D3D10DDI_CORELAYER_DEVICECALLBACKS
---

# D3D10DDI_CORELAYER_DEVICECALLBACKS structure
The D3D10DDI_CORELAYER_DEVICECALLBACKS structure contains Microsoft Direct3D 10 runtime callback functions that the user-mode display driver can use.

## Syntax
````
typedef struct D3D10DDI_CORELAYER_DEVICECALLBACKS {
  PFND3D10DDI_SETERROR_CB                                      pfnSetErrorCb;
  PFND3D10DDI_STATE_VS_CONSTBUF_CB                             pfnStateVsConstBufCb;
  PFND3D10DDI_STATE_PS_SRV_CB                                  pfnStatePsSrvCb;
  PFND3D10DDI_STATE_PS_SHADER_CB                               pfnStatePsShaderCb;
  PFND3D10DDI_STATE_PS_SAMPLER_CB                              pfnStatePsSamplerCb;
  PFND3D10DDI_STATE_VS_SHADER_CB                               pfnStateVsShaderCb;
  PFND3D10DDI_STATE_PS_CONSTBUF_CB                             pfnStatePsConstBufCb;
  PFND3D10DDI_STATE_IA_INPUTLAYOUT_CB                          pfnStateIaInputLayoutCb;
  PFND3D10DDI_STATE_IA_VERTEXBUF_CB                            pfnStateIaVertexBufCb;
  PFND3D10DDI_STATE_IA_INDEXBUF_CB                             pfnStateIaIndexBufCb;
  PFND3D10DDI_STATE_GS_CONSTBUF_CB                             pfnStateGsConstBufCb;
  PFND3D10DDI_STATE_GS_SHADER_CB                               pfnStateGsShaderCb;
  PFND3D10DDI_STATE_IA_PRIMITIVE_TOPOLOGY_CB                   pfnStateIaPrimitiveTopologyCb;
  PFND3D10DDI_STATE_VS_SRV_CB                                  pfnStateVsSrvCb;
  PFND3D10DDI_STATE_VS_SAMPLER_CB                              pfnStateVsSamplerCb;
  PFND3D10DDI_STATE_GS_SRV_CB                                  pfnStateGsSrvCb;
  PFND3D10DDI_STATE_GS_SAMPLER_CB                              pfnStateGsSamplerCb;
  PFND3D10DDI_STATE_OM_RENDERTARGETS_CB                        pfnStateOmRenderTargetsCb;
  PFND3D10DDI_STATE_OM_BLENDSTATE_CB                           pfnStateOmBlendStateCb;
  PFND3D10DDI_STATE_OM_DEPTHSTATE_CB                           pfnStateOmDepthStateCb;
  PFND3D10DDI_STATE_RS_RASTSTATE_CB                            pfnStateRsRastStateCb;
  PFND3D10DDI_STATE_SO_TARGETS_CB                              pfnStateSoTargetsCb;
  PFND3D10DDI_STATE_RS_VIEWPORTS_CB                            pfnStateRsViewportsCb;
  PFND3D10DDI_STATE_RS_SCISSOR_CB                              pfnStateRsScissorCb;
  PFND3D10DDI_DISABLE_DEFERRED_STAGING_RESOURCE_DESTRUCTION_CB pfnDisableDeferredStagingResourceDestruction;
  PFND3D10DDI_STATE_TEXTFILTERSIZE_CB                          pfnStateTextFilterSizeCb;
} D3D10DDI_CORELAYER_DEVICECALLBACKS;
````

## Members


`pfnDisableDeferredStagingResourceDestruction`

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_disable_deferred_staging_resource_destruction_cb.md">pfnDisableDeferredStagingResourceDestruction</a> function. By default, the Direct3D 10 runtime defers the destruction of staging resources until the driver indicates that the hardware no longer requires them. The driver can call this function to disable this feature if the driver does not require the deferred destruction functionality.

`pfnSetErrorCb`

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function, which the driver uses to send errors back to the Direct3D 10 runtime because many of the driver's functions (in <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>) return void.

`pfnStateGsConstBufCb`

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_gs_constbuf_cb.md">pfnStateGsConstBufCb</a> function.

`pfnStateGsSamplerCb`

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_gs_sampler_cb.md">pfnStateGsSamplerCb</a> function.

`pfnStateGsShaderCb`

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_gs_shader_cb.md">pfnStateGsShaderCb</a> function.

`pfnStateGsSrvCb`

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_gs_srv_cb.md">pfnStateGsSrvCb</a> function.

`pfnStateIaIndexBufCb`

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_ia_indexbuf_cb.md">pfnStateIaIndexBufCb</a> function.

`pfnStateIaInputLayoutCb`

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_ia_inputlayout_cb.md">pfnStateIaInputLayoutCb</a> function.

`pfnStateIaPrimitiveTopologyCb`

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_ia_primitive_topology_cb.md">pfnStateIaPrimitiveTopologyCb</a> function.

`pfnStateIaVertexBufCb`

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_ia_vertexbuf_cb.md">pfnStateIaVertexBufCb</a> function.

`pfnStateOmBlendStateCb`

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_om_blendstate_cb.md">pfnStateOmBlendStateCb</a> function.

`pfnStateOmDepthStateCb`

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_om_depthstate_cb.md">pfnStateOmDepthStateCb</a> function.

`pfnStateOmRenderTargetsCb`

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_om_rendertargets_cb.md">pfnStateOmRenderTargetsCb</a> function.

`pfnStatePsConstBufCb`

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_ps_constbuf_cb.md">pfnStatePsConstBufCb</a> function.

`pfnStatePsSamplerCb`

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_ps_sampler_cb.md">pfnStatePsSamplerCb</a> function.

`pfnStatePsShaderCb`

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_ps_shader_cb.md">pfnStatePsShaderCb</a> function.

`pfnStatePsSrvCb`

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_ps_srv_cb.md">pfnStatePsSrvCb</a> function.

`pfnStateRsRastStateCb`

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_rs_raststate_cb.md">pfnStateRsRastStateCb</a> function.

`pfnStateRsScissorCb`

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_rs_scissor_cb.md">pfnStateRsScissorCb</a> function.

`pfnStateRsViewportsCb`

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_rs_viewports_cb.md">pfnStateRsViewportsCb</a> function.

`pfnStateSoTargetsCb`

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_so_targets_cb.md">pfnStateSoTargetsCb</a> function.

`pfnStateTextFilterSizeCb`

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_textfiltersize_cb.md">pfnStateTextFilterSizeCb</a> function.

`pfnStateVsConstBufCb`

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_vs_constbuf_cb.md">pfnStateVsConstBufCb</a> function.

`pfnStateVsSamplerCb`

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_vs_sampler_cb.md">pfnStateVsSamplerCb</a> function.

`pfnStateVsShaderCb`

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_vs_shader_cb.md">pfnStateVsShaderCb</a> function.

`pfnStateVsSrvCb`

A pointer to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_state_vs_srv_cb.md">pfnStateVsSrvCb</a> function.

## Remarks
Because the Direct3D 10 runtime might change the function pointers dynamically, the user-mode display driver cannot cache the function pointers directly. 

The driver uses the functions with "State" in their name to retrieve the current state of the pipeline.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createdevice.md">D3D10DDIARG_CREATEDEVICE</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10DDI_CORELAYER_DEVICECALLBACKS structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>