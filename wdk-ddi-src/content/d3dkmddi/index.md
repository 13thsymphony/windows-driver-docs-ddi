---
UID: NA:d3dkmddi
ms.assetid: a83eb75d-c795-391b-b806-21315243d434
ms.author: windowsdriverdev
ms.date: 01/18/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# d3dkmddi.h header



d3dkmddi.h contains the following programming interfaces:





## Functions
| Title | Description |
| ---- |:---- |
| [DXGKCB_COMPLETEFSTATETRANSITION](nc-d3dkmddi-dxgkcb_completefstatetransition.md) | Called by a Windows Display Driver Model (WDDM) 1.2 or later display miniport driver to notify the port driver that a power component has completed the F-state transition. |
| [DXGKCB_CREATECONTEXTALLOCATION](nc-d3dkmddi-dxgkcb_createcontextallocation.md) | Called by a Windows Display Driver Model (WDDM) 1.2 or later display miniport driver to allocate a GPU context or device-specific context. |
| [DXGKCB_DESTROYCONTEXTALLOCATION](nc-d3dkmddi-dxgkcb_destroycontextallocation.md) | Called by a WDDM 1.2 or later display miniport driver to free a resource that was previously allocated for a GPU or device-specific context. |
| [DXGKCB_ENUMHANDLECHILDREN](nc-d3dkmddi-dxgkcb_enumhandlechildren.md) | The DxgkCbEnumHandleChildren function enumerates all of the allocations that are associated with a given resource, one allocation at a time. |
| [DXGKCB_GETCAPTUREADDRESS](nc-d3dkmddi-dxgkcb_getcaptureaddress.md) | The DxgkCbGetCaptureAddress function retrieves the physical address and segment identifier of a capture buffer that is associated with the given allocation handle. |
| [DXGKCB_GETHANDLEDATA](nc-d3dkmddi-dxgkcb_gethandledata.md) | The DxgkCbGetHandleData function retrieves the private data that is associated with an allocation. |
| [DXGKCB_GETHANDLEPARENT](nc-d3dkmddi-dxgkcb_gethandleparent.md) | The DxgkCbGetHandleParent function retrieves the parent resource from the specified allocation. |
| [DXGKCB_HARDWARECONTENTPROTECTIONTEARDOWN](nc-d3dkmddi-dxgkcb_hardwarecontentprotectionteardown.md) | DxgkCbHardwareContentProtectionTeardown is used to indicate when a hardware content protection event occurs. |
| [DXGKCB_INDICATE_CONNECTOR_CHANGE](nc-d3dkmddi-dxgkcb_indicate_connector_change.md) | DXGKCB_INDICATE_CONNECTOR_CHANGE is called by the KMD to indicate that it has added changes to its change queue which the OS should now query. |
| [DXGKCB_MAPCONTEXTALLOCATION](nc-d3dkmddi-dxgkcb_mapcontextallocation.md) | Maps a graphics processing unit (GPU) virtual address to the specified context allocation. |
| [DXGKCB_MULTIPLANEOVERLAYDISABLED](nc-d3dkmddi-dxgkcb_multiplaneoverlaydisabled.md) | This callback allows the kernel mode driver to indicate that the current multiplane overlay configuration is no longer supported on the specified VidPnSourceId. |
| [DXGKCB_NOTIFY_DPC](nc-d3dkmddi-dxgkcb_notify_dpc.md) | The DxgkCbNotifyDpc function informs the graphics processing unit (GPU) scheduler about a graphics hardware update at deferred-procedure-call (DPC) time. |
| [DXGKCB_NOTIFY_INTERRUPT](nc-d3dkmddi-dxgkcb_notify_interrupt.md) | The DxgkCbNotifyInterrupt function informs the graphics processing unit (GPU) scheduler about a graphics hardware update at interrupt-service-routine (ISR) time. |
| [DXGKCB_POWERRUNTIMECONTROLREQUEST](nc-d3dkmddi-dxgkcb_powerruntimecontrolrequest.md) | Called by the display miniport driver to exchange information with the Power Engine Plug-in (PEP). |
| [DXGKCB_QUERYMONITORINTERFACE](nc-d3dkmddi-dxgkcb_querymonitorinterface.md) | The DxgkCbQueryMonitorInterface function returns a pointer to a DXGK_MONITOR_INTERFACE structure. |
| [DXGKCB_QUERYVIDPNINTERFACE](nc-d3dkmddi-dxgkcb_queryvidpninterface.md) | The DxgkCbQueryVidPnInterface function returns a pointer to a DXGK_VIDPN_INTERFACE structure. The structure contains pointers to functions that the display miniport driver can call to inspect and alter a VidPN object. |
| [DXGKCB_RESERVEGPUVIRTUALADDRESSRANGE](nc-d3dkmddi-dxgkcb_reservegpuvirtualaddressrange.md) | DxgkCbReserveGpuVirtualAddressRange allows the kernel mode driver to reserve a graphics processing unit (GPU) virtual address range during creation of a process. |
| [DXGKCB_SETPOWERCOMPONENTACTIVE](nc-d3dkmddi-dxgkcb_setpowercomponentactive.md) | Called by the display miniport driver to access a power component. |
| [DXGKCB_SETPOWERCOMPONENTIDLE](nc-d3dkmddi-dxgkcb_setpowercomponentidle.md) | Called by the display miniport driver to notify the Microsoft DirectX graphics kernel subsystem that a power component is no longer needed. |
| [DXGKCB_SETPOWERCOMPONENTLATENCY](nc-d3dkmddi-dxgkcb_setpowercomponentlatency.md) | Called by the display miniport driver to set the latency tolerance for a power component of type DXGK_POWER_COMPONENT_OTHER. |
| [DXGKCB_SETPOWERCOMPONENTRESIDENCY](nc-d3dkmddi-dxgkcb_setpowercomponentresidency.md) | Called by the display miniport driver to set the expected residency for a power component of type DXGK_POWER_COMPONENT_OTHER. |
| [DXGKCB_UPDATECONTEXTALLOCATION](nc-d3dkmddi-dxgkcb_updatecontextallocation.md) | DxgkCbUpdateContextAllocation is used to update the content of a context allocation. |
| [DXGKDDI_ACQUIRESWIZZLINGRANGE](nc-d3dkmddi-dxgkddi_acquireswizzlingrange.md) | The DxgkDdiAcquireSwizzlingRange function makes an allocation accessible through the central processing unit (CPU) aperture for the given segment. |
| [DXGKDDI_BUILDPAGINGBUFFER](nc-d3dkmddi-dxgkddi_buildpagingbuffer.md) | The DxgkDdiBuildPagingBuffer function builds paging buffers for memory operations. |
| [DXGKDDI_CALIBRATEGPUCLOCK](nc-d3dkmddi-dxgkddi_calibrategpuclock.md) | Called by the Microsoft DirectX graphics kernel subsystem to calibrate the GPU time stamps in the DXGK_HISTORY_BUFFER history buffer with the CPU clock time. |
| [DXGKDDI_CANCELCOMMAND](nc-d3dkmddi-dxgkddi_cancelcommand.md) | Cleans up internal resources associated with a direct memory access (DMA) packet that was in the GPU scheduler's software queue but never reached the hardware queue because the device went into an error state. |
| [DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT](nc-d3dkmddi-dxgkddi_checkmultiplaneoverlaysupport.md) | Called by the Microsoft DirectX graphics kernel subsystem to check the details of hardware support for multiplane overlays. |
| [DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT2](nc-d3dkmddi-dxgkddi_checkmultiplaneoverlaysupport2.md) | DxgkDdiCheckMultiPlaneOverlaySupport2 is called to determine whether a specific multi-plane overlay configuration is supported. |
| [DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT3](nc-d3dkmddi-dxgkddi_checkmultiplaneoverlaysupport3.md) | The following new function is called to determine whether a specific multi-plane overlay configuration is supported. |
| [DXGKDDI_CLOSEALLOCATION](nc-d3dkmddi-dxgkddi_closeallocation.md) | The DxgkDdiCloseAllocation function unbinds device-specific allocations that the DxgkDdiOpenAllocation function created. |
| [DXGKDDI_COLLECTDBGINFO](nc-d3dkmddi-dxgkddi_collectdbginfo.md) | The DxgkDdiCollectDbgInfo function outputs driver information for a debug report. |
| [DXGKDDI_COMMITVIDPN](nc-d3dkmddi-dxgkddi_commitvidpn.md) | The DxgkDdiCommitVidPn function makes a specified video present network (VidPN) active on a display adapter. |
| [DXGKDDI_CONTROLINTERRUPT](nc-d3dkmddi-dxgkddi_controlinterrupt.md) | The DxgkDdiControlInterrupt function enables or disables the given interrupt type on the graphics hardware. |
| [DXGKDDI_CONTROLINTERRUPT2](nc-d3dkmddi-dxgkddi_controlinterrupt2.md) | The DxgkDdi_ControlInterrupt2 function enables or disables the given interrupt type on the graphics hardware. |
| [DXGKDDI_CREATEALLOCATION](nc-d3dkmddi-dxgkddi_createallocation.md) | The DxgkDdiCreateAllocation function creates allocations of system or video memory. |
| [DXGKDDI_CREATECONTEXT](nc-d3dkmddi-dxgkddi_createcontext.md) | The DxgkDdiCreateContext function creates a graphics processing unit (GPU) context. |
| [DXGKDDI_CREATEDEVICE](nc-d3dkmddi-dxgkddi_createdevice.md) | The DxgkDdiCreateDevice function creates a graphics context device that is subsequently used in calls to the display miniport driver's device-specific functions. |
| [DXGKDDI_CREATEOVERLAY](nc-d3dkmddi-dxgkddi_createoverlay.md) | The DxgkDdiCreateOverlay function enables the overlay hardware if the hardware is capable. |
| [DXGKDDI_CREATEPERIODICFRAMENOTIFICATION](nc-d3dkmddi-dxgkddi_createperiodicframenotification.md) | Used to create a periodic frame notification. |
| [DXGKDDI_CREATEPROCESS](nc-d3dkmddi-dxgkddi_createprocess.md) | DxgkDdiCreateProcess creates a graphics kernel process object. |
| [DXGKDDI_CREATEPROTECTEDSESSION](nc-d3dkmddi-dxgkddi_createprotectedsession.md) | Used to create a protected session. |
| [DXGKDDI_DESCRIBEALLOCATION](nc-d3dkmddi-dxgkddi_describeallocation.md) | The DxgkDdiDescribeAllocation function retrieves information about an existing allocation that is not otherwise available to the Microsoft DirectX graphics kernel subsystem. |
| [DXGKDDI_DESTROYALLOCATION](nc-d3dkmddi-dxgkddi_destroyallocation.md) | The DxgkDdiDestroyAllocation function releases allocations. |
| [DXGKDDI_DESTROYCONTEXT](nc-d3dkmddi-dxgkddi_destroycontext.md) | The DxgkDdiDestroyContext function destroys the specified graphics processing unit (GPU) context. |
| [DXGKDDI_DESTROYDEVICE](nc-d3dkmddi-dxgkddi_destroydevice.md) | The DxgkDdiDestroyDevice function destroys a graphics context device. |
| [DXGKDDI_DESTROYOVERLAY](nc-d3dkmddi-dxgkddi_destroyoverlay.md) | The DxgkDdiDestroyOverlay function disables overlay hardware and deletes the specified overlay handle. |
| [DXGKDDI_DESTROYPERIODICFRAMENOTIFICATION](nc-d3dkmddi-dxgkddi_destroyperiodicframenotification.md) | Used to destroy a periodic frame notification. |
| [DXGKDDI_DESTROYPROCESS](nc-d3dkmddi-dxgkddi_destroyprocess.md) | DxgkDdiDestroyProcess destroys a kernel mode driver process object. |
| [DXGKDDI_DESTROYPROTECTEDSESSION](nc-d3dkmddi-dxgkddi_destroyprotectedsession.md) | Used to destroy a protected session. |
| [DXGKDDI_DISPLAYDETECTCONTROL](nc-d3dkmddi-dxgkddi_displaydetectcontrol.md) | Used to turn hot plug detection on and off and to initiate status polls on either a specific target or all targets. |
| [DXGKDDI_ENUMVIDPNCOFUNCMODALITY](nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality.md) | The DxgkDdiEnumVidPnCofuncModality function makes the source and target modes sets of a VidPN cofunctional with the VidPN's topology and the modes that have already been pinned. |
| [DXGKDDI_ESCAPE](nc-d3dkmddi-dxgkddi_escape.md) | The DxgkDdiEscape function shares information with the user-mode display driver. |
| [DXGKDDI_FLIPOVERLAY](nc-d3dkmddi-dxgkddi_flipoverlay.md) | The DxgkDdiFlipOverlay function displays a new allocation by using the specified overlay. |
| [DXGKDDI_FORMATHISTORYBUFFER](nc-d3dkmddi-dxgkddi_formathistorybuffer.md) | Copies unformatted data from the history buffer into a buffer that's properly formatted to be submitted to the Event Tracing for Windows (ETW) facility. |
| [DXGKDDI_GETMULTIPLANEOVERLAYCAPS](nc-d3dkmddi-dxgkddi_getmultiplaneoverlaycaps.md) | Called to retrieve multiplane overlay capabilities. Support for this DDI is required for any WDDM 2.2 driver that wants to support multiple planes. |
| [DXGKDDI_GETNODEMETADATA](nc-d3dkmddi-dxgkddi_getnodemetadata.md) | From a provided adapter handle, returns the engine type and friendly name of an engine on a specified GPU node. Must be implemented by Windows Display Driver Model (WDDM) 1.3 and later display miniport drivers. |
| [DXGKDDI_GETPOSTCOMPOSITIONCAPS](nc-d3dkmddi-dxgkddi_getpostcompositioncaps.md) | Called to retrieve post composition capabilities. Support for this DDI is required for any WDDM 2.2 driver that wants to support post composition scaling. |
| [DXGKDDI_GETROOTPAGETABLESIZE](nc-d3dkmddi-dxgkddi_getrootpagetablesize.md) | DxgkDdiGetRootPageTableSize returns the minimum root page table size, in bytes, that is needed to hold the given number of page table entries. |
| [DXGKDDI_GETSCANLINE](nc-d3dkmddi-dxgkddi_getscanline.md) | The DxgkDdiGetScanLine function determines whether the specified video present target of a video present network (VidPN) is in vertical blanking mode and retrieves the current scan line. |
| [DXGKDDI_GETSTANDARDALLOCATIONDRIVERDATA](nc-d3dkmddi-dxgkddi_getstandardallocationdriverdata.md) | The DxgkDdiGetStandardAllocationDriverData function returns a description of a standard allocation type. |
| [DXGKDDI_ISSUPPORTEDVIDPN](nc-d3dkmddi-dxgkddi_issupportedvidpn.md) | The DxgkDdiIsSupportedVidPn function determines whether a specified VidPN is supported on a display adapter. |
| [DXGKDDI_MAPCPUHOSTAPERTURE](nc-d3dkmddi-dxgkddi_mapcpuhostaperture.md) | DxgkDdiMapCpuHostAperture is called to map an allocation that is resident in a local memory segment into the CPU host aperture in order to make it visible to the CPU. |
| [DXGKDDI_MONITOR_ACQUIREMONITORSOURCEMODESET](nc-d3dkmddi-dxgkddi_monitor_acquiremonitorsourcemodeset.md) | The pfnAcquireMonitorSourceModeSet function returns a handle to the monitor source mode set object that is associated with a specified monitor. |
| [DXGKDDI_MONITOR_GETADDITIONALMONITORMODESET](nc-d3dkmddi-dxgkddi_monitor_getadditionalmonitormodeset.md) | The pfnGetAdditionalMonitorModeSet function, available in the DXGK_MONITOR_INTERFACE_V2 interface beginning with Windows 7, returns a handle to an additional monitor source mode set object that is associated with a specified monitor. |
| [DXGKDDI_MONITOR_GETMONITORDESCRIPTORSET](nc-d3dkmddi-dxgkddi_monitor_getmonitordescriptorset.md) | The pfnGetMonitorDescriptorSet function returns a handle to a monitor descriptor set object that is associated with a specified monitor. |
| [DXGKDDI_MONITOR_GETMONITORFREQUENCYRANGESET](nc-d3dkmddi-dxgkddi_monitor_getmonitorfrequencyrangeset.md) | The pfnGetMonitorFrequencyRangeSet function returns a handle to the monitor frequency range set object that is associated with a specified monitor. |
| [DXGKDDI_MONITOR_RELEASEADDITIONALMONITORMODESET](nc-d3dkmddi-dxgkddi_monitor_releaseadditionalmonitormodeset.md) | The pfnReleaseAdditionalMonitorModeSet function, available in the DXGK_MONITOR_INTERFACE_V2 interface beginning with Windows 7, releases a handle to an additional monitor source mode set object that is associated with a specified monitor. |
| [DXGKDDI_MONITOR_RELEASEMONITORSOURCEMODESET](nc-d3dkmddi-dxgkddi_monitor_releasemonitorsourcemodeset.md) | The pfnReleaseMonitorSourceModeSet function releases a handle to a monitor source mode set object. |
| [DXGKDDI_MONITORDESCRIPTORSET_ACQUIREFIRSTDESCRIPTORINFO](nc-d3dkmddi-dxgkddi_monitordescriptorset_acquirefirstdescriptorinfo.md) | The pfnAcquireFirstDescriptorInfo function returns the first descriptor in a monitor descriptor set object. |
| [DXGKDDI_MONITORDESCRIPTORSET_ACQUIRENEXTDESCRIPTORINFO](nc-d3dkmddi-dxgkddi_monitordescriptorset_acquirenextdescriptorinfo.md) | The pfnAcquireNextDescriptorInfo function returns the next descriptor in a monitor descriptor set, given the current descriptor. |
| [DXGKDDI_MONITORDESCRIPTORSET_GETNUMDESCRIPTORS](nc-d3dkmddi-dxgkddi_monitordescriptorset_getnumdescriptors.md) | The pfnGetNumDescriptors function returns the number of descriptors in a monitor descriptor set. |
| [DXGKDDI_MONITORDESCRIPTORSET_RELEASEDESCRIPTORINFO](nc-d3dkmddi-dxgkddi_monitordescriptorset_releasedescriptorinfo.md) | The pfnReleaseDescriptorInfo function releases a D3DKMDT_MONITOR_DESCRIPTOR structure that the VidPN manager previously provided to the display miniport driver. |
| [DXGKDDI_MONITORFREQUENCYRANGESET_ACQUIREFIRSTFREQUENCYRANGEINFO](nc-d3dkmddi-dxgkddi_monitorfrequencyrangeset_acquirefirstfrequencyrangeinfo.md) | The DXGKDDI_MONITORFREQUENCYRANGESET_ACQUIREFIRSTFREQUENCYRANGEINFO function returns the first frequency range descriptor in a specified monitor frequency range set object. |
| [DXGKDDI_MONITORFREQUENCYRANGESET_ACQUIRENEXTFREQUENCYRANGEINFO](nc-d3dkmddi-dxgkddi_monitorfrequencyrangeset_acquirenextfrequencyrangeinfo.md) | The pfnAcquireNextFrequencyRangeInfo function returns the next frequency range descriptor in a monitor frequency range set, given the current frequency range descriptor. |
| [DXGKDDI_MONITORFREQUENCYRANGESET_GETNUMFREQUENCYRANGES](nc-d3dkmddi-dxgkddi_monitorfrequencyrangeset_getnumfrequencyranges.md) | The pfnGetNumFrequencyRanges returns the number of frequency range descriptors in a specified monitor frequency range set object. |
| [DXGKDDI_MONITORFREQUENCYRANGESET_RELEASEFREQUENCYRANGEINFO](nc-d3dkmddi-dxgkddi_monitorfrequencyrangeset_releasefrequencyrangeinfo.md) | The pfnReleaseFrequencyRangeInfo function releases a D3DKMDT_MONITOR_FREQUENCY_RANGE structure that the VidPN manager previously provided to the display miniport driver. |
| [DXGKDDI_MONITORSOURCEMODESET_ACQUIREFIRSTMODEINFO](nc-d3dkmddi-dxgkddi_monitorsourcemodeset_acquirefirstmodeinfo.md) | The pfnAcquireFirstModeInfo function returns a descriptor of the first mode in a specified monitor source mode set. |
| [DXGKDDI_MONITORSOURCEMODESET_ACQUIRENEXTMODEINFO](nc-d3dkmddi-dxgkddi_monitorsourcemodeset_acquirenextmodeinfo.md) | The pfnAcquireNextModeInfo function returns a descriptor of the next mode in a specified monitor source mode set, given the current mode. |
| [DXGKDDI_MONITORSOURCEMODESET_ACQUIREPREFERREDMODEINFO](nc-d3dkmddi-dxgkddi_monitorsourcemodeset_acquirepreferredmodeinfo.md) | The pfnAcquirePreferredModeInfo returns a descriptor of the preferred mode in a specified monitor source mode set object. |
| [DXGKDDI_MONITORSOURCEMODESET_ADDMODE](nc-d3dkmddi-dxgkddi_monitorsourcemodeset_addmode.md) | The pfnAddMode function adds a monitor source mode to a specified monitor source mode set object. |
| [DXGKDDI_MONITORSOURCEMODESET_CREATENEWMODEINFO](nc-d3dkmddi-dxgkddi_monitorsourcemodeset_createnewmodeinfo.md) | The pfnCreateNewModeInfo function returns a pointer to a D3DKMDT_MONITOR_SOURCE_MODE structure that the display miniport driver populates before calling pfnAddMode. |
| [DXGKDDI_MONITORSOURCEMODESET_GETNUMMODES](nc-d3dkmddi-dxgkddi_monitorsourcemodeset_getnummodes.md) | The pfnGetNumModes function returns the number modes in a specified monitor source mode set. |
| [DXGKDDI_MONITORSOURCEMODESET_RELEASEMODEINFO](nc-d3dkmddi-dxgkddi_monitorsourcemodeset_releasemodeinfo.md) | The pfnReleaseModeInfo function releases a D3DKMDT_MONITOR_SOURCE_MODE structure that the VidPN manager previously provided to the display miniport driver. |
| [DXGKDDI_OPENALLOCATIONINFO](nc-d3dkmddi-dxgkddi_openallocationinfo.md) | The DxgkDdiOpenAllocation function binds non-device-specific allocations that the DxgkDdiCreateAllocation function created to allocations that are specific to the specified graphics context device. |
| [DXGKDDI_PATCH](nc-d3dkmddi-dxgkddi_patch.md) | The DxgkDdiPatch function assigns physical addresses to the given direct memory access (DMA) buffer before the DMA buffer is submitted to the graphics hardware. |
| [DXGKDDI_POSTMULTIPLANEOVERLAYPRESENT](nc-d3dkmddi-dxgkddi_postmultiplaneoverlaypresent.md) | Called after a new multi-plane overlay configuration has taken effect, allowing the driver to optimize hardware state. Optional for Windows Display Driver Model (WDDM) 2.0 or later drivers that support multi-plane overlays. |
| [DXGKDDI_PREEMPTCOMMAND](nc-d3dkmddi-dxgkddi_preemptcommand.md) | The DxgkDdiPreemptCommand function preempts a direct memory access (DMA) buffer that was previously submitted to and currently queued in the hardware command execution unit. |
| [DXGKDDI_PRESENT](nc-d3dkmddi-dxgkddi_present.md) | The DxgkDdiPresent function copies content from source allocations to a primary surface (and sometimes to off-screen system memory allocations). |
| [DXGKDDI_PRESENTDISPLAYONLY](nc-d3dkmddi-dxgkddi_presentdisplayonly.md) | Presents the screen image to the display device of a kernel mode display-only driver (KMDOD). |
| [DXGKDDI_QUERYADAPTERINFO](nc-d3dkmddi-dxgkddi_queryadapterinfo.md) | The DxgkDdiQueryAdapterInfo function retrieves configuration information from the graphics adapter. |
| [DXGKDDI_QUERYCONNECTIONCHANGE](nc-d3dkmddi-dxgkddi_queryconnectionchange.md) | The OS calls this in response to a status change reported through DxgkCbIndicateConnectorChange or when the OutputFlags.ConnectorStatusChanges field indicates that a call to SetTimingsFromVidPn has detected connector status changes. |
| [DXGKDDI_QUERYCURRENTFENCE](nc-d3dkmddi-dxgkddi_querycurrentfence.md) | The DxgkDdiQueryCurrentFence function queries about the latest completed submission fence identifier in the hardware command execution unit. |
| [DXGKDDI_QUERYDEPENDENTENGINEGROUP](nc-d3dkmddi-dxgkddi_querydependentenginegroup.md) | Called by the display port driver's GPU scheduler to query dependencies of nodes in a physical display adapter. |
| [DXGKDDI_QUERYENGINESTATUS](nc-d3dkmddi-dxgkddi_queryenginestatus.md) | The display port driver's GPU scheduler calls this function to determine the progress of a node within an active physical display adapter (engine). |
| [DXGKDDI_QUERYVIDPNHWCAPABILITY](nc-d3dkmddi-dxgkddi_queryvidpnhwcapability.md) | The DxgkDdiQueryVidPnHWCapability function requests that the display miniport driver report the capabilities of the hardware on a functional VidPn path. |
| [DXGKDDI_RECOMMENDFUNCTIONALVIDPN](nc-d3dkmddi-dxgkddi_recommendfunctionalvidpn.md) | The DxgkDdiRecommendFunctionalVidPn function creates a functional VidPN that can be implemented on a specified display adapter. |
| [DXGKDDI_RECOMMENDMONITORMODES](nc-d3dkmddi-dxgkddi_recommendmonitormodes.md) | The DxgkDdiRecommendMonitorModes function inspects the monitor source mode set that is associated with a particular video present target and possibly adds modes to the set. |
| [DXGKDDI_RECOMMENDVIDPNTOPOLOGY](nc-d3dkmddi-dxgkddi_recommendvidpntopology.md) | The DxgkDdiRecommendVidPnTopology function creates the topology of a specified VidPN or augments the topology with a new path to video present targets. |
| [DXGKDDI_RELEASESWIZZLINGRANGE](nc-d3dkmddi-dxgkddi_releaseswizzlingrange.md) | The DxgkDdiReleaseSwizzlingRange function releases a swizzling range that the DxgkDdiAcquireSwizzlingRange function previously set up. |
| [DXGKDDI_RENDER](nc-d3dkmddi-dxgkddi_render.md) | The DxgkDdiRender function generates a direct memory access (DMA) buffer from the command buffer that the user-mode display driver passed. |
| [DXGKDDI_RENDERGDI](nc-d3dkmddi-dxgkddi_rendergdi.md) | DxgkDdiRenderGdi is used when submitting Windows Graphics Device Interface (GDI) commands for contexts that support virtual addressing. |
| [DXGKDDI_RENDERKM](nc-d3dkmddi-dxgkddi_renderkm.md) | For display adapters that support GDI hardware acceleration, the DxgkDdiRenderKm function generates a direct memory access (DMA) buffer from the command buffer that the kernel-mode Canonical Display Driver (CDD) passed. |
| [DXGKDDI_RESETENGINE](nc-d3dkmddi-dxgkddi_resetengine.md) | The display port driver's GPU scheduler calls this function to reset an active node on a physical display adapter when the scheduler detects a timeout condition on the adapter. |
| [DXGKDDI_RESETFROMTIMEOUT](nc-d3dkmddi-dxgkddi_resetfromtimeout.md) | The DxgkDdiResetFromTimeout function resets the graphics processing unit (GPU) after a hardware timeout occurs and guarantees that the GPU is not writing or reading any memory by the time that DxgkDdiResetFromTimeout returns. |
| [DXGKDDI_RESTARTFROMTIMEOUT](nc-d3dkmddi-dxgkddi_restartfromtimeout.md) | The DxgkDdiRestartFromTimeout function indicates that the driver can access the graphics processing unit (GPU) again after the recovery from a hardware timeout has completed. |
| [DXGKDDI_SETDISPLAYPRIVATEDRIVERFORMAT](nc-d3dkmddi-dxgkddi_setdisplayprivatedriverformat.md) | The DxgkDdiSetDisplayPrivateDriverFormat function changes the private-format attribute of a video present source. |
| [DXGKDDI_SETPALETTE](nc-d3dkmddi-dxgkddi_setpalette.md) | The DxgkDdiSetPalette function programs the color registers for palettized 8 bits-per-pixel (bpp) modes. |
| [DXGKDDI_SETPOINTERPOSITION](nc-d3dkmddi-dxgkddi_setpointerposition.md) | The DxgkDdiSetPointerPosition function sets the location and visibility state of the mouse pointer. |
| [DXGKDDI_SETPOINTERSHAPE](nc-d3dkmddi-dxgkddi_setpointershape.md) | The DxgkDdiSetPointerShape function sets the appearance and location of the mouse pointer. |
| [DXGKDDI_SETROOTPAGETABLE](nc-d3dkmddi-dxgkddi_setrootpagetable.md) | DxgkDdiSetRootPageTable sets the root page table for the given context. This function is used to notify a context when its associated root page table is resized or moved in memory. |
| [DXGKDDI_SETTARGETANALOGCOPYPROTECTION](nc-d3dkmddi-dxgkddi_settargetanalogcopyprotection.md) | Sets the analog copy protection on the specified target id. This is functionally equivalent to the DxgkDdiUpdateActiveVidPnPresentPath in previous WDDM versions if only the D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION is changed. |
| [DXGKDDI_SETTARGETCONTENTTYPE](nc-d3dkmddi-dxgkddi_settargetcontenttype.md) | Passes the content type for which the driver should optimize on the specified target. |
| [DXGKDDI_SETTARGETGAMMA](nc-d3dkmddi-dxgkddi_settargetgamma.md) | Allows the gamma LUT to be set on a path which is identified by the target id.Note  This is functionally equivalent to the DxgkDdi_UpdateActiveVidPnPresentPath in previous WDDM versions if only the D3DKMDT_GAMMA_RAMP field is changed. . |
| [DXGKDDI_SETTIMINGSFROMVIDPN](nc-d3dkmddi-dxgkddi_settimingsfromvidpn.md) | DXGKDDI_SETTIMINGSFROMVIDPN is called to set or modify the display timings on an adapter. This DDI replaces DxgkDdiCommitVidPn. |
| [DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY](nc-d3dkmddi-dxgkddi_setvidpnsourceaddresswithmultiplaneoverlay.md) | Sets the addresses of multiple surfaces, including the Desktop Window Manager (DWM)'s swapchain, that are associated with a particular video present source. This function is used to present multiple surfaces (including the DWM’s swapchain) to the screen. |
| [DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2](nc-d3dkmddi-dxgkddi_setvidpnsourceaddresswithmultiplaneoverlay2.md) | DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay2 is called to change the overlay configuration being displayed. |
| [DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3](nc-d3dkmddi-dxgkddi_setvidpnsourceaddresswithmultiplaneoverlay3.md) | Called to change the overlay configuration being displayed. |
| [DXGKDDI_SETVIDPNSOURCEVISIBILITY](nc-d3dkmddi-dxgkddi_setvidpnsourcevisibility.md) | The DxgkDdiSetVidPnSourceVisibility function programs the video output codec that is associated with a specified video present source to either start scanning or stop scanning the source's primary surface. |
| [DXGKDDI_STOPCAPTURE](nc-d3dkmddi-dxgkddi_stopcapture.md) | The DxgkDdiStopCapture function stops the capture hardware from using the given allocation as a capture buffer. |
| [DXGKDDI_SUBMITCOMMAND](nc-d3dkmddi-dxgkddi_submitcommand.md) | The DxgkDdiSubmitCommand function submits a direct memory access (DMA) buffer to the hardware command execution unit. |
| [DXGKDDI_SUBMITCOMMANDVIRTUAL](nc-d3dkmddi-dxgkddi_submitcommandvirtual.md) | DxgkDdiSubmitCommandVirtual is used to submit a direct memory access (DMA) buffer to a context that supports virtual addressing. |
| [DXGKDDI_UNMAPCPUHOSTAPERTURE](nc-d3dkmddi-dxgkddi_unmapcpuhostaperture.md) | DxgkDdiUnmapCpuHostAperture is used to unmap a previously mapped range of the CPU host aperture. |
| [DXGKDDI_UPDATEACTIVEVIDPNPRESENTPATH](nc-d3dkmddi-dxgkddi_updateactivevidpnpresentpath.md) | The DxgkDdiUpdateActiveVidPnPresentPath function updates one of the video present paths that is currently active on the display adapter. |
| [DXGKDDI_UPDATEHWCONTEXTSTATE](nc-d3dkmddi-dxgkddi_updatehwcontextstate.md) | Used to update the hardware context state. |
| [DXGKDDI_UPDATEOVERLAY](nc-d3dkmddi-dxgkddi_updateoverlay.md) | The DxgkDdiUpdateOverlay function modifies the overlay hardware. |
| [DXGKDDI_VIDPN_ACQUIRESOURCEMODESET](nc-d3dkmddi-dxgkddi_vidpn_acquiresourcemodeset.md) | The pfnAcquireSourceModeSet function returns a handle to a particular source mode set object that is contained by a specified VidPN object. |
| [DXGKDDI_VIDPN_ACQUIRETARGETMODESET](nc-d3dkmddi-dxgkddi_vidpn_acquiretargetmodeset.md) | The pfnAcquireTargetModeSet function returns a handle to a particular target mode set object that is contained by a specified VidPN object. |
| [DXGKDDI_VIDPN_ASSIGNMULTISAMPLINGMETHODSET](nc-d3dkmddi-dxgkddi_vidpn_assignmultisamplingmethodset.md) | The pfnAssignMultisamplingMethodSet function assigns a set of multisampling methods to a particular video present source in a specified VidPN. |
| [DXGKDDI_VIDPN_ASSIGNSOURCEMODESET](nc-d3dkmddi-dxgkddi_vidpn_assignsourcemodeset.md) | The pfnAssignSourceModeSet function assigns a source mode set to a particular source in a specified VidPN. |
| [DXGKDDI_VIDPN_ASSIGNTARGETMODESET](nc-d3dkmddi-dxgkddi_vidpn_assigntargetmodeset.md) | The pfnAssignTargetModeSet function assigns a target mode set to a particular target in a specified VidPN. |
| [DXGKDDI_VIDPN_CREATENEWSOURCEMODESET](nc-d3dkmddi-dxgkddi_vidpn_createnewsourcemodeset.md) | The pfnCreateNewSourceModeSet function creates a new source mode set object within a specified VidPN object. |
| [DXGKDDI_VIDPN_CREATENEWTARGETMODESET](nc-d3dkmddi-dxgkddi_vidpn_createnewtargetmodeset.md) | The pfnCreateNewTargetModeSet function creates a new target mode set object within a specified VidPN object. |
| [DXGKDDI_VIDPN_GETTOPOLOGY](nc-d3dkmddi-dxgkddi_vidpn_gettopology.md) | The pfnGetTopology function returns a handle to the VidPN topology object contained by a specified VidPN object. |
| [DXGKDDI_VIDPN_RELEASESOURCEMODESET](nc-d3dkmddi-dxgkddi_vidpn_releasesourcemodeset.md) | The pfnReleaseSourceModeSet function releases a handle to a source mode set object. |
| [DXGKDDI_VIDPN_RELEASETARGETMODESET](nc-d3dkmddi-dxgkddi_vidpn_releasetargetmodeset.md) | The pfnReleaseTargetModeSet function releases a handle to a target mode set object. |
| [DXGKDDI_VIDPNSOURCEMODESET_ACQUIREFIRSTMODEINFO](nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_acquirefirstmodeinfo.md) | The pfnAcquireFirstModeInfo function returns a descriptor of the first mode in a specified VidPN source mode set. |
| [DXGKDDI_VIDPNSOURCEMODESET_ACQUIRENEXTMODEINFO](nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_acquirenextmodeinfo.md) | The pfnAcquireNextModeInfo function returns a descriptor of the next mode in a specified VidPN source mode set, given the current mode. |
| [DXGKDDI_VIDPNSOURCEMODESET_ACQUIREPINNEDMODEINFO](nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_acquirepinnedmodeinfo.md) | The pfnAcquirePinnedModeInfo function returns a descriptor of the pinned mode in a specified VidPN source mode set. |
| [DXGKDDI_VIDPNSOURCEMODESET_ADDMODE](nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_addmode.md) | The pfnAddMode function adds a VidPN source mode to a specified VidPN source mode set object. |
| [DXGKDDI_VIDPNSOURCEMODESET_CREATENEWMODEINFO](nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_createnewmodeinfo.md) | The pfnCreateNewModeInfo function returns a pointer to a D3DKMDT_VIDPN_SOURCE_MODE structure that the display miniport driver populates before calling pfnAddMode. |
| [DXGKDDI_VIDPNSOURCEMODESET_GETNUMMODES](nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_getnummodes.md) | The pfnGetNumModes function returns the number of source modes in a specified VidPN source mode set. |
| [DXGKDDI_VIDPNSOURCEMODESET_PINMODE](nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_pinmode.md) | The pfnPinMode function pins a specified mode in a VidPN source mode set. |
| [DXGKDDI_VIDPNSOURCEMODESET_RELEASEMODEINFO](nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_releasemodeinfo.md) | The pfnReleaseModeInfo function releases a D3DKMDT_VIDPN_SOURCE_MODE structure that the VidPN manager previously provided to the display miniport driver. |
| [DXGKDDI_VIDPNTARGETMODESET_ACQUIREFIRSTMODEINFO](nc-d3dkmddi-dxgkddi_vidpntargetmodeset_acquirefirstmodeinfo.md) | The pfnAcquireFirstModeInfo function returns a descriptor of the first mode in a specified VidPN target mode set. |
| [DXGKDDI_VIDPNTARGETMODESET_ACQUIRENEXTMODEINFO](nc-d3dkmddi-dxgkddi_vidpntargetmodeset_acquirenextmodeinfo.md) | The pfnAcquireNextModeInfo function returns a descriptor of the next mode in a specified VidPN target mode set, given the current mode. |
| [DXGKDDI_VIDPNTARGETMODESET_ACQUIREPINNEDMODEINFO](nc-d3dkmddi-dxgkddi_vidpntargetmodeset_acquirepinnedmodeinfo.md) | The pfnAcquirePinnedModeInfo function returns a descriptor of the pinned mode in a specified VidPN target mode set. |
| [DXGKDDI_VIDPNTARGETMODESET_ADDMODE](nc-d3dkmddi-dxgkddi_vidpntargetmodeset_addmode.md) | The pfnAddMode function adds a VidPN target mode to a specified VidPN target mode set object. |
| [DXGKDDI_VIDPNTARGETMODESET_CREATENEWMODEINFO](nc-d3dkmddi-dxgkddi_vidpntargetmodeset_createnewmodeinfo.md) | The pfnCreateNewModeInfo function returns a pointer to a D3DKMDT_VIDPN_TARGET_MODE structure that the display miniport driver populates before calling pfnAddMode. |
| [DXGKDDI_VIDPNTARGETMODESET_GETNUMMODES](nc-d3dkmddi-dxgkddi_vidpntargetmodeset_getnummodes.md) | The pfnGetNumModes function returns the number of target modes in a specified VidPN target mode set. |
| [DXGKDDI_VIDPNTARGETMODESET_PINMODE](nc-d3dkmddi-dxgkddi_vidpntargetmodeset_pinmode.md) | The pfnPinMode function pins a specified mode in a VidPN target mode set. |
| [DXGKDDI_VIDPNTARGETMODESET_RELEASEMODEINFO](nc-d3dkmddi-dxgkddi_vidpntargetmodeset_releasemodeinfo.md) | The pfnReleaseModeInfo function releases a D3DKMDT_VIDPN_TARGET_MODE structure that the VidPN manager previously provided to the display miniport driver. |
| [DXGKDDI_VIDPNTOPOLOGY_ACQUIREFIRSTPATHINFO](nc-d3dkmddi-dxgkddi_vidpntopology_acquirefirstpathinfo.md) | The pfnAcquireFirstPathInfo structure returns a descriptor of the first path in a specified VidPN topology object. |
| [DXGKDDI_VIDPNTOPOLOGY_ACQUIRENEXTPATHINFO](nc-d3dkmddi-dxgkddi_vidpntopology_acquirenextpathinfo.md) | The pfnAcquireNextPathInfo function returns a descriptor of the next video present path in a specified VidPN topology, given the current path. |
| [DXGKDDI_VIDPNTOPOLOGY_ACQUIREPATHINFO](nc-d3dkmddi-dxgkddi_vidpntopology_acquirepathinfo.md) | The pfnAcquirePathInfo function returns a descriptor of the video present path specified by a video present source and a video present target within a particular VidPN topology. |
| [DXGKDDI_VIDPNTOPOLOGY_ADDPATH](nc-d3dkmddi-dxgkddi_vidpntopology_addpath.md) | The pfnAddPath function adds a video present path to a specified VidPN topology object. |
| [DXGKDDI_VIDPNTOPOLOGY_CREATENEWPATHINFO](nc-d3dkmddi-dxgkddi_vidpntopology_createnewpathinfo.md) | The pfnCreateNewPathInfo function returns a pointer to a D3DKMDT_VIDPN_PRESENT_PATH structure that the display miniport driver populates before calling pfnAddPath. |
| [DXGKDDI_VIDPNTOPOLOGY_ENUMPATHTARGETSFROMSOURCE](nc-d3dkmddi-dxgkddi_vidpntopology_enumpathtargetsfromsource.md) | The pfnEnumPathTargetsFromSource function returns the identifier of one of the video present targets associated with a specified video present source. |
| [DXGKDDI_VIDPNTOPOLOGY_GETNUMPATHS](nc-d3dkmddi-dxgkddi_vidpntopology_getnumpaths.md) | The pfnGetNumPaths function returns the number of video present paths in a specified VidPN topology. |
| [DXGKDDI_VIDPNTOPOLOGY_GETNUMPATHSFROMSOURCE](nc-d3dkmddi-dxgkddi_vidpntopology_getnumpathsfromsource.md) | The pfnGetNumPathsFromSource function returns the number of video present paths that contain a specified video present source. |
| [DXGKDDI_VIDPNTOPOLOGY_GETPATHSOURCEFROMTARGET](nc-d3dkmddi-dxgkddi_vidpntopology_getpathsourcefromtarget.md) | The pfnGetPathSourceFromTarget function returns the identifier of the video present source that is associated with a specified video present target. |
| [DXGKDDI_VIDPNTOPOLOGY_RELEASEPATHINFO](nc-d3dkmddi-dxgkddi_vidpntopology_releasepathinfo.md) | The pfnReleasePathInfo function releases a D3DKMDT_VIDPN_PRESENT_PATH structure that the VidPN manager previously provided to the display miniport driver. |
| [DXGKDDI_VIDPNTOPOLOGY_REMOVEPATH](nc-d3dkmddi-dxgkddi_vidpntopology_removepath.md) | The pfnRemovePath function removes a video present path to a specified VidPN topology object. |
| [DXGKDDI_VIDPNTOPOLOGY_UPDATEPATHSUPPORTINFO](nc-d3dkmddi-dxgkddi_vidpntopology_updatepathsupportinfo.md) | The pfnUpdatePathSupportInfo function updates the transformation and copy protection support of a particular path in a specified VidPN topology. |
| [DXGKDDIPOWERRUNTIMECONTROLREQUEST](nc-d3dkmddi-dxgkddipowerruntimecontrolrequest.md) | Called by the Power Engine Plug-in (PEP) to exchange information with the display miniport driver. Also called by the Microsoft DirectX graphics kernel subsystem to notify the display miniport driver about certain events. |
| [DXGKDDISETPOWERCOMPONENTFSTATE](nc-d3dkmddi-dxgkddisetpowercomponentfstate.md) | Called by the Microsoft DirectX graphics kernel subsystem to transition a power component to an idle state (an F-state). |



## Structures
| Title | Description |
| ---- |:---- |
| [_D3DKM_TRANSPARENTBLTFLAGS](ns-d3dkmddi-_d3dkm_transparentbltflags.md) | The D3DKM_TRANSPARENTBLTFLAGS structure specifies the display adapter's ability to perform a hardware-accelerated bit-block transfer (bitblt) with transparency. |
| [_D3DKMT_PRESENT_DISPLAY_ONLY_FLAGS](ns-d3dkmddi-_d3dkmt_present_display_only_flags.md) | Indicates how a kernel mode display-only driver (KMDOD) is to perform a present operation. |
| [_DXGK_ALLOCATIONINFO](ns-d3dkmddi-_dxgk_allocationinfo.md) | The DXGK_ALLOCATIONINFO structure describes parameters for creating an allocation. |
| [_DXGK_ALLOCATIONINFOFLAGS](ns-d3dkmddi-_dxgk_allocationinfoflags.md) | The DXGK_ALLOCATIONINFOFLAGS structure identifies properties for an allocation. The display miniport driver specifies these flags for the video memory manager. |
| [_DXGK_ALLOCATIONLIST](ns-d3dkmddi-_dxgk_allocationlist.md) | The DXGK_ALLOCATIONLIST structure describes an allocation specification that is used in direct memory access (DMA) buffering. |
| [_DXGK_ALLOCATIONUSAGEHINT](ns-d3dkmddi-_dxgk_allocationusagehint.md) | The DXGK_ALLOCATIONUSAGEHINT structure contains allocation usage and version information that is used as a hint about how to use an allocation. |
| [_DXGK_ALLOCATIONUSAGEINFO1](ns-d3dkmddi-_dxgk_allocationusageinfo1.md) | The DXGK_ALLOCATIONUSAGEINFO1 structure describes how an allocation can be used in DMA buffering. |
| [_DXGK_BUILDPAGINGBUFFER_COPY_RANGE](ns-d3dkmddi-_dxgk_buildpagingbuffer_copy_range.md) | DXGK_BUILDPAGINGBUFFER_COPY_RANGE is used as part of a page table entry copy operation. |
| [_DXGK_BUILDPAGINGBUFFER_COPYPAGETABLEENTRIES](ns-d3dkmddi-_dxgk_buildpagingbuffer_copypagetableentries.md) | DXGK_BUILDPAGINGBUFFER_COPYPAGETABLEENTRIES describes the operation used copy page table entries from one location to another. |
| [_DXGK_BUILDPAGINGBUFFER_FILLVIRTUAL](ns-d3dkmddi-_dxgk_buildpagingbuffer_fillvirtual.md) | DXGK_BUILDPAGINGBUFFER_FILLVIRTUAL is used as part of an operation to fill an allocation with a pattern. |
| [_DXGK_BUILDPAGINGBUFFER_FLUSHTLB](ns-d3dkmddi-_dxgk_buildpagingbuffer_flushtlb.md) | DXGK_BUILDPAGINGBUFFER_FLUSHTLB is used as part of a flush translation look-aside buffer (TLB) operation. |
| [_DXGK_BUILDPAGINGBUFFER_NOTIFYRESIDENCY](ns-d3dkmddi-_dxgk_buildpagingbuffer_notifyresidency.md) | DXGK_BUILDPAGINGBUFFER_NOTIFYRESIDENCY describes a residency allocation change operation. |
| [_DXGK_BUILDPAGINGBUFFER_TRANSFERVIRTUAL](ns-d3dkmddi-_dxgk_buildpagingbuffer_transfervirtual.md) | DXGK_BUILDPAGINGBUFFER_TRANSFERVIRTUAL is used as part of an allocation transfer operation. |
| [_DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION](ns-d3dkmddi-_dxgk_buildpagingbuffer_updatecontextallocation.md) | DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION describes an operation used to update the content of a context or device allocation. |
| [_DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE](ns-d3dkmddi-_dxgk_buildpagingbuffer_updatepagetable.md) | DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE is used as part of a page table update operation. |
| [_DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE](ns-d3dkmddi-_dxgk_check_multiplane_overlay_support_plane.md) | Specifies the support attributes that the hardware provides for multiplane overlays. |
| [_DXGK_COLORIMETRY](ns-d3dkmddi-_dxgk_colorimetry.md) | Describes colorimetry and closely related fields used to describe overrides from the descriptor retrieved from the display device. |
| [_DXGK_COLORTRANSFORMCAPS](ns-d3dkmddi-_dxgk_colortransformcaps.md) | This structure replaces the DXGK_GAMMARAMPCAPS structure in the DXGK_DRIVERCAPS structure to describe both the gamma and color transform capabilities of the display pipelines. |
| [_DXGK_CONNECTION_CHANGE](ns-d3dkmddi-_dxgk_connection_change.md) | Structure to describe the most recently updated status of the link for a target. |
| [_DXGK_CONTEXTINFO](ns-d3dkmddi-_dxgk_contextinfo.md) | The DXGK_CONTEXTINFO structure describes a device context. |
| [_DXGK_CONTEXTINFO_CAPS](ns-d3dkmddi-_dxgk_contextinfo_caps.md) | DXGK_CONTEXTINFO_CAPS is used to describe the capabilities supported by a driver. |
| [_DXGK_CPUHOSTAPERTURE](ns-d3dkmddi-_dxgk_cpuhostaperture.md) | DXGK_CPUHOSTAPERTURE describes a memory segment supporting a CPU host aperture. |
| [_DXGK_CREATEALLOCATIONFLAGS](ns-d3dkmddi-_dxgk_createallocationflags.md) | The DXGK_CREATEALLOCATIONFLAGS structure identifies how to create allocations. |
| [_DXGK_CREATECONTEXTALLOCATIONFLAGS](ns-d3dkmddi-_dxgk_createcontextallocationflags.md) | Specifies the properties of the context to be allocated. |
| [_DXGK_CREATECONTEXTFLAGS](ns-d3dkmddi-_dxgk_createcontextflags.md) | The DXGK_CREATECONTEXTFLAGS structure identifies how to create contexts. |
| [_DXGK_CREATEDEVICEFLAGS](ns-d3dkmddi-_dxgk_createdeviceflags.md) | The DXGK_CREATEDEVICEFLAGS structure identifies how to create devices. |
| [_DXGK_CREATEPROCESSFLAGS](ns-d3dkmddi-_dxgk_createprocessflags.md) | DXGK_CREATEPROCESSFLAGS is used with DXGKARG_CREATEPROCESS and DxgkDdiCreateProcess to create a kernel mode driver object for a Microsoft DirectX graphics kernel process object. |
| [_DXGK_DESCRIBEALLOCATIONFLAGS](ns-d3dkmddi-_dxgk_describeallocationflags.md) | Used in the DXGKARG_DESCRIBEALLOCATION.Flags member to describe whether an existing allocation is being queried for its display mode. |
| [_DXGK_DESTROYALLOCATIONFLAGS](ns-d3dkmddi-_dxgk_destroyallocationflags.md) | The DXGK_DESTROYALLOCATIONFLAGS structure identifies how to release allocations. |
| [_DXGK_DEVICEINFO](ns-d3dkmddi-_dxgk_deviceinfo.md) | The DXGK_DEVICEINFO structure describes parameters that the Microsoft DirectX graphics kernel subsystem requires from the display miniport driver. |
| [_DXGK_DEVICEINFOFLAGS](ns-d3dkmddi-_dxgk_deviceinfoflags.md) | The DXGK_DEVICEINFOFLAGS structure identifies, in bit-field flags, information about a graphics device. |
| [_DXGK_DISCARDCONTENTFLAGS](ns-d3dkmddi-_dxgk_discardcontentflags.md) | The DXGK_DISCARDCONTENTFLAGS structure identifies the type of discard-content operation to set up in a call to the DxgkDdiBuildPagingBuffer function. |
| [_DXGK_DRIVERCAPS](ns-d3dkmddi-_dxgk_drivercaps.md) | The DXGK_DRIVERCAPS structure describes capabilities of a display miniport driver that the driver provides through a call to its DxgkDdiQueryAdapterInfo function. |
| [_DXGK_ENGINESTATUS](ns-d3dkmddi-_dxgk_enginestatus.md) | Indicates the progress of a node within an active physical display adapter (engine) specified by a DXGKARG_QUERYENGINESTATUS structure. |
| [_DXGK_ENUM_PIVOT](ns-d3dkmddi-_dxgk_enum_pivot.md) | The DXGK_ENUM_PIVOT structure identifies either a video present source or a video present target as the enumeration pivot in a call to DxgkDdiEnumVidPnCofuncModality. |
| [_DXGK_FLIPCAPS](ns-d3dkmddi-_dxgk_flipcaps.md) | The DXGK_FLIPCAPS structure identifies flipping capabilities of the display miniport driver that the driver provides through a call to its DxgkDdiQueryAdapterInfo function. |
| [_DXGK_GAMMARAMPCAPS](ns-d3dkmddi-_dxgk_gammarampcaps.md) | The DXGK_GAMMARAMPCAPS structure identifies gamma-ramp capabilities of the display miniport driver that the driver provides through a call to its DxgkDdiQueryAdapterInfo function. |
| [_DXGK_GDIARG_ALPHABLEND](ns-d3dkmddi-_dxgk_gdiarg_alphablend.md) | The DXGK_GDIARG_ALPHABLEND structure describes the characteristics of a GDI hardware-accelerated alpha blend operation. |
| [_DXGK_GDIARG_BITBLT](ns-d3dkmddi-_dxgk_gdiarg_bitblt.md) | The DXGK_GDIARG_BITBLT structure describes the characteristics of a GDI hardware-accelerated bit-block transfer (bitblt) with no stretching. |
| [_DXGK_GDIARG_CLEARTYPEBLEND](ns-d3dkmddi-_dxgk_gdiarg_cleartypeblend.md) | The DXGK_GDIARG_CLEARTYPEBLEND structure describes the characteristics of a GDI hardware-accelerated ClearType and antialiased text pixel blending operation. |
| [_DXGK_GDIARG_COLORFILL](ns-d3dkmddi-_dxgk_gdiarg_colorfill.md) | The DXGK_GDIARG_COLORFILL structure describes the characteristics of a GDI hardware-accelerated color fill operation. |
| [_DXGK_GDIARG_STRETCHBLT](ns-d3dkmddi-_dxgk_gdiarg_stretchblt.md) | The DXGK_GDIARG_STRETCHBLT structure describes the characteristics of a GDI hardware-accelerated stretch bit-block transfer (bitblt) operation. |
| [_DXGK_GDIARG_TRANSPARENTBLT](ns-d3dkmddi-_dxgk_gdiarg_transparentblt.md) | The DXGK_GDIARG_TRANSPARENTBLT structure describes the characteristics of a GDI hardware-accelerated bit-block transfer (bitblt) operation with transparency. |
| [_DXGK_GPUENGINETOPOLOGY](ns-d3dkmddi-_dxgk_gpuenginetopology.md) | The DXGK_GPUENGINETOPOLOGY structure describes the graphics processing unit (GPU)-engine topology that a driver can support. |
| [_DXGK_GPUMMUCAPS](ns-d3dkmddi-_dxgk_gpummucaps.md) | The DXGK_GPUMMUCAPS structure is used by the kernel mode driver to express virtual memory addressing capabilities. |
| [_DXGK_HDR_METADATA](ns-d3dkmddi-_dxgk_hdr_metadata.md) | Contains information about the HDR metadata. |
| [_DXGK_HISTORY_BUFFER](ns-d3dkmddi-_dxgk_history_buffer.md) | Specifies a history buffer that stores time stamps that record GPU activity throughout the execution lifetime of a direct memory access (DMA) buffer. |
| [_DXGK_HISTORY_BUFFER_HEADER](ns-d3dkmddi-_dxgk_history_buffer_header.md) | Specifies how data is stored in a DXGK_HISTORY_BUFFER history buffer. |
| [_DXGK_INHERITED_TIMING_INFO](ns-d3dkmddi-_dxgk_inherited_timing_info.md) | Structure passed to the driver in the pPrivateDriverData argument of DxgkDdiRecommendFunctionalVidPn, which the driver should use to describe the color space and wire format which cannot be described easily in the VidPn the DDI builds. |
| [_DXGK_INTEGRATEDDISPLAYFLAGS](ns-d3dkmddi-_dxgk_integrateddisplayflags.md) | Flags which describe simple properties of an integrated display. |
| [_DXGK_MAPAPERTUREFLAGS](ns-d3dkmddi-_dxgk_mapapertureflags.md) | The DXGK_MAPAPERTUREFLAGS structure identifies the type of map-aperture-segment operation to set up in a call to the DxgkDdiBuildPagingBuffer function. |
| [_DXGK_MEMORYRANGE](ns-d3dkmddi-_dxgk_memoryrange.md) | DXGK_MEMORYRANGE is used with DxgkDdiQueryAdapterInfo and DXGK_QUERYSEGMENTMEMORYSTATE to query bad graphics processing unit (GPU) memory ranges. |
| [_DXGK_MONITOR_INTERFACE](ns-d3dkmddi-_dxgk_monitor_interface.md) | The DXGK_MONITOR_INTERFACE structure contains pointers to functions that belong to the Monitor Interface, which is implemented by the video present network (VidPN) manager. |
| [_DXGK_MONITOR_INTERFACE_V2](ns-d3dkmddi-_dxgk_monitor_interface_v2.md) | The DXGK_MONITOR_INTERFACE_V2 structure, available beginning with Windows 7, contains pointers to functions that belong to the Monitor Interface, which is implemented by the video present network (VidPN) manager. |
| [_DXGK_MONITORDESCRIPTORSET_INTERFACE](ns-d3dkmddi-_dxgk_monitordescriptorset_interface.md) | The DXGK_MONITORDESCRIPTORSET_INTERFACE structure contains pointers to functions that belong to the Monitor Descriptor Set Interface, which is implemented by the video present network (VidPN) manager. |
| [_DXGK_MONITORFREQUENCYRANGESET_INTERFACE](ns-d3dkmddi-_dxgk_monitorfrequencyrangeset_interface.md) | The DXGK_MONITORFREQUENCYRANGESET_INTERFACE structure contains pointers to functions that belong to the Monitor Frequency Range Set interface, which is implemented by the video present network (VidPN) manager. |
| [_DXGK_MONITORLINKINFO](ns-d3dkmddi-_dxgk_monitorlinkinfo.md) | This structure was defined in WDDM 2.1, however the usage hints and capabilities structure definitions were nested within DXGK_MONITORLINKINFO. |
| [_DXGK_MONITORSOURCEMODESET_INTERFACE](ns-d3dkmddi-_dxgk_monitorsourcemodeset_interface.md) | The DXGK_MONITORSOURCEMODESET_INTERFACE structure contains pointers to functions that belong to the Monitor Source Mode Set interface, which is implemented by the video present network (VidPN) manager. |
| [_DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES](ns-d3dkmddi-_dxgk_multiplane_overlay_attributes.md) | Used by the display miniport driver to specify overlay plane attributes. |
| [_DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES2](ns-d3dkmddi-_dxgk_multiplane_overlay_attributes2.md) | DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES2 is used by the display miniport driver to specify overlay plane attributes. |
| [_DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES3](ns-d3dkmddi-_dxgk_multiplane_overlay_attributes3.md) | A structure containing the attributes used for the image in a multiplane overlay. |
| [_DXGK_MULTIPLANE_OVERLAY_BLEND](ns-d3dkmddi-_dxgk_multiplane_overlay_blend.md) | Identifies a blend operation to be performed on an overlay plane. |
| [_DXGK_MULTIPLANE_OVERLAY_FLAGS](ns-d3dkmddi-_dxgk_multiplane_overlay_flags.md) | Identifies a flip operation to be performed on an overlay plane. |
| [_DXGK_MULTIPLANE_OVERLAY_PLANE](ns-d3dkmddi-_dxgk_multiplane_overlay_plane.md) | Specifies an overlay plane to display in a call to the DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay function. |
| [_DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE](ns-d3dkmddi-_dxgk_multiplane_overlay_plane_with_source.md) | DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE describes the multi-plane overlay plane attributes, allocation, and video present network source identification number. |
| [_DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE2](ns-d3dkmddi-_dxgk_multiplane_overlay_plane_with_source2.md) | Used in a call to the DxgkDdiCheckMultiPlaneOverlaySupport3 function to check details on hardware support for multi-plane overlays. |
| [_DXGK_MULTIPLANE_OVERLAY_PLANE2](ns-d3dkmddi-_dxgk_multiplane_overlay_plane2.md) | DXGK_MULTIPLANE_OVERLAY_PLANE2 is used with the DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay2 function to specify an overlay plane to display. |
| [_DXGK_MULTIPLANE_OVERLAY_PLANE3](ns-d3dkmddi-_dxgk_multiplane_overlay_plane3.md) | Specifies an overlay plane to display in a call to the DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay3 function. |
| [_DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION](ns-d3dkmddi-_dxgk_multiplane_overlay_post_composition.md) | Specifies information about any additional transforms that should occur after the planes are composed. |
| [_DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION_FLAGS](ns-d3dkmddi-_dxgk_multiplane_overlay_post_composition_flags.md) | A structure containing the flags describing the transformations applied to an image. |
| [_DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION_WITH_SOURCE](ns-d3dkmddi-_dxgk_multiplane_overlay_post_composition_with_source.md) | Used in a call to the DxgkDdiCheckMultiPlaneOverlaySupport3 function to check details on hardware support for post composition transform support. |
| [_DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO](ns-d3dkmddi-_dxgk_multiplane_overlay_vsync_info.md) | Specifies an overlay plane to display during a VSync interval. |
| [_DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2](ns-d3dkmddi-_dxgk_multiplane_overlay_vsync_info2.md) | Used by new drivers to report per-plane flip completion after a VSYNC. |
| [_DXGK_MULTIPLANE_OVERLAY_YCbCr_FLAGS](ns-d3dkmddi-_dxgk_multiplane_overlay_ycbcr_flags.md) | Identifies YUV range and conversion info that describes a multiplane overlay. |
| [_DXGK_MULTIPLANEOVERLAYCAPS](ns-d3dkmddi-_dxgk_multiplaneoverlaycaps.md) | Multiplane overlay capabilities returned by the DxgkDdiGetMultiPlaneOverlayCaps function. |
| [_DXGK_OPENALLOCATIONFLAGS](ns-d3dkmddi-_dxgk_openallocationflags.md) | The DXGK_OPENALLOCATIONFLAGS structure identifies the operation to perform for allocations. |
| [_DXGK_OPENALLOCATIONINFO](ns-d3dkmddi-_dxgk_openallocationinfo.md) | The DXGK_OPENALLOCATIONINFO structure contains handles to nondevice-specific and device-specific allocations that the DxgkDdiOpenAllocation function associates. |
| [_DXGK_OVERLAYINFO](ns-d3dkmddi-_dxgk_overlayinfo.md) | The DXGK_OVERLAYINFO structure describes parameters that are required to create or modify an overlay. |
| [_DXGK_PAGE_TABLE_LEVEL_DESC](ns-d3dkmddi-_dxgk_page_table_level_desc.md) | The DXGK_PAGE_TABLE_LEVEL_DESC structure describes capabilities that are applied at the page level. |
| [_DXGK_PAGETABLEUPDATEADDRESS](ns-d3dkmddi-_dxgk_pagetableupdateaddress.md) | DXGK_PAGETABLEUPDATEADDRESS contains the address of a page table to update. The member containing the address is defined as part of a DxgkDdiBuildPagingBuffer operation in the DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE structure. |
| [_DXGK_PATCHFLAGS](ns-d3dkmddi-_dxgk_patchflags.md) | The DXGK_PATCHFLAGS structure identifies, in bit-field flags, information about the direct memory access (DMA) buffer that requires patching. |
| [_DXGK_PHYSICALADAPTERCAPS](ns-d3dkmddi-_dxgk_physicaladaptercaps.md) | The DXGK_PHYSICALADAPTERCAPS structure is used to report details of a physical adapter. |
| [_DXGK_PHYSICALADAPTERFLAGS](ns-d3dkmddi-_dxgk_physicaladapterflags.md) | DXGK_PHYSICALADAPTERFLAGS defines a set of flags that used to indicate the type of memory management model that is supported by a device. |
| [_DXGK_PLANE_SPECIFIC_INPUT_FLAGS](ns-d3dkmddi-_dxgk_plane_specific_input_flags.md) | A structure containing the input flags to be used for the driver that apply to a plane. |
| [_DXGK_PLANE_SPECIFIC_OUTPUT_FLAGS](ns-d3dkmddi-_dxgk_plane_specific_output_flags.md) | A structure containing the flags that apply to a plane set by the driver. |
| [_DXGK_POINTERFLAGS](ns-d3dkmddi-_dxgk_pointerflags.md) | The DXGK_POINTERFLAGS structure identifies mouse pointer capabilities of the display miniport driver that the driver provides through a call to its DxgkDdiQueryAdapterInfo function. |
| [_DXGK_POWER_COMPONENT_FLAGS](ns-d3dkmddi-_dxgk_power_component_flags.md) | Describes state transition information about a power component. |
| [_DXGK_POWER_COMPONENT_MAPPING](ns-d3dkmddi-_dxgk_power_component_mapping.md) | Used in the DXGK_POWER_RUNTIME_COMPONENT.ComponentMapping member to define the standard component types of the Microsoft DirectX graphics kernel subsystem (Dxgkrnl.sys) that describe the power component. |
| [_DXGK_POWER_RUNTIME_COMPONENT](ns-d3dkmddi-_dxgk_power_runtime_component.md) | Describes information about a power component&#8212;for example, a graphics processing engine, a display device, or a block of memory. |
| [_DXGK_POWER_RUNTIME_STATE](ns-d3dkmddi-_dxgk_power_runtime_state.md) | Describes the characteristics of an idle state (an F-state). |
| [_DXGK_PREEMPTCOMMANDFLAGS](ns-d3dkmddi-_dxgk_preemptcommandflags.md) | The DXGK_PREEMPTCOMMANDFLAGS structure specifies a union that contains either a structure with a reserved member or a 32-bit value. No bit-field flags are currently defined. |
| [_DXGK_PRESENTATIONCAPS](ns-d3dkmddi-_dxgk_presentationcaps.md) | The DXGK_PRESENTATIONCAPS structure identifies presentation capabilities of a display miniport driver that the driver provides through a call to its DxgkDdiQueryAdapterInfo function. |
| [_DXGK_PRESENTFLAGS](ns-d3dkmddi-_dxgk_presentflags.md) | The DXGK_PRESENTFLAGS structure identifies, in bit-field flags, the type of present operation to perform. |
| [_DXGK_PRESENTMULTIPLANEOVERLAYINFO](ns-d3dkmddi-_dxgk_presentmultiplaneoverlayinfo.md) | Specifies info on a VidPN input and an overlay plane to display. |
| [_DXGK_PRESENTMULTIPLANEOVERLAYLIST](ns-d3dkmddi-_dxgk_presentmultiplaneoverlaylist.md) | Specifies an overlay plane to display in a call to the DxgkDdiPresent function. |
| [_DXGK_QAITARGETIN](ns-d3dkmddi-_dxgk_qaitargetin.md) | Used to integrate a target. |
| [_DXGK_QUERYDISPLAYIDIN](ns-d3dkmddi-_dxgk_querydisplayidin.md) | Used to query a display ID. |
| [_DXGK_QUERYDISPLAYIDOUT](ns-d3dkmddi-_dxgk_querydisplayidout.md) | Used to query a display ID. |
| [_DXGK_QUERYGPUMMUCAPSIN](ns-d3dkmddi-_dxgk_querygpummucapsin.md) | The DXGK_QUERYGPUMMUCAPSIN structure holds the index of the adapter being queried. |
| [_DXGK_QUERYPAGETABLELEVELDESCIN](ns-d3dkmddi-_dxgk_querypagetableleveldescin.md) | The DXGK_QUERYPAGETABLELEVELDESCIN structure is used to request page level descriptors from the Dxgkrnl Interface. |
| [_DXGK_QUERYPHYSICALADAPTERCAPSIN](ns-d3dkmddi-_dxgk_queryphysicaladaptercapsin.md) | The DXGK_QUERYPHYSICALADAPTERCAPSIN structure is used to query the display driver for the capabilities of the physical display adapter. |
| [_DXGK_QUERYSEGMENTIN](ns-d3dkmddi-_dxgk_querysegmentin.md) | The DXGK_QUERYSEGMENTIN structure describes relevant information for a memory-segment query through a call to the display miniport driver's DxgkDdiQueryAdapterInfo function. |
| [_DXGK_QUERYSEGMENTIN4](ns-d3dkmddi-_dxgk_querysegmentin4.md) | The DXGK_QUERYSEGMENTIN4 structure is used to specify the adapter to query. |
| [_DXGK_QUERYSEGMENTMEMORYSTATE](ns-d3dkmddi-_dxgk_querysegmentmemorystate.md) | DXGK_QUERYSEGMENTMEMORYSTATE is used with DxgkDdiQueryAdapterInfo to query invalid graphics processing unit (GPU) memory ranges. |
| [_DXGK_QUERYSEGMENTOUT](ns-d3dkmddi-_dxgk_querysegmentout.md) | The DXGK_QUERYSEGMENTOUT structure describes memory-segment information that the display miniport driver should return from a call to its DxgkDdiQueryAdapterInfo function. |
| [_DXGK_QUERYSEGMENTOUT3](ns-d3dkmddi-_dxgk_querysegmentout3.md) | Describes memory-segment information that a Windows Display Driver Model (WDDM) 1.2 or later display miniport driver should return from a call to its DxgkDdiQueryAdapterInfo function. |
| [_DXGK_QUERYSEGMENTOUT4](ns-d3dkmddi-_dxgk_querysegmentout4.md) | The DXGK_QUERYSEGMENTOUT4 structure contains memory segment information returned from the driver. |
| [_DXGK_RENDERKM_COMMAND](ns-d3dkmddi-_dxgk_renderkm_command.md) | The DXGK_RENDERKM_COMMAND structure is used to construct a command buffer to control GDI hardware-accelerated rendering. |
| [_DXGK_SEGMENTBANKPREFERENCE](ns-d3dkmddi-_dxgk_segmentbankpreference.md) | The DXGK_SEGMENTBANKPREFERENCE structure describes bank preferences for paging in an allocation. |
| [_DXGK_SEGMENTDESCRIPTOR](ns-d3dkmddi-_dxgk_segmentdescriptor.md) | The DXGK_SEGMENTDESCRIPTOR structure contains information about a segment that the driver supports. |
| [_DXGK_SEGMENTDESCRIPTOR3](ns-d3dkmddi-_dxgk_segmentdescriptor3.md) | Contains information about a driver-supported segment that is composed of both BIOS-reserved memory (which is purged during a transition to a low-power state) and driver-reserved memory. |
| [_DXGK_SEGMENTDESCRIPTOR4](ns-d3dkmddi-_dxgk_segmentdescriptor4.md) | The DXGK_SEGMENTDESCRIPTOR4 structure describes a programmable CPU host aperture. |
| [_DXGK_SEGMENTFLAGS](ns-d3dkmddi-_dxgk_segmentflags.md) | The DXGK_SEGMENTFLAGS structure identifies properties for a segment that the driver provides through a call to its DxgkDdiQueryAdapterInfo function. |
| [_DXGK_SET_TIMING_FLAGS](ns-d3dkmddi-_dxgk_set_timing_flags.md) | Structure to hold flags used to modify SetTiming behavior. Currently no flags are defined. |
| [_DXGK_SET_TIMING_PATH_INFO](ns-d3dkmddi-_dxgk_set_timing_path_info.md) | Structure to hold information to modify SetTiming path. |
| [_DXGK_SET_TIMING_RESULTS](ns-d3dkmddi-_dxgk_set_timing_results.md) | Structure to report result flags from the SetTiming call which apply to the complete call rather than individual paths. |
| [_DXGK_SETPOINTERPOSITIONFLAGS](ns-d3dkmddi-_dxgk_setpointerpositionflags.md) | The DXGK_SETPOINTERPOSITIONFLAGS structure identifies, in bit-field flags, information about a mouse pointer. |
| [_DXGK_SETVIDPNSOURCEADDRESS_FLAGS](ns-d3dkmddi-_dxgk_setvidpnsourceaddress_flags.md) | The DXGK_SETVIDPNSOURCEADDRESS_FLAGS structure identifies the specific type of operation to perform in a call to the display miniport driver's DxgkDdiSetVidPnSourceAddress or DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay functions. |
| [_DXGK_SETVIDPNSOURCEADDRESS_INPUT_FLAGS](ns-d3dkmddi-_dxgk_setvidpnsourceaddress_input_flags.md) | A structure containing the set of flags needed to set the VidPN source address. |
| [_DXGK_SETVIDPNSOURCEADDRESS_OUTPUT_FLAGS](ns-d3dkmddi-_dxgk_setvidpnsourceaddress_output_flags.md) | A structure containing the flags used to set the VidPN source address. |
| [_DXGK_STANDARD_COLORIMETRY_FLAGS](ns-d3dkmddi-_dxgk_standard_colorimetry_flags.md) | Flags describing standard colorimetry and related support. |
| [_DXGK_SUBMITCOMMANDFLAGS](ns-d3dkmddi-_dxgk_submitcommandflags.md) | The DXGK_SUBMITCOMMANDFLAGS structure identifies, in bit-field flags, information about a direct memory access (DMA) buffer to submit to the graphics processing unit (GPU). |
| [_DXGK_TRANSFERFLAGS](ns-d3dkmddi-_dxgk_transferflags.md) | The DXGK_TRANSFERFLAGS structure identifies the type of transfer operation to set up in a call to the DxgkDdiBuildPagingBuffer function. |
| [_DXGK_TRANSFERVIRTUALFLAGS](ns-d3dkmddi-_dxgk_transfervirtualflags.md) | DXGK_TRANSFERVIRTUALFLAGS is used as part of an allocation transfer operation. |
| [_DXGK_UPDATEHWCONTEXTSTATE_FLAGS](ns-d3dkmddi-_dxgk_updatehwcontextstate_flags.md) | Used to update the HW context state flags. |
| [_DXGK_UPDATEPAGETABLEFLAGS](ns-d3dkmddi-_dxgk_updatepagetableflags.md) | DXGK_UPDATEPAGETABLEFLAGS is used as part of a page table update operation. |
| [_DXGK_VIDMMCAPS](ns-d3dkmddi-_dxgk_vidmmcaps.md) | The DXGK_VIDMMCAPS structure identifies the video memory management capabilities that a display miniport driver can support. |
| [_DXGK_VIDPN_INTERFACE](ns-d3dkmddi-_dxgk_vidpn_interface.md) | The DXGK_VIDPN_INTERFACE structure contains pointers to functions that belong to the VidPn interface, which is implemented by the video present network (VidPN) manager. |
| [_DXGK_VIDPNSOURCEMODESET_INTERFACE](ns-d3dkmddi-_dxgk_vidpnsourcemodeset_interface.md) | The DXGK_VIDPNSOURCEMODESET_INTERFACE structure contains pointers to functions that belong to the VidPn Source Mode Set interface, which is implemented by the video present network (VidPN) manager. |
| [_DXGK_VIDPNTARGETMODESET_INTERFACE](ns-d3dkmddi-_dxgk_vidpntargetmodeset_interface.md) | The DXGK_VIDPNTARGETMODESET_INTERFACE structure contains pointers to functions that belong to the VidPn Target Mode Set interface, which is implemented by the VidPN manager. |
| [_DXGK_VIDPNTOPOLOGY_INTERFACE](ns-d3dkmddi-_dxgk_vidpntopology_interface.md) | The DXGK_VIDPNTOPOLOGY_INTERFACE structure contains pointers to functions that belong to the VidPn Topology interface, which is implemented by the video present network (VidPN) manager. |
| [_DXGK_VIDSCHCAPS](ns-d3dkmddi-_dxgk_vidschcaps.md) | The DXGK_VIDSCHCAPS structure identifies the graphics processing unit (GPU) scheduling capabilities, in bit-field flags, that a driver can support. |
| [_DXGKARG_ACQUIRESWIZZLINGRANGE](ns-d3dkmddi-_dxgkarg_acquireswizzlingrange.md) | The DXGKARG_ACQUIRESWIZZLINGRANGE structure describes parameters for making an allocation accessible through a CPU aperture. |
| [_DXGKARG_BUILDPAGINGBUFFER](ns-d3dkmddi-_dxgkarg_buildpagingbuffer.md) | The DXGKARG_BUILDPAGINGBUFFER structure describes parameters for building a paging buffer that is used in a memory-transfer operation. |
| [_DXGKARG_CANCELCOMMAND](ns-d3dkmddi-_dxgkarg_cancelcommand.md) | Specifies internal resources that are cleaned up by the DxgkDdiCancelCommand function after a command is removed from the hardware queue. |
| [_DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT](ns-d3dkmddi-_dxgkarg_checkmultiplaneoverlaysupport.md) | Used in a call to the DxgkDdiCheckMultiPlaneOverlaySupport function to check details on hardware support for multiplane overlays. |
| [_DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT2](ns-d3dkmddi-_dxgkarg_checkmultiplaneoverlaysupport2.md) | DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT2 is passed to the DxgkDdiCheckMultiPlaneOverlaySupport2 function to determine whether a specific multi-plane overlay configuration is supported. |
| [_DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT3](ns-d3dkmddi-_dxgkarg_checkmultiplaneoverlaysupport3.md) | Used in a call to the DxgkDdiCheckMultiPlaneOverlaySupport3 function to check details on hardware support for multi-plane overlays. |
| [_DXGKARG_CLOSEALLOCATION](ns-d3dkmddi-_dxgkarg_closeallocation.md) | The DXGKARG_CLOSEALLOCATION structure describes allocations that the display miniport driver should close. |
| [_DXGKARG_COLLECTDBGINFO](ns-d3dkmddi-_dxgkarg_collectdbginfo.md) | The DXGKARG_COLLECTDBGINFO structure describes information for a debug report. |
| [_DXGKARG_COLLECTDBGINFO_EXT](ns-d3dkmddi-_dxgkarg_collectdbginfo_ext.md) | The DXGKARG_COLLECTDBGINFO_EXT structure describes extension information for a debug report. |
| [_DXGKARG_COMMITVIDPN](ns-d3dkmddi-_dxgkarg_commitvidpn.md) | The DXGKARG_COMMITVIDPN structure holds arguments for the DxgkDdiCommitVidPn function. The DxgkDdiCommitVidPn function makes a specified video present network (VidPN) active on a display adapter. |
| [_DXGKARG_COMMITVIDPN_FLAGS](ns-d3dkmddi-_dxgkarg_commitvidpn_flags.md) | The DXGKARG_COMMITVIDPN_FLAGS structure identifies details about a call to the DxgkDdiCommitVidPn function. |
| [_DXGKARG_CONTROLINTERRUPT2](ns-d3dkmddi-_dxgkarg_controlinterrupt2.md) | The DXGKARG_CONTROLINTERRUPT2 structure is used in DxgkDdi_ControlInterrupt2 calls to describe the state of interrupts. |
| [_DXGKARG_CREATEALLOCATION](ns-d3dkmddi-_dxgkarg_createallocation.md) | The DXGKARG_CREATEALLOCATION structure describes how the display miniport driver should create allocations. |
| [_DXGKARG_CREATECONTEXT](ns-d3dkmddi-_dxgkarg_createcontext.md) | The DXGKARG_CREATECONTEXT structure describes parameters to create a device context. |
| [_DXGKARG_CREATEDEVICE](ns-d3dkmddi-_dxgkarg_createdevice.md) | The DXGKARG_CREATEDEVICE structure describes a graphics context device. |
| [_DXGKARG_CREATEOVERLAY](ns-d3dkmddi-_dxgkarg_createoverlay.md) | The DXGKARG_CREATEOVERLAY structure describes parameters to create an overlay. |
| [_DXGKARG_CREATEPERIODICFRAMENOTIFICATION](ns-d3dkmddi-_dxgkarg_createperiodicframenotification.md) | The arguments needed to create a periodic frame notification. |
| [_DXGKARG_CREATEPROCESS](ns-d3dkmddi-_dxgkarg_createprocess.md) | DXGKARG_CREATEPROCESS is used with DxgkDdiCreateProcess to create a kernel mode driver object for a Microsoft DirectX graphics kernel process object. |
| [_DXGKARG_CREATEPROTECTEDSESSION](ns-d3dkmddi-_dxgkarg_createprotectedsession.md) | Used to create a protected session. |
| [_DXGKARG_DESCRIBEALLOCATION](ns-d3dkmddi-_dxgkarg_describeallocation.md) | The DXGKARG_DESCRIBEALLOCATION structure describes an existing allocation. |
| [_DXGKARG_DESTROYALLOCATION](ns-d3dkmddi-_dxgkarg_destroyallocation.md) | The DXGKARG_DESTROYALLOCATION structure describes how the display miniport driver should release allocations. |
| [_DXGKARG_DESTROYPERIODICFRAMENOTIFICATION](ns-d3dkmddi-_dxgkarg_destroyperiodicframenotification.md) | The arguments used to destroy a periodic frame notification. |
| [_DXGKARG_DISPLAYDETECTCONTROL](ns-d3dkmddi-_dxgkarg_displaydetectcontrol.md) | Used to hold the arguments for DXGKDDI_DISPLAYDETECTCONTROL. |
| [_DXGKARG_ENUMVIDPNCOFUNCMODALITY](ns-d3dkmddi-_dxgkarg_enumvidpncofuncmodality.md) | The DXGKARG_ENUMVIDPNCOFUNCMODALITY structure contains arguments for the DxgkDdiEnumVidPnCofuncModality function. |
| [_DXGKARG_ESCAPE](ns-d3dkmddi-_dxgkarg_escape.md) | The DXGKARG_ESCAPE structure describes information that the user-mode display driver shares with the display miniport driver. |
| [_DXGKARG_FLIPOVERLAY](ns-d3dkmddi-_dxgkarg_flipoverlay.md) | The DXGKARG_FLIPOVERLAY structure describes a new allocation to display for the overlay. |
| [_DXGKARG_FORMATHISTORYBUFFER](ns-d3dkmddi-_dxgkarg_formathistorybuffer.md) | Contains info for the display miniport driver to format a history buffer. |
| [_DXGKARG_GETMULTIPLANEOVERLAYCAPS](ns-d3dkmddi-_dxgkarg_getmultiplaneoverlaycaps.md) | Arguments to the DxgkDdiGetMultiPlaneOverlayCaps function. |
| [_DXGKARG_GETPOSTCOMPOSITIONCAPS](ns-d3dkmddi-_dxgkarg_getpostcompositioncaps.md) | Arguments for the DxgkDdiGetPostCompositionCaps function. |
| [_DXGKARG_GETROOTPAGETABLESIZE](ns-d3dkmddi-_dxgkarg_getrootpagetablesize.md) | DXGKARG_GETROOTPAGETABLESIZE is used with DxgkDdiGetRootPageTableSize. |
| [_DXGKARG_GETSCANLINE](ns-d3dkmddi-_dxgkarg_getscanline.md) | The DXGKARG_GETSCANLINE structure contains information about a video present target's vertical blanking status. |
| [_DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA](ns-d3dkmddi-_dxgkarg_getstandardallocationdriverdata.md) | The DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA structure describes a standard allocation type. |
| [_DXGKARG_HISTORYBUFFERPRECISION](ns-d3dkmddi-_dxgkarg_historybufferprecision.md) | Indicates info about the precision of history buffer data used by the display miniport driver. |
| [_DXGKARG_ISSUPPORTEDVIDPN](ns-d3dkmddi-_dxgkarg_issupportedvidpn.md) | The DXGKARG_ISSUPPORTEDVIDPN structure contains arguments for the DxgkDdiIsSupportedVidPn function. The DxgkDdiIsSupportedVidPn function determines whether a specified video present network (VidPN) is supported on a display adapter. |
| [_DXGKARG_MAPCPUHOSTAPERTURE](ns-d3dkmddi-_dxgkarg_mapcpuhostaperture.md) | The DXGKARG_MAPCPUHOSTAPERTURE structure is used to map an allocation, resident in a local memory segment, into the CPU host aperture in order to make it visible to the CPU. |
| [_DXGKARG_OPENALLOCATION](ns-d3dkmddi-_dxgkarg_openallocation.md) | The DXGKARG_OPENALLOCATION structure describes allocations that the display miniport driver should open. |
| [_DXGKARG_PATCH](ns-d3dkmddi-_dxgkarg_patch.md) | The DXGKARG_PATCH structure describes a direct memory access (DMA) buffer that requires patching (that is, requires the assignment of physical addresses). |
| [_DXGKARG_POSTMULTIPLANEOVERLAYPRESENT](ns-d3dkmddi-_dxgkarg_postmultiplaneoverlaypresent.md) | Contains arguments for the DxgkDdiPostMultiPlaneOverlayPresent function. |
| [_DXGKARG_PREEMPTCOMMAND](ns-d3dkmddi-_dxgkarg_preemptcommand.md) | The DXGKARG_PREEMPTCOMMAND structure describes a command that a display miniport driver must use to preempt a direct memory access (DMA) buffer that the DxgkDdiSubmitCommand function previously submitted to the hardware command execution unit. |
| [_DXGKARG_PRESENT](ns-d3dkmddi-_dxgkarg_present.md) | The DXGKARG_PRESENT structure describes a source-to-primary copy operation. |
| [_DXGKARG_PRESENT_DISPLAYONLY](ns-d3dkmddi-_dxgkarg_present_displayonly.md) | Indicates how a kernel mode display-only driver (KMDOD) is to perform a present operation. |
| [_DXGKARG_QUERYADAPTERINFO](ns-d3dkmddi-_dxgkarg_queryadapterinfo.md) | The DXGKARG_QUERYADAPTERINFO structure contains parameters for a query. |
| [_DXGKARG_QUERYCONNECTIONCHANGE](ns-d3dkmddi-_dxgkarg_queryconnectionchange.md) | Used to hold the arguments for DXGKDDI_QUERYCONNECTIONCHANGE. |
| [_DXGKARG_QUERYCURRENTFENCE](ns-d3dkmddi-_dxgkarg_querycurrentfence.md) | The DXGKARG_QUERYCURRENTFENCE structure describes the latest completed submission fence. |
| [_DXGKARG_QUERYDEPENDENTENGINEGROUP](ns-d3dkmddi-_dxgkarg_querydependentenginegroup.md) | Describes all nodes on the physical display adapter (engine) that are to be queried when the display port driver's GPU scheduler calls the DxgkDdiQueryDependentEngineGroup function to query node dependencies. |
| [_DXGKARG_QUERYENGINESTATUS](ns-d3dkmddi-_dxgkarg_queryenginestatus.md) | Used in a call to the DxgkDdiQueryEngineStatus function to specify a node within an active physical adapter (engine) that is to be queried for its progress. |
| [_DXGKARG_QUERYVIDPNHWCAPABILITY](ns-d3dkmddi-_dxgkarg_queryvidpnhwcapability.md) | The DXGKARG_QUERYVIDPNHWCAPABILITY structure is used by the display miniport driver to describe the hardware capabilities of a functional VidPN in response to a call to the DxgkDdiQueryVidPnHWCapability function. |
| [_DXGKARG_RECOMMENDFUNCTIONALVIDPN](ns-d3dkmddi-_dxgkarg_recommendfunctionalvidpn.md) | The DXGKARG_RECOMMENDFUNCTIONALVIDPN structure contains arguments for the DxgkDdiRecommendFunctionalVidPn function. |
| [_DXGKARG_RECOMMENDMONITORMODES](ns-d3dkmddi-_dxgkarg_recommendmonitormodes.md) | The DXGKARG_RECOMMENDMONITORMODES structure contains arguments for the DxgkDdiRecommendMonitorModes function. |
| [_DXGKARG_RECOMMENDVIDPNTOPOLOGY](ns-d3dkmddi-_dxgkarg_recommendvidpntopology.md) | The DXGKARG_RECOMMENDVIDPNTOPOLOGY structure contains arguments for the display miniport driver's DxgkDdiRecommendVidPnTopology function. |
| [_DXGKARG_RELEASESWIZZLINGRANGE](ns-d3dkmddi-_dxgkarg_releaseswizzlingrange.md) | The DXGKARG_RELEASESWIZZLINGRANGE structure describes parameters for releasing a swizzling range. |
| [_DXGKARG_RENDER](ns-d3dkmddi-_dxgkarg_render.md) | The DXGKARG_RENDER structure describes members for generating a direct memory access (DMA) buffer from a command buffer. |
| [_DXGKARG_RENDERGDI](ns-d3dkmddi-_dxgkarg_rendergdi.md) | The DXGKARG_RENDERGDI structure is used when submitting Windows Graphics Device Interface (GDI) commands for contexts that support virtual addressing. |
| [_DXGKARG_RESETENGINE](ns-d3dkmddi-_dxgkarg_resetengine.md) | Specifies a node within the physical display adapter that can be reset when the display port driver's GPU scheduler calls the DxgkDdiResetEngine function to request a reset operation. |
| [_DXGKARG_SETDISPLAYPRIVATEDRIVERFORMAT](ns-d3dkmddi-_dxgkarg_setdisplayprivatedriverformat.md) | The DXGKARG_SETDISPLAYPRIVATEDRIVERFORMAT structure describes how to set the private-format attribute for a video present source. |
| [_DXGKARG_SETPOINTERPOSITION](ns-d3dkmddi-_dxgkarg_setpointerposition.md) | The DXGKARG_SETPOINTERPOSITION structure describes where and how to display the mouse pointer. |
| [_DXGKARG_SETPOINTERSHAPE](ns-d3dkmddi-_dxgkarg_setpointershape.md) | The DXGKARG_SETPOINTERSHAPE structure describes the appearance of the mouse pointer and the location that it should be displayed in. |
| [_DXGKARG_SETROOTPAGETABLE](ns-d3dkmddi-_dxgkarg_setrootpagetable.md) | DXGKARG_SETROOTPAGETABLE is used by the DxgkDdiSetRootPageTabledevice driver interface (DDI) to notify a context when its associated root page table is resized or moved in memory. |
| [_DXGKARG_SETTARGETANALOGCOPYPROTECTION](ns-d3dkmddi-_dxgkarg_settargetanalogcopyprotection.md) | Holds information to set analog copy protection on a display adapter's video present target. |
| [_DXGKARG_SETTARGETCONTENTTYPE](ns-d3dkmddi-_dxgkarg_settargetcontenttype.md) | Used to hold the arguments for DXGKDDI_SETTARGETCONTENTTYPE. |
| [_DXGKARG_SETTARGETGAMMA](ns-d3dkmddi-_dxgkarg_settargetgamma.md) | Used to hold the arguments for DXGKDDI_SETTARGETGAMMA. |
| [_DXGKARG_SETTIMINGSFROMVIDPN](ns-d3dkmddi-_dxgkarg_settimingsfromvidpn.md) | Used to hold the arguments for DXGKDDI_SETTIMINGSFROMVIDPN. |
| [_DXGKARG_SETVIDPNSOURCEADDRESS](ns-d3dkmddi-_dxgkarg_setvidpnsourceaddress.md) | The DXGKARG_SETVIDPNSOURCEADDRESS structure contains arguments for the DxgkDdiSetVidPnSourceAddress function. |
| [_DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY](ns-d3dkmddi-_dxgkarg_setvidpnsourceaddresswithmultiplaneoverlay.md) | Contains arguments for the DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay function. |
| [_DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2](ns-d3dkmddi-_dxgkarg_setvidpnsourceaddresswithmultiplaneoverlay2.md) | DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2 is passed to the DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay2 function to change the overlay configuration being displayed.DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2 is passed to the DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay2 function to change the overlay configuration being displayed. |
| [_DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3](ns-d3dkmddi-_dxgkarg_setvidpnsourceaddresswithmultiplaneoverlay3.md) | Contains arguments for the DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay3 function. |
| [_DXGKARG_SETVIDPNSOURCEVISIBILITY](ns-d3dkmddi-_dxgkarg_setvidpnsourcevisibility.md) | The DXGKARG_SETVIDPNSOURCEVISIBILITY structure contains arguments for the DxgkDdiSetVidPnSourceVisibility function. |
| [_DXGKARG_STOPCAPTURE](ns-d3dkmddi-_dxgkarg_stopcapture.md) | The DXGKARG_STOPCAPTURE structure contains the handle to the allocation that is used for a capture buffer. |
| [_DXGKARG_SUBMITCOMMAND](ns-d3dkmddi-_dxgkarg_submitcommand.md) | The DXGKARG_SUBMITCOMMAND structure describes the direct memory access (DMA) buffer that a display miniport driver submits to the hardware command execution unit. |
| [_DXGKARG_SUBMITCOMMANDVIRTUAL](ns-d3dkmddi-_dxgkarg_submitcommandvirtual.md) | DXGKARG_SUBMITCOMMANDVIRTUAL is used to submit a direct memory access (DMA) buffer to a context that supports virtual addressing with the DxgkDdiSubmitCommandVirtualdevice driver interface (DDI). |
| [_DXGKARG_UNMAPCPUHOSTAPERTURE](ns-d3dkmddi-_dxgkarg_unmapcpuhostaperture.md) | The DXGKARG_UNMAPCPUHOSTAPERTURE structure is used to unmap a previously mapped range of the CPU host aperture. |
| [_DXGKARG_UPDATEACTIVEVIDPNPRESENTPATH](ns-d3dkmddi-_dxgkarg_updateactivevidpnpresentpath.md) | The DXGKARG_UPDATEACTIVEVIDPNPRESENTPATH structure contains a D3DKMDT_VIDPN_PRESENT_PATH structure, which contains arguments for the DxgkDdiUpdateActiveVidPnPresentPath function. |
| [_DXGKARG_UPDATEHWCONTEXTSTATE](ns-d3dkmddi-_dxgkarg_updatehwcontextstate.md) | Used to update the context state. |
| [_DXGKARG_UPDATEOVERLAY](ns-d3dkmddi-_dxgkarg_updateoverlay.md) | The DXGKARG_UPDATEOVERLAY structure describes parameters for modifying an overlay. |
| [_DXGKARG_VALIDATEUPDATEALLOCPROPERTY](ns-d3dkmddi-_dxgkarg_validateupdateallocproperty.md) | The DXGARG_VALIDATEUPDATEALLOCPROPERTY structure holds the information needed to validate the parameters to update the properties of an allocation. |
| [_DXGKARGCB_CREATECONTEXTALLOCATION](ns-d3dkmddi-_dxgkargcb_createcontextallocation.md) | Specifies the allocation attributes of a GPU context or device-specific context. |
| [_DXGKARGCB_ENUMHANDLECHILDREN](ns-d3dkmddi-_dxgkargcb_enumhandlechildren.md) | The DXGKARGCB_ENUMHANDLECHILDREN structure describes a parent resource and the index of one of its child allocations. |
| [_DXGKARGCB_GETCAPTUREADDRESS](ns-d3dkmddi-_dxgkargcb_getcaptureaddress.md) | The DXGKARGCB_GETCAPTUREADDRESS structure describes parameters for retrieving information about a capture buffer that is associated with an allocation. |
| [_DXGKARGCB_GETHANDLEDATA](ns-d3dkmddi-_dxgkargcb_gethandledata.md) | The DXGKARGCB_GETHANDLEDATA structure describes a handle to private data. |
| [_DXGKARGCB_MAPCONTEXTALLOCATION](ns-d3dkmddi-_dxgkargcb_mapcontextallocation.md) | DXGKARGCB_MAPCONTEXTALLOCATION is used with DxgkCbMapContextAllocation to map a graphics processing unit (GPU) virtual address to the specified context allocation. |
| [_DXGKARGCB_NOTIFY_INTERRUPT_DATA](ns-d3dkmddi-_dxgkargcb_notify_interrupt_data.md) | The DXGKARGCB_NOTIFY_INTERRUPT_DATA structure describes notification information. |
| [_DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS](ns-d3dkmddi-_dxgkargcb_present_displayonly_progress.md) | Provides the progress of a kernel mode display-only driver's (KMDOD) present operation that was requested by the operating system. |
| [_DXGKARGCB_PROTECTEDSESSIONSTATUS](ns-d3dkmddi-_dxgkargcb_protectedsessionstatus.md) | Used for information on the status of the protected session. |
| [_DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE](ns-d3dkmddi-_dxgkargcb_reservegpuvirtualaddressrange.md) | DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE is used with the DxgkCbReserveGpuVirtualAddressRangedevice driver interface (DDI) to allow the kernel mode driver to reserve a graphics processing unit (GPU) virtual address range during creation of a process. |
| [_DXGKARGCB_UPDATECONTEXTALLOCATION](ns-d3dkmddi-_dxgkargcb_updatecontextallocation.md) | DXGKARGCB_UPDATECONTEXTALLOCATION contains the data used to call DxgkCbUpdateContextAllocation. |
| [_DXGKCB_GETHANDLEDATAFLAGS](ns-d3dkmddi-_dxgkcb_gethandledataflags.md) | The DXGKCB_GETHANDLEDATAFLAGS structure indicates if allocations belong to a resource. |
| [_DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS](ns-d3dkmddi-_dxgkcb_notify_interrupt_data_flags.md) | The DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS structure indicates whether the display miniport driver provides a physical adapter mask in a call to the DxgkCbNotifyInterrupt function. |
| [_DXGKCB_NOTIFY_MPO_VSYNC_FLAGS](ns-d3dkmddi-_dxgkcb_notify_mpo_vsync_flags.md) | A structure containing the flags set by the driver to process a flip entry. |
| [DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_RETURN_INFO](ns-d3dkmddi-dxgk_check_multiplane_overlay_support_return_info.md) | Specifies limitations on hardware support of multiplane overlays. |


## Enumerations
| Title | Description |
| ---- |:---- |
| [_DXGK_ACTIVE_VIDPN_INVALIDATION_REASON](ne-d3dkmddi-_dxgk_active_vidpn_invalidation_reason.md) | The DXGK_ACTIVE_VIDPN_INVALIDATION_REASON enumeration is used to indicate the reason why an active VidPN is invalidated and a new VidPN is requested. |
| [_DXGK_BUILDPAGINGBUFFER_OPERATION](ne-d3dkmddi-_dxgk_buildpagingbuffer_operation.md) | Indicates the type of memory operation to perform. |
| [_DXGK_CONNECTION_STATUS](ne-d3dkmddi-_dxgk_connection_status.md) | Enumeration indicating the connection status values which can be reported. |
| [_DXGK_CRTC_VSYNC_STATE](ne-d3dkmddi-_dxgk_crtc_vsync_state.md) | Provides additional information for DxgkDdi_ControlInterrupt2 when VSYNC is being utilized. |
| [_DXGK_DISPLAYDETECTCONTROLTYPE](ne-d3dkmddi-_dxgk_displaydetectcontroltype.md) | Enumeration indicating the type of display detection action. |
| [_DXGK_DISPLAYPANELORIENTATION](ne-d3dkmddi-_dxgk_displaypanelorientation.md) | Enum used to express the orientation of an integrated panel. |
| [_DXGK_GDIROP_BITBLT](ne-d3dkmddi-_dxgk_gdirop_bitblt.md) | The DXGK_GDIROP_COLORFILL enumeration indicates the type of GDI raster operation (ROP) to implement in a GDI hardware-accelerated bit-block transfer (bitblt) operation. |
| [_DXGK_GDIROP_COLORFILL](ne-d3dkmddi-_dxgk_gdirop_colorfill.md) | The DXGK_GDIROP_COLORFILL enumeration indicates the type of GDI raster operation (ROP) to implement in a GDI hardware-accelerated color fill operation. |
| [_DXGK_GLITCH_CAUSE](ne-d3dkmddi-_dxgk_glitch_cause.md) | Enumeration that describes what caused a glitch during a SetTimingsFromVidPn call. |
| [_DXGK_GLITCH_DURATION](ne-d3dkmddi-_dxgk_glitch_duration.md) | Enumeration that describes the duration of a user visible effect of a glitch during a SetTimingsFromVidPn call. |
| [_DXGK_GLITCH_EFFECT](ne-d3dkmddi-_dxgk_glitch_effect.md) | Enumeration which describes the user visible effect of a glitch during a SetTimingsFromVidPn call. |
| [_DXGK_HARDWARE_CONTENT_PROTECTION_TEARDOWN_FLAGS](ne-d3dkmddi-_dxgk_hardware_content_protection_teardown_flags.md) | DXGK_HARDWARE_CONTENT_PROTECTION_TEARDOWN_FLAGS provides additional information to the driver in a DxgkCbHardwareContentProtectionTeardown call. |
| [_DXGK_INTERRUPT_STATE](ne-d3dkmddi-_dxgk_interrupt_state.md) | "." |
| [_DXGK_INTERRUPT_TYPE](ne-d3dkmddi-_dxgk_interrupt_type.md) | The DXGK_INTERRUPT_TYPE enumeration indicates the type of interrupt that the display miniport driver notifies the graphics processing unit (GPU) scheduler about. |
| [_DXGK_MEMORY_TRANSFER_DIRECTION](ne-d3dkmddi-_dxgk_memory_transfer_direction.md) | DXGK_MEMORY_TRANSFER_DIRECTION is used as part of an allocation transfer operation to specify the direction of the transfer. |
| [_DXGK_MONITOR_INTERFACE_VERSION](ne-d3dkmddi-_dxgk_monitor_interface_version.md) | Indicates a particular version of the Monitor interface. |
| [_DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE](ne-d3dkmddi-_dxgk_multiplane_overlay_stereo_flip_mode.md) | Identifies the overlay plane's stereo flip mode. Only the DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_NONE value is supported. |
| [_DXGK_MULTIPLANE_OVERLAY_STEREO_FORMAT](ne-d3dkmddi-_dxgk_multiplane_overlay_stereo_format.md) | Identifies the overlay plane's stereo presentation format. Only the DXGK_MULTIPLANE_OVERLAY_STEREO_FORMAT_MONO value is supported. |
| [_DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY](ne-d3dkmddi-_dxgk_multiplane_overlay_stretch_quality.md) | Identifies filtering processes that the hardware should perform when it stretches or shrinks multiplane overlay data. |
| [_DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT](ne-d3dkmddi-_dxgk_multiplane_overlay_video_frame_format.md) | Identifies the overlay plane's video frame format. Only the DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_PROGRESSIVE value is supported. |
| [_DXGK_PAGETABLEUPDATEMODE](ne-d3dkmddi-_dxgk_pagetableupdatemode.md) | DXGK_PAGETABLEUPDATEMODE is used as part of a DxgkDdiBuildPagingBuffer operation to indicate which member of the related DXGK_PAGETABLEUPDATEADDRESS structure contains the address of the page table to update. |
| [_DXGK_PATH_UPDATE](ne-d3dkmddi-_dxgk_path_update.md) | Enum which indicates how this path has been modified since the previous successful call to SetTimingsFromVidPn. |
| [_DXGK_POWER_COMPONENT_TYPE](ne-d3dkmddi-_dxgk_power_component_type.md) | Indicates the power component type that is reported by the display miniport driver to the Microsoft DirectX graphics kernel subsystem. |
| [_DXGK_PRESENT_DISPLAY_ONLY_PROGRESS_ID](ne-d3dkmddi-_dxgk_present_display_only_progress_id.md) | Indicates the status of the current present operation. |
| [_DXGK_PROTECTED_SESSION_STATUS](ne-d3dkmddi-_dxgk_protected_session_status.md) | Used to indicate the status of the current session. |
| [_DXGK_QUERYADAPTERINFOTYPE](ne-d3dkmddi-_dxgk_queryadapterinfotype.md) | The DXGK_QUERYADAPTERINFOTYPE enumeration indicates the type of information to retrieve. |
| [_DXGK_RECOMMENDFUNCTIONALVIDPN_REASON](ne-d3dkmddi-_dxgk_recommendfunctionalvidpn_reason.md) | The DXGK_RECOMMENDFUNCTIONALVIDPN_REASON enumeration indicates the reason for calling the display miniport driver's DxgkDdiRecommendFunctionalVidPn function. |
| [_DXGK_RECOMMENDVIDPNTOPOLOGY_REASON](ne-d3dkmddi-_dxgk_recommendvidpntopology_reason.md) | Indicates the reason for calling the display miniport driver's DxgkDdiRecommendVidPnTopology function. |
| [_DXGK_RENDERKM_OPERATION](ne-d3dkmddi-_dxgk_renderkm_operation.md) | The DXGK_RENDERKM_OPERATION enumeration indicates the type of GDI hardware-accelerated rendering operation to perform when the DxgkDdiRenderKm function is called. |
| [_DXGK_VIDPN_INTERFACE_VERSION](ne-d3dkmddi-_dxgk_vidpn_interface_version.md) | The DXGK_VIDPN_INTERFACE_VERSION enumeration indicates the version of a video present network (VidPN) interface. |
| [_DXGK_WDDMVERSION](ne-d3dkmddi-_dxgk_wddmversion.md) | The DXGK_WDDMVERSION enumeration is reserved for system use. Except for the case noted below, do not use it in your driver. |