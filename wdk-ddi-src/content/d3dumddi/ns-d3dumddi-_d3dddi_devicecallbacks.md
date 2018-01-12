---
UID: NS:d3dumddi._D3DDDI_DEVICECALLBACKS
title: _D3DDDI_DEVICECALLBACKS
author: windows-driver-content
description: The D3DDDI_DEVICECALLBACKS structure contains Microsoft Direct3D runtime callback functions that the user-mode display driver can use.
old-location: display\d3dddi_devicecallbacks.htm
old-project: display
ms.assetid: 29810132-5f53-4ba6-8302-6de315ecd04a
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DDDI_DEVICECALLBACKS, D3DDDI_DEVICECALLBACKS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDI_DEVICECALLBACKS
req.alt-loc: D3dumddi.h
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
req.typenames: D3DDDI_DEVICECALLBACKS
---

# _D3DDDI_DEVICECALLBACKS structure



## -description
The D3DDDI_DEVICECALLBACKS structure contains Microsoft Direct3D runtime callback functions that the user-mode display driver can use.



## -syntax

````
typedef struct _D3DDDI_DEVICECALLBACKS {
  PFND3DDDI_ALLOCATECB                            pfnAllocateCb;
  PFND3DDDI_DEALLOCATECB                          pfnDeallocateCb;
  PFND3DDDI_SETPRIORITYCB                         pfnSetPriorityCb;
  PFND3DDDI_QUERYRESIDENCYCB                      pfnQueryResidencyCb;
  PFND3DDDI_SETDISPLAYMODECB                      pfnSetDisplayModeCb;
  PFND3DDDI_PRESENTCB                             pfnPresentCb;
  PFND3DDDI_RENDERCB                              pfnRenderCb;
  PFND3DDDI_LOCKCB                                pfnLockCb;
  PFND3DDDI_UNLOCKCB                              pfnUnlockCb;
  PFND3DDDI_ESCAPECB                              pfnEscapeCb;
  PFND3DDDI_CREATEOVERLAYCB                       pfnCreateOverlayCb;
  PFND3DDDI_UPDATEOVERLAYCB                       pfnUpdateOverlayCb;
  PFND3DDDI_FLIPOVERLAYCB                         pfnFlipOverlayCb;
  PFND3DDDI_DESTROYOVERLAYCB                      pfnDestroyOverlayCb;
  PFND3DDDI_CREATECONTEXTCB                       pfnCreateContextCb;
  PFND3DDDI_DESTROYCONTEXTCB                      pfnDestroyContextCb;
  PFND3DDDI_CREATESYNCHRONIZATIONOBJECTCB         pfnCreateSynchronizationObjectCb;
  PFND3DDDI_DESTROYSYNCHRONIZATIONOBJECTCB        pfnDestroySynchronizationObjectCb;
  PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTCB        pfnWaitForSynchronizationObjectCb;
  PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTCB         pfnSignalSynchronizationObjectCb;
  PFND3DDDI_SETASYNCCALLBACKSCB                   pfnSetAsyncCallbacksCb;
  PFND3DDDI_SETDISPLAYPRIVATEDRIVERFORMATCB       pfnSetDisplayPrivateDriverFormatCb;
#if (D3D_UMD_INTERFACE_VERSION >= D3D_UMD_INTERFACE_VERSION_WIN8)
  PFND3DDDI_OFFERALLOCATIONSCB                    pfnOfferAllocationsCb;
  PFND3DDDI_RECLAIMALLOCATIONSCB                  pfnReclaimAllocationsCb;
  PFND3DDDI_CREATESYNCHRONIZATIONOBJECT2CB        pfnCreateSynchronizationObject2Cb;
  PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECT2CB       pfnWaitForSynchronizationObject2Cb;
  PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECT2CB        pfnSignalSynchronizationObject2Cb;
  PFND3DDDI_PRESENTMULTIPLANEOVERLAYCB            pfnPresentMultiPlaneOverlayCb;
#endif 
#if (D3D_UMD_INTERFACE_VERSION >= D3D_UMD_INTERFACE_VERSION_WDDM1_3)
  PFND3DDDI_LOGUMDMARKERCB                        pfnLogUMDMarkerCb;
#endif 
#if (D3D_UMD_INTERFACE_VERSION >= D3D_UMD_INTERFACE_VERSION_WDDM2_0)
  PFND3DDDI_MAKERESIDENTCB                        pfnMakeResidentCb;
  PFND3DDDI_EVICTCB                               pfnEvictCb;
  PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMCPUCB pfnWaitForSynchronizationObjectFromCpuCb;
  PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTFROMCPUCB  pfnSignalSynchronizationObjectFromCpuCb;
  PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMGPUCB pfnWaitForSynchronizationObjectFromGpuCb;
  PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTFROMGPUCB  pfnSignalSynchronizationObjectFromGpuCb;
  PFND3DDDI_CREATEPAGINGQUEUECB                   pfnCreatePagingQueueCb;
  PFND3DDDI_DESTROYPAGINGQUEUECB                  pfnDestroyPagingQueueCb;
  PFND3DDDI_LOCK2CB                               pfnLock2Cb;
  PFND3DDDI_UNLOCK2CB                             pfnUnlock2Cb;
  PFND3DDDI_INVALIDATECACHECB                     pfnInvalidateCacheCb;
  PFND3DDDI_RESERVEGPUVIRTUALADDRESSCB            pfnReserveGpuVirtualAddressCb;
  PFND3DDDI_MAPGPUVIRTUALADDRESSCB                pfnMapGpuVirtualAddressCb;
  PFND3DDDI_FREEGPUVIRTUALADDRESSCB               pfnFreeGpuVirtualAddressCb;
  PFND3DDDI_UPDATEGPUVIRTUALADDRESSCB             pfnUpdateGpuVirtualAddressCb;
  PFND3DDDI_CREATECONTEXTVIRTUALCB                pfnCreateContextVirtualCb;
  PFND3DDDI_SUBMITCOMMANDCB                       pfnSubmitCommandCb;
  PFND3DDDI_DEALLOCATE2CB                         pfnDeallocate2Cb;
  PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2CB pfnSignalSynchronizationObjectFromGpu2Cb;
  PFND3DDDI_RECLAIMALLOCATIONS2CB                 pfnReclaimAllocations2Cb;
  PFND3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATACB pfnGetResourcePresentPrivateDriverDataCb;
#endif 
#if (D3D_UMD_INTERFACE_VERSION >= D3D_UMD_INTERFACE_VERSION_WDDM2_1_1)
  PFND3DDDI_UPDATEALLOCATIONPROPERTYCB            pfnUpdateAllocationPropertyCb;
#endif 
  PFND3DDDI_OFFERALLOCATIONS2CB                   pfnOfferAllocations2Cb;
  PFND3DDDI_RECLAIMALLOCATIONS3CB                 pfnReclaimAllocations3Cb;
} D3DDDI_DEVICECALLBACKS;
````


## -struct-fields

### -field pfnAllocateCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_allocatecb.md">pfnAllocateCb</a> function, which the user-mode display driver uses to request that the Direct3D runtime create a memory allocation for use by the driver.


### -field pfnDeallocateCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_deallocatecb.md">pfnDeallocateCb</a> function, which the user-mode display driver uses to request that the Direct3D runtime free memory that was previously allocated.


### -field pfnSetPriorityCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setprioritycb.md">pfnSetPriorityCb</a> function, which the user-mode display driver uses to set the priority of a resource or list of allocations.


### -field pfnQueryResidencyCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_queryresidencycb.md">pfnQueryResidencyCb</a> function, which the user-mode display driver uses to query the residency status of a resource or list of allocations.


### -field pfnSetDisplayModeCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setdisplaymodecb.md">pfnSetDisplayModeCb</a> function, which the user-mode display driver uses to set an allocation for displaying.


### -field pfnPresentCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_presentcb.md">pfnPresentCb</a> function, which the user-mode display driver uses to submit a present command to the display miniport driver.


### -field pfnRenderCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_rendercb.md">pfnRenderCb</a> function, which the user-mode display driver uses to submit a command buffer to the display miniport driver.


### -field pfnLockCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockcb.md">pfnLockCb</a> function, which the user-mode display driver uses to request a lock from the display miniport driver. This lock cannot be handled completely by the user-mode display driver.


### -field pfnUnlockCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_unlockcb.md">pfnUnlockCb</a> function, which the user-mode display driver uses to call the display miniport driver for an unlock. This unlock cannot be handled completely by the user-mode display driver. 


### -field pfnEscapeCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_escapecb.md">pfnEscapeCb</a> function, which the user-mode display driver uses to share information with the display miniport driver. 


### -field pfnCreateOverlayCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createoverlaycb.md">pfnCreateOverlayCb</a> function, which the user-mode display driver uses to create and display a kernel-mode overlay object. 


### -field pfnUpdateOverlayCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_updateoverlaycb.md">pfnUpdateOverlayCb</a> function, which the user-mode display driver uses to modify a kernel-mode overlay object. 


### -field pfnFlipOverlayCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_flipoverlaycb.md">pfnFlipOverlayCb</a> function, which the user-mode display driver uses to change the allocation that the overlay displays. 


### -field pfnDestroyOverlayCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroyoverlaycb.md">pfnDestroyOverlayCb</a> function, which the user-mode display driver uses to destroy a kernel-mode overlay object and stop the overlay from being displayed. 


### -field pfnCreateContextCb

A pointer to the <a href="https://msdn.microsoft.com/f3f5d6bc-3bc6-4214-830a-cffff01069cc">pfnCreateContextCb</a> function, which the user-mode display driver uses to create a context to submit requests to. 


### -field pfnDestroyContextCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroycontextcb.md">pfnDestroyContextCb</a> function, which the user-mode display driver uses to destroy a context that <a href="https://msdn.microsoft.com/f3f5d6bc-3bc6-4214-830a-cffff01069cc">pfnCreateContextCb</a> created. 


### -field pfnCreateSynchronizationObjectCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createsynchronizationobjectcb.md">pfnCreateSynchronizationObjectCb</a> function, which the user-mode display driver uses to create a synchronization object. 


### -field pfnDestroySynchronizationObjectCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroysynchronizationobjectcb.md">pfnDestroySynchronizationObjectCb</a> function, which the user-mode display driver uses to destroy a synchronization object that <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createsynchronizationobjectcb.md">pfnCreateSynchronizationObjectCb</a> created. 


### -field pfnWaitForSynchronizationObjectCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_waitforsynchronizationobjectcb.md">pfnWaitForSynchronizationObjectCb</a> function, which the user-mode display driver uses to wait for synchronization events to occur and then uses to return. 


### -field pfnSignalSynchronizationObjectCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectcb.md">pfnSignalSynchronizationObjectCb</a> function, which the user-mode display driver uses to signal that synchronization events are no longer owned by a context. 


### -field pfnSetAsyncCallbacksCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setasynccallbackscb.md">pfnSetAsyncCallbacksCb</a> function that the user-mode display driver uses to notify the Direct3D runtime whether the runtime will start or stop receiving calls to the runtime's callback functions from a worker thread.

Only DirectX 9 and Direct 9L versions of the runtime support the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setasynccallbackscb.md">pfnSetAsyncCallbacksCb</a> function. DirectX 10 and later versions of the runtime set the <b>pfnSetAsyncCallbacksCb</b> member to <b>NULL</b> when the runtime calls the user-mode display driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a> function to create a rendering device. 


### -field pfnSetDisplayPrivateDriverFormatCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setdisplayprivatedriverformatcb.md">pfnSetDisplayPrivateDriverFormatCb</a> function that the user-mode display driver uses to change the format of the shared primary surface. 


### -field pfnOfferAllocationsCb

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451693">pfnOfferAllocationsCb</a> function, which a WDDM 1.2 and later user-mode display driver   calls to offer  video memory allocations for reuse.

Supported starting with Windows 8.


### -field pfnReclaimAllocationsCb

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451695">pfnReclaimAllocationsCb</a> function, which a WDDM 1.2 and later user-mode display driver   calls to reclaim access to video memory allocations that were previously offered  for reuse.

Supported starting with Windows 8.


### -field pfnCreateSynchronizationObject2Cb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createsynchronizationobject2cb.md">pfnCreateSynchronizationObject2Cb</a> function, which a WDDM 1.2 and later user-mode display driver uses to create a GPU synchronization object.

Supported starting with Windows 8.


### -field pfnWaitForSynchronizationObject2Cb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_waitforsynchronizationobject2cb.md">pfnWaitForSynchronizationObject2Cb</a> function, which a WDDM 1.2 and later user-mode display driver uses to wait for GPU synchronization events to occur and then uses to return.

Supported starting with Windows 8.


### -field pfnSignalSynchronizationObject2Cb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobject2cb.md">pfnSignalSynchronizationObject2Cb</a> function, which a WDDM 1.2 and later user-mode display driver uses to signal that GPU synchronization events are no longer owned by a context.

Supported starting with Windows 8.


### -field pfnPresentMultiPlaneOverlayCb

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh780323">pfnPresentMultiPlaneOverlayCb (D3D)</a> function, which a WDDM 1.3 and later user-mode display driver uses to copy content from a source multiplane overlay allocation to a destination allocation.

Supported starting with Windows 8.1.


### -field pfnLogUMDMarkerCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_logumdmarkercb.md">pfnLogUMDMarkerCb</a> function, which a WDDM 1.3 and later user-mode display driver calls to log a custom Event Tracing for Windows (ETW) marker event.

Supported starting with Windows 8.1.


### -field pfnMakeResidentCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_makeresidentcb.md">pfnMakeResidentCb</a> function.


### -field pfnEvictCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_evictcb.md">pfnEvictCb</a> function.


### -field pfnWaitForSynchronizationObjectFromCpuCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_waitforsynchronizationobjectfromcpucb.md">pfnWaitForSynchronizationObjectFromCpuCb</a> function.


### -field pfnSignalSynchronizationObjectFromCpuCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectfromcpucb.md">pfnSignalSynchronizationObjectFromCpuCb</a> function.


### -field pfnWaitForSynchronizationObjectFromGpuCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_waitforsynchronizationobjectfromgpucb.md">pfnWaitForSynchronizationObjectFromGpuCb</a> function.


### -field pfnSignalSynchronizationObjectFromGpuCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectfromgpucb.md">pfnSignalSynchronizationObjectFromGpuCb</a> function.


### -field pfnCreatePagingQueueCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createpagingqueuecb.md">pfnCreatePagingQueueCb</a> function.


### -field pfnDestroyPagingQueueCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroypagingqueuecb.md">pfnDestroyPagingQueueCb</a> function.


### -field pfnLock2Cb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lock2cb.md">pfnLock2Cb</a> function.


### -field pfnUnlock2Cb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_unlock2cb.md">pfnUnlock2Cb</a> function.


### -field pfnInvalidateCacheCb

A pointer to the <a href="https://msdn.microsoft.com/56DF8936-4DD1-4352-9063-72F441FDF343">pfnInvalidateCacheCb</a> function.


### -field pfnReserveGpuVirtualAddressCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_reservegpuvirtualaddresscb.md">pfnReserveGpuVirtualAddressCb</a> function.


### -field pfnMapGpuVirtualAddressCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_mapgpuvirtualaddresscb.md">pfnMapGpuVirtualAddressCb</a> function.


### -field pfnFreeGpuVirtualAddressCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_freegpuvirtualaddresscb.md">pfnFreeGpuVirtualAddressCb</a> function.


### -field pfnUpdateGpuVirtualAddressCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_updategpuvirtualaddresscb.md">pfnUpdateGpuVirtualAddressCb</a> function.


### -field pfnCreateContextVirtualCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createcontextvirtualcb.md">pfnCreateContextVirtualCb</a> function.


### -field pfnSubmitCommandCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_submitcommandcb.md">pfnSubmitCommandCb</a> function.


### -field pfnDeallocate2Cb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_deallocate2cb.md">pfnDeallocate2Cb</a> function.


### -field pfnSignalSynchronizationObjectFromGpu2Cb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectfromgpu2cb.md">pfnSignalSynchronizationObjectFromGpu2Cb</a> function.


### -field pfnReclaimAllocations2Cb

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/dn903528">pfnReclaimAllocations2Cb</a> function.


### -field pfnGetResourcePresentPrivateDriverDataCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getresourcepresentprivatedriverdatacb.md">pfnGetResourcePresentPrivateDriverDataCb</a> function.


### -field pfnUpdateAllocationPropertyCb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_updateallocationpropertycb.md">pfnUpdateAllocationPropertyCb</a> function.


### -field pfnOfferAllocations2Cb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_offerallocations2cb.md">pfnOfferAllocations2Cb</a> function.


### -field pfnReclaimAllocations3Cb

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_reclaimallocations3cb.md">pfnReclaimAllocations3Cb</a> function.


## -remarks
The following code, from D3dumddi.h, shows the function declarations for the callback functions that the members of <b>D3DDDI_DEVICECALLBACKS</b> point to.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createdevice.md">CreateDevice</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_allocatecb.md">pfnAllocateCb</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/f3f5d6bc-3bc6-4214-830a-cffff01069cc">pfnCreateContextCb</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createoverlaycb.md">pfnCreateOverlayCb</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createsynchronizationobjectcb.md">pfnCreateSynchronizationObjectCb</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createsynchronizationobject2cb.md">pfnCreateSynchronizationObject2Cb</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_deallocatecb.md">pfnDeallocateCb</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroycontextcb.md">pfnDestroyContextCb</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroyoverlaycb.md">pfnDestroyOverlayCb</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroysynchronizationobjectcb.md">pfnDestroySynchronizationObjectCb</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_escapecb.md">pfnEscapeCb</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_flipoverlaycb.md">pfnFlipOverlayCb</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockcb.md">pfnLockCb</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_logumdmarkercb.md">pfnLogUMDMarkerCb</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_presentcb.md">pfnPresentCb</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_queryresidencycb.md">pfnQueryResidencyCb</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_rendercb.md">pfnRenderCb</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setasynccallbackscb.md">pfnSetAsyncCallbacksCb</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setdisplaymodecb.md">pfnSetDisplayModeCb</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setdisplayprivatedriverformatcb.md">pfnSetDisplayPrivateDriverFormatCb</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setprioritycb.md">pfnSetPriorityCb</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectcb.md">pfnSignalSynchronizationObjectCb</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobject2cb.md">pfnSignalSynchronizationObject2Cb</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_unlockcb.md">pfnUnlockCb</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_updateoverlaycb.md">pfnUpdateOverlayCb</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_waitforsynchronizationobjectcb.md">pfnWaitForSynchronizationObjectCb</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_waitforsynchronizationobject2cb.md">pfnWaitForSynchronizationObject2Cb</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh780323">pfnPresentMultiPlaneOverlayCb (D3D)</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_offerallocations2cb.md">pfnOfferAllocations2Cb</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_reclaimallocations3cb.md">pfnReclaimAllocations3Cb</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_DEVICECALLBACKS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

