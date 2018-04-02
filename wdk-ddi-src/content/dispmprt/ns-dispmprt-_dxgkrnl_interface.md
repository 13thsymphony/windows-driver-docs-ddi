---
UID: NS:dispmprt._DXGKRNL_INTERFACE
title: "_DXGKRNL_INTERFACE"
author: windows-driver-content
description: The DXGKRNL_INTERFACE structure contains a handle to a display adapter and a set of function pointers.
old-location: display\dxgkrnl_interface2.htm
old-project: display
ms.assetid: d97d3ec6-aaa5-4f4a-a39f-42c09473b18e
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PDXGKRNL_INTERFACE, DXGKDDI_INTERFACE_VERSION_VISTA, DXGKDDI_INTERFACE_VERSION_VISTA_SP1, DXGKDDI_INTERFACE_VERSION_VISTA_WIN7, DXGKDDI_INTERFACE_VERSION_WIN8, DXGKRNL_INTERFACE, DXGKRNL_INTERFACE structure [Display Devices], DmStructs_86ab8b5f-f30b-4ad3-ac4d-34fc3a864f27.xml, PDXGKRNL_INTERFACE, PDXGKRNL_INTERFACE structure pointer [Display Devices], _DXGKRNL_INTERFACE, display.dxgkrnl_interface2, dispmprt/DXGKRNL_INTERFACE, dispmprt/PDXGKRNL_INTERFACE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Windows
req.target-min-winverclnt: Available beginning with Windows Vista.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Dispmprt.h
api_name:
-	DXGKRNL_INTERFACE
product:
- Windows
targetos: Windows
req.typenames: DXGKRNL_INTERFACE, *PDXGKRNL_INTERFACE
---

# _DXGKRNL_INTERFACE structure
The <b>DXGKRNL_INTERFACE</b> structure contains a handle to a display adapter and  a set of function pointers. The functions are implemented by the display port driver and called by the display miniport driver. The display port driver provides the display miniport driver with the handle and function pointers by passing a <b>DXGKRNL_INTERFACE</b> structure to <a href="https://msdn.microsoft.com/ffacbb39-2581-4207-841d-28ce57fbc64d">DxgkDdiStartDevice</a>.

## Syntax
```
typedef struct _DXGKRNL_INTERFACE {
  ULONG                                    Size;
  ULONG                                    Version;
  HANDLE                                   DeviceHandle;
  DXGKCB_EVAL_ACPI_METHOD                  DxgkCbEvalAcpiMethod;
  DXGKCB_GET_DEVICE_INFORMATION            DxgkCbGetDeviceInformation;
  DXGKCB_INDICATE_CHILD_STATUS             DxgkCbIndicateChildStatus;
  DXGKCB_MAP_MEMORY                        DxgkCbMapMemory;
  DXGKCB_QUEUE_DPC                         DxgkCbQueueDpc;
  DXGKCB_QUERY_SERVICES                    DxgkCbQueryServices;
  DXGKCB_READ_DEVICE_SPACE                 DxgkCbReadDeviceSpace;
  DXGKCB_SYNCHRONIZE_EXECUTION             DxgkCbSynchronizeExecution;
  DXGKCB_UNMAP_MEMORY                      DxgkCbUnmapMemory;
  DXGKCB_WRITE_DEVICE_SPACE                DxgkCbWriteDeviceSpace;
  DXGKCB_IS_DEVICE_PRESENT                 DxgkCbIsDevicePresent;
  DXGKCB_GETHANDLEDATA                     DxgkCbGetHandleData;
  DXGKCB_GETHANDLEPARENT                   DxgkCbGetHandleParent;
  DXGKCB_ENUMHANDLECHILDREN                DxgkCbEnumHandleChildren;
  DXGKCB_NOTIFY_INTERRUPT                  DxgkCbNotifyInterrupt;
  DXGKCB_NOTIFY_DPC                        DxgkCbNotifyDpc;
  DXGKCB_QUERYVIDPNINTERFACE               DxgkCbQueryVidPnInterface;
  DXGKCB_QUERYMONITORINTERFACE             DxgkCbQueryMonitorInterface;
  DXGKCB_GETCAPTUREADDRESS                 DxgkCbGetCaptureAddress;
  DXGKCB_LOG_ETW_EVENT                     DxgkCbLogEtwEvent;
  DXGKCB_EXCLUDE_ADAPTER_ACCESS            DxgkCbExcludeAdapterAccess;
  DXGKCB_CREATECONTEXTALLOCATION           DxgkCbCreateContextAllocation;
  DXGKCB_DESTROYCONTEXTALLOCATION          DxgkCbDestroyContextAllocation;
  DXGKCB_SETPOWERCOMPONENTACTIVE           DxgkCbSetPowerComponentActive;
  DXGKCB_SETPOWERCOMPONENTIDLE             DxgkCbSetPowerComponentIdle;
  DXGKCB_ACQUIRE_POST_DISPLAY_OWNERSHIP    DxgkCbAcquirePostDisplayOwnership;
  DXGKCB_POWERRUNTIMECONTROLREQUEST        DxgkCbPowerRuntimeControlRequest;
  DXGKCB_SETPOWERCOMPONENTLATENCY          DxgkCbSetPowerComponentLatency;
  DXGKCB_SETPOWERCOMPONENTRESIDENCY        DxgkCbSetPowerComponentResidency;
  DXGKCB_COMPLETEFSTATETRANSITION          DxgkCbCompleteFStateTransition;
  DXGKCB_COMPLETEPSTATETRANSITION          DxgkCbCompletePStateTransition;
  DXGKCB_MAPCONTEXTALLOCATION              DxgkCbMapContextAllocation;
  DXGKCB_UPDATECONTEXTALLOCATION           DxgkCbUpdateContextAllocation;
  DXGKCB_RESERVEGPUVIRTUALADDRESSRANGE     DxgkCbReserveGpuVirtualAddressRange;
  DXGKCB_ACQUIREHANDLEDATA                 DxgkCbAcquireHandleData;
  DXGKCB_RELEASEHANDLEDATA                 DxgkCbReleaseHandleData;
  DXGKCB_HARDWARECONTENTPROTECTIONTEARDOWN DxgkCbHardwareContentProtectionTeardown;
  DXGKCB_MULTIPLANEOVERLAYDISABLED         DxgkCbMultiPlaneOverlayDisabled;
  DXGKCB_DXGKCB_MITIGATEDRANGEUPDATE       DxgkCbMitigatedRangeUpdate;
  DXGKCB_INVALIDATEHWCONTEXT               DxgkCbInvalidateHwContext;
  DXGKCB_INDICATE_CONNECTOR_CHANGE         DxgkCbIndicateConnectorChange;
  DXGKCB_UNBLOCKUEFIFRAMEBUFFERRANGES      DxgkCbUnblockUEFIFrameBufferRanges;
  DXGKCB_ACQUIRE_POST_DISPLAY_OWNERSHIP2   DxgkCbAcquirePostDisplayOwnership2;
  DXGKCB_SETPROTECTEDSESSIONSTATUS         DxgkCbSetProtectedSessionStatus;
} DXGKRNL_INTERFACE, *PDXGKRNL_INTERFACE;
```

## Members


`Size`

An integer that indicates the size, in bytes, of this structure.

`Version`

A positive integer that indicates the version of the functional interface implemented by the display port driver.


The following are the allowed values, which are defined in D3dukmdt.h.



<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="DXGKDDI_INTERFACE_VERSION_VISTA"></a><a id="dxgkddi_interface_version_vista"></a><dl>
<dt><b>DXGKDDI_INTERFACE_VERSION_VISTA</b></dt>
</dl>
</td>
<td width="60%">
Windows Vista

</td>
</tr>
<tr>
<td width="40%"><a id="DXGKDDI_INTERFACE_VERSION_VISTA_SP1"></a><a id="dxgkddi_interface_version_vista_sp1"></a><dl>
<dt><b>DXGKDDI_INTERFACE_VERSION_VISTA_SP1</b></dt>
</dl>
</td>
<td width="60%">
Windows Vista with SP1

</td>
</tr>
<tr>
<td width="40%"><a id="DXGKDDI_INTERFACE_VERSION_VISTA_WIN7"></a><a id="dxgkddi_interface_version_vista_win7"></a><dl>
<dt><b>DXGKDDI_INTERFACE_VERSION_VISTA_WIN7</b></dt>
</dl>
</td>
<td width="60%">
Windows 7

</td>
</tr>
<tr>
<td width="40%"><a id="DXGKDDI_INTERFACE_VERSION_WIN8"></a><a id="dxgkddi_interface_version_win8"></a><dl>
<dt><b>DXGKDDI_INTERFACE_VERSION_WIN8</b></dt>
</dl>
</td>
<td width="60%">
Windows 8

</td>
</tr>
</table>

`DeviceHandle`

A handle, generated by the display port driver, that represents a display adapter. The display miniport driver passes the handle as an argument each time it calls any of the functions in DXGKRNL_INTERFACE.

`DxgkCbEvalAcpiMethod`

A pointer to the display port driver's <a href="https://msdn.microsoft.com/ce54cf4e-5b50-4142-b3c7-ff29b7bdbb35">DxgkCbEvalAcpiMethod</a> function.

`DxgkCbGetDeviceInformation`

A pointer to the display port driver's <a href="https://msdn.microsoft.com/cb627eab-93b9-49c5-bd35-4a57220366e7">DxgkCbGetDeviceInformation</a> function.

`DxgkCbIndicateChildStatus`

A pointer to the display port driver's <a href="https://msdn.microsoft.com/780a8867-bba1-4b1b-a941-b55bfe087b7b">DxgkCbIndicateChildStatus</a> function.

`DxgkCbMapMemory`

A pointer to the display port driver's <a href="https://msdn.microsoft.com/916a4d1d-0c40-4125-89ae-488251b04810">DxgkCbMapMemory</a> function.

`DxgkCbQueueDpc`

A pointer to the display port driver's <a href="https://msdn.microsoft.com/c8c26675-8b87-4818-ad51-4e0a341965d0">DxgkCbQueueDpc</a> function.

`DxgkCbQueryServices`

A pointer to the display port driver's <a href="https://msdn.microsoft.com/0ce5df90-2019-4a92-97d6-0218acc8b1e8">DxgkCbQueryServices</a> function.

`DxgkCbReadDeviceSpace`

A pointer to the display port driver's <a href="https://msdn.microsoft.com/118ea0b9-6463-4050-9f33-192a3d42fdce">DxgkCbReadDeviceSpace</a> function.

`DxgkCbSynchronizeExecution`

A pointer to the display port driver's <a href="https://msdn.microsoft.com/9c659319-d0a5-43a7-b9a9-9fad18397a09">DxgkCbSynchronizeExecution</a> function.

`DxgkCbUnmapMemory`

A pointer to the display port driver's <a href="https://msdn.microsoft.com/71e8eb0e-599b-44cf-955b-828f6667edf6">DxgkCbUnmapMemory</a> function.

`DxgkCbWriteDeviceSpace`

A pointer to the display port driver's <a href="https://msdn.microsoft.com/797d6b0c-91a4-4923-ad40-937cfde50067">DxgkCbWriteDeviceSpace</a> function.

`DxgkCbIsDevicePresent`

A pointer to the display port driver's <a href="https://msdn.microsoft.com/82716a1a-e361-40ad-b3cd-bdcd3abc75f8">DxgkCbIsDevicePresent</a> function.

`DxgkCbGetHandleData`

A pointer to the display port driver's <a href="https://msdn.microsoft.com/144429e5-34e6-4416-980e-2838e8f9e415">DxgkCbGetHandleData</a> function.

`DxgkCbGetHandleParent`

A pointer to the display port driver's <a href="https://msdn.microsoft.com/db8e7a91-d62a-4d2f-ac21-266e365a352c">DxgkCbGetHandleParent</a> function.

`DxgkCbEnumHandleChildren`

A pointer to the display port driver's <a href="https://msdn.microsoft.com/36307e63-9e94-4441-92c6-fd4293ea8fa9">DxgkCbEnumHandleChildren</a> function.

`DxgkCbNotifyInterrupt`

A pointer to the display port driver's <a href="https://msdn.microsoft.com/7968d26d-0195-463d-8954-e7ebef4f9dea">DxgkCbNotifyInterrupt</a> function.

`DxgkCbNotifyDpc`

A pointer to the display port driver's <a href="https://msdn.microsoft.com/3df3f7d4-3721-46f5-b9e3-19bd3d870292">DxgkCbNotifyDpc</a> function.

`DxgkCbQueryVidPnInterface`

A pointer to the display port driver's <a href="https://msdn.microsoft.com/649ce7fc-6852-43f3-b944-b2b64fcba874">DxgkCbQueryVidPnInterface</a> function.

`DxgkCbQueryMonitorInterface`

A pointer to the display port driver's <a href="https://msdn.microsoft.com/0c23e72d-3eb9-4511-a386-1dcc2f4910b7">DxgkCbQueryMonitorInterface</a> function.

`DxgkCbGetCaptureAddress`

A pointer to the display port driver's <a href="https://msdn.microsoft.com/f87a5a5f-20d3-48cb-93f0-114eafe7238b">DxgkCbGetCaptureAddress</a> function.

`DxgkCbLogEtwEvent`

A pointer to the display port driver's <a href="https://msdn.microsoft.com/d869f933-4316-440e-899a-d46d72a0d10f">DxgkCbLogEtwEvent</a> function.

`DxgkCbExcludeAdapterAccess`

A pointer to the display port driver's <a href="https://msdn.microsoft.com/e74e79fe-3b36-427e-ae0b-4072a0438c4e">DxgkCbExcludeAdapterAccess</a> function.

`DxgkCbCreateContextAllocation`

A pointer to the display port driver's <a href="https://msdn.microsoft.com/b6b142a4-20eb-4368-bd7f-8a25f4fe48ca">DxgkCbCreateContextAllocation</a> function.

Supported starting with Windows 8.

`DxgkCbDestroyContextAllocation`

A pointer to the display port driver's <a href="https://msdn.microsoft.com/f613e019-0b6d-43fc-a802-a6cd3803a00d">DxgkCbDestroyContextAllocation</a> function.

Supported starting with Windows 8.

`DxgkCbSetPowerComponentActive`

A pointer to the display port driver's <a href="https://msdn.microsoft.com/12008d80-8bcb-4289-97ea-d3325731a95f">DxgkCbSetPowerComponentActive</a> function.

Supported starting with Windows 8.

`DxgkCbSetPowerComponentIdle`

A pointer to the display port driver's <a href="https://msdn.microsoft.com/7746d09a-7fb6-4e5d-926c-4ded6830b06d">DxgkCbSetPowerComponentIdle</a> function.

Supported starting with Windows 8.

`DxgkCbAcquirePostDisplayOwnership`

A pointer to the display port driver's <a href="https://msdn.microsoft.com/6454adb3-c958-467b-acbc-b8937b98cd57">DxgkCbAcquirePostDisplayOwnership</a> function.

Supported starting with Windows 8.

`DxgkCbPowerRuntimeControlRequest`

A pointer to the display port driver's <a href="https://msdn.microsoft.com/28984c89-a1d9-4720-8c4c-2b2ce34e0899">DxgkCbPowerRuntimeControlRequest</a> function.

Supported starting with Windows 8.

`DxgkCbSetPowerComponentLatency`

A pointer to the display port driver's <a href="https://msdn.microsoft.com/8FF86746-15A2-4BDF-98AF-23B5F9960DB9">DxgkCbSetPowerComponentLatency</a> function.

Supported starting with Windows 8.

`DxgkCbSetPowerComponentResidency`

A pointer to the display port driver's <a href="https://msdn.microsoft.com/9D567380-2E77-4A63-8674-E19A13C7B8BC">DxgkCbSetPowerComponentResidency</a> function.

Supported starting with Windows 8.

`DxgkCbCompleteFStateTransition`

A pointer to the display port driver's <a href="https://msdn.microsoft.com/69a6d9bc-44a9-4204-988e-e11c80f67f28">DxgkCbCompleteFStateTransition</a> function.

Supported starting with Windows 8.

`DxgkCbCompletePStateTransition`

Reserved for system use. Do not use in your driver.

Supported starting with Windows 8.1.

`DxgkCbMapContextAllocation`



`DxgkCbUpdateContextAllocation`



`DxgkCbReserveGpuVirtualAddressRange`



`DxgkCbAcquireHandleData`



`DxgkCbReleaseHandleData`



`DxgkCbHardwareContentProtectionTeardown`



`DxgkCbMultiPlaneOverlayDisabled`



`DxgkCbMitigatedRangeUpdate`



`DxgkCbInvalidateHwContext`



`DxgkCbIndicateConnectorChange`



`DxgkCbUnblockUEFIFrameBufferRanges`



`DxgkCbAcquirePostDisplayOwnership2`



`DxgkCbSetProtectedSessionStatus`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available beginning with Windows Vista. Available beginning with Windows Vista. |
| **Header** | dispmprt.h (include Dispmprt.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556157">DriverEntry of Display Miniport Driver</a>



<a href="https://msdn.microsoft.com/ffacbb39-2581-4207-841d-28ce57fbc64d">DxgkDdiStartDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560940">Dxgkrnl Interface</a>