---
UID: NS:d3dumddi._D3DDDI_DEVICECALLBACKS
title: "_D3DDDI_DEVICECALLBACKS"
author: windows-driver-content
description: The D3DDDI_DEVICECALLBACKS structure contains Microsoft Direct3D runtime callback functions that the user-mode display driver can use.
old-location: display\d3dddi_devicecallbacks.htm
old-project: display
ms.assetid: 29810132-5f53-4ba6-8302-6de315ecd04a
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3DDDI_DEVICECALLBACKS, D3DDDI_DEVICECALLBACKS structure [Display Devices], D3D_other_Structs_a835da78-4f70-4fc5-9f0f-43cef61bd304.xml, _D3DDDI_DEVICECALLBACKS, d3dumddi/D3DDDI_DEVICECALLBACKS, display.d3dddi_devicecallbacks
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
-	D3dumddi.h
api_name:
-	D3DDDI_DEVICECALLBACKS
product: Windows
targetos: Windows
req.typenames: D3DDDI_DEVICECALLBACKS
---

# _D3DDDI_DEVICECALLBACKS structure
The D3DDDI_DEVICECALLBACKS structure contains Microsoft Direct3D runtime callback functions that the user-mode display driver can use.

## Syntax
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

## Members


`pfnAcquireResourceCb`



`pfnAllocateCb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_allocatecb.md">pfnAllocateCb</a> function, which the user-mode display driver uses to request that the Direct3D runtime create a memory allocation for use by the driver.

`pfnCreateContextCb`

A pointer to the <a href="https://msdn.microsoft.com/f3f5d6bc-3bc6-4214-830a-cffff01069cc">pfnCreateContextCb</a> function, which the user-mode display driver uses to create a context to submit requests to.

`pfnCreateContextVirtualCb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createcontextvirtualcb.md">pfnCreateContextVirtualCb</a> function.

`pfnCreateHwContextCb`



`pfnCreateHwQueueCb`



`pfnCreateOverlayCb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createoverlaycb.md">pfnCreateOverlayCb</a> function, which the user-mode display driver uses to create and display a kernel-mode overlay object.

`pfnCreatePagingQueueCb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createpagingqueuecb.md">pfnCreatePagingQueueCb</a> function.

`pfnCreateSynchronizationObject2Cb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createsynchronizationobject2cb.md">pfnCreateSynchronizationObject2Cb</a> function, which a WDDM 1.2 and later user-mode display driver uses to create a GPU synchronization object.

Supported starting with Windows 8.

`pfnCreateSynchronizationObjectCb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createsynchronizationobjectcb.md">pfnCreateSynchronizationObjectCb</a> function, which the user-mode display driver uses to create a synchronization object.

`pfnDeallocate2Cb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_deallocate2cb.md">pfnDeallocate2Cb</a> function.

`pfnDeallocateCb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_deallocatecb.md">pfnDeallocateCb</a> function, which the user-mode display driver uses to request that the Direct3D runtime free memory that was previously allocated.

`pfnDestroyContextCb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroycontextcb.md">pfnDestroyContextCb</a> function, which the user-mode display driver uses to destroy a context that <a href="https://msdn.microsoft.com/f3f5d6bc-3bc6-4214-830a-cffff01069cc">pfnCreateContextCb</a> created.

`pfnDestroyHwContextCb`



`pfnDestroyHwQueueCb`



`pfnDestroyOverlayCb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroyoverlaycb.md">pfnDestroyOverlayCb</a> function, which the user-mode display driver uses to destroy a kernel-mode overlay object and stop the overlay from being displayed.

`pfnDestroyPagingQueueCb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroypagingqueuecb.md">pfnDestroyPagingQueueCb</a> function.

`pfnDestroySynchronizationObjectCb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroysynchronizationobjectcb.md">pfnDestroySynchronizationObjectCb</a> function, which the user-mode display driver uses to destroy a synchronization object that <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createsynchronizationobjectcb.md">pfnCreateSynchronizationObjectCb</a> created.

`pfnEscapeCb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_escapecb.md">pfnEscapeCb</a> function, which the user-mode display driver uses to share information with the display miniport driver.

`pfnEvictCb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_evictcb.md">pfnEvictCb</a> function.

`pfnFlipOverlayCb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_flipoverlaycb.md">pfnFlipOverlayCb</a> function, which the user-mode display driver uses to change the allocation that the overlay displays.

`pfnFreeGpuVirtualAddressCb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_freegpuvirtualaddresscb.md">pfnFreeGpuVirtualAddressCb</a> function.

`pfnGetResourcePresentPrivateDriverDataCb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getresourcepresentprivatedriverdatacb.md">pfnGetResourcePresentPrivateDriverDataCb</a> function.

`pfnInvalidateCacheCb`

A pointer to the <a href="https://msdn.microsoft.com/56DF8936-4DD1-4352-9063-72F441FDF343">pfnInvalidateCacheCb</a> function.

`pfnLock2Cb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lock2cb.md">pfnLock2Cb</a> function.

`pfnLockCb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockcb.md">pfnLockCb</a> function, which the user-mode display driver uses to request a lock from the display miniport driver. This lock cannot be handled completely by the user-mode display driver.

`pfnLogUMDMarkerCb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_logumdmarkercb.md">pfnLogUMDMarkerCb</a> function, which a WDDM 1.3 and later user-mode display driver calls to log a custom Event Tracing for Windows (ETW) marker event.

Supported starting with Windows 8.1.

`pfnMakeResidentCb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_makeresidentcb.md">pfnMakeResidentCb</a> function.

`pfnMapGpuVirtualAddressCb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_mapgpuvirtualaddresscb.md">pfnMapGpuVirtualAddressCb</a> function.

`pfnOfferAllocations2Cb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_offerallocations2cb.md">pfnOfferAllocations2Cb</a> function.

`pfnOfferAllocationsCb`

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451693">pfnOfferAllocationsCb</a> function, which a WDDM 1.2 and later user-mode display driver   calls to offer  video memory allocations for reuse.

Supported starting with Windows 8.

`pfnPresentCb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_presentcb.md">pfnPresentCb</a> function, which the user-mode display driver uses to submit a present command to the display miniport driver.

`pfnPresentMultiPlaneOverlayCb`

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh780323">pfnPresentMultiPlaneOverlayCb (D3D)</a> function, which a WDDM 1.3 and later user-mode display driver uses to copy content from a source multiplane overlay allocation to a destination allocation.

Supported starting with Windows 8.1.

`pfnQueryResidencyCb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_queryresidencycb.md">pfnQueryResidencyCb</a> function, which the user-mode display driver uses to query the residency status of a resource or list of allocations.

`pfnReclaimAllocations2Cb`

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/dn903528">pfnReclaimAllocations2Cb</a> function.

`pfnReclaimAllocations3Cb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_reclaimallocations3cb.md">pfnReclaimAllocations3Cb</a> function.

`pfnReclaimAllocationsCb`

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451695">pfnReclaimAllocationsCb</a> function, which a WDDM 1.2 and later user-mode display driver   calls to reclaim access to video memory allocations that were previously offered  for reuse.

Supported starting with Windows 8.

`pfnReleaseResourceCb`



`pfnRenderCb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_rendercb.md">pfnRenderCb</a> function, which the user-mode display driver uses to submit a command buffer to the display miniport driver.

`pfnReserveGpuVirtualAddressCb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_reservegpuvirtualaddresscb.md">pfnReserveGpuVirtualAddressCb</a> function.

`pfnSetAsyncCallbacksCb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setasynccallbackscb.md">pfnSetAsyncCallbacksCb</a> function that the user-mode display driver uses to notify the Direct3D runtime whether the runtime will start or stop receiving calls to the runtime's callback functions from a worker thread.

Only DirectX 9 and Direct 9L versions of the runtime support the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setasynccallbackscb.md">pfnSetAsyncCallbacksCb</a> function. DirectX 10 and later versions of the runtime set the <b>pfnSetAsyncCallbacksCb</b> member to <b>NULL</b> when the runtime calls the user-mode display driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a> function to create a rendering device.

`pfnSetDisplayModeCb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setdisplaymodecb.md">pfnSetDisplayModeCb</a> function, which the user-mode display driver uses to set an allocation for displaying.

`pfnSetDisplayPrivateDriverFormatCb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setdisplayprivatedriverformatcb.md">pfnSetDisplayPrivateDriverFormatCb</a> function that the user-mode display driver uses to change the format of the shared primary surface.

`pfnSetPriorityCb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setprioritycb.md">pfnSetPriorityCb</a> function, which the user-mode display driver uses to set the priority of a resource or list of allocations.

`pfnSignalSynchronizationObject2Cb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobject2cb.md">pfnSignalSynchronizationObject2Cb</a> function, which a WDDM 1.2 and later user-mode display driver uses to signal that GPU synchronization events are no longer owned by a context.

Supported starting with Windows 8.

`pfnSignalSynchronizationObjectCb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectcb.md">pfnSignalSynchronizationObjectCb</a> function, which the user-mode display driver uses to signal that synchronization events are no longer owned by a context.

`pfnSignalSynchronizationObjectFromCpuCb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectfromcpucb.md">pfnSignalSynchronizationObjectFromCpuCb</a> function.

`pfnSignalSynchronizationObjectFromGpu2Cb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectfromgpu2cb.md">pfnSignalSynchronizationObjectFromGpu2Cb</a> function.

`pfnSignalSynchronizationObjectFromGpuCb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectfromgpucb.md">pfnSignalSynchronizationObjectFromGpuCb</a> function.

`pfnSubmitCommandCb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_submitcommandcb.md">pfnSubmitCommandCb</a> function.

`pfnSubmitCommandToHwQueueCb`



`pfnSubmitSignalSyncObjectsToHwQueueCb`



`pfnSubmitWaitForSyncObjectsToHwQueueCb`



`pfnUnlock2Cb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_unlock2cb.md">pfnUnlock2Cb</a> function.

`pfnUnlockCb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_unlockcb.md">pfnUnlockCb</a> function, which the user-mode display driver uses to call the display miniport driver for an unlock. This unlock cannot be handled completely by the user-mode display driver.

`pfnUpdateAllocationPropertyCb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_updateallocationpropertycb.md">pfnUpdateAllocationPropertyCb</a> function.

`pfnUpdateGpuVirtualAddressCb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_updategpuvirtualaddresscb.md">pfnUpdateGpuVirtualAddressCb</a> function.

`pfnUpdateOverlayCb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_updateoverlaycb.md">pfnUpdateOverlayCb</a> function, which the user-mode display driver uses to modify a kernel-mode overlay object.

`pfnWaitForSynchronizationObject2Cb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_waitforsynchronizationobject2cb.md">pfnWaitForSynchronizationObject2Cb</a> function, which a WDDM 1.2 and later user-mode display driver uses to wait for GPU synchronization events to occur and then uses to return.

Supported starting with Windows 8.

`pfnWaitForSynchronizationObjectCb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_waitforsynchronizationobjectcb.md">pfnWaitForSynchronizationObjectCb</a> function, which the user-mode display driver uses to wait for synchronization events to occur and then uses to return.

`pfnWaitForSynchronizationObjectFromCpuCb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_waitforsynchronizationobjectfromcpucb.md">pfnWaitForSynchronizationObjectFromCpuCb</a> function.

`pfnWaitForSynchronizationObjectFromGpuCb`

A pointer to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_waitforsynchronizationobjectfromgpucb.md">pfnWaitForSynchronizationObjectFromGpuCb</a> function.

## Remarks
The following code, from D3dumddi.h, shows the function declarations for the callback functions that the members of <b>D3DDDI_DEVICECALLBACKS</b> point to.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_ALLOCATECB)(
        _In_ HANDLE hDevice, _Inout_ D3DDDICB_ALLOCATE*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_DEALLOCATECB)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDICB_DEALLOCATE*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_SETPRIORITYCB)(
        _In_ HANDLE hDevice, _In_ D3DDDICB_SETPRIORITY*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_QUERYRESIDENCYCB)(
        _In_ HANDLE hDevice, _Inout_ CONST D3DDDICB_QUERYRESIDENCY*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_SETDISPLAYMODECB)(
        _In_ HANDLE hDevice, _Inout_ D3DDDICB_SETDISPLAYMODE*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_SETDISPLAYPRIVATEDRIVERFORMATCB)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDICB_SETDISPLAYPRIVATEDRIVERFORMAT*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_PRESENTCB)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDICB_PRESENT*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_RENDERCB)(
        _In_ HANDLE hDevice, _Inout_ D3DDDICB_RENDER*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_LOCKCB)(
        _In_ HANDLE hDevice, _Inout_ D3DDDICB_LOCK*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_UNLOCKCB)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDICB_UNLOCK*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_ESCAPECB)(
        _In_ HANDLE hAdapter, _Inout_ CONST D3DDDICB_ESCAPE*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_CREATEOVERLAYCB)(
        _In_ HANDLE hDevice, _Inout_ D3DDDICB_CREATEOVERLAY*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_UPDATEOVERLAYCB)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDICB_UPDATEOVERLAY*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_FLIPOVERLAYCB)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDICB_FLIPOVERLAY*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_DESTROYOVERLAYCB)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDICB_DESTROYOVERLAY*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_CREATECONTEXTCB)(
        _In_ HANDLE hDevice, _Inout_ D3DDDICB_CREATECONTEXT*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_DESTROYCONTEXTCB)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDICB_DESTROYCONTEXT*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_CREATESYNCHRONIZATIONOBJECTCB)(
        _In_ HANDLE hDevice, _Inout_ D3DDDICB_CREATESYNCHRONIZATIONOBJECT*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_DESTROYSYNCHRONIZATIONOBJECTCB)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECTCB)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTCB)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_SETASYNCCALLBACKSCB)(
        _In_ HANDLE hDevice, _In_ BOOL Enable);
#if (D3D_UMD_INTERFACE_VERSION &gt;= D3D_UMD_INTERFACE_VERSION_WIN8)
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_CREATESYNCHRONIZATIONOBJECT2CB)(
        _In_ HANDLE hDevice, _Inout_ D3DDDICB_CREATESYNCHRONIZATIONOBJECT2*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_WAITFORSYNCHRONIZATIONOBJECT2CB)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT2*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECT2CB)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT2*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_OFFERALLOCATIONSCB)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDICB_OFFERALLOCATIONS*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_RECLAIMALLOCATIONSCB)(
        _In_ HANDLE hDevice, _Inout_ CONST D3DDDICB_RECLAIMALLOCATIONS*);
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_PRESENTMULTIPLANEOVERLAYCB)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDICB_PRESENTMULTIPLANEOVERLAY*);
#endif
#if (D3D_UMD_INTERFACE_VERSION &gt;= D3D_UMD_INTERFACE_VERSION_WDDM1_3)
typedef _Check_return_ HRESULT (APIENTRY CALLBACK *PFND3DDDI_LOGUMDMARKERCB)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDICB_LOGUMDMARKER*);
#endif
</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createoverlaycb.md">pfnCreateOverlayCb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createsynchronizationobject2cb.md">pfnCreateSynchronizationObject2Cb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_unlockcb.md">pfnUnlockCb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setdisplayprivatedriverformatcb.md">pfnSetDisplayPrivateDriverFormatCb</a>



<a href="https://msdn.microsoft.com/f3f5d6bc-3bc6-4214-830a-cffff01069cc">pfnCreateContextCb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroysynchronizationobjectcb.md">pfnDestroySynchronizationObjectCb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setasynccallbackscb.md">pfnSetAsyncCallbacksCb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createdevice.md">CreateDevice</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_presentcb.md">pfnPresentCb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_deallocatecb.md">pfnDeallocateCb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_escapecb.md">pfnEscapeCb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createsynchronizationobjectcb.md">pfnCreateSynchronizationObjectCb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_offerallocations2cb.md">pfnOfferAllocations2Cb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockcb.md">pfnLockCb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobject2cb.md">pfnSignalSynchronizationObject2Cb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh780323">pfnPresentMultiPlaneOverlayCb (D3D)</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectcb.md">pfnSignalSynchronizationObjectCb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_waitforsynchronizationobjectcb.md">pfnWaitForSynchronizationObjectCb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroycontextcb.md">pfnDestroyContextCb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_rendercb.md">pfnRenderCb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_reclaimallocations3cb.md">pfnReclaimAllocations3Cb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_queryresidencycb.md">pfnQueryResidencyCb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_flipoverlaycb.md">pfnFlipOverlayCb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setprioritycb.md">pfnSetPriorityCb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_logumdmarkercb.md">pfnLogUMDMarkerCb</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setdisplaymodecb.md">pfnSetDisplayModeCb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_waitforsynchronizationobject2cb.md">pfnWaitForSynchronizationObject2Cb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_updateoverlaycb.md">pfnUpdateOverlayCb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_allocatecb.md">pfnAllocateCb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroyoverlaycb.md">pfnDestroyOverlayCb</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_DEVICECALLBACKS structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>