---
UID : NS:dispmprt._DRIVER_INITIALIZATION_DATA
title : "_DRIVER_INITIALIZATION_DATA"
author : windows-driver-content
description : The DRIVER_INITIALIZATION_DATA structure contains pointers to functions implemented by the display miniport driver.
old-location : display\driver_initialization_data.htm
old-project : display
ms.assetid : 3ab00f9c-7ce9-41bf-85c5-96be31d19719
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : DRIVER_INITIALIZATION_DATA structure [Display Devices], _DRIVER_INITIALIZATION_DATA, dispmprt/DRIVER_INITIALIZATION_DATA, display.driver_initialization_data, dispmprt/PDRIVER_INITIALIZATION_DATA, DmStructs_7b91bf58-dfda-4c7c-ae26-21e577bdc152.xml, PDRIVER_INITIALIZATION_DATA, *PDRIVER_INITIALIZATION_DATA, DRIVER_INITIALIZATION_DATA, PDRIVER_INITIALIZATION_DATA structure pointer [Display Devices]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : dispmprt.h
req.include-header : Dispmprt.h
req.target-type : Windows
req.target-min-winverclnt : Available starting with Windows Vista.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PDRIVER_INITIALIZATION_DATA, DRIVER_INITIALIZATION_DATA"
---

# _DRIVER_INITIALIZATION_DATA structure
The <b>DRIVER_INITIALIZATION_DATA</b> structure contains pointers to functions implemented by the display miniport driver. The display miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> function provides the Microsoft DirectX graphics kernel subsystem with entry points by filling in the members of this structure.

## Syntax
````
typedef struct _DRIVER_INITIALIZATION_DATA {
  ULONG                                                   Version;
  PDXGKDDI_ADD_DEVICE                                     DxgkDdiAddDevice;
  PDXGKDDI_START_DEVICE                                   DxgkDdiStartDevice;
  PDXGKDDI_STOP_DEVICE                                    DxgkDdiStopDevice;
  PDXGKDDI_REMOVE_DEVICE                                  DxgkDdiRemoveDevice;
  PDXGKDDI_DISPATCH_IO_REQUEST                            DxgkDdiDispatchIoRequest;
  PDXGKDDI_INTERRUPT_ROUTINE                              DxgkDdiInterruptRoutine;
  PDXGKDDI_DPC_ROUTINE                                    DxgkDdiDpcRoutine;
  PDXGKDDI_QUERY_CHILD_RELATIONS                          DxgkDdiQueryChildRelations;
  PDXGKDDI_QUERY_CHILD_STATUS                             DxgkDdiQueryChildStatus;
  PDXGKDDI_QUERY_DEVICE_DESCRIPTOR                        DxgkDdiQueryDeviceDescriptor;
  PDXGKDDI_SET_POWER_STATE                                DxgkDdiSetPowerState;
  PDXGKDDI_NOTIFY_ACPI_EVENT                              DxgkDdiNotifyAcpiEvent;
  PDXGKDDI_RESET_DEVICE                                   DxgkDdiResetDevice;
  PDXGKDDI_UNLOAD                                         DxgkDdiUnload;
  PDXGKDDI_QUERY_INTERFACE                                DxgkDdiQueryInterface;
  PDXGKDDI_CONTROL_ETW_LOGGING                            DxgkDdiControlEtwLogging;
  PDXGKDDI_QUERYADAPTERINFO                               DxgkDdiQueryAdapterInfo;
  PDXGKDDI_CREATEDEVICE                                   DxgkDdiCreateDevice;
  PDXGKDDI_CREATEALLOCATION                               DxgkDdiCreateAllocation;
  PDXGKDDI_DESTROYALLOCATION                              DxgkDdiDestroyAllocation;
  PDXGKDDI_DESCRIBEALLOCATION                             DxgkDdiDescribeAllocation;
  PDXGKDDI_GETSTANDARDALLOCATIONDRIVERDATA                DxgkDdiGetStandardAllocationDriverData;
  PDXGKDDI_ACQUIRESWIZZLINGRANGE                          DxgkDdiAcquireSwizzlingRange;
  PDXGKDDI_RELEASESWIZZLINGRANGE                          DxgkDdiReleaseSwizzlingRange;
  PDXGKDDI_PATCH                                          DxgkDdiPatch;
  PDXGKDDI_SUBMITCOMMAND                                  DxgkDdiSubmitCommand;
  PDXGKDDI_PREEMPTCOMMAND                                 DxgkDdiPreemptCommand;
  PDXGKDDI_BUILDPAGINGBUFFER                              DxgkDdiBuildPagingBuffer;
  PDXGKDDI_SETPALETTE                                     DxgkDdiSetPalette;
  PDXGKDDI_SETPOINTERPOSITION                             DxgkDdiSetPointerPosition;
  PDXGKDDI_SETPOINTERSHAPE                                DxgkDdiSetPointerShape;
  PDXGKDDI_RESETFROMTIMEOUT                               DxgkDdiResetFromTimeout;
  PDXGKDDI_RESTARTFROMTIMEOUT                             DxgkDdiRestartFromTimeout;
  PDXGKDDI_ESCAPE                                         DxgkDdiEscape;
  PDXGKDDI_COLLECTDBGINFO                                 DxgkDdiCollectDbgInfo;
  PDXGKDDI_QUERYCURRENTFENCE                              DxgkDdiQueryCurrentFence;
  PDXGKDDI_ISSUPPORTEDVIDPN                               DxgkDdiIsSupportedVidPn;
  PDXGKDDI_RECOMMENDFUNCTIONALVIDPN                       DxgkDdiRecommendFunctionalVidPn;
  PDXGKDDI_ENUMVIDPNCOFUNCMODALITY                        DxgkDdiEnumVidPnCofuncModality;
  PDXGKDDI_SETVIDPNSOURCEADDRESS                          DxgkDdiSetVidPnSourceAddress;
  PDXGKDDI_SETVIDPNSOURCEVISIBILITY                       DxgkDdiSetVidPnSourceVisibility;
  PDXGKDDI_COMMITVIDPN                                    DxgkDdiCommitVidPn;
  PDXGKDDI_UPDATEACTIVEVIDPNPRESENTPATH                   DxgkDdiUpdateActiveVidPnPresentPath;
  PDXGKDDI_RECOMMENDMONITORMODES                          DxgkDdiRecommendMonitorModes;
  PDXGKDDI_RECOMMENDVIDPNTOPOLOGY                         DxgkDdiRecommendVidPnTopology;
  PDXGKDDI_GETSCANLINE                                    DxgkDdiGetScanLine;
  PDXGKDDI_STOPCAPTURE                                    DxgkDdiStopCapture;
  PDXGKDDI_CONTROLINTERRUPT                               DxgkDdiControlInterrupt;
  PDXGKDDI_CREATEOVERLAY                                  DxgkDdiCreateOverlay;
  PDXGKDDI_DESTROYDEVICE                                  DxgkDdiDestroyDevice;
  PDXGKDDI_OPENALLOCATIONINFO                             DxgkDdiOpenAllocation;
  PDXGKDDI_CLOSEALLOCATION                                DxgkDdiCloseAllocation;
  PDXGKDDI_RENDER                                         DxgkDdiRender;
  PDXGKDDI_PRESENT                                        DxgkDdiPresent;
  PDXGKDDI_UPDATEOVERLAY                                  DxgkDdiUpdateOverlay;
  PDXGKDDI_FLIPOVERLAY                                    DxgkDdiFlipOverlay;
  PDXGKDDI_DESTROYOVERLAY                                 DxgkDdiDestroyOverlay;
  PDXGKDDI_CREATECONTEXT                                  DxgkDdiCreateContext;
  PDXGKDDI_DESTROYCONTEXT                                 DxgkDdiDestroyContext;
  PDXGKDDI_LINK_DEVICE                                    DxgkDdiLinkDevice;
  PDXGKDDI_SETDISPLAYPRIVATEDRIVERFORMAT                  DxgkDdiSetDisplayPrivateDriverFormat;
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WIN7)
  PDXGKDDI_DESCRIBEPAGETABLE                              DxgkDdiDescribePageTable;
  PDXGKDDI_UPDATEPAGETABLE                                DxgkDdiUpdatePageTable;
  PDXGKDDI_UPDATEPAGEDIRECTORY                            DxgkDdiUpdatePageDirectory;
  PDXGKDDI_MOVEPAGEDIRECTORY                              DxgkDdiMovePageDirectory;
  PDXGKDDI_SUBMITRENDER                                   DxgkDdiSubmitRender;
  PDXGKDDI_CREATEALLOCATION2                              DxgkDdiCreateAllocation2;
  PDXGKDDI_RENDER                                         DxgkDdiRenderKm;
  VOID                                                    *Reserved;
  PDXGKDDI_QUERYVIDPNHWCAPABILITY                         DxgkDdiQueryVidPnHWCapability;
#endif 
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WIN8)
  PDXGKDDISETPOWERCOMPONENTFSTATE                         DxgkDdiSetPowerComponentFState;
  PDXGKDDI_QUERYDEPENDENTENGINEGROUP                      DxgkDdiQueryDependentEngineGroup;
  PDXGKDDI_QUERYENGINESTATUS                              DxgkDdiQueryEngineStatus;
  PDXGKDDI_RESETENGINE                                    DxgkDdiResetEngine;
  PDXGKDDI_STOP_DEVICE_AND_RELEASE_POST_DISPLAY_OWNERSHIP DxgkDdiStopDeviceAndReleasePostDisplayOwnership;
  PDXGKDDI_SYSTEM_DISPLAY_ENABLE                          DxgkDdiSystemDisplayEnable;
  PDXGKDDI_SYSTEM_DISPLAY_WRITE                           DxgkDdiSystemDisplayWrite;
  PDXGKDDI_CANCELCOMMAND                                  DxgkDdiCancelCommand;
  PDXGKDDI_GET_CHILD_CONTAINER_ID                         DxgkDdiGetChildContainerId;
  PDXGKDDIPOWERRUNTIMECONTROLREQUEST                      DxgkDdiPowerRuntimeControlRequest;
  PDXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY     DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay;
  PDXGKDDI_NOTIFY_SURPRISE_REMOVAL                        DxgkDdiNotifySurpriseRemoval;
#endif 
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM1_3)
  PDXGKDDI_GETNODEMETADATA                                DxgkDdiGetNodeMetadata;
  PDXGKDDISETPOWERPSTATE                                  DxgkDdiSetPowerPState;
  PDXGKDDI_CONTROLINTERRUPT2                              DxgkDdiControlInterrupt2;
  PDXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT                  DxgkDdiCheckMultiPlaneOverlaySupport;
  PDXGKDDI_CALIBRATEGPUCLOCK                              DxgkDdiCalibrateGpuClock;
  PDXGKDDI_FORMATHISTORYBUFFER                            DxgkDdiFormatHistoryBuffer;
#endif 
} DRIVER_INITIALIZATION_DATA, *PDRIVER_INITIALIZATION_DATA;
````

## Members


`DxgkDdiAcquireSwizzlingRange`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_acquireswizzlingrange.md">DxgkDdiAcquireSwizzlingRange</a> function.

`DxgkDdiAddDevice`

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.

`DxgkDdiBuildPagingBuffer`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_buildpagingbuffer.md">DxgkDdiBuildPagingBuffer</a> function.

`DxgkDdiCalibrateGpuClock`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_calibrategpuclock.md">DxgkDdiCalibrateGpuClock</a> function.

Supported starting with Windows 8.1.

`DxgkDdiCancelCommand`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_cancelcommand.md">DxgkDdiCancelCommand</a> function.

Supported starting with Windows 8.

`DxgkDdiCheckMultiPlaneOverlaySupport`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_checkmultiplaneoverlaysupport.md">DxgkDdiCheckMultiPlaneOverlaySupport</a> function.

Supported starting with Windows 8.1.

`DxgkDdiCheckMultiPlaneOverlaySupport2`



`DxgkDdiCheckMultiPlaneOverlaySupport3`



`DxgkDdiCloseAllocation`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_closeallocation.md">DxgkDdiCloseAllocation</a> function.

`DxgkDdiCollectDbgInfo`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_collectdbginfo.md">DxgkDdiCollectDbgInfo</a> function.

`DxgkDdiCommitVidPn`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_commitvidpn.md">DxgkDdiCommitVidPn</a>  function.

`DxgkDdiControlEtwLogging`

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_control_etw_logging.md">DxgkDdiControlEtwLogging</a> function.

`DxgkDdiControlInterrupt`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_controlinterrupt.md">DxgkDdiControlInterrupt</a> function.

`DxgkDdiControlInterrupt2`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_controlinterrupt2.md">DxgkDdiControlInterrupt2</a> function.

Supported starting with Windows 10

`DxgkDdiControlModeBehavior`



`DxgkDdiCreateAllocation`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a> function.

`DxgkDdiCreateAllocation2`

This member is reserved and should be set to zero.
     

Available only when DXGKDDI_INTERFACE_VERSION ≥ DXGKDDI_INTERFACE_VERSION_WIN7.
<div class="alert"><b>Note</b>  The following 3 functions are available beginning with Windows 7:</div><div> </div>

`DxgkDdiCreateContext`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createcontext.md">DxgkDdiCreateContext</a> function.

`DxgkDdiCreateDevice`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createdevice.md">DxgkDdiCreateDevice</a> function.

`DxgkDdiCreateHwContext`



`DxgkDdiCreateHwQueue`



`DxgkDdiCreateOverlay`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createoverlay.md">DxgkDdiCreateOverlay</a> function.
<div class="alert"><b>Note</b>  The following 5 functions are specific to the graphics context device that was created through <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createdevice.md">DxgkDdiCreateDevice</a>:</div><div> </div>

`DxgkDdiCreatePeriodicFrameNotification`



`DxgkDdiCreateProcess`



`DxgkDdiCreateProtectedSession`



`DxgkDdiDescribeAllocation`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_describeallocation.md">DxgkDdiDescribeAllocation</a> function.

`DxgkDdiDescribePageTable`

This member is reserved and should be set to zero.
     

Available only when DXGKDDI_INTERFACE_VERSION ≥ DXGKDDI_INTERFACE_VERSION_WIN7.

`DxgkDdiDestroyAllocation`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_destroyallocation.md">DxgkDdiDestroyAllocation</a> function.

`DxgkDdiDestroyContext`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_destroycontext.md">DxgkDdiDestroyContext</a> function.

`DxgkDdiDestroyDevice`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_destroydevice.md">DxgkDdiDestroyDevice</a> function.

`DxgkDdiDestroyHwContext`



`DxgkDdiDestroyHwQueue`



`DxgkDdiDestroyOverlay`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_destroyoverlay.md">DxgkDdiDestroyOverlay</a> function.
<div class="alert"><b>Note</b>  The following 2 functions are specific to supporting contexts:</div><div> </div>

`DxgkDdiDestroyPeriodicFrameNotification`



`DxgkDdiDestroyProcess`



`DxgkDdiDestroyProtectedSession`



`DxgkDdiDispatchIoRequest`

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_dispatch_io_request.md">DxgkDdiDispatchIoRequest</a> function.

`DxgkDdiDisplayDetectControl`



`DxgkDdiDpcRoutine`

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_dpc_routine.md">DxgkDdiDpcRoutine</a> function.

`DxgkDdiEnumVidPnCofuncModality`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality.md">DxgkDdiEnumVidPnCofuncModality</a> function.

`DxgkDdiEscape`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_escape.md">DxgkDdiEscape</a> function.

`DxgkDdiExchangePreStartInfo`



`DxgkDdiFlipOverlay`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_flipoverlay.md">DxgkDdiFlipOverlay</a> function.

`DxgkDdiFormatHistoryBuffer`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_formathistorybuffer.md">DxgkDdiFormatHistoryBuffer</a> function.

Supported starting with Windows 8.1.

`DxgkDdiGetChildContainerId`

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_get_child_container_id.md">DxgkDdiGetChildContainerId</a> function.

Supported starting with Windows 8.

`DxgkDdiGetMultiPlaneOverlayCaps`



`DxgkDdiGetNodeMetadata`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_getnodemetadata.md">DxgkDdiGetNodeMetadata</a> function.

Supported starting with Windows 8.1.

`DxgkDdiGetPostCompositionCaps`



`DxgkDdiGetRootPageTableSize`



`DxgkDdiGetScanLine`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_getscanline.md">DxgkDdiGetScanLine</a> function.

`DxgkDdiGetStandardAllocationDriverData`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_getstandardallocationdriverdata.md">DxgkDdiGetStandardAllocationDriverData</a> function.

`DxgkDdiInterruptRoutine`

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_interrupt_routine.md">DxgkDdiInterruptRoutine</a> function.

`DxgkDdiIsSupportedVidPn`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_issupportedvidpn.md">DxgkDdiIsSupportedVidPn</a> function.

`DxgkDdiLinkDevice`

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_link_device.md">DxgkDdiLinkDevice</a> function. Be aware that this function is specific to supporting linked graphics adapters.

`DxgkDdiMapCpuHostAperture`



`DxgkDdiMovePageDirectory`

This member is reserved and should be set to zero.
     

Available only when DXGKDDI_INTERFACE_VERSION ≥ DXGKDDI_INTERFACE_VERSION_WIN7.

`DxgkDdiNotifyAcpiEvent`

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_notify_acpi_event.md">DxgkDdiNotifyAcpiEvent</a> function.

`DxgkDdiNotifySurpriseRemoval`

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_notify_surprise_removal.md">DxgkDdiNotifySurpriseRemoval</a> function.

Supported starting with Windows 8.

`DxgkDdiOpenAllocation`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_openallocationinfo.md">DxgkDdiOpenAllocation</a> function.

`DxgkDdiPatch`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_patch.md">DxgkDdiPatch</a> function.

`DxgkDdiPostMultiPlaneOverlayPresent`



`DxgkDdiPowerRuntimeControlRequest`

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/56535128-3107-4fb5-b0e1-2e913c386cc2">DxgkDdiPowerRuntimeControlRequest</a> function.

Supported starting with Windows 8.

`DxgkDdiPowerRuntimeSetDeviceHandle`



`DxgkDdiPreemptCommand`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_preemptcommand.md">DxgkDdiPreemptCommand</a> function.

`DxgkDdiPresent`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_present.md">DxgkDdiPresent</a> function.
<div class="alert"><b>Note</b>  The following 3 functions are specific to the overlay that was created through <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createoverlay.md">DxgkDdiCreateOverlay</a>:</div><div> </div>

`DxgkDdiQueryAdapterInfo`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a> function.

`DxgkDdiQueryChildRelations`

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_relations.md">DxgkDdiQueryChildRelations</a> function.

`DxgkDdiQueryChildStatus`

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_status.md">DxgkDdiQueryChildStatus</a> function.

`DxgkDdiQueryConnectionChange`



`DxgkDdiQueryCurrentFence`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_querycurrentfence.md">DxgkDdiQueryCurrentFence</a> function.

`DxgkDdiQueryDependentEngineGroup`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_querydependentenginegroup.md">DxgkDdiQueryDependentEngineGroup</a> function.

Supported starting with Windows 8.

`DxgkDdiQueryDeviceDescriptor`

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_query_device_descriptor.md">DxgkDdiQueryDeviceDescriptor</a> function.

`DxgkDdiQueryEngineStatus`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryenginestatus.md">DxgkDdiQueryEngineStatus</a> function.

Supported starting with Windows 8.

`DxgkDdiQueryInterface`

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_query_interface.md">DxgkDdiQueryInterface</a> function.

`DxgkDdiQueryVidPnHWCapability`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryvidpnhwcapability.md">DxgkDdiQueryVidPnHWCapability</a> function.
     

Available only when DXGKDDI_INTERFACE_VERSION ≥ DXGKDDI_INTERFACE_VERSION_WIN7.
<div class="alert"><b>Note</b>  The following 12 functions, including one reserved function, are available beginning with Windows 8:</div><div> </div>

`DxgkDdiRecommendFunctionalVidPn`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_recommendfunctionalvidpn.md">DxgkDdiRecommendFunctionalVidPn</a> function.

`DxgkDdiRecommendMonitorModes`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_recommendmonitormodes.md">DxgkDdiRecommendMonitorModes</a> function.

`DxgkDdiRecommendVidPnTopology`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_recommendvidpntopology.md">DxgkDdiRecommendVidPnTopology</a> function.

`DxgkDdiReleaseSwizzlingRange`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_releaseswizzlingrange.md">DxgkDdiReleaseSwizzlingRange</a> function.

`DxgkDdiRemoveDevice`

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_remove_device.md">DxgkDdiRemoveDevice</a> function.

`DxgkDdiRender`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_render.md">DxgkDdiRender</a> function.

`DxgkDdiRenderGdi`



`DxgkDdiRenderKm`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_renderkm.md">DxgkDdiRenderKm</a> function.
     

Available only when DXGKDDI_INTERFACE_VERSION ≥ DXGKDDI_INTERFACE_VERSION_WIN7.

`DxgkDdiResetDevice`

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_reset_device.md">DxgkDdiResetDevice</a> function.

`DxgkDdiResetEngine`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_resetengine.md">DxgkDdiResetEngine</a> function.

Supported starting with Windows 8.

`DxgkDdiResetFromTimeout`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_resetfromtimeout.md">DxgkDdiResetFromTimeout</a> function.

`DxgkDdiResetHwEngine`



`DxgkDdiRestartFromTimeout`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_restartfromtimeout.md">DxgkDdiRestartFromTimeout</a> function.

`DxgkDdiSetDisplayPrivateDriverFormat`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_setdisplayprivatedriverformat.md">DxgkDdiSetDisplayPrivateDriverFormat</a> function.
<div class="alert"><b>Note</b>  The following 6 <a href="https://msdn.microsoft.com/F92F15A7-439D-4D45-84EE-A92D1E6AD779">reserved functions</a> declared in Dispmrt.h are available beginning with Windows 7:</div><div> </div>

`DxgkDdiSetPalette`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_setpalette.md">DxgkDdiSetPalette</a> function that sets the palette for the display.

`DxgkDdiSetPointerPosition`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_setpointerposition.md">DxgkDdiSetPointerPosition</a> function.

`DxgkDdiSetPointerShape`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_setpointershape.md">DxgkDdiSetPointerShape</a> function.

`DxgkDdiSetPowerComponentFState`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddisetpowercomponentfstate.md">DxgkDdiSetPowerComponentFState</a> function.

Supported starting with Windows 8.

`DxgkDdiSetPowerPState`

This member is reserved and should be set to zero.

Supported starting with Windows 8.1.

`DxgkDdiSetPowerState`

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_set_power_state.md">DxgkDdiSetPowerState</a> function.

`DxgkDdiSetRootPageTable`



`DxgkDdiSetStablePowerState`



`DxgkDdiSetTargetAdjustedColorimetry`



`DxgkDdiSetTargetAnalogCopyProtection`



`DxgkDdiSetTargetContentType`



`DxgkDdiSetTargetGamma`



`DxgkDdiSetTimingsFromVidPn`



`DxgkDdiSetVideoProtectedRegion`



`DxgkDdiSetVidPnSourceAddress`

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/488c929b-3816-457f-b5c2-c176b93d5546">DxgkDdiSetVidPnSourceAddress</a> function.

`DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_setvidpnsourceaddresswithmultiplaneoverlay.md">DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay</a> function.

Supported starting with Windows 8.1.

`DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay2`



`DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay3`



`DxgkDdiSetVidPnSourceVisibility`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_setvidpnsourcevisibility.md">DxgkDdiSetVidPnSourceVisibility</a> function.

`DxgkDdiStartDevice`

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a> function.

`DxgkDdiStopCapture`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_stopcapture.md">DxgkDdiStopCapture</a> function.

`DxgkDdiStopDevice`

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_stop_device.md">DxgkDdiStopDevice</a> function.

`DxgkDdiStopDeviceAndReleasePostDisplayOwnership`

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_stop_device_and_release_post_display_ownership.md">DxgkDdiStopDeviceAndReleasePostDisplayOwnership</a> function.

Supported starting with Windows 8.

`DxgkDdiSubmitCommand`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_submitcommand.md">DxgkDdiSubmitCommand</a> function.

`DxgkDdiSubmitCommandToHwQueue`



`DxgkDdiSubmitCommandVirtual`



`DxgkDdiSubmitRender`

This member is reserved and should be set to zero.
     

Available only when DXGKDDI_INTERFACE_VERSION ≥ DXGKDDI_INTERFACE_VERSION_WIN7.

`DxgkDdiSwitchToHwContextList`



`DxgkDdiSystemDisplayEnable`

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_system_display_enable.md">DxgkDdiSystemDisplayEnable</a> function.

Supported starting with Windows 8.

`DxgkDdiSystemDisplayWrite`

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_system_display_write.md">DxgkDdiSystemDisplayWrite</a> function.

Supported starting with Windows 8.

`DxgkDdiUnload`

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_unload.md">DxgkDdiUnload</a> function.

`DxgkDdiUnmapCpuHostAperture`



`DxgkDdiUpdateActiveVidPnPresentPath`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_updateactivevidpnpresentpath.md">DxgkDdiUpdateActiveVidPnPresentPath</a> function.

`DxgkDdiUpdateHwContextState`



`DxgkDdiUpdateMonitorLinkInfo`



`DxgkDdiUpdateOverlay`

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_updateoverlay.md">DxgkDdiUpdateOverlay</a> function.

`DxgkDdiUpdatePageDirectory`

This member is reserved and should be set to zero.
     

Available only when DXGKDDI_INTERFACE_VERSION ≥ DXGKDDI_INTERFACE_VERSION_WIN7.

`DxgkDdiUpdatePageTable`

This member is reserved and should be set to zero.
     

Available only when DXGKDDI_INTERFACE_VERSION ≥ DXGKDDI_INTERFACE_VERSION_WIN7.

`DxgkDdiValidateUpdateAllocationProperty`



`Reserved`

This member is reserved and should be set to zero.
     

Available only when DXGKDDI_INTERFACE_VERSION ≥ DXGKDDI_INTERFACE_VERSION_WIN7.

`Reserved1`



`Reserved2`



`Version`

A positive integer that indicates the version of the functional interface implemented by the display miniport driver. The display miniport driver must set this member to <b>DXGKDDI_INTERFACE_VERSION</b>, which is defined in Dispmprt.h.

## Remarks
The following <b>typedef</b> declarations provide function data types from data types that are dereferenced pointers to functions:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef DXGKDDI_ADD_DEVICE  *PDXGKDDI_ADD_DEVICE;
typedef DXGKDDI_START_DEVICE  *PDXGKDDI_START_DEVICE;
typedef DXGKDDI_STOP_DEVICE  *PDXGKDDI_STOP_DEVICE;
typedef DXGKDDI_REMOVE_DEVICE  *PDXGKDDI_REMOVE_DEVICE;
typedef DXGKDDI_DISPATCH_IO_REQUEST  *PDXGKDDI_DISPATCH_IO_REQUEST;
typedef DXGKDDI_QUERY_CHILD_RELATIONS  *PDXGKDDI_QUERY_CHILD_RELATIONS;
typedef DXGKDDI_QUERY_CHILD_STATUS  *PDXGKDDI_QUERY_CHILD_STATUS;
typedef DXGKDDI_INTERRUPT_ROUTINE  *PDXGKDDI_INTERRUPT_ROUTINE;
typedef DXGKDDI_DPC_ROUTINE  *PDXGKDDI_DPC_ROUTINE;
typedef DXGKDDI_QUERY_DEVICE_DESCRIPTOR  *PDXGKDDI_QUERY_DEVICE_DESCRIPTOR;
typedef DXGKDDI_SET_POWER_STATE  *PDXGKDDI_SET_POWER_STATE;
typedef DXGKDDI_NOTIFY_ACPI_EVENT  *PDXGKDDI_NOTIFY_ACPI_EVENT;
typedef DXGKDDI_RESET_DEVICE  *PDXGKDDI_RESET_DEVICE;
typedef DXGKDDI_UNLOAD  *PDXGKDDI_UNLOAD;
typedef DXGKDDI_QUERY_INTERFACE  *PDXGKDDI_QUERY_INTERFACE;
typedef DXGKDDI_CONTROL_ETW_LOGGING  *PDXGKDDI_CONTROL_ETW_LOGGING;
typedef DXGKDDI_QUERYADAPTERINFO  *PDXGKDDI_QUERYADAPTERINFO;
typedef DXGKDDI_CREATEDEVICE  *PDXGKDDI_CREATEDEVICE;
typedef DXGKDDI_CREATEALLOCATION  *PDXGKDDI_CREATEALLOCATION;
typedef DXGKDDI_DESTROYALLOCATION  *PDXGKDDI_DESTROYALLOCATION;
typedef DXGKDDI_DESCRIBEALLOCATION  *PDXGKDDI_DESCRIBEALLOCATION;
typedef DXGKDDI_GETSTANDARDALLOCATIONDRIVERDATA  *PDXGKDDI_GETSTANDARDALLOCATIONDRIVERDATA;
typedef DXGKDDI_ACQUIRESWIZZLINGRANGE  *PDXGKDDI_ACQUIRESWIZZLINGRANGE;
typedef DXGKDDI_RELEASESWIZZLINGRANGE  *PDXGKDDI_RELEASESWIZZLINGRANGE;
typedef DXGKDDI_PATCH  *PDXGKDDI_PATCH;
typedef DXGKDDI_SUBMITCOMMAND  *PDXGKDDI_SUBMITCOMMAND;
typedef DXGKDDI_PREEMPTCOMMAND  *PDXGKDDI_PREEMPTCOMMAND;
typedef DXGKDDI_BUILDPAGINGBUFFER  *PDXGKDDI_BUILDPAGINGBUFFER;
typedef DXGKDDI_SETPALETTE  *PDXGKDDI_SETPALETTE;
typedef DXGKDDI_SETPOINTERPOSITION  *PDXGKDDI_SETPOINTERPOSITION;
typedef DXGKDDI_SETPOINTERSHAPE  *PDXGKDDI_SETPOINTERSHAPE;
typedef DXGKDDI_RESETFROMTIMEOUT  *PDXGKDDI_RESETFROMTIMEOUT;
typedef DXGKDDI_RESTARTFROMTIMEOUT  *PDXGKDDI_RESTARTFROMTIMEOUT;
typedef DXGKDDI_ESCAPE  *PDXGKDDI_ESCAPE;
typedef DXGKDDI_COLLECTDBGINFO  *PDXGKDDI_COLLECTDBGINFO;
typedef DXGKDDI_QUERYCURRENTFENCE  *PDXGKDDI_QUERYCURRENTFENCE;
typedef DXGKDDI_ISSUPPORTEDVIDPN  *PDXGKDDI_ISSUPPORTEDVIDPN;
typedef DXGKDDI_RECOMMENDFUNCTIONALVIDPN  *PDXGKDDI_RECOMMENDFUNCTIONALVIDPN;
typedef DXGKDDI_ENUMVIDPNCOFUNCMODALITY  *PDXGKDDI_ENUMVIDPNCOFUNCMODALITY;
typedef DXGKDDI_SETVIDPNSOURCEADDRESS  *PDXGKDDI_SETVIDPNSOURCEADDRESS;
typedef DXGKDDI_SETVIDPNSOURCEVISIBILITY  *PDXGKDDI_SETVIDPNSOURCEVISIBILITY;
typedef DXGKDDI_COMMITVIDPN  *PDXGKDDI_COMMITVIDPN;
typedef DXGKDDI_UPDATEACTIVEVIDPNPRESENTPATH  *PDXGKDDI_UPDATEACTIVEVIDPNPRESENTPATH;
typedef DXGKDDI_RECOMMENDMONITORMODES  *PDXGKDDI_RECOMMENDMONITORMODES;
typedef DXGKDDI_RECOMMENDVIDPNTOPOLOGY  *PDXGKDDI_RECOMMENDVIDPNTOPOLOGY;
typedef DXGKDDI_GETSCANLINE  *PDXGKDDI_GETSCANLINE;
typedef DXGKDDI_STOPCAPTURE  *PDXGKDDI_STOPCAPTURE;
typedef DXGKDDI_CONTROLINTERRUPT  *PDXGKDDI_CONTROLINTERRUPT;
typedef DXGKDDI_CREATEOVERLAY  *PDXGKDDI_CREATEOVERLAY;
typedef DXGKDDI_DESTROYDEVICE  *PDXGKDDI_DESTROYDEVICE;
typedef DXGKDDI_OPENALLOCATIONINFO  *PDXGKDDI_OPENALLOCATIONINFO;
typedef DXGKDDI_CLOSEALLOCATION  *PDXGKDDI_CLOSEALLOCATION;
typedef DXGKDDI_RENDER  *PDXGKDDI_RENDER;
typedef DXGKDDI_PRESENT  *PDXGKDDI_PRESENT;
typedef DXGKDDI_UPDATEOVERLAY  *PDXGKDDI_UPDATEOVERLAY;
typedef DXGKDDI_FLIPOVERLAY  *PDXGKDDI_FLIPOVERLAY;
typedef DXGKDDI_DESTROYOVERLAY  *PDXGKDDI_DESTROYOVERLAY;
typedef DXGKDDI_CREATECONTEXT  *PDXGKDDI_CREATECONTEXT; 
typedef DXGKDDI_DESTROYCONTEXT  *PDXGKDDI_DESTROYCONTEXT;
typedef DXGKDDI_LINK_DEVICE  *PDXGKDDI_LINK_DEVICE;
typedef DXGKDDI_SETDISPLAYPRIVATEDRIVERFORMAT  *PDXGKDDI_SETDISPLAYPRIVATEDRIVERFORMAT;
#if (DXGKDDI_INTERFACE_VERSION &gt;= DXGKDDI_INTERFACE_VERSION_WIN7)
typedef DXGKDDI_DESCRIBEPAGETABLE  *PDXGKDDI_DESCRIBEPAGETABLE;
typedef DXGKDDI_UPDATEPAGETABLE  *PDXGKDDI_UPDATEPAGETABLE;
typedef DXGKDDI_UPDATEPAGEDIRECTORY  *PDXGKDDI_UPDATEPAGEDIRECTORY;
typedef DXGKDDI_MOVEPAGEDIRECTORY  *PDXGKDDI_MOVEPAGEDIRECTORY;
typedef DXGKDDI_SUBMITRENDER  *PDXGKDDI_SUBMITRENDER;
typedef DXGKDDI_CREATEALLOCATION2  *PDXGKDDI_CREATEALLOCATION2;
typedef DXGKDDI_RENDERKM  *PDXGKDDI_RENDERKM;
typedef DXGKDDI_QUERYVIDPNHWCAPABILITY  *PDXGKDDI_QUERYVIDPNHWCAPABILITY;
#endif // DXGKDDI_INTERFACE_VERSION_WIN7
#if (DXGKDDI_INTERFACE_VERSION &gt;= DXGKDDI_INTERFACE_VERSION_WIN8)
typedef DXGKDDISETPOWERCOMPONENTFSTATE  *PDXGKDDISETPOWERCOMPONENTFSTATE;
typedef DXGKDDI_QUERYDEPENDENTENGINEGROUP  *PDXGKDDI_QUERYDEPENDENTENGINEGROUP;
typedef DXGKDDI_QUERYENGINESTATUS  *PDXGKDDI_QUERYENGINESTATUS;
typedef DXGKDDI_RESETENGINE  *PDXGKDDI_RESETENGINE;
typedef DXGKDDI_STOP_DEVICE_AND_RELEASE_POST_DISPLAY_OWNERSHIP  *PDXGKDDI_STOP_DEVICE_AND_RELEASE_POST_DISPLAY_OWNERSHIP;
typedef DXGKDDI_SYSTEM_DISPLAY_ENABLE  *PDXGKDDI_SYSTEM_DISPLAY_ENABLE;
typedef DXGKDDI_SYSTEM_DISPLAY_WRITE  *PDXGKDDI_SYSTEM_DISPLAY_WRITE; 
typedef DXGKDDI_CANCELCOMMAND  *PDXGKDDI_CANCELCOMMAND;
typedef DXGKDDI_GET_CHILD_CONTAINER_ID  *PDXGKDDI_GET_CHILD_CONTAINER_ID;
typedef DXGKDDIPOWERRUNTIMECONTROLREQUEST  *PDXGKDDIPOWERRUNTIMECONTROLREQUEST; 
typedef DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY *PDXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY;
typedef DXGKDDI_NOTIFY_SURPRISE_REMOVAL         *PDXGKDDI_NOTIFY_SURPRISE_REMOVAL;
#endif //
#if (DXGKDDI_INTERFACE_VERSION &gt;= DXGKDDI_INTERFACE_VERSION_WDDM1_3)
typedef DXGKDDI_GETNODEMETADATA  *PDXGKDDI_GETNODEMETADATA;
typedef DXGKDDI_CONTROLINTERRUPT2  *PDXGKDDI_CONTROLINTERRUPT2;
typedef DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT  *PDXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT;
typedef DXGKDDI_FORMATHISTORYBUFFER  *PDXGKDDI_FORMATHISTORYBUFFER;
typedef DXGKDDI_CALIBRATEGPUCLOCK  *PDXGKDDI_CALIBRATEGPUCLOCK; 
#endif</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dispmprt.h (include Dispmprt.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556157">DriverEntry of Display Miniport Driver</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DRIVER_INITIALIZATION_DATA structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>