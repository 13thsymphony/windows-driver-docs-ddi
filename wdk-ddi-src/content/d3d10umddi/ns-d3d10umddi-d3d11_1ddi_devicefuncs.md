---
UID: NS:d3d10umddi.D3D11_1DDI_DEVICEFUNCS
title: D3D11_1DDI_DEVICEFUNCS
author: windows-driver-content
description: Contains functions that a user-mode display driver that is optimized for the Microsoft Direct3D version 11.1 runtime can implement to render graphics primitives and process state changes.
old-location: display\d3d11_1ddi_devicefuncs.htm
old-project: display
ms.assetid: 5429D886-4CC0-438D-AC9F-739159802062
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D11_1DDI_DEVICEFUNCS, D3D11_1DDI_DEVICEFUNCS structure [Display Devices], d3d10umddi/D3D11_1DDI_DEVICEFUNCS, display.d3d11_1ddi_devicefuncs
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d10umddi.h
api_name:
-	D3D11_1DDI_DEVICEFUNCS
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_DEVICEFUNCS
---

# D3D11_1DDI_DEVICEFUNCS structure
Contains functions that a user-mode display driver that is optimized for the Microsoft Direct3D version 11.1 runtime can implement to render graphics primitives and process state changes.

## Syntax
````
typedef struct D3D11_1DDI_DEVICEFUNCS {
  PFND3D11_1DDI_RESOURCEUPDATESUBRESOURCEUP               pfnDefaultConstantBufferUpdateSubresourceUP;
  PFND3D11_1DDI_SETCONSTANTBUFFERS                        pfnVsSetConstantBuffers;
  PFND3D10DDI_SETSHADERRESOURCES                          pfnPsSetShaderResources;
  PFND3D10DDI_SETSHADER                                   pfnPsSetShader;
  PFND3D10DDI_SETSAMPLERS                                 pfnPsSetSamplers;
  PFND3D10DDI_SETSHADER                                   pfnVsSetShader;
  PFND3D10DDI_DRAWINDEXED                                 pfnDrawIndexed;
  PFND3D10DDI_DRAW                                        pfnDraw;
  PFND3D10DDI_RESOURCEMAP                                 pfnDynamicIABufferMapNoOverwrite;
  PFND3D10DDI_RESOURCEUNMAP                               pfnDynamicIABufferUnmap;
  PFND3D10DDI_RESOURCEMAP                                 pfnDynamicConstantBufferMapDiscard;
  PFND3D10DDI_RESOURCEMAP                                 pfnDynamicIABufferMapDiscard;
  PFND3D10DDI_RESOURCEUNMAP                               pfnDynamicConstantBufferUnmap;
  PFND3D11_1DDI_SETCONSTANTBUFFERS                        pfnPsSetConstantBuffers;
  PFND3D10DDI_SETINPUTLAYOUT                              pfnIaSetInputLayout;
  PFND3D10DDI_IA_SETVERTEXBUFFERS                         pfnIaSetVertexBuffers;
  PFND3D10DDI_IA_SETINDEXBUFFER                           pfnIaSetIndexBuffer;
  PFND3D10DDI_DRAWINDEXEDINSTANCED                        pfnDrawIndexedInstanced;
  PFND3D10DDI_DRAWINSTANCED                               pfnDrawInstanced;
  PFND3D10DDI_RESOURCEMAP                                 pfnDynamicResourceMapDiscard;
  PFND3D10DDI_RESOURCEUNMAP                               pfnDynamicResourceUnmap;
  PFND3D11_1DDI_SETCONSTANTBUFFERS                        pfnGsSetConstantBuffers;
  PFND3D10DDI_SETSHADER                                   pfnGsSetShader;
  PFND3D10DDI_IA_SETTOPOLOGY                              pfnIaSetTopology;
  PFND3D10DDI_RESOURCEMAP                                 pfnStagingResourceMap;
  PFND3D10DDI_RESOURCEUNMAP                               pfnStagingResourceUnmap;
  PFND3D10DDI_SETSHADERRESOURCES                          pfnVsSetShaderResources;
  PFND3D10DDI_SETSAMPLERS                                 pfnVsSetSamplers;
  PFND3D10DDI_SETSHADERRESOURCES                          pfnGsSetShaderResources;
  PFND3D10DDI_SETSAMPLERS                                 pfnGsSetSamplers;
  PFND3D11DDI_SETRENDERTARGETS                            pfnSetRenderTargets;
  PFND3D10DDI_SHADERRESOURCEVIEWREADAFTERWRITEHAZARD      pfnShaderResourceViewReadAfterWriteHazard;
  PFND3D10DDI_RESOURCEREADAFTERWRITEHAZARD                pfnResourceReadAfterWriteHazard;
  PFND3D10DDI_SETBLENDSTATE                               pfnSetBlendState;
  PFND3D10DDI_SETDEPTHSTENCILSTATE                        pfnSetDepthStencilState;
  PFND3D10DDI_SETRASTERIZERSTATE                          pfnSetRasterizerState;
  PFND3D10DDI_QUERYEND                                    pfnQueryEnd;
  PFND3D10DDI_QUERYBEGIN                                  pfnQueryBegin;
  PFND3D11_1DDI_RESOURCECOPYREGION                        pfnResourceCopyRegion;
  PFND3D11_1DDI_RESOURCEUPDATESUBRESOURCEUP               pfnResourceUpdateSubresourceUP;
  PFND3D10DDI_SO_SETTARGETS                               pfnSoSetTargets;
  PFND3D10DDI_DRAWAUTO                                    pfnDrawAuto;
  PFND3D10DDI_SETVIEWPORTS                                pfnSetViewports;
  PFND3D10DDI_SETSCISSORRECTS                             pfnSetScissorRects;
  PFND3D10DDI_CLEARRENDERTARGETVIEW                       pfnClearRenderTargetView;
  PFND3D10DDI_CLEARDEPTHSTENCILVIEW                       pfnClearDepthStencilView;
  PFND3D10DDI_SETPREDICATION                              pfnSetPredication;
  PFND3D10DDI_QUERYGETDATA                                pfnQueryGetData;
  PFND3D11_1DDI_FLUSH                                     pfnFlush;
  PFND3D10DDI_GENMIPS                                     pfnGenMips;
  PFND3D10DDI_RESOURCECOPY                                pfnResourceCopy;
  PFND3D10DDI_RESOURCERESOLVESUBRESOURCE                  pfnResourceResolveSubresource;
  PFND3D10DDI_RESOURCEMAP                                 pfnResourceMap;
  PFND3D10DDI_RESOURCEUNMAP                               pfnResourceUnmap;
  PFND3D10DDI_RESOURCEISSTAGINGBUSY                       pfnResourceIsStagingBusy;
  PFND3D11_1DDI_RELOCATEDEVICEFUNCS                       pfnRelocateDeviceFuncs;
  PFND3D11DDI_CALCPRIVATERESOURCESIZE                     pfnCalcPrivateResourceSize;
  PFND3D10DDI_CALCPRIVATEOPENEDRESOURCESIZE               pfnCalcPrivateOpenedResourceSize;
  PFND3D11DDI_CREATERESOURCE                              pfnCreateResource;
  PFND3D10DDI_OPENRESOURCE                                pfnOpenResource;
  PFND3D10DDI_DESTROYRESOURCE                             pfnDestroyResource;
  PFND3D11DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE           pfnCalcPrivateShaderResourceViewSize;
  PFND3D11DDI_CREATESHADERRESOURCEVIEW                    pfnCreateShaderResourceView;
  PFND3D10DDI_DESTROYSHADERRESOURCEVIEW                   pfnDestroyShaderResourceView;
  PFND3D10DDI_CALCPRIVATERENDERTARGETVIEWSIZE             pfnCalcPrivateRenderTargetViewSize;
  PFND3D10DDI_CREATERENDERTARGETVIEW                      pfnCreateRenderTargetView;
  PFND3D10DDI_DESTROYRENDERTARGETVIEW                     pfnDestroyRenderTargetView;
  PFND3D11DDI_CALCPRIVATEDEPTHSTENCILVIEWSIZE             pfnCalcPrivateDepthStencilViewSize;
  PFND3D11DDI_CREATEDEPTHSTENCILVIEW                      pfnCreateDepthStencilView;
  PFND3D10DDI_DESTROYDEPTHSTENCILVIEW                     pfnDestroyDepthStencilView;
  PFND3D10DDI_CALCPRIVATEELEMENTLAYOUTSIZE                pfnCalcPrivateElementLayoutSize;
  PFND3D10DDI_CREATEELEMENTLAYOUT                         pfnCreateElementLayout;
  PFND3D10DDI_DESTROYELEMENTLAYOUT                        pfnDestroyElementLayout;
  PFND3D11_1DDI_CALCPRIVATEBLENDSTATESIZE                 pfnCalcPrivateBlendStateSize;
  PFND3D11_1DDI_CREATEBLENDSTATE                          pfnCreateBlendState;
  PFND3D10DDI_DESTROYBLENDSTATE                           pfnDestroyBlendState;
  PFND3D10DDI_CALCPRIVATEDEPTHSTENCILSTATESIZE            pfnCalcPrivateDepthStencilStateSize;
  PFND3D10DDI_CREATEDEPTHSTENCILSTATE                     pfnCreateDepthStencilState;
  PFND3D10DDI_DESTROYDEPTHSTENCILSTATE                    pfnDestroyDepthStencilState;
  PFND3D11_1DDI_CALCPRIVATERASTERIZERSTATESIZE            pfnCalcPrivateRasterizerStateSize;
  PFND3D11_1DDI_CREATERASTERIZERSTATE                     pfnCreateRasterizerState;
  PFND3D10DDI_DESTROYRASTERIZERSTATE                      pfnDestroyRasterizerState;
  PFND3D11_1DDI_CALCPRIVATESHADERSIZE                     pfnCalcPrivateShaderSize;
  PFND3D11_1DDI_CREATEVERTEXSHADER                        pfnCreateVertexShader;
  PFND3D11_1DDI_CREATEGEOMETRYSHADER                      pfnCreateGeometryShader;
  PFND3D11_1DDI_CREATEPIXELSHADER                         pfnCreatePixelShader;
  PFND3D11_1DDI_CALCPRIVATEGEOMETRYSHADERWITHSTREAMOUTPUT pfnCalcPrivateGeometryShaderWithStreamOutput;
  PFND3D11_1DDI_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT      pfnCreateGeometryShaderWithStreamOutput;
  PFND3D10DDI_DESTROYSHADER                               pfnDestroyShader;
  PFND3D10DDI_CALCPRIVATESAMPLERSIZE                      pfnCalcPrivateSamplerSize;
  PFND3D10DDI_CREATESAMPLER                               pfnCreateSampler;
  PFND3D10DDI_DESTROYSAMPLER                              pfnDestroySampler;
  PFND3D10DDI_CALCPRIVATEQUERYSIZE                        pfnCalcPrivateQuerySize;
  PFND3D10DDI_CREATEQUERY                                 pfnCreateQuery;
  PFND3D10DDI_DESTROYQUERY                                pfnDestroyQuery;
  PFND3D10DDI_CHECKFORMATSUPPORT                          pfnCheckFormatSupport;
  PFND3D10DDI_CHECKMULTISAMPLEQUALITYLEVELS               pfnCheckMultisampleQualityLevels;
  PFND3D10DDI_CHECKCOUNTERINFO                            pfnCheckCounterInfo;
  PFND3D10DDI_CHECKCOUNTER                                pfnCheckCounter;
  PFND3D10DDI_DESTROYDEVICE                               pfnDestroyDevice;
  PFND3D10DDI_SETTEXTFILTERSIZE                           pfnSetTextFilterSize;
  PFND3D10DDI_RESOURCECOPY                                pfnResourceConvert;
  PFND3D11_1DDI_RESOURCECOPYREGION                        pfnResourceConvertRegion;
  PFND3D11DDI_DRAWINDEXEDINSTANCEDINDIRECT                pfnDrawIndexedInstancedIndirect;
  PFND3D11DDI_DRAWINSTANCEDINDIRECT                       pfnDrawInstancedIndirect;
  PFND3D11DDI_COMMANDLISTEXECUTE                          pfnCommandListExecute;
  PFND3D10DDI_SETSHADERRESOURCES                          pfnHsSetShaderResources;
  PFND3D10DDI_SETSHADER                                   pfnHsSetShader;
  PFND3D10DDI_SETSAMPLERS                                 pfnHsSetSamplers;
  PFND3D11_1DDI_SETCONSTANTBUFFERS                        pfnHsSetConstantBuffers;
  PFND3D10DDI_SETSHADERRESOURCES                          pfnDsSetShaderResources;
  PFND3D10DDI_SETSHADER                                   pfnDsSetShader;
  PFND3D10DDI_SETSAMPLERS                                 pfnDsSetSamplers;
  PFND3D11_1DDI_SETCONSTANTBUFFERS                        pfnDsSetConstantBuffers;
  PFND3D11_1DDI_CREATEHULLSHADER                          pfnCreateHullShader;
  PFND3D11_1DDI_CREATEDOMAINSHADER                        pfnCreateDomainShader;
  PFND3D11DDI_CHECKDEFERREDCONTEXTHANDLESIZES             pfnCheckDeferredContextHandleSizes;
  PFND3D11DDI_CALCDEFERREDCONTEXTHANDLESIZE               pfnCalcDeferredContextHandleSize;
  PFND3D11DDI_CALCPRIVATEDEFERREDCONTEXTSIZE              pfnCalcPrivateDeferredContextSize;
  PFND3D11DDI_CREATEDEFERREDCONTEXT                       pfnCreateDeferredContext;
  PFND3D11DDI_ABANDONCOMMANDLIST                          pfnAbandonCommandList;
  PFND3D11DDI_CALCPRIVATECOMMANDLISTSIZE                  pfnCalcPrivateCommandListSize;
  PFND3D11DDI_CREATECOMMANDLIST                           pfnCreateCommandList;
  PFND3D11DDI_DESTROYCOMMANDLIST                          pfnDestroyCommandList;
  PFND3D11_1DDI_CALCPRIVATETESSELLATIONSHADERSIZE         pfnCalcPrivateTessellationShaderSize;
  PFND3D11DDI_SETSHADER_WITH_IFACES                       pfnPsSetShaderWithIfaces;
  PFND3D11DDI_SETSHADER_WITH_IFACES                       pfnVsSetShaderWithIfaces;
  PFND3D11DDI_SETSHADER_WITH_IFACES                       pfnGsSetShaderWithIfaces;
  PFND3D11DDI_SETSHADER_WITH_IFACES                       pfnHsSetShaderWithIfaces;
  PFND3D11DDI_SETSHADER_WITH_IFACES                       pfnDsSetShaderWithIfaces;
  PFND3D11DDI_SETSHADER_WITH_IFACES                       pfnCsSetShaderWithIfaces;
  PFND3D11DDI_CREATECOMPUTESHADER                         pfnCreateComputeShader;
  PFND3D10DDI_SETSHADER                                   pfnCsSetShader;
  PFND3D10DDI_SETSHADERRESOURCES                          pfnCsSetShaderResources;
  PFND3D10DDI_SETSAMPLERS                                 pfnCsSetSamplers;
  PFND3D11_1DDI_SETCONSTANTBUFFERS                        pfnCsSetConstantBuffers;
  PFND3D11DDI_CALCPRIVATEUNORDEREDACCESSVIEWSIZE          pfnCalcPrivateUnorderedAccessViewSize;
  PFND3D11DDI_CREATEUNORDEREDACCESSVIEW                   pfnCreateUnorderedAccessView;
  PFND3D11DDI_DESTROYUNORDEREDACCESSVIEW                  pfnDestroyUnorderedAccessView;
  PFND3D11DDI_CLEARUNORDEREDACCESSVIEWUINT                pfnClearUnorderedAccessViewUint;
  PFND3D11DDI_CLEARUNORDEREDACCESSVIEWFLOAT               pfnClearUnorderedAccessViewFloat;
  PFND3D11DDI_SETUNORDEREDACCESSVIEWS                     pfnCsSetUnorderedAccessViews;
  PFND3D11DDI_DISPATCH                                    pfnDispatch;
  PFND3D11DDI_DISPATCHINDIRECT                            pfnDispatchIndirect;
  PFND3D11DDI_SETRESOURCEMINLOD                           pfnSetResourceMinLOD;
  PFND3D11DDI_COPYSTRUCTURECOUNT                          pfnCopyStructureCount;
  PFND3D11DDI_RECYCLECOMMANDLIST                          pfnRecycleCommandList;
  PFND3D11DDI_RECYCLECREATECOMMANDLIST                    pfnRecycleCreateCommandList;
  PFND3D11DDI_RECYCLECREATEDEFERREDCONTEXT                pfnRecycleCreateDeferredContext;
  PFND3D11DDI_DESTROYCOMMANDLIST                          pfnRecycleDestroyCommandList;
  PFND3D11_1DDI_DISCARD                                   pfnDiscard;
  PFND3D11_1DDI_ASSIGNDEBUGBINARY                         pfnAssignDebugBinary;
  PFND3D10DDI_RESOURCEMAP                                 pfnDynamicConstantBufferMapNoOverwrite;
  PFND3D11_1DDI_CHECKDIRECTFLIPSUPPORT                    pfnCheckDirectFlipSupport;
  PFND3D11_1DDI_CLEARVIEW                                 pfnClearView;
} D3D11_1DDI_DEVICEFUNCS;
````

## Members


`pfnDefaultConstantBufferUpdateSubresourceUP`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_resourceupdatesubresourceup.md">DefaultConstantBufferUpdateSubresourceUP(D3D11_1)</a> function.

`pfnVsSetConstantBuffers`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_setconstantbuffers.md">VsSetConstantBuffers(D3D11_1)</a> function.

`pfnPsSetShaderResources`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setshaderresources.md">PsSetShaderResources</a> function.

`pfnPsSetShader`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setshader.md">PsSetShader</a> function.

`pfnPsSetSamplers`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setsamplers.md">PsSetSamplers</a> function.

`pfnVsSetShader`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setshader.md">VsSetShader</a> function.

`pfnDrawIndexed`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_drawindexed.md">DrawIndexed</a> function.

`pfnDraw`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_draw.md">Draw</a> function.

`pfnDynamicIABufferMapNoOverwrite`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcemap.md">ResourceMap</a> function. For more information about whether to implement a separate <i>DynamicIABufferMapNoOverwrite</i> function or to point to the multipurpose <i>ResourceMap</i>, see the Remarks section of <i>ResourceMap</i>.

`pfnDynamicIABufferUnmap`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourceunmap.md">ResourceUnmap</a> function. For more information about whether to implement a separate <i>DynamicIABufferUnmap</i> function or to point to the multipurpose <i>ResourceUnmap</i>, see the Remarks section of <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcemap.md">ResourceMap</a>.

`pfnDynamicConstantBufferMapDiscard`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcemap.md">ResourceMap</a> function. For more information about whether to implement a separate <i>DynamicConstantBufferMapDiscard</i> function or to point to the multipurpose <i>ResourceMap</i>, see the Remarks section of <i>ResourceMap</i>.

`pfnDynamicIABufferMapDiscard`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcemap.md">ResourceMap</a> function. For more information about whether to implement a separate <i>DynamicIABufferMapDiscard</i> function or to point to the multipurpose <i>ResourceMap</i>, see the Remarks section of <i>ResourceMap</i>.

`pfnDynamicConstantBufferUnmap`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourceunmap.md">ResourceUnmap</a> function. For more information about whether to implement a separate <i>DynamicConstantBufferUnmap</i> function or to point to the multipurpose <i>ResourceUnmap</i>, see the Remarks section of <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcemap.md">ResourceMap</a>.

`pfnPsSetConstantBuffers`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_setconstantbuffers.md">PsSetConstantBuffers(D3D11_1)</a> function.

`pfnIaSetInputLayout`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setinputlayout.md">IaSetInputLayout</a> function.

`pfnIaSetVertexBuffers`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_ia_setvertexbuffers.md">IaSetVertexBuffers</a> function.

`pfnIaSetIndexBuffer`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_ia_setindexbuffer.md">IaSetIndexBuffer</a> function.

`pfnDrawIndexedInstanced`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_drawindexedinstanced.md">DrawIndexedInstanced</a> function.

`pfnDrawInstanced`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_drawinstanced.md">DrawInstanced</a> function.

`pfnDynamicResourceMapDiscard`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcemap.md">ResourceMap</a> function. For more information about whether to implement a separate <i>DynamicResourceMapDiscard</i> function or to point to the multipurpose <i>ResourceMap</i>, see the Remarks section of <i>ResourceMap</i>.

`pfnDynamicResourceUnmap`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourceunmap.md">ResourceUnmap</a> function. For more information about whether to implement a separate <i>DynamicResourceUnmap</i> function or to point to the multipurpose <i>ResourceUnmap</i>, see the Remarks section of <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcemap.md">ResourceMap</a>.

`pfnGsSetConstantBuffers`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_setconstantbuffers.md">GsSetConstantBuffers(D3D11_1)</a> function.

`pfnGsSetShader`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setshader.md">GsSetShader</a> function.

`pfnIaSetTopology`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_ia_settopology.md">IaSetTopology</a> function.

`pfnStagingResourceMap`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcemap.md">ResourceMap</a> function. For more information about whether to implement a separate <i>StagingResourceMap</i> function or to point to the multipurpose <i>ResourceMap</i>, see the Remarks section of <i>ResourceMap</i>.

`pfnStagingResourceUnmap`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourceunmap.md">ResourceUnmap</a> function. For more information about whether to implement a separate <i>StagingResourceUnmap</i> function or to point to the multipurpose <i>ResourceUnmap</i>, see the Remarks section of <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcemap.md">ResourceMap</a>.

`pfnVsSetShaderResources`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setshaderresources.md">VsSetShaderResources</a> function.

`pfnVsSetSamplers`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setsamplers.md">VsSetSamplers</a> function.

`pfnGsSetShaderResources`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setshaderresources.md">GsSetShaderResources</a> function.

`pfnGsSetSamplers`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setsamplers.md">GsSetSamplers</a> function.

`pfnSetRenderTargets`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_setrendertargets.md">SetRenderTargets(D3D11)</a> function.

`pfnShaderResourceViewReadAfterWriteHazard`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_shaderresourceviewreadafterwritehazard.md">ShaderResourceViewReadAfterWriteHazard</a> function.

`pfnResourceReadAfterWriteHazard`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcereadafterwritehazard.md">ResourceReadAfterWriteHazard</a> function.

`pfnSetBlendState`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setblendstate.md">SetBlendState</a> function.

`pfnSetDepthStencilState`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setdepthstencilstate.md">SetDepthStencilState</a> function.

`pfnSetRasterizerState`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setrasterizerstate.md">SetRasterizerState</a> function.

`pfnQueryEnd`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_queryend.md">QueryEnd</a> function.

`pfnQueryBegin`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_querybegin.md">QueryBegin</a> function.

`pfnResourceCopyRegion`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_resourcecopyregion.md">ResourceCopyRegion(D3D11_1)</a> function.

`pfnResourceUpdateSubresourceUP`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_resourceupdatesubresourceup.md">ResourceUpdateSubresourceUP(D3D11_1)</a> function.

`pfnSoSetTargets`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_so_settargets.md">SoSetTargets</a> function.

`pfnDrawAuto`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_drawauto.md">DrawAuto</a> function.

`pfnSetViewports`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setviewports.md">SetViewports</a> function.

`pfnSetScissorRects`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setscissorrects.md">SetScissorRects</a> function.

`pfnClearRenderTargetView`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_clearrendertargetview.md">ClearRenderTargetView</a> function.

`pfnClearDepthStencilView`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_cleardepthstencilview.md">ClearDepthStencilView</a> function.

`pfnSetPredication`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setpredication.md">SetPredication</a> function.

`pfnQueryGetData`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_querygetdata.md">QueryGetData</a> function.

`pfnFlush`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_flush.md">Flush(D3D11_1)</a> function.

`pfnGenMips`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_genmips.md">GenMips</a> function.

`pfnResourceCopy`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcecopy.md">ResourceCopy</a> function.

`pfnResourceResolveSubresource`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourceresolvesubresource.md">ResourceResolveSubresource</a> function.

`pfnResourceMap`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcemap.md">ResourceMap</a> function.

`pfnResourceUnmap`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourceunmap.md">ResourceUnmap</a> function.

`pfnResourceIsStagingBusy`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourceisstagingbusy.md">ResourceIsStagingBusy</a> function.

`pfnRelocateDeviceFuncs`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_relocatedevicefuncs.md">RelocateDeviceFuncs(D3D11_1)</a> function.

`pfnCalcPrivateResourceSize`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_calcprivateresourcesize.md">CalcPrivateResourceSize(D3D11)</a> function.

`pfnCalcPrivateOpenedResourceSize`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivateopenedresourcesize.md">CalcPrivateOpenedResourceSize</a> function.

`pfnCreateResource`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createresource.md">CreateResource(D3D11)</a> function.

`pfnOpenResource`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_openresource.md">OpenResource(D3D10)</a> function.

`pfnDestroyResource`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroyresource.md">DestroyResource(D3D10)</a> function.

`pfnCalcPrivateShaderResourceViewSize`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_calcprivateshaderresourceviewsize.md">CalcPrivateShaderResourceViewSize(D3D11)</a> function.

`pfnCreateShaderResourceView`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createshaderresourceview.md">CreateShaderResourceView(D3D11)</a> function.

`pfnDestroyShaderResourceView`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroyshaderresourceview.md">DestroyShaderResourceView</a> function.

`pfnCalcPrivateRenderTargetViewSize`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivaterendertargetviewsize.md">CalcPrivateRenderTargetViewSize</a> function.

`pfnCreateRenderTargetView`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createrendertargetview.md">CreateRenderTargetView</a> function.

`pfnDestroyRenderTargetView`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroyrendertargetview.md">DestroyRenderTargetView</a> function.

`pfnCalcPrivateDepthStencilViewSize`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_calcprivatedepthstencilviewsize.md">CalcPrivateDepthStencilViewSize(D3D11)</a> function.

`pfnCreateDepthStencilView`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createdepthstencilview.md">CreateDepthStencilView(D3D11)</a> function.

`pfnDestroyDepthStencilView`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroydepthstencilview.md">DestroyDepthStencilView</a> function.

`pfnCalcPrivateElementLayoutSize`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivateelementlayoutsize.md">CalcPrivateElementLayoutSize</a> function.

`pfnCreateElementLayout`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createelementlayout.md">CreateElementLayout</a> function.

`pfnDestroyElementLayout`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroyelementlayout.md">DestroyElementLayout</a> function.

`pfnCalcPrivateBlendStateSize`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivateblendstatesize.md">CalcPrivateBlendStateSize(D3D11_1)</a> function.

`pfnCreateBlendState`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createblendstate.md">CreateBlendState(D3D11_1)</a> function.

`pfnDestroyBlendState`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroyblendstate.md">DestroyBlendState</a> function.

`pfnCalcPrivateDepthStencilStateSize`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivatedepthstencilstatesize.md">CalcPrivateDepthStencilStateSize</a> function.

`pfnCreateDepthStencilState`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdepthstencilstate.md">CreateDepthStencilState</a> function.

`pfnDestroyDepthStencilState`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroydepthstencilstate.md">DestroyDepthStencilState</a> function.

`pfnCalcPrivateRasterizerStateSize`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivaterasterizerstatesize.md">CalcPrivateRasterizerStateSize(D3D11_1)</a> function.

`pfnCreateRasterizerState`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createrasterizerstate.md">CreateRasterizerState(D3D11_1)</a> function.

`pfnDestroyRasterizerState`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroyrasterizerstate.md">DestroyRasterizerState</a> function.

`pfnCalcPrivateShaderSize`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivateshadersize.md">CalcPrivateShaderSize(D3D11_1)</a> function.

`pfnCreateVertexShader`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvertexshader.md">CreateVertexShader(D3D11_1)</a> function.

`pfnCreateGeometryShader`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_creategeometryshader.md">CreateGeometryShader(D3D11_1)</a> function.

`pfnCreatePixelShader`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createpixelshader.md">CreatePixelShader(D3D11_1)</a> function.

`pfnCalcPrivateGeometryShaderWithStreamOutput`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivategeometryshaderwithstreamoutput.md">CalcPrivateGeometryShaderWithStreamOutput(D3D11_1)</a> function.

`pfnCreateGeometryShaderWithStreamOutput`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_creategeometryshaderwithstreamoutput.md">CreateGeometryShaderWithStreamOutput(D3D11_1)</a> function.

`pfnDestroyShader`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroyshader.md">DestroyShader</a> function.

`pfnCalcPrivateSamplerSize`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivatesamplersize.md">CalcPrivateSamplerSize</a> function.

`pfnCreateSampler`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createsampler.md">CreateSampler</a> function.

`pfnDestroySampler`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroysampler.md">DestroySampler</a> function.

`pfnCalcPrivateQuerySize`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivatequerysize.md">CalcPrivateQuerySize</a> function.

`pfnCreateQuery`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createquery.md">CreateQuery(D3D10)</a> function.

`pfnDestroyQuery`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroyquery.md">DestroyQuery(D3D10)</a> function.

`pfnCheckFormatSupport`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_checkformatsupport.md">CheckFormatSupport</a> function.

`pfnCheckMultisampleQualityLevels`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_checkmultisamplequalitylevels.md">CheckMultisampleQualityLevels</a> function.

`pfnCheckCounterInfo`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_checkcounterinfo.md">CheckCounterInfo</a> function.

`pfnCheckCounter`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_checkcounter.md">CheckCounter</a> function.

`pfnDestroyDevice`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroydevice.md">DestroyDevice(D3D10)</a> function.

`pfnSetTextFilterSize`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_settextfiltersize.md">SetTextFilterSize</a> function.

`pfnResourceConvert`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcecopy.md">ResourceCopy</a> function. For more information about whether to implement a separate <i>ResourceConvert</i> function or to point to the multipurpose <i>ResourceCopy</i>, see the Remarks section of <i>ResourceCopy</i>.

`pfnResourceConvertRegion`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_resourcecopyregion.md">ResourceCopyRegion(D3D11_1)</a> function. For more information about whether to implement a separate <i>ResourceConvertRegion(D3D11_1)</i> function or to point to the multipurpose <i>ResourceCopyRegion(D3D11_1)</i>, see the Remarks section of <i>ResourceCopyRegion(D3D11_1)</i>.

`pfnResetPrimitiveID`



`pfnSetVertexPipelineOutput`



`pfnDrawIndexedInstancedIndirect`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_drawindexedinstancedindirect.md">DrawIndexedInstancedIndirect</a> function.

`pfnDrawInstancedIndirect`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_drawinstancedindirect.md">DrawInstancedIndirect</a> function.

`pfnCommandListExecute`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_commandlistexecute.md">CommandListExecute</a> function. The driver is only required to implement <i>CommandListExecute</i> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability.

`pfnHsSetShaderResources`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setshaderresources.md">HsSetShaderResources</a> function.

`pfnHsSetShader`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setshader.md">HsSetShader</a> function.

`pfnHsSetSamplers`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setsamplers.md">HsSetSamplers</a> function.

`pfnHsSetConstantBuffers`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_setconstantbuffers.md">HsSetConstantBuffers(D3D11_1)</a> function.

`pfnDsSetShaderResources`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setshaderresources.md">DsSetShaderResources</a> function.

`pfnDsSetShader`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setshader.md">DsSetShader</a> function.

`pfnDsSetSamplers`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setsamplers.md">DsSetSamplers</a> function.

`pfnDsSetConstantBuffers`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_setconstantbuffers.md">DsSetConstantBuffers(D3D11_1)</a> function.

`pfnCreateHullShader`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createhullshader.md">CreateHullShader(D3D11_1)</a> function.

`pfnCreateDomainShader`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createdomainshader.md">CreateDomainShader(D3D11_1)</a> function.

`pfnCheckDeferredContextHandleSizes`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_checkdeferredcontexthandlesizes.md">CheckDeferredContextHandleSizes</a> function. The driver is only required to implement <i>CheckDeferredContextHandleSizes</i> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability.

`pfnCalcDeferredContextHandleSize`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_calcdeferredcontexthandlesize.md">CalcDeferredContextHandleSize</a> function. The driver is only required to implement <i>CalcDeferredContextHandleSize</i> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability.

`pfnCalcPrivateDeferredContextSize`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_calcprivatedeferredcontextsize.md">CalcPrivateDeferredContextSize</a> function. The driver is only required to implement <i>CalcPrivateDeferredContextSize</i> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability.

`pfnCreateDeferredContext`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createdeferredcontext.md">CreateDeferredContext</a> function. The driver is only required to implement <i>CreateDeferredContext</i> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability.

`pfnAbandonCommandList`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_abandoncommandlist.md">AbandonCommandList</a> function. The driver is only required to implement <i>AbandonCommandList</i> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability.

`pfnCalcPrivateCommandListSize`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_calcprivatecommandlistsize.md">CalcPrivateCommandListSize</a> function. The driver is only required to implement <i>CalcPrivateCommandListSize</i> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability.

`pfnCreateCommandList`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createcommandlist.md">CreateCommandList</a> function. The driver is only required to implement <i>CreateCommandList</i> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability.

`pfnDestroyCommandList`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_destroycommandlist.md">DestroyCommandList</a> function. The driver is only required to implement <i>DestroyCommandList</i> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability.

`pfnCalcPrivateTessellationShaderSize`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_calcprivatetessellationshadersize.md">CalcPrivateTessellationShaderSize(D3D11_1)</a> function.

`pfnPsSetShaderWithIfaces`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces.md">PsSetShaderWithIfaces</a> function.

`pfnVsSetShaderWithIfaces`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces.md">VsSetShaderWithIfaces</a> function.

`pfnGsSetShaderWithIfaces`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces.md">GsSetShaderWithIfaces</a> function.

`pfnHsSetShaderWithIfaces`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces.md">HsSetShaderWithIfaces</a> function.

`pfnDsSetShaderWithIfaces`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces.md">DsSetShaderWithIfaces</a> function.

`pfnCsSetShaderWithIfaces`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces.md">CsSetShaderWithIfaces</a> function.

`pfnCreateComputeShader`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createcomputeshader.md">CreateComputeShader</a> function.

`pfnCsSetShader`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setshader.md">CsSetShader</a> function.

`pfnCsSetShaderResources`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setshaderresources.md">CsSetShaderResources</a> function.

`pfnCsSetSamplers`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setsamplers.md">CsSetSamplers</a> function.

`pfnCsSetConstantBuffers`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_setconstantbuffers.md">CsSetConstantBuffers(D3D11_1)</a> function.

`pfnCalcPrivateUnorderedAccessViewSize`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_calcprivateunorderedaccessviewsize.md">CalcPrivateUnorderedAccessViewSize</a> function.

`pfnCreateUnorderedAccessView`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createunorderedaccessview.md">CreateUnorderedAccessView</a> function.

`pfnDestroyUnorderedAccessView`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_destroyunorderedaccessview.md">DestroyUnorderedAccessView</a> function.

`pfnClearUnorderedAccessViewUint`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_clearunorderedaccessviewuint.md">ClearUnorderedAccessViewUINT</a> function.

`pfnClearUnorderedAccessViewFloat`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_clearunorderedaccessviewfloat.md">ClearUnorderedAccessViewFLOAT</a> function.

`pfnCsSetUnorderedAccessViews`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_setunorderedaccessviews.md">CsSetUnorderedAccessViews</a> function.

`pfnDispatch`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_dispatch.md">Dispatch</a> function.

`pfnDispatchIndirect`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_dispatchindirect.md">DispatchIndirect</a> function.

`pfnSetResourceMinLOD`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_setresourceminlod.md">SetResourceMinLOD</a> function.

`pfnCopyStructureCount`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_copystructurecount.md">CopyStructureCount</a> function.

`pfnRecycleCommandList`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_recyclecommandlist.md">RecycleCommandList</a> function.

`pfnRecycleCreateCommandList`

A pointer to the driver's   <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_recyclecreatecommandlist.md">RecycleCreateCommandList</a> function.

`pfnRecycleCreateDeferredContext`

A pointer to the driver's  <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_recyclecreatedeferredcontext.md">RecycleCreateDeferredContext</a> function.

`pfnRecycleDestroyCommandList`

A pointer to the driver's  <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_destroycommandlist.md">RecycleDestroyCommandList</a> function.

`pfnDiscard`

A pointer to the driver's  <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_discard.md">Discard(D3D11_1)</a> function.

`pfnAssignDebugBinary`

A pointer to the driver's  <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_assigndebugbinary.md">AssignDebugBinary</a> function.

`pfnDynamicConstantBufferMapNoOverwrite`

A pointer to the driver's  <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcemap.md">ResourceMap</a> function.

`pfnCheckDirectFlipSupport`

A pointer to the driver's  <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_checkdirectflipsupport.md">CheckDirectFlipSupport(D3D11_1)</a> function.

`pfnClearView`

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_clearview.md">ClearView</a>  function.

## Remarks
The order of user-mode display driver functions (that is, the order of the members of the <b>D3D11_1DDI_DEVICEFUNCS</b> structure) is in decreasing order of priority (in regard to performance).

The user-mode display driver can use different names for these functions because the address of the function table (this structure) is shared between the Direct3D 11.1 runtime and the driver through the call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a> function.

The <b>pfnResetPrimitiveID</b> and  <b>pfnSetVertexPipelineOutput</b> members (not shown here) and their data types are reserved for system use and should not be used in your driver.

<h3><a id="Deferred_contexts"></a><a id="deferred_contexts"></a><a id="DEFERRED_CONTEXTS"></a>Deferred contexts</h3>
For a list of the functions that are not leveraged for deferred contexts, see <a href="https://msdn.microsoft.com/f6e7898a-7fb8-4a70-ab2e-3372a28db6f4">Excluding DDI Functions for Deferred Contexts</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_devicefuncs.md">D3D11DDI_DEVICEFUNCS</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createdevice.md">D3D10DDIARG_CREATEDEVICE</a>