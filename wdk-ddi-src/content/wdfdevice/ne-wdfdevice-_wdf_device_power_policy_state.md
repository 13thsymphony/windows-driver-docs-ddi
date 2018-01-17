---
UID: NE:wdfdevice._WDF_DEVICE_POWER_POLICY_STATE
title: _WDF_DEVICE_POWER_POLICY_STATE
author: windows-driver-content
description: The WDF_DEVICE_POWER_POLICY_STATE enumeration identifies all of the states that the framework's power policy state machine can enter.
old-location: wdf\wdf_device_power_policy_state.htm
old-project: wdf
ms.assetid: 87fa78f7-417a-4720-9520-0eb90486630a
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _WDF_DEVICE_POWER_POLICY_STATE, *PWDF_DEVICE_POWER_POLICY_STATE, WDF_DEVICE_POWER_POLICY_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WDF_DEVICE_POWER_POLICY_STATE
req.alt-loc: wdfdevice.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.typenames: *PWDF_DEVICE_POWER_POLICY_STATE, WDF_DEVICE_POWER_POLICY_STATE
req.product: Windows 10 or later.
---

# _WDF_DEVICE_POWER_POLICY_STATE enumeration



## -description
<p class="CCE_Message">[Applies to KMDF only]

The WDF_DEVICE_POWER_POLICY_STATE enumeration identifies all of the states that the framework's power policy state machine can enter.



## -syntax

````
typedef enum _WDF_DEVICE_POWER_POLICY_STATE { 
  WdfDevStatePwrPolInvalid                                                     = 0x00,
  WdfDevStatePwrPolObjectCreated                                               = 0x500,
  WdfDevStatePwrPolStarting                                                    = 0x501,
  WdfDevStatePwrPolStartingSucceeded                                           = 0x502,
  WdfDevStatePwrPolStartingFailed                                              = 0x503,
  WdfDevStatePwrPolStartingDecideS0Wake                                        = 0x504,
  WdfDevStatePwrPolStartedIdleCapable                                          = 0x505,
  WdfDevStatePwrPolTimerExpiredNoWake                                          = 0x506,
  WdfDevStatePwrPolTimerExpiredNoWakeCompletePowerDown                         = 0x507,
  WdfDevStatePwrPolWaitingUnarmed                                              = 0x508,
  WdfDevStatePwrPolWaitingUnarmedQueryIdle                                     = 0x509,
  WdfDevStatePwrPolS0NoWakePowerUp                                             = 0x50A,
  WdfDevStatePwrPolS0NoWakeCompletePowerUp                                     = 0x50B,
  WdfDevStatePwrPolSystemSleepFromDeviceWaitingUnarmed                         = 0x50C,
  WdfDevStatePwrPolSystemSleepNeedWake                                         = 0x50D,
  WdfDevStatePwrPolSystemSleepNeedWakeCompletePowerUp                          = 0x50E,
  WdfDevStatePwrPolSystemSleepPowerRequestFailed                               = 0x50F,
  WdfDevStatePwrPolCheckPowerPageable                                          = 0x510,
  WdfDevStatePwrPolSleepingWakeWakeArrived                                     = 0x511,
  WdfDevStatePwrPolSleepingWakeRevertArmWake                                   = 0x512,
  WdfDevStatePwrPolSystemAsleepWakeArmed                                       = 0x513,
  WdfDevStatePwrPolSystemWakeDeviceWakeEnabled                                 = 0x514,
  WdfDevStatePwrPolSystemWakeDeviceWakeEnabledWakeCanceled                     = 0x515,
  WdfDevStatePwrPolSystemWakeDeviceWakeDisarm                                  = 0x516,
  WdfDevStatePwrPolSystemWakeDeviceWakeTriggered                               = 0x517,
  WdfDevStatePwrPolSystemWakeDeviceWakeTriggeredS0                             = 0x518,
  WdfDevStatePwrPolSystemWakeDeviceWokeDisarm                                  = 0x519,
  WdfDevStatePwrPolSleepingWakeWakeArrivedNP                                   = 0x51A | WdfDevStateNP,
  WdfDevStatePwrPolSleepingWakeRevertArmWakeNP                                 = 0x51B | WdfDevStateNP,
  WdfDevStatePwrPolSleepingWakePowerDownFailed                                 = 0x51C,
  WdfDevStatePwrPolSleepingWakePowerDownFailedWakeCanceled                     = 0x51D,
  WdfDevStatePwrPolSystemAsleepWakeArmedNP                                     = 0x51E | WdfDevStateNP,
  WdfDevStatePwrPolSystemWakeDeviceWakeEnabledNP                               = 0x51F | WdfDevStateNP,
  WdfDevStatePwrPolSystemWakeDeviceWakeEnabledWakeCanceledNP                   = 0x520 | WdfDevStateNP,
  WdfDevStatePwrPolSystemWakeDeviceWakeDisarmNP                                = 0x521 | WdfDevStateNP,
  WdfDevStatePwrPolSystemWakeDeviceWakeTriggeredNP                             = 0x522 | WdfDevStateNP,
  WdfDevStatePwrPolSystemWakeDeviceWakeTriggeredS0NP                           = 0x523 | WdfDevStateNP,
  WdfDevStatePwrPolSystemWakeDeviceWokeDisarmNP                                = 0x524 | WdfDevStateNP,
  WdfDevStatePwrPolSystemWakeDeviceWakeCompletePowerUp                         = 0x525,
  WdfDevStatePwrPolSleeping                                                    = 0x526,
  WdfDevStatePwrPolSleepingNoWakePowerDown                                     = 0x527,
  WdfDevStatePwrPolSleepingNoWakeCompletePowerDown                             = 0x528,
  WdfDevStatePwrPolSleepingNoWakeDxRequestFailed                               = 0x529,
  WdfDevStatePwrPolSleepingWakePowerDown                                       = 0x52A,
  WdfDevStatePwrPolSleepingSendWake                                            = 0x52B,
  WdfDevStatePwrPolSystemAsleepNoWake                                          = 0x52C,
  WdfDevStatePwrPolSystemWakeDeviceWakeDisabled                                = 0x52D,
  WdfDevStatePwrPolSystemWakeDeviceToD0                                        = 0x52E,
  WdfDevStatePwrPolSystemWakeDeviceToD0CompletePowerUp                         = 0x52F,
  WdfDevStatePwrPolSystemWakeQueryIdle                                         = 0x530,
  WdfDevStatePwrPolStartedWakeCapable                                          = 0x531,
  WdfDevStatePwrPolTimerExpiredDecideUsbSS                                     = 0x532,
  WdfDevStatePwrPolTimerExpiredWakeCapablePowerDown                            = 0x533,
  WdfDevStatePwrPolTimerExpiredWakeCapableSendWake                             = 0x534,
  WdfDevStatePwrPolTimerExpiredWakeCapableUsbSS                                = 0x535,
  WdfDevStatePwrPolTimerExpiredWakeCapableWakeArrived                          = 0x536,
  WdfDevStatePwrPolTimerExpiredWakeCapableCancelWake                           = 0x537,
  WdfDevStatePwrPolTimerExpiredWakeCapableWakeCanceled                         = 0x538,
  WdfDevStatePwrPolTimerExpiredWakeCapableCleanup                              = 0x539,
  WdfDevStatePwrPolTimerExpiredWakeCapableDxAllocFailed                        = 0x53A,
  WdfDevStatePwrPolTimerExpiredWakeCompletedPowerDown                          = 0x53B,
  WdfDevStatePwrPolTimerExpiredWakeCompletedPowerUp                            = 0x53C,
  WdfDevStatePwrPolWaitingArmedUsbSS                                           = 0x53D,
  WdfDevStatePwrPolWaitingArmed                                                = 0x53E,
  WdfDevStatePwrPolWaitingArmedQueryIdle                                       = 0x53F,
  WdfDevStatePwrPolIoPresentArmed                                              = 0x540,
  WdfDevStatePwrPolIoPresentArmedWakeCanceled                                  = 0x541,
  WdfDevStatePwrPolS0WakeDisarm                                                = 0x542,
  WdfDevStatePwrPolS0WakeCompletePowerUp                                       = 0x543,
  WdfDevStatePwrPolTimerExpiredWakeSucceeded                                   = 0x544,
  WdfDevStatePwrPolTimerExpiredWakeCompletedDisarm                             = 0x545,
  WdfDevStatePwrPolTimerExpiredWakeCapableWakeSucceeded                        = 0x546,
  WdfDevStatePwrPolTimerExpiredWakeCapableWakeFailed                           = 0x547,
  WdfDevStatePwrPolWakeFailedUsbSS                                             = 0x548,
  WdfDevStatePwrPolTimerExpiredWakeCapablePowerDownFailedCancelWake            = 0x549,
  WdfDevStatePwrPolTimerExpiredWakeCapablePowerDownFailedWakeCanceled          = 0x54A,
  WdfDevStatePwrPolTimerExpiredWakeCapablePowerDownFailedUsbSS                 = 0x54B,
  WdfDevStatePwrPolCancelingWakeForSystemSleep                                 = 0x54C,
  WdfDevStatePwrPolCancelingWakeForSystemSleepWakeCanceled                     = 0x54D,
  WdfDevStatePwrPolDisarmingWakeForSystemSleepCompletePowerUp                  = 0x54E,
  WdfDevStatePwrPolPowerUpForSystemSleepFailed                                 = 0x54F,
  WdfDevStatePwrPolWokeFromS0UsbSS                                             = 0x550,
  WdfDevStatePwrPolWokeFromS0                                                  = 0x551,
  WdfDevStatePwrPolWokeFromS0NotifyDriver                                      = 0x552,
  WdfDevStatePwrPolStoppingResetDevice                                         = 0x553,
  WdfDevStatePwrPolStoppingResetDeviceCompletePowerUp                          = 0x554,
  WdfDevStatePwrPolStoppingResetDeviceFailed                                   = 0x555,
  WdfDevStatePwrPolStoppingD0                                                  = 0x556,
  WdfDevStatePwrPolStoppingD0Failed                                            = 0x557,
  WdfDevStatePwrPolStoppingDisarmWake                                          = 0x558,
  WdfDevStatePwrPolStoppingDisarmWakeCancelWake                                = 0x559,
  WdfDevStatePwrPolStoppingDisarmWakeWakeCanceled                              = 0x55A,
  WdfDevStatePwrPolStopping                                                    = 0x55B,
  WdfDevStatePwrPolStoppingFailed                                              = 0x55C,
  WdfDevStatePwrPolStoppingSendStatus                                          = 0x55D,
  WdfDevStatePwrPolStoppingCancelTimer                                         = 0x55E,
  WdfDevStatePwrPolStoppingWaitForIdleTimeout                                  = 0x55F,
  WdfDevStatePwrPolStoppingCancelUsbSS                                         = 0x560,
  WdfDevStatePwrPolStoppingWaitForUsbSSCompletion                              = 0x561,
  WdfDevStatePwrPolStoppingCancelWake                                          = 0x562,
  WdfDevStatePwrPolStopped                                                     = 0x563,
  WdfDevStatePwrPolCancelUsbSS                                                 = 0x564,
  WdfDevStatePwrPolStarted                                                     = 0x565,
  WdfDevStatePwrPolStartedCancelTimer                                          = 0x566,
  WdfDevStatePwrPolStartedWaitForIdleTimeout                                   = 0x567,
  WdfDevStatePwrPolStartedWakeCapableCancelTimerForSleep                       = 0x568,
  WdfDevStatePwrPolStartedWakeCapableWaitForIdleTimeout                        = 0x569,
  WdfDevStatePwrPolStartedWakeCapableSleepingUsbSS                             = 0x56A,
  WdfDevStatePwrPolStartedIdleCapableCancelTimerForSleep                       = 0x56B,
  WdfDevStatePwrPolStartedIdleCapableWaitForIdleTimeout                        = 0x56C,
  WdfDevStatePwrPolDeviceD0PowerRequestFailed                                  = 0x56D,
  WdfDevStatePwrPolDevicePowerRequestFailed                                    = 0x56E,
  WdfDevStatePwrPolGotoDx                                                      = 0x56F,
  WdfDevStatePwrPolGotoDxInDx                                                  = 0x570,
  WdfDevStatePwrPolDx                                                          = 0x571,
  WdfDevStatePwrPolGotoD0                                                      = 0x572,
  WdfDevStatePwrPolGotoD0InD0                                                  = 0x573,
  WdfDevStatePwrPolFinal                                                       = 0x574,
  WdfDevStatePwrPolSleepingPowerDownNotProcessed                               = 0x575,
  WdfDevStatePwrPolTimerExpiredWakeCapablePowerDownNotProcessed                = 0x576,
  WdfDevStatePwrPolTimerExpiredNoWakePowerDownNotProcessed                     = 0x577,
  WdfDevStatePwrPolTimerExpiredNoWakePoweredDownDisableIdleTimer               = 0x578,
  WdfDevStatePwrPolStoppingWaitingForImplicitPowerDown                         = 0x579,
  WdfDevStatePwrPolStoppingPoweringUp                                          = 0x57A,
  WdfDevStatePwrPolStoppingPoweringDown                                        = 0x57B,
  WdfDevStatePwrPolPowerUpForSystemSleepNotSeen                                = 0x57C,
  WdfDevStatePwrPolWaitingArmedStoppingCancelUsbSS                             = 0x57D,
  WdfDevStatePwrPolWaitingArmedWakeFailedCancelUsbSS                           = 0x57E,
  WdfDevStatePwrPolWaitingArmedIoPresentCancelUsbSS                            = 0x57F,
  WdfDevStatePwrPolWaitingArmedWakeSucceededCancelUsbSS                        = 0x580,
  WdfDevStatePwrPolCancelingUsbSSForSystemSleep                                = 0x581,
  WdfDevStatePwrPolStoppingD0CancelUsbSS                                       = 0x582,
  WdfDevStatePwrPolStartingPoweredUp                                           = 0x583,
  WdfDevStatePwrPolIdleCapableDeviceIdle                                       = 0x584,
  WdfDevStatePwrPolDeviceIdleReturnToActive                                    = 0x585,
  WdfDevStatePwrPolDeviceIdleSleeping                                          = 0x586,
  WdfDevStatePwrPolDeviceIdleStopping                                          = 0x587,
  WdfDevStatePwrPolTimerExpiredNoWakeUndoPowerDown                             = 0x588,
  WdfDevStatePwrPolWakeCapableDeviceIdle                                       = 0x589,
  WdfDevStatePwrPolWakeCapableUsbSSCompleted                                   = 0x58A,
  WdfDevStatePwrPolTimerExpiredWakeCapableUndoPowerDown                        = 0x58B,
  WdfDevStatePwrPolTimerExpiredWakeCompletedHardwareStarted                    = 0x58C,
  WdfDevStatePwrPolStoppedRemoving                                             = 0x58D,
  WdfDevStatePwrPolRemoved                                                     = 0x58E,
  WdfDevStatePwrPolRestarting                                                  = 0x58F,
  WdfDevStatePwrPolRestartingFailed                                            = 0x590,
  WdfDevStatePwrPolStartingPoweredUpFailed                                     = 0x591,
  WdfDevStatePwrPolTimerExpiredNoWakeReturnToActive                            = 0x592,
  WdfDevStatePwrPolWaitingArmedWakeInterruptFired                              = 0x593,
  WdfDevStatePwrPolSystemWakeDeviceWakeInterruptFired                          = 0x594,
  WdfDevStatePwrPolSystemWakeDeviceWakeInterruptFiredNP                        = 0x595 | WdfDevStateNP,
  WdfDevStatePwrPolTimerExpiredWakeCapableWakeInterruptArrived                 = 0x596,
  WdfDevStatePwrPolTimerExpiredWakeCapablePowerDownFailedWakeInterruptArrived  = 0x597,
  WdfDevStatePwrPolWaitingArmedWakeInterruptFiredDuringPowerDown               = 0x598,
  WdfDevStatePwrPolNull                                                        = 0x599
} WDF_DEVICE_POWER_POLICY_STATE, *PWDF_DEVICE_POWER_POLICY_STATE;
````


## -enum-fields

### -field WdfDevStatePwrPolInvalid


### -field WdfDevStatePwrPolObjectCreated


### -field WdfDevStatePwrPolStarting


### -field WdfDevStatePwrPolStartingSucceeded


### -field WdfDevStatePwrPolStartingFailed


### -field WdfDevStatePwrPolStartingDecideS0Wake


### -field WdfDevStatePwrPolStartedIdleCapable


### -field WdfDevStatePwrPolTimerExpiredNoWake


### -field WdfDevStatePwrPolTimerExpiredNoWakeCompletePowerDown


### -field WdfDevStatePwrPolWaitingUnarmed


### -field WdfDevStatePwrPolWaitingUnarmedQueryIdle


### -field WdfDevStatePwrPolS0NoWakePowerUp


### -field WdfDevStatePwrPolS0NoWakeCompletePowerUp


### -field WdfDevStatePwrPolSystemSleepFromDeviceWaitingUnarmed


### -field WdfDevStatePwrPolSystemSleepNeedWake


### -field WdfDevStatePwrPolSystemSleepNeedWakeCompletePowerUp


### -field WdfDevStatePwrPolSystemSleepPowerRequestFailed


### -field WdfDevStatePwrPolCheckPowerPageable


### -field WdfDevStatePwrPolSleepingWakeWakeArrived


### -field WdfDevStatePwrPolSleepingWakeRevertArmWake


### -field WdfDevStatePwrPolSystemAsleepWakeArmed


### -field WdfDevStatePwrPolSystemWakeDeviceWakeEnabled


### -field WdfDevStatePwrPolSystemWakeDeviceWakeEnabledWakeCanceled


### -field WdfDevStatePwrPolSystemWakeDeviceWakeDisarm


### -field WdfDevStatePwrPolSystemWakeDeviceWakeTriggered


### -field WdfDevStatePwrPolSystemWakeDeviceWakeTriggeredS0


### -field WdfDevStatePwrPolSystemWakeDeviceWokeDisarm


### -field WdfDevStatePwrPolSleepingWakeWakeArrivedNP


### -field WdfDevStatePwrPolSleepingWakeRevertArmWakeNP


### -field WdfDevStatePwrPolSleepingWakePowerDownFailed


### -field WdfDevStatePwrPolSleepingWakePowerDownFailedWakeCanceled


### -field WdfDevStatePwrPolSystemAsleepWakeArmedNP


### -field WdfDevStatePwrPolSystemWakeDeviceWakeEnabledNP


### -field WdfDevStatePwrPolSystemWakeDeviceWakeEnabledWakeCanceledNP


### -field WdfDevStatePwrPolSystemWakeDeviceWakeDisarmNP


### -field WdfDevStatePwrPolSystemWakeDeviceWakeTriggeredNP


### -field WdfDevStatePwrPolSystemWakeDeviceWakeTriggeredS0NP


### -field WdfDevStatePwrPolSystemWakeDeviceWokeDisarmNP


### -field WdfDevStatePwrPolSystemWakeDeviceWakeCompletePowerUp


### -field WdfDevStatePwrPolSleeping


### -field WdfDevStatePwrPolSleepingNoWakePowerDown


### -field WdfDevStatePwrPolSleepingNoWakeCompletePowerDown


### -field WdfDevStatePwrPolSleepingNoWakeDxRequestFailed


### -field WdfDevStatePwrPolSleepingWakePowerDown


### -field WdfDevStatePwrPolSleepingSendWake


### -field WdfDevStatePwrPolSystemAsleepNoWake


### -field WdfDevStatePwrPolSystemWakeDeviceWakeDisabled


### -field WdfDevStatePwrPolSystemWakeDeviceToD0


### -field WdfDevStatePwrPolSystemWakeDeviceToD0CompletePowerUp


### -field WdfDevStatePwrPolSystemWakeQueryIdle


### -field WdfDevStatePwrPolStartedWakeCapable


### -field WdfDevStatePwrPolTimerExpiredDecideUsbSS


### -field WdfDevStatePwrPolTimerExpiredWakeCapablePowerDown


### -field WdfDevStatePwrPolTimerExpiredWakeCapableSendWake


### -field WdfDevStatePwrPolTimerExpiredWakeCapableUsbSS


### -field WdfDevStatePwrPolTimerExpiredWakeCapableWakeArrived


### -field WdfDevStatePwrPolTimerExpiredWakeCapableCancelWake


### -field WdfDevStatePwrPolTimerExpiredWakeCapableWakeCanceled


### -field WdfDevStatePwrPolTimerExpiredWakeCapableCleanup


### -field WdfDevStatePwrPolTimerExpiredWakeCapableDxAllocFailed


### -field WdfDevStatePwrPolTimerExpiredWakeCompletedPowerDown


### -field WdfDevStatePwrPolTimerExpiredWakeCompletedPowerUp


### -field WdfDevStatePwrPolWaitingArmedUsbSS


### -field WdfDevStatePwrPolWaitingArmed


### -field WdfDevStatePwrPolWaitingArmedQueryIdle


### -field WdfDevStatePwrPolIoPresentArmed


### -field WdfDevStatePwrPolIoPresentArmedWakeCanceled


### -field WdfDevStatePwrPolS0WakeDisarm


### -field WdfDevStatePwrPolS0WakeCompletePowerUp


### -field WdfDevStatePwrPolTimerExpiredWakeSucceeded


### -field WdfDevStatePwrPolTimerExpiredWakeCompletedDisarm


### -field WdfDevStatePwrPolTimerExpiredWakeCapableWakeSucceeded


### -field WdfDevStatePwrPolTimerExpiredWakeCapableWakeFailed


### -field WdfDevStatePwrPolWakeFailedUsbSS


### -field WdfDevStatePwrPolTimerExpiredWakeCapablePowerDownFailedCancelWake


### -field WdfDevStatePwrPolTimerExpiredWakeCapablePowerDownFailedWakeCanceled


### -field WdfDevStatePwrPolTimerExpiredWakeCapablePowerDownFailedUsbSS


### -field WdfDevStatePwrPolCancelingWakeForSystemSleep


### -field WdfDevStatePwrPolCancelingWakeForSystemSleepWakeCanceled


### -field WdfDevStatePwrPolDisarmingWakeForSystemSleepCompletePowerUp


### -field WdfDevStatePwrPolPowerUpForSystemSleepFailed


### -field WdfDevStatePwrPolWokeFromS0UsbSS


### -field WdfDevStatePwrPolWokeFromS0


### -field WdfDevStatePwrPolWokeFromS0NotifyDriver


### -field WdfDevStatePwrPolStoppingResetDevice


### -field WdfDevStatePwrPolStoppingResetDeviceCompletePowerUp


### -field WdfDevStatePwrPolStoppingResetDeviceFailed


### -field WdfDevStatePwrPolStoppingD0


### -field WdfDevStatePwrPolStoppingD0Failed


### -field WdfDevStatePwrPolStoppingDisarmWake


### -field WdfDevStatePwrPolStoppingDisarmWakeCancelWake


### -field WdfDevStatePwrPolStoppingDisarmWakeWakeCanceled


### -field WdfDevStatePwrPolStopping


### -field WdfDevStatePwrPolStoppingFailed


### -field WdfDevStatePwrPolStoppingSendStatus


### -field WdfDevStatePwrPolStoppingCancelTimer


### -field WdfDevStatePwrPolStoppingWaitForIdleTimeout


### -field WdfDevStatePwrPolStoppingCancelUsbSS


### -field WdfDevStatePwrPolStoppingWaitForUsbSSCompletion


### -field WdfDevStatePwrPolStoppingCancelWake


### -field WdfDevStatePwrPolStopped


### -field WdfDevStatePwrPolCancelUsbSS


### -field WdfDevStatePwrPolStarted


### -field WdfDevStatePwrPolStartedCancelTimer


### -field WdfDevStatePwrPolStartedWaitForIdleTimeout


### -field WdfDevStatePwrPolStartedWakeCapableCancelTimerForSleep


### -field WdfDevStatePwrPolStartedWakeCapableWaitForIdleTimeout


### -field WdfDevStatePwrPolStartedWakeCapableSleepingUsbSS


### -field WdfDevStatePwrPolStartedIdleCapableCancelTimerForSleep


### -field WdfDevStatePwrPolStartedIdleCapableWaitForIdleTimeout


### -field WdfDevStatePwrPolDeviceD0PowerRequestFailed


### -field WdfDevStatePwrPolDevicePowerRequestFailed


### -field WdfDevStatePwrPolGotoDx


### -field WdfDevStatePwrPolGotoDxInDx


### -field WdfDevStatePwrPolDx


### -field WdfDevStatePwrPolGotoD0


### -field WdfDevStatePwrPolGotoD0InD0


### -field WdfDevStatePwrPolFinal


### -field WdfDevStatePwrPolSleepingPowerDownNotProcessed


### -field WdfDevStatePwrPolTimerExpiredWakeCapablePowerDownNotProcessed


### -field WdfDevStatePwrPolTimerExpiredNoWakePowerDownNotProcessed


### -field WdfDevStatePwrPolTimerExpiredNoWakePoweredDownDisableIdleTimer


### -field WdfDevStatePwrPolStoppingWaitingForImplicitPowerDown


### -field WdfDevStatePwrPolStoppingPoweringUp


### -field WdfDevStatePwrPolStoppingPoweringDown


### -field WdfDevStatePwrPolPowerUpForSystemSleepNotSeen


### -field WdfDevStatePwrPolWaitingArmedStoppingCancelUsbSS


### -field WdfDevStatePwrPolWaitingArmedWakeFailedCancelUsbSS


### -field WdfDevStatePwrPolWaitingArmedIoPresentCancelUsbSS


### -field WdfDevStatePwrPolWaitingArmedWakeSucceededCancelUsbSS


### -field WdfDevStatePwrPolCancelingUsbSSForSystemSleep


### -field WdfDevStatePwrPolStoppingD0CancelUsbSS


### -field WdfDevStatePwrPolStartingPoweredUp


### -field WdfDevStatePwrPolIdleCapableDeviceIdle


### -field WdfDevStatePwrPolDeviceIdleReturnToActive


### -field WdfDevStatePwrPolDeviceIdleSleeping


### -field WdfDevStatePwrPolDeviceIdleStopping


### -field WdfDevStatePwrPolTimerExpiredNoWakeUndoPowerDown


### -field WdfDevStatePwrPolWakeCapableDeviceIdle


### -field WdfDevStatePwrPolWakeCapableUsbSSCompleted


### -field WdfDevStatePwrPolTimerExpiredWakeCapableUndoPowerDown


### -field WdfDevStatePwrPolTimerExpiredWakeCompletedHardwareStarted


### -field WdfDevStatePwrPolStoppedRemoving


### -field WdfDevStatePwrPolRemoved


### -field WdfDevStatePwrPolRestarting


### -field WdfDevStatePwrPolRestartingFailed


### -field WdfDevStatePwrPolStartingPoweredUpFailed


### -field WdfDevStatePwrPolTimerExpiredNoWakeReturnToActive


### -field WdfDevStatePwrPolWaitingArmedWakeInterruptFired


### -field WdfDevStatePwrPolSystemWakeDeviceWakeInterruptFired


### -field WdfDevStatePwrPolSystemWakeDeviceWakeInterruptFiredNP


### -field WdfDevStatePwrPolTimerExpiredWakeCapableWakeInterruptArrived


### -field WdfDevStatePwrPolTimerExpiredWakeCapablePowerDownFailedWakeInterruptArrived


### -field WdfDevStatePwrPolWaitingArmedWakeInterruptFiredDuringPowerDown


### -field WdfDevStatePwrPolNull


## -remarks
The WDF_DEVICE_POWER_POLICY_STATE enumeration is used as a member type in the <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_power_policy_notification_data.md">WDF_DEVICE_POWER_POLICY_NOTIFICATION_DATA</a> structure and as the return type for the <a href="..\wdfdevice\nf-wdfdevice-wdfdevicegetdevicepowerpolicystate.md">WdfDeviceGetDevicePowerPolicyState</a> method.</p>