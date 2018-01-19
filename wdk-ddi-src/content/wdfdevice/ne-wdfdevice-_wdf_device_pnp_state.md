---
UID : NE:wdfdevice._WDF_DEVICE_PNP_STATE
title : _WDF_DEVICE_PNP_STATE
author : windows-driver-content
description : The WDF_DEVICE_PNP_STATE enumeration identifies all of the states that the framework's Plug and Play state machine can enter.
old-location : wdf\wdf_device_pnp_state.htm
old-project : wdf
ms.assetid : b907a1ca-d9ef-45e9-9e1b-26e58e3e1e07
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : _WDF_DEVICE_PNP_STATE, *PWDF_DEVICE_PNP_STATE, WDF_DEVICE_PNP_STATE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : wdfdevice.h
req.include-header : Wdf.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 
req.alt-api : WDF_DEVICE_PNP_STATE
req.alt-loc : wdfdevice.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : See Remarks section.
req.typenames : "*PWDF_DEVICE_PNP_STATE, WDF_DEVICE_PNP_STATE"
req.product : Windows 10 or later.
---

# _WDF_DEVICE_PNP_STATE Enumeration
<p class="CCE_Message">[Applies to KMDF only]

The WDF_DEVICE_PNP_STATE enumeration identifies all of the states that the framework's Plug and Play state machine can enter.

## Syntax
````
typedef enum _WDF_DEVICE_PNP_STATE { 
  WdfDevStatePnpInvalid                             = 0x00,
  WdfDevStatePnpObjectCreated                       = 0x100,
  WdfDevStatePnpCheckForDevicePresence              = 0x101,
  WdfDevStatePnpEjectFailed                         = 0x102,
  WdfDevStatePnpEjectHardware                       = 0x103,
  WdfDevStatePnpEjectedWaitingForRemove             = 0x104,
  WdfDevStatePnpInit                                = 0x105,
  WdfDevStatePnpInitStarting                        = 0x106,
  WdfDevStatePnpInitSurpriseRemoved                 = 0x107,
  WdfDevStatePnpHardwareAvailable                   = 0x108,
  WdfDevStatePnpEnableInterfaces                    = 0x109,
  WdfDevStatePnpHardwareAvailablePowerPolicyFailed  = 0x10A,
  WdfDevStatePnpQueryRemoveAskDriver                = 0x10B,
  WdfDevStatePnpQueryRemovePending                  = 0x10C,
  WdfDevStatePnpQueryRemoveStaticCheck              = 0x10D,
  WdfDevStatePnpQueriedRemoving                     = 0x10E,
  WdfDevStatePnpQueryStopAskDriver                  = 0x10F,
  WdfDevStatePnpQueryStopPending                    = 0x110,
  WdfDevStatePnpQueryStopStaticCheck                = 0x111,
  WdfDevStatePnpQueryCanceled                       = 0x112,
  WdfDevStatePnpRemoved                             = 0x113,
  WdfDevStatePnpPdoRemoved                          = 0x114,
  WdfDevStatePnpRemovedPdoWait                      = 0x115,
  WdfDevStatePnpRemovedPdoSurpriseRemoved           = 0x116,
  WdfDevStatePnpRemovingDisableInterfaces           = 0x117,
  WdfDevStatePnpRestarting                          = 0x118,
  WdfDevStatePnpStarted                             = 0x119,
  WdfDevStatePnpStartedCancelStop                   = 0x11A,
  WdfDevStatePnpStartedCancelRemove                 = 0x11B,
  WdfDevStatePnpStartedRemoving                     = 0x11C,
  WdfDevStatePnpStartingFromStopped                 = 0x11D,
  WdfDevStatePnpStopped                             = 0x11E,
  WdfDevStatePnpStoppedWaitForStartCompletion       = 0x11F,
  WdfDevStatePnpStartedStopping                     = 0x120,
  WdfDevStatePnpSurpriseRemove                      = 0x121,
  WdfDevStatePnpInitQueryRemove                     = 0x122,
  WdfDevStatePnpInitQueryRemoveCanceled             = 0x123,
  WdfDevStatePnpFdoRemoved                          = 0x124,
  WdfDevStatePnpRemovedWaitForChildren              = 0x125,
  WdfDevStatePnpQueriedSurpriseRemove               = 0x126,
  WdfDevStatePnpSurpriseRemoveIoStarted             = 0x127,
  WdfDevStatePnpFailedPowerDown                     = 0x128,
  WdfDevStatePnpFailedIoStarting                    = 0x129,
  WdfDevStatePnpFailedOwnHardware                   = 0x12A,
  WdfDevStatePnpFailed                              = 0x12B,
  WdfDevStatePnpFailedSurpriseRemoved               = 0x12C,
  WdfDevStatePnpFailedStarted                       = 0x12D,
  WdfDevStatePnpFailedWaitForRemove                 = 0x12E,
  WdfDevStatePnpFailedInit                          = 0x12F,
  WdfDevStatePnpPdoInitFailed                       = 0x130,
  WdfDevStatePnpRestart                             = 0x131,
  WdfDevStatePnpRestartReleaseHardware              = 0x132,
  WdfDevStatePnpRestartHardwareAvailable            = 0x133,
  WdfDevStatePnpPdoRestart                          = 0x134,
  WdfDevStatePnpFinal                               = 0x135,
  WdfDevStatePnpRemovedChildrenRemoved              = 0x136,
  WdfDevStatePnpQueryRemoveEnsureDeviceAwake        = 0x137,
  WdfDevStatePnpQueryStopEnsureDeviceAwake          = 0x138,
  WdfDevStatePnpFailedPowerPolicyRemoved            = 0x139,
  WdfDevStatePnpNull                                = 0x13A
} WDF_DEVICE_PNP_STATE, *PWDF_DEVICE_PNP_STATE;
````

## Constants

<table>

<tr>
<td>WdfDevStatePnpCheckForDevicePresence</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpEjectedWaitingForRemove</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpEjectFailed</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpEjectHardware</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpEnableInterfaces</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpFailed</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpFailedInit</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpFailedIoStarting</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpFailedOwnHardware</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpFailedPowerDown</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpFailedPowerPolicyRemoved</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpFailedStarted</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpFailedSurpriseRemoved</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpFailedWaitForRemove</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpFdoRemoved</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpFinal</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpHardwareAvailable</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpHardwareAvailablePowerPolicyFailed</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpInit</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpInitQueryRemove</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpInitQueryRemoveCanceled</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpInitStarting</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpInitSurpriseRemoved</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpInvalid</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpNull</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpObjectCreated</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpPdoInitFailed</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpPdoRemoved</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpPdoRestart</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpQueriedRemoving</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpQueriedSurpriseRemove</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpQueryCanceled</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpQueryRemoveAskDriver</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpQueryRemoveEnsureDeviceAwake</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpQueryRemovePending</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpQueryRemoveStaticCheck</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpQueryStopAskDriver</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpQueryStopEnsureDeviceAwake</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpQueryStopPending</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpQueryStopStaticCheck</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpRemoved</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpRemovedChildrenRemoved</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpRemovedPdoSurpriseRemoved</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpRemovedPdoWait</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpRemovedWaitForChildren</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpRemovingDisableInterfaces</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpRestart</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpRestartHardwareAvailable</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpRestarting</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpRestartReleaseHardware</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpStarted</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpStartedCancelRemove</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpStartedCancelStop</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpStartedRemoving</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpStartedStopping</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpStartingFromStopped</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpStopped</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpStoppedWaitForStartCompletion</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpSurpriseRemove</td>
<td></td>
</tr>

<tr>
<td>WdfDevStatePnpSurpriseRemoveIoStarted</td>
<td></td>
</tr>
</table>

## Remarks

The WDF_DEVICE_PNP_STATE enumeration is used as a member type for  the <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_pnp_notification_data.md">WDF_DEVICE_PNP_NOTIFICATION_DATA</a> structure and as the return type for the <a href="..\wdfdevice\nf-wdfdevice-wdfdevicegetdevicepnpstate.md">WdfDeviceGetDevicePnpState</a> method.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** |  |
| **Header** | wdfdevice.h (include Wdf.h) |