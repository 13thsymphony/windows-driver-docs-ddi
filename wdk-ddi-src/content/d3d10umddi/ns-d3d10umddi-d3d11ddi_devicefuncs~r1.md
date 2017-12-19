---
UID: NS.D3D10UMDDI.D3D11DDI_DEVICEFUNCS~R1
title: D3D11DDI_DEVICEFUNCS
author: windows-driver-content
description: The D3D11DDI_DEVICEFUNCS structure contains functions that a user-mode display driver that is optimized for the Microsoft Direct3D version 11 runtime can implement to render graphics primitives and process state changes.
old-location: display\d3d11ddi_devicefuncs.htm
old-project: display
ms.assetid: fabd77b9-2a2e-4995-a99f-50b46806e312
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: D3D11DDI_DEVICEFUNCS, D3D11DDI_DEVICEFUNCS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D11DDI_DEVICEFUNCS is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D11DDI_DEVICEFUNCS
req.alt-loc: d3d10umddi.h
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
---

# D3D11DDI_DEVICEFUNCS structure



## -description
The D3D11DDI_DEVICEFUNCS structure contains functions that a user-mode display driver that is optimized for the Microsoft Direct3D version 11 runtime can implement to render graphics primitives and process state changes.



## -syntax

````
typedef struct D3D11DDI_DEVICEFUNCS {
  PFND3D10DDI_RESOURCEUPDATESUBRESOURCEUP               pfnDefaultConstantBufferUpdateSubresourceUP;
  PFND3D10DDI_SETCONSTANTBUFFERS                        pfnVsSetConstantBuffers;
  PFND3D10DDI_SETSHADERRESOURCES                        pfnPsSetShaderResources;
  PFND3D10DDI_SETSHADER                                 pfnPsSetShader;
  PFND3D10DDI_SETSAMPLERS                               pfnPsSetSamplers;
  PFND3D10DDI_SETSHADER                                 pfnVsSetShader;
  PFND3D10DDI_DRAWINDEXED                               pfnDrawIndexed;
  PFND3D10DDI_DRAW                                      pfnDraw;
  PFND3D10DDI_RESOURCEMAP                               pfnDynamicIABufferMapNoOverwrite;
  PFND3D10DDI_RESOURCEUNMAP                             pfnDynamicIABufferUnmap;
  PFND3D10DDI_RESOURCEMAP                               pfnDynamicConstantBufferMapDiscard;
  PFND3D10DDI_RESOURCEMAP                               pfnDynamicIABufferMapDiscard;
  PFND3D10DDI_RESOURCEUNMAP                             pfnDynamicConstantBufferUnmap;
  PFND3D10DDI_SETCONSTANTBUFFERS                        pfnPsSetConstantBuffers;
  PFND3D10DDI_SETINPUTLAYOUT                            pfnIaSetInputLayout;
  PFND3D10DDI_IA_SETVERTEXBUFFERS                       pfnIaSetVertexBuffers;
  PFND3D10DDI_IA_SETINDEXBUFFER                         pfnIaSetIndexBuffer;
  PFND3D10DDI_DRAWINDEXEDINSTANCED                      pfnDrawIndexedInstanced;
  PFND3D10DDI_DRAWINSTANCED                             pfnDrawInstanced;
  PFND3D10DDI_RESOURCEMAP                               pfnDynamicResourceMapDiscard;
  PFND3D10DDI_RESOURCEUNMAP                             pfnDynamicResourceUnmap;
  PFND3D10DDI_SETCONSTANTBUFFERS                        pfnGsSetConstantBuffers;
  PFND3D10DDI_SETSHADER                                 pfnGsSetShader;
  PFND3D10DDI_IA_SETTOPOLOGY                            pfnIaSetTopology;
  PFND3D10DDI_RESOURCEMAP                               pfnStagingResourceMap;
  PFND3D10DDI_RESOURCEUNMAP                             pfnStagingResourceUnmap;
  PFND3D10DDI_SETSHADERRESOURCES                        pfnVsSetShaderResources;
  PFND3D10DDI_SETSAMPLERS                               pfnVsSetSamplers;
  PFND3D10DDI_SETSHADERRESOURCES                        pfnGsSetShaderResources;
  PFND3D10DDI_SETSAMPLERS                               pfnGsSetSamplers;
  PFND3D11DDI_SETRENDERTARGETS                          pfnSetRenderTargets;
  PFND3D10DDI_SHADERRESOURCEVIEWREADAFTERWRITEHAZARD    pfnShaderResourceViewReadAfterWriteHazard;
  PFND3D10DDI_RESOURCEREADAFTERWRITEHAZARD              pfnResourceReadAfterWriteHazard;
  PFND3D10DDI_SETBLENDSTATE                             pfnSetBlendState;
  PFND3D10DDI_SETDEPTHSTENCILSTATE                      pfnSetDepthStencilState;
  PFND3D10DDI_SETRASTERIZERSTATE                        pfnSetRasterizerState;
  PFND3D10DDI_QUERYEND                                  pfnQueryEnd;
  PFND3D10DDI_QUERYBEGIN                                pfnQueryBegin;
  PFND3D10DDI_RESOURCECOPYREGION                        pfnResourceCopyRegion;
  PFND3D10DDI_RESOURCEUPDATESUBRESOURCEUP               pfnResourceUpdateSubresourceUP;
  PFND3D10DDI_SO_SETTARGETS                             pfnSoSetTargets;
  PFND3D10DDI_DRAWAUTO                                  pfnDrawAuto;
  PFND3D10DDI_SETVIEWPORTS                              pfnSetViewports;
  PFND3D10DDI_SETSCISSORRECTS                           pfnSetScissorRects;
  PFND3D10DDI_CLEARRENDERTARGETVIEW                     pfnClearRenderTargetView;
  PFND3D10DDI_CLEARDEPTHSTENCILVIEW                     pfnClearDepthStencilView;
  PFND3D10DDI_SETPREDICATION                            pfnSetPredication;
  PFND3D10DDI_QUERYGETDATA                              pfnQueryGetData;
  PFND3D10DDI_FLUSH                                     pfnFlush;
  PFND3D10DDI_GENMIPS                                   pfnGenMips;
  PFND3D10DDI_RESOURCECOPY                              pfnResourceCopy;
  PFND3D10DDI_RESOURCERESOLVESUBRESOURCE                pfnResourceResolveSubresource;
  PFND3D10DDI_RESOURCEMAP                               pfnResourceMap;
  PFND3D10DDI_RESOURCEUNMAP                             pfnResourceUnmap;
  PFND3D10DDI_RESOURCEISSTAGINGBUSY                     pfnResourceIsStagingBusy;
  PFND3D11DDI_RELOCATEDEVICEFUNCS                       pfnRelocateDeviceFuncs;
  PFND3D11DDI_CALCPRIVATERESOURCESIZE                   pfnCalcPrivateResourceSize;
  PFND3D10DDI_CALCPRIVATEOPENEDRESOURCESIZE             pfnCalcPrivateOpenedResourceSize;
  PFND3D11DDI_CREATERESOURCE                            pfnCreateResource;
  PFND3D10DDI_OPENRESOURCE                              pfnOpenResource;
  PFND3D10DDI_DESTROYRESOURCE                           pfnDestroyResource;
  PFND3D11DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE         pfnCalcPrivateShaderResourceViewSize;
  PFND3D11DDI_CREATESHADERRESOURCEVIEW                  pfnCreateShaderResourceView;
  PFND3D10DDI_DESTROYSHADERRESOURCEVIEW                 pfnDestroyShaderResourceView;
  PFND3D10DDI_CALCPRIVATERENDERTARGETVIEWSIZE           pfnCalcPrivateRenderTargetViewSize;
  PFND3D10DDI_CREATERENDERTARGETVIEW                    pfnCreateRenderTargetView;
  PFND3D10DDI_DESTROYRENDERTARGETVIEW                   pfnDestroyRenderTargetView;
  PFND3D11DDI_CALCPRIVATEDEPTHSTENCILVIEWSIZE           pfnCalcPrivateDepthStencilViewSize;
  PFND3D11DDI_CREATEDEPTHSTENCILVIEW                    pfnCreateDepthStencilView;
  PFND3D10DDI_DESTROYDEPTHSTENCILVIEW                   pfnDestroyDepthStencilView;
  PFND3D10DDI_CALCPRIVATEELEMENTLAYOUTSIZE              pfnCalcPrivateElementLayoutSize;
  PFND3D10DDI_CREATEELEMENTLAYOUT                       pfnCreateElementLayout;
  PFND3D10DDI_DESTROYELEMENTLAYOUT                      pfnDestroyElementLayout;
  PFND3D10_1DDI_CALCPRIVATEBLENDSTATESIZE               pfnCalcPrivateBlendStateSize;
  PFND3D10_1DDI_CREATEBLENDSTATE                        pfnCreateBlendState;
  PFND3D10DDI_DESTROYBLENDSTATE                         pfnDestroyBlendState;
  PFND3D10DDI_CALCPRIVATEDEPTHSTENCILSTATESIZE          pfnCalcPrivateDepthStencilStateSize;
  PFND3D10DDI_CREATEDEPTHSTENCILSTATE                   pfnCreateDepthStencilState;
  PFND3D10DDI_DESTROYDEPTHSTENCILSTATE                  pfnDestroyDepthStencilState;
  PFND3D10DDI_CALCPRIVATERASTERIZERSTATESIZE            pfnCalcPrivateRasterizerStateSize;
  PFND3D10DDI_CREATERASTERIZERSTATE                     pfnCreateRasterizerState;
  PFND3D10DDI_DESTROYRASTERIZERSTATE                    pfnDestroyRasterizerState;
  PFND3D10DDI_CALCPRIVATESHADERSIZE                     pfnCalcPrivateShaderSize;
  PFND3D10DDI_CREATEVERTEXSHADER                        pfnCreateVertexShader;
  PFND3D10DDI_CREATEGEOMETRYSHADER                      pfnCreateGeometryShader;
  PFND3D10DDI_CREATEPIXELSHADER                         pfnCreatePixelShader;
  PFND3D11DDI_CALCPRIVATEGEOMETRYSHADERWITHSTREAMOUTPUT pfnCalcPrivateGeometryShaderWithStreamOutput;
  PFND3D11DDI_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT      pfnCreateGeometryShaderWithStreamOutput;
  PFND3D10DDI_DESTROYSHADER                             pfnDestroyShader;
  PFND3D10DDI_CALCPRIVATESAMPLERSIZE                    pfnCalcPrivateSamplerSize;
  PFND3D10DDI_CREATESAMPLER                             pfnCreateSampler;
  PFND3D10DDI_DESTROYSAMPLER                            pfnDestroySampler;
  PFND3D10DDI_CALCPRIVATEQUERYSIZE                      pfnCalcPrivateQuerySize;
  PFND3D10DDI_CREATEQUERY                               pfnCreateQuery;
  PFND3D10DDI_DESTROYQUERY                              pfnDestroyQuery;
  PFND3D10DDI_CHECKFORMATSUPPORT                        pfnCheckFormatSupport;
  PFND3D10DDI_CHECKMULTISAMPLEQUALITYLEVELS             pfnCheckMultisampleQualityLevels;
  PFND3D10DDI_CHECKCOUNTERINFO                          pfnCheckCounterInfo;
  PFND3D10DDI_CHECKCOUNTER                              pfnCheckCounter;
  PFND3D10DDI_DESTROYDEVICE                             pfnDestroyDevice;
  PFND3D10DDI_SETTEXTFILTERSIZE                         pfnSetTextFilterSize;
  PFND3D10DDI_RESOURCECOPY                              pfnResourceConvert;
  PFND3D10DDI_RESOURCECOPYREGION                        pfnResourceConvertRegion;
  PFND3D11DDI_DRAWINDEXEDINSTANCEDINDIRECT              pfnDrawIndexedInstancedIndirect;
  PFND3D11DDI_DRAWINSTANCEDINDIRECT                     pfnDrawInstancedIndirect;
  PFND3D11DDI_COMMANDLISTEXECUTE                        pfnCommandListExecute;
  PFND3D10DDI_SETSHADERRESOURCES                        pfnHsSetShaderResources;
  PFND3D10DDI_SETSHADER                                 pfnHsSetShader;
  PFND3D10DDI_SETSAMPLERS                               pfnHsSetSamplers;
  PFND3D10DDI_SETCONSTANTBUFFERS                        pfnHsSetConstantBuffers;
  PFND3D10DDI_SETSHADERRESOURCES                        pfnDsSetShaderResources;
  PFND3D10DDI_SETSHADER                                 pfnDsSetShader;
  PFND3D10DDI_SETSAMPLERS                               pfnDsSetSamplers;
  PFND3D10DDI_SETCONSTANTBUFFERS                        pfnDsSetConstantBuffers;
  PFND3D11DDI_CREATEHULLSHADER                          pfnCreateHullShader;
  PFND3D11DDI_CREATEDOMAINSHADER                        pfnCreateDomainShader;
  PFND3D11DDI_CHECKDEFERREDCONTEXTHANDLESIZES           pfnCheckDeferredContextHandleSizes;
  PFND3D11DDI_CALCDEFERREDCONTEXTHANDLESIZE             pfnCalcDeferredContextHandleSize;
  PFND3D11DDI_CALCPRIVATEDEFERREDCONTEXTSIZE            pfnCalcPrivateDeferredContextSize;
  PFND3D11DDI_CREATEDEFERREDCONTEXT                     pfnCreateDeferredContext;
  PFND3D11DDI_ABANDONCOMMANDLIST                        pfnAbandonCommandList;
  PFND3D11DDI_CALCPRIVATECOMMANDLISTSIZE                pfnCalcPrivateCommandListSize;
  PFND3D11DDI_CREATECOMMANDLIST                         pfnCreateCommandList;
  PFND3D11DDI_DESTROYCOMMANDLIST                        pfnDestroyCommandList;
  PFND3D11DDI_CALCPRIVATETESSELLATIONSHADERSIZE         pfnCalcPrivateTessellationShaderSize;
  PFND3D11DDI_SETSHADER_WITH_IFACES                     pfnPsSetShaderWithIfaces;
  PFND3D11DDI_SETSHADER_WITH_IFACES                     pfnVsSetShaderWithIfaces;
  PFND3D11DDI_SETSHADER_WITH_IFACES                     pfnGsSetShaderWithIfaces;
  PFND3D11DDI_SETSHADER_WITH_IFACES                     pfnHsSetShaderWithIfaces;
  PFND3D11DDI_SETSHADER_WITH_IFACES                     pfnDsSetShaderWithIfaces;
  PFND3D11DDI_SETSHADER_WITH_IFACES                     pfnCsSetShaderWithIfaces;
  PFND3D11DDI_CREATECOMPUTESHADER                       pfnCreateComputeShader;
  PFND3D10DDI_SETSHADER                                 pfnCsSetShader;
  PFND3D10DDI_SETSHADERRESOURCES                        pfnCsSetShaderResources;
  PFND3D10DDI_SETSAMPLERS                               pfnCsSetSamplers;
  PFND3D10DDI_SETCONSTANTBUFFERS                        pfnCsSetConstantBuffers;
  PFND3D11DDI_CALCPRIVATEUNORDEREDACCESSVIEWSIZE        pfnCalcPrivateUnorderedAccessViewSize;
  PFND3D11DDI_CREATEUNORDEREDACCESSVIEW                 pfnCreateUnorderedAccessView;
  PFND3D11DDI_DESTROYUNORDEREDACCESSVIEW                pfnDestroyUnorderedAccessView;
  PFND3D11DDI_CLEARUNORDEREDACCESSVIEWUINT              pfnClearUnorderedAccessViewUint;
  PFND3D11DDI_CLEARUNORDEREDACCESSVIEWFLOAT             pfnClearUnorderedAccessViewFloat;
  PFND3D11DDI_SETUNORDEREDACCESSVIEWS                   pfnCsSetUnorderedAccessViews;
  PFND3D11DDI_DISPATCH                                  pfnDispatch;
  PFND3D11DDI_DISPATCHINDIRECT                          pfnDispatchIndirect;
  PFND3D11DDI_SETRESOURCEMINLOD                         pfnSetResourceMinLOD;
  PFND3D11DDI_COPYSTRUCTURECOUNT                        pfnCopyStructureCount;
  PFND3D11DDI_RECYCLECOMMANDLIST                        pfnRecycleCommandList;
  PFND3D11DDI_RECYCLECREATECOMMANDLIST                  pfnRecycleCreateCommandList;
  PFND3D11DDI_RECYCLECREATEDEFERREDCONTEXT              pfnRecycleCreateDeferredContext;
  PFND3D11DDI_DESTROYCOMMANDLIST                        pfnRecycleDestroyCommandList;
} D3D11DDI_DEVICEFUNCS;
````


## -struct-fields

### -field pfnDefaultConstantBufferUpdateSubresourceUP

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourceupdatesubresourceup.md">DefaultConstantBufferUpdateSubresourceUP</a> function.


### -field pfnVsSetConstantBuffers

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setconstantbuffers.md">VsSetConstantBuffers</a> function.


### -field pfnPsSetShaderResources

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setshaderresources.md">PsSetShaderResources</a> function.


### -field pfnPsSetShader

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setshader.md">PsSetShader</a> function. 


### -field pfnPsSetSamplers

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setsamplers.md">PsSetSamplers</a> function.


### -field pfnVsSetShader

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setshader.md">VsSetShader</a> function.


### -field pfnDrawIndexed

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_drawindexed.md">DrawIndexed</a> function.


### -field pfnDraw

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_draw.md">Draw</a> function.


### -field pfnDynamicIABufferMapNoOverwrite

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcemap.md">ResourceMap</a> function. For more information about whether to implement a separate <b>DynamicIABufferMapNoOverwrite</b> function or to point to the multipurpose <i>ResourceMap</i>, see the Remarks section of <i>ResourceMap</i>. 


### -field pfnDynamicIABufferUnmap

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourceunmap.md">ResourceUnmap</a> function. For more information about whether to implement a separate <b>DynamicIABufferUnmap</b> function or to point to the multipurpose <i>ResourceUnmap</i>, see the Remarks section of <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcemap.md">ResourceMap</a>. 


### -field pfnDynamicConstantBufferMapDiscard

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcemap.md">ResourceMap</a> function. For more information about whether to implement a separate <b>DynamicConstantBufferMapDiscard</b> function or to point to the multipurpose <i>ResourceMap</i>, see the Remarks section of <i>ResourceMap</i>. 


### -field pfnDynamicIABufferMapDiscard

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcemap.md">ResourceMap</a> function. For more information about whether to implement a separate <b>DynamicIABufferMapDiscard</b> function or to point to the multipurpose <i>ResourceMap</i>, see the Remarks section of <i>ResourceMap</i>. 


### -field pfnDynamicConstantBufferUnmap

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourceunmap.md">ResourceUnmap</a> function. For more information about whether to implement a separate <b>DynamicConstantBufferUnmap</b> function or to point to the multipurpose <i>ResourceUnmap</i>, see the Remarks section of <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcemap.md">ResourceMap</a>. 


### -field pfnPsSetConstantBuffers

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setconstantbuffers.md">PsSetConstantBuffers</a> function.


### -field pfnIaSetInputLayout

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setinputlayout.md">IaSetInputLayout</a> function.


### -field pfnIaSetVertexBuffers

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_ia_setvertexbuffers.md">IaSetVertexBuffers</a> function.


### -field pfnIaSetIndexBuffer

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_ia_setindexbuffer.md">IaSetIndexBuffer</a> function.


### -field pfnDrawIndexedInstanced

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_drawindexedinstanced.md">DrawIndexedInstanced</a> function.


### -field pfnDrawInstanced

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_drawinstanced.md">DrawInstanced</a> function.


### -field pfnDynamicResourceMapDiscard

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcemap.md">ResourceMap</a> function. For more information about whether to implement a separate <b>DynamicResourceMapDiscard</b> function or to point to the multipurpose <i>ResourceMap</i>, see the Remarks section of <i>ResourceMap</i>. 


### -field pfnDynamicResourceUnmap

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourceunmap.md">ResourceUnmap</a> function. For more information about whether to implement a separate <b>DynamicResourceUnmap</b> function or to point to the multipurpose <i>ResourceUnmap</i>, see the Remarks section of <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcemap.md">ResourceMap</a>. 


### -field pfnGsSetConstantBuffers

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setconstantbuffers.md">GsSetConstantBuffers</a> function.


### -field pfnGsSetShader

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setshader.md">GsSetShader</a> function.


### -field pfnIaSetTopology

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_ia_settopology.md">IaSetTopology</a> function.


### -field pfnStagingResourceMap

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcemap.md">ResourceMap</a> function. For more information about whether to implement a separate <b>StagingResourceMap</b> function or to point to the multipurpose <i>ResourceMap</i>, see the Remarks section of <i>ResourceMap</i>. 


### -field pfnStagingResourceUnmap

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourceunmap.md">ResourceUnmap</a> function. For more information about whether to implement a separate <b>StagingResourceUnmap</b> function or to point to the multipurpose <i>ResourceUnmap</i>, see the Remarks section of <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcemap.md">ResourceMap</a>. 


### -field pfnVsSetShaderResources

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setshaderresources.md">VsSetShaderResources</a> function.


### -field pfnVsSetSamplers

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setsamplers.md">VsSetSamplers</a> function.


### -field pfnGsSetShaderResources

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setshaderresources.md">GsSetShaderResources</a> function.


### -field pfnGsSetSamplers

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setsamplers.md">GsSetSamplers</a> function.


### -field pfnSetRenderTargets

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_setrendertargets.md">SetRenderTargets(D3D11)</a> function.


### -field pfnShaderResourceViewReadAfterWriteHazard

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_shaderresourceviewreadafterwritehazard.md">ShaderResourceViewReadAfterWriteHazard</a> function.


### -field pfnResourceReadAfterWriteHazard

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcereadafterwritehazard.md">ResourceReadAfterWriteHazard</a> function.


### -field pfnSetBlendState

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setblendstate.md">SetBlendState</a> function.


### -field pfnSetDepthStencilState

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setdepthstencilstate.md">SetDepthStencilState</a> function.


### -field pfnSetRasterizerState

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setrasterizerstate.md">SetRasterizerState</a> function.


### -field pfnQueryEnd

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_queryend.md">QueryEnd</a> function.


### -field pfnQueryBegin

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_querybegin.md">QueryBegin</a> function.


### -field pfnResourceCopyRegion

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcecopyregion.md">ResourceCopyRegion</a> function.


### -field pfnResourceUpdateSubresourceUP

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourceupdatesubresourceup.md">ResourceUpdateSubresourceUP</a> function.


### -field pfnSoSetTargets

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_so_settargets.md">SoSetTargets</a> function.


### -field pfnDrawAuto

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_drawauto.md">DrawAuto</a> function.


### -field pfnSetViewports

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setviewports.md">SetViewports</a> function.


### -field pfnSetScissorRects

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setscissorrects.md">SetScissorRects</a> function.


### -field pfnClearRenderTargetView

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_clearrendertargetview.md">ClearRenderTargetView</a> function.


### -field pfnClearDepthStencilView

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_cleardepthstencilview.md">ClearDepthStencilView</a> function.


### -field pfnSetPredication

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setpredication.md">SetPredication</a> function.


### -field pfnQueryGetData

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_querygetdata.md">QueryGetData</a> function.


### -field pfnFlush

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_flush.md">Flush(D3D10)</a> function.


### -field pfnGenMips

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_genmips.md">GenMips</a> function.


### -field pfnResourceCopy

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcecopy.md">ResourceCopy</a> function.


### -field pfnResourceResolveSubresource

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourceresolvesubresource.md">ResourceResolveSubresource</a> function.


### -field pfnResourceMap

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcemap.md">ResourceMap</a> function.


### -field pfnResourceUnmap

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourceunmap.md">ResourceUnmap</a> function.


### -field pfnResourceIsStagingBusy

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourceisstagingbusy.md">ResourceIsStagingBusy</a> function.


### -field pfnRelocateDeviceFuncs

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_relocatedevicefuncs.md">RelocateDeviceFuncs(D3D11)</a> function.


### -field pfnCalcPrivateResourceSize

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_calcprivateresourcesize.md">CalcPrivateResourceSize(D3D11)</a> function.


### -field pfnCalcPrivateOpenedResourceSize

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivateopenedresourcesize.md">CalcPrivateOpenedResourceSize</a> function.


### -field pfnCreateResource

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createresource.md">CreateResource(D3D11)</a> function.


### -field pfnOpenResource

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_openresource.md">OpenResource(D3D10)</a> function.


### -field pfnDestroyResource

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroyresource.md">DestroyResource(D3D10)</a> function.


### -field pfnCalcPrivateShaderResourceViewSize

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_calcprivateshaderresourceviewsize.md">CalcPrivateShaderResourceViewSize(D3D11)</a> function.


### -field pfnCreateShaderResourceView

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createshaderresourceview.md">CreateShaderResourceView(D3D11)</a> function.


### -field pfnDestroyShaderResourceView

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroyshaderresourceview.md">DestroyShaderResourceView</a> function.


### -field pfnCalcPrivateRenderTargetViewSize

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivaterendertargetviewsize.md">CalcPrivateRenderTargetViewSize</a> function.


### -field pfnCreateRenderTargetView

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createrendertargetview.md">CreateRenderTargetView</a> function.


### -field pfnDestroyRenderTargetView

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroyrendertargetview.md">DestroyRenderTargetView</a> function.


### -field pfnCalcPrivateDepthStencilViewSize

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_calcprivatedepthstencilviewsize.md">CalcPrivateDepthStencilViewSize(D3D11)</a> function.


### -field pfnCreateDepthStencilView

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createdepthstencilview.md">CreateDepthStencilView(D3D11)</a> function.


### -field pfnDestroyDepthStencilView

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroydepthstencilview.md">DestroyDepthStencilView</a> function.


### -field pfnCalcPrivateElementLayoutSize

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivateelementlayoutsize.md">CalcPrivateElementLayoutSize</a> function.


### -field pfnCreateElementLayout

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createelementlayout.md">CreateElementLayout</a> function.


### -field pfnDestroyElementLayout

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroyelementlayout.md">DestroyElementLayout</a> function.


### -field pfnCalcPrivateBlendStateSize

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10_1ddi_calcprivateblendstatesize.md">CalcPrivateBlendStateSize(D3D10_1)</a> function.


### -field pfnCreateBlendState

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10_1ddi_createblendstate.md">CreateBlendState(D3D10_1)</a> function.


### -field pfnDestroyBlendState

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroyblendstate.md">DestroyBlendState</a> function.


### -field pfnCalcPrivateDepthStencilStateSize

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivatedepthstencilstatesize.md">CalcPrivateDepthStencilStateSize</a> function.


### -field pfnCreateDepthStencilState

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdepthstencilstate.md">CreateDepthStencilState</a> function.


### -field pfnDestroyDepthStencilState

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroydepthstencilstate.md">DestroyDepthStencilState</a> function.


### -field pfnCalcPrivateRasterizerStateSize

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivaterasterizerstatesize.md">CalcPrivateRasterizerStateSize</a> function.


### -field pfnCreateRasterizerState

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createrasterizerstate.md">CreateRasterizerState</a> function.


### -field pfnDestroyRasterizerState

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroyrasterizerstate.md">DestroyRasterizerState</a> function.


### -field pfnCalcPrivateShaderSize

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivateshadersize.md">CalcPrivateShaderSize</a> function.


### -field pfnCreateVertexShader

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createvertexshader.md">CreateVertexShader(D3D10)</a> function.


### -field pfnCreateGeometryShader

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_creategeometryshader.md">CreateGeometryShader</a> function.


### -field pfnCreatePixelShader

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createpixelshader.md">CreatePixelShader(D3D10)</a> function.


### -field pfnCalcPrivateGeometryShaderWithStreamOutput

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_calcprivategeometryshaderwithstreamoutput.md">CalcPrivateGeometryShaderWithStreamOutput(D3D11)</a> function. 


### -field pfnCreateGeometryShaderWithStreamOutput

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_creategeometryshaderwithstreamoutput.md">CreateGeometryShaderWithStreamOutput(D3D11)</a> function.


### -field pfnDestroyShader

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroyshader.md">DestroyShader</a> function.


### -field pfnCalcPrivateSamplerSize

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivatesamplersize.md">CalcPrivateSamplerSize</a> function.


### -field pfnCreateSampler

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createsampler.md">CreateSampler</a> function.


### -field pfnDestroySampler

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroysampler.md">DestroySampler</a> function.


### -field pfnCalcPrivateQuerySize

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivatequerysize.md">CalcPrivateQuerySize</a> function.


### -field pfnCreateQuery

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createquery.md">CreateQuery(D3D10)</a> function.


### -field pfnDestroyQuery

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroyquery.md">DestroyQuery(D3D10)</a> function.


### -field pfnCheckFormatSupport

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_checkformatsupport.md">CheckFormatSupport</a> function.


### -field pfnCheckMultisampleQualityLevels

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_checkmultisamplequalitylevels.md">CheckMultisampleQualityLevels</a> function.


### -field pfnCheckCounterInfo

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_checkcounterinfo.md">CheckCounterInfo</a> function.


### -field pfnCheckCounter

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_checkcounter.md">CheckCounter</a> function.


### -field pfnDestroyDevice

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroydevice.md">DestroyDevice(D3D10)</a> function.


### -field pfnSetTextFilterSize

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_settextfiltersize.md">SetTextFilterSize</a> function.

<b>The following two functions are supported beginning with Windows Vista with Service Pack 1 (SP1) and Windows Server 2008:  </b>


### -field pfnResourceConvert

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcecopy.md">ResourceCopy</a> function. For more information about whether to implement a separate <b>ResourceConvert</b> function or to point to the multipurpose <i>ResourceCopy</i>, see the Remarks section of <i>ResourceCopy</i>.  


### -field pfnResourceConvertRegion

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcecopyregion.md">ResourceCopyRegion</a> function. For more information about whether to implement a separate <b>ResourceConvertRegion</b> function or to point to the multipurpose <i>ResourceCopyRegion</i>, see the Remarks section of <i>ResourceCopyRegion</i>.

<b>The following functions are supported beginning with Windows 7:  </b>


### -field pfnDrawIndexedInstancedIndirect

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_drawindexedinstancedindirect.md">DrawIndexedInstancedIndirect</a> function.


### -field pfnDrawInstancedIndirect

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_drawinstancedindirect.md">DrawInstancedIndirect</a> function.


### -field pfnCommandListExecute

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_commandlistexecute.md">CommandListExecute</a> function. The driver is only required to implement <i>CommandListExecute</i> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability. 


### -field pfnHsSetShaderResources

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setshaderresources.md">HsSetShaderResources</a> function.


### -field pfnHsSetShader

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setshader.md">HsSetShader</a> function.


### -field pfnHsSetSamplers

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setsamplers.md">HsSetSamplers</a> function.


### -field pfnHsSetConstantBuffers

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setconstantbuffers.md">HsSetConstantBuffers</a> function.


### -field pfnDsSetShaderResources

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setshaderresources.md">DsSetShaderResources</a> function.


### -field pfnDsSetShader

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setshader.md">DsSetShader</a> function.


### -field pfnDsSetSamplers

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setsamplers.md">DsSetSamplers</a> function.


### -field pfnDsSetConstantBuffers

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setconstantbuffers.md">DsSetConstantBuffers</a> function.


### -field pfnCreateHullShader

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createhullshader.md">CreateHullShader</a> function.


### -field pfnCreateDomainShader

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createdomainshader.md">CreateDomainShader</a> function.


### -field pfnCheckDeferredContextHandleSizes

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_checkdeferredcontexthandlesizes.md">CheckDeferredContextHandleSizes</a> function. The driver is only required to implement <i>CheckDeferredContextHandleSizes</i> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability. 


### -field pfnCalcDeferredContextHandleSize

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_calcdeferredcontexthandlesize.md">CalcDeferredContextHandleSize</a> function. The driver is only required to implement <i>CalcDeferredContextHandleSize</i> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability. 


### -field pfnCalcPrivateDeferredContextSize

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_calcprivatedeferredcontextsize.md">CalcPrivateDeferredContextSize</a> function. The driver is only required to implement <i>CalcPrivateDeferredContextSize</i> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability. 


### -field pfnCreateDeferredContext

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createdeferredcontext.md">CreateDeferredContext</a> function. The driver is only required to implement <i>CreateDeferredContext</i> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability. 


### -field pfnAbandonCommandList

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_abandoncommandlist.md">AbandonCommandList</a> function. The driver is only required to implement <i>AbandonCommandList</i> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability. 


### -field pfnCalcPrivateCommandListSize

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_calcprivatecommandlistsize.md">CalcPrivateCommandListSize</a> function. The driver is only required to implement <i>CalcPrivateCommandListSize</i> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability. 


### -field pfnCreateCommandList

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createcommandlist.md">CreateCommandList</a> function. The driver is only required to implement <i>CreateCommandList</i> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability. 


### -field pfnDestroyCommandList

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_destroycommandlist.md">DestroyCommandList</a> function. The driver is only required to implement <i>DestroyCommandList</i> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability. 


### -field pfnCalcPrivateTessellationShaderSize

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_calcprivatetessellationshadersize.md">CalcPrivateTessellationShaderSize</a> function. 


### -field pfnPsSetShaderWithIfaces

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces.md">PsSetShaderWithIfaces</a> function. 


### -field pfnVsSetShaderWithIfaces

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces.md">VsSetShaderWithIfaces</a> function. 


### -field pfnGsSetShaderWithIfaces

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces.md">GsSetShaderWithIfaces</a> function. 


### -field pfnHsSetShaderWithIfaces

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces.md">HsSetShaderWithIfaces</a> function. 


### -field pfnDsSetShaderWithIfaces

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces.md">DsSetShaderWithIfaces</a> function. 


### -field pfnCsSetShaderWithIfaces

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_setshader_with_ifaces.md">CsSetShaderWithIfaces</a> function. 


### -field pfnCreateComputeShader

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createcomputeshader.md">CreateComputeShader</a> function. 


### -field pfnCsSetShader

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setshader.md">CsSetShader</a> function. 


### -field pfnCsSetShaderResources

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setshaderresources.md">CsSetShaderResources</a> function. 


### -field pfnCsSetSamplers

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setsamplers.md">CsSetSamplers</a> function. 


### -field pfnCsSetConstantBuffers

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setconstantbuffers.md">CsSetConstantBuffers</a> function. 


### -field pfnCalcPrivateUnorderedAccessViewSize

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_calcprivateunorderedaccessviewsize.md">CalcPrivateUnorderedAccessViewSize</a> function. 


### -field pfnCreateUnorderedAccessView

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createunorderedaccessview.md">CreateUnorderedAccessView</a> function. 


### -field pfnDestroyUnorderedAccessView

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_destroyunorderedaccessview.md">DestroyUnorderedAccessView</a> function. 


### -field pfnClearUnorderedAccessViewUint

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_clearunorderedaccessviewuint.md">ClearUnorderedAccessViewUINT</a> function. 


### -field pfnClearUnorderedAccessViewFloat

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_clearunorderedaccessviewfloat.md">ClearUnorderedAccessViewFLOAT</a> function. 


### -field pfnCsSetUnorderedAccessViews

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_setunorderedaccessviews.md">CsSetUnorderedAccessViews</a> function. 


### -field pfnDispatch

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_dispatch.md">Dispatch</a> function. 


### -field pfnDispatchIndirect

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_dispatchindirect.md">DispatchIndirect</a> function. 


### -field pfnSetResourceMinLOD

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_setresourceminlod.md">SetResourceMinLOD</a> function. 


### -field pfnCopyStructureCount

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_copystructurecount.md">CopyStructureCount</a> function. 


### -field pfnRecycleCommandList

A pointer to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_recyclecommandlist.md">RecycleCommandList</a> function. 


### -field pfnRecycleCreateCommandList

A pointer to the driver's   <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_recyclecreatecommandlist.md">RecycleCreateCommandList</a> function. 


### -field pfnRecycleCreateDeferredContext

A pointer to the driver's  <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_recyclecreatedeferredcontext.md">RecycleCreateDeferredContext</a> function. 


### -field pfnRecycleDestroyCommandList

A pointer to the driver's  <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_destroycommandlist.md">RecycleDestroyCommandList</a> function. 


## -remarks
The order of user-mode display driver functions (that is, the order of the members of the D3D11DDI_DEVICEFUNCS structure) is in decreasing order of priority (in regard to performance).

The user-mode display driver can use different names for these functions because the address of the function table (this structure) is shared between the Direct3D 11 runtime and the driver through the call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a> function.

The <b>pfnResetPrimitiveID</b> and  <b>pfnSetVertexPipelineOutput</b> members (not shown here) and their data types are reserved for system use and should not be used in your driver.

For a list of the functions that are not leveraged for deferred contexts, see <a href="https://msdn.microsoft.com/f6e7898a-7fb8-4a70-ab2e-3372a28db6f4">Excluding DDI Functions for Deferred Contexts</a>.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
D3D11DDI_DEVICEFUNCS is supported beginning with the Windows 7 operating system. 

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3d10umddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createdevice.md">D3D10DDIARG_CREATEDEVICE</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_devicefuncs~r1.md">D3D11_1DDI_DEVICEFUNCS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11DDI_DEVICEFUNCS structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

