---
UID: NF:ursdevice.UrsSetPoHandle
title: UrsSetPoHandle function
author: windows-driver-content
description: Registers and deletes the client driver's registration with the power management framework (PoFx).
old-location: buses\urssetpohandle.htm
old-project: usbref
ms.assetid: 87B34452-DC2C-4FD4-B0F8-51EFAF2D4AA6
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UrsSetPoHandle, UrsSetPoHandle function [Buses], buses.urssetpohandle, ursdevice/UrsSetPoHandle
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ursdevice.h
req.include-header: Urscx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Urscxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Urscxstub.lib
-	Urscxstub.dll
api_name:
-	UrsSetPoHandle
product: Windows
targetos: Windows
req.typenames: UMDETW_ALLOCATION_USAGE
req.product: Windows 10 or later.
---


# UrsSetPoHandle function
Registers and deletes the client driver's registration with the power management framework (PoFx).

## Syntax

````
FORCEINLINE void UrsSetPoHandle(
  _In_ WDFDEVICE Device,
  _In_ POHANDLE  PoHandle
);
````

## Parameters

`Device`

A handle to the framework device object that the client driver retrieved in the previous call to <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>.

`PoHandle`

A handle that represents the registration of the device with PoFx. The client driver receives this handle from WDF in  <a href="..\wdfdevice\nc-wdfdevice-evt_wdfdevice_wdm_post_po_fx_register_device.md">EvtDeviceWdmPostPoFxRegisterDevice</a>  and <a href="..\wdfdevice\nc-wdfdevice-evt_wdfdevice_wdm_pre_po_fx_unregister_device.md">EvtDeviceWdmPrePoFxUnregisterDevice</a> callback functions.


## Return Value

This function does not return a value.

## Remarks

The client driver for the dual-role controller must be the power policy owner. The driver can receive notifications from the power management framework (PoFx). To do so, after calling <a href="..\ursdevice\nf-ursdevice-ursdeviceinitialize.md">UrsDeviceInitialize</a>, the driver must register PoFx callback functions. The client driver registers the device with the power framework directly or obtains a POHANDLE from WDF in <a href="..\wdfdevice\nc-wdfdevice-evt_wdfdevice_wdm_post_po_fx_register_device.md">EvtDeviceWdmPostPoFxRegisterDevice</a>. After registration is successful, the driver provides that handle to the USB dual-role class extension.

In the client driver's implementation of the <a href="..\wdfdevice\nc-wdfdevice-evt_wdfdevice_wdm_post_po_fx_register_device.md">EvtDeviceWdmPostPoFxRegisterDevice</a> callback function, the driver is expected to call <b>UrsSetPoHandle</b> by passing the received handle. On some platforms, the class extension might use the POHANDLE to power-manage the controller. Conversely, before the class extension deletes the registration with the power framework, it invokes the client driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdfdevice_wdm_pre_po_fx_unregister_device.md">EvtDeviceWdmPrePoFxUnregisterDevice</a> implementation. The driver is expected to call  <b>UrsSetPoHandle</b> by passing NULL as the PoHandle value.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>

EVT_WDFDEVICE_WDM_POST_PO_FX_REGISTER_DEVICE EvtDevicePostPoFxRegister;

EVT_WDFDEVICE_WDM_PRE_PO_FX_UNREGISTER_DEVICE EvtDevicePrePoFxUnregister;


EvtDriverDeviceAdd (
    _In_ WDFDRIVER Driver,
    _Inout_ PWDFDEVICE_INIT DeviceInit
    )
{
...

    WDFDEVICE device;
    NTSTATUS status;
...

    WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS idleSettings;
    WDF_POWER_FRAMEWORK_SETTINGS poFxSettings;
...
 
    TRY {

        WDF_POWER_FRAMEWORK_SETTINGS_INIT(&amp;poFxSettings);
        poFxSettings.EvtDeviceWdmPostPoFxRegisterDevice = EvtDevicePostPoFxRegister;
        poFxSettings.EvtDeviceWdmPrePoFxUnregisterDevice = EvtDevicePrePoFxUnregister;

        status = WdfDeviceWdmAssignPowerFrameworkSettings(device, &amp;poFxSettings);
        if (!NT_SUCCESS(status)) {
            // WdfDeviceWdmAssignPowerFrameworkSettings failed.

        }

        WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT(&amp;idleSettings, IdleCannotWakeFromS0);
        idleSettings.IdleTimeoutType = SystemManagedIdleTimeout;

        status = WdfDeviceAssignS0IdleSettings(device, &amp;idleSettings);
        if (!NT_SUCCESS(status)) {
            // WdfDeviceAssignS0IdleSettings failed.

        }

    } FINALLY {
    }

..

}

NTSTATUS
EvtDevicePostPoFxRegister (
    _In_ WDFDEVICE Device,
    _In_ POHANDLE PoHandle
    )
{
    UrsSetPoHandle(Device, PoHandle);

    return STATUS_SUCCESS;
}


VOID
EvtDevicePrePoFxUnregister (
    _In_ WDFDEVICE Device,
    _In_ POHANDLE PoHandle
    )
{
    UNREFERENCED_PARAMETER(PoHandle);

    UrsSetPoHandle(Device, NULL);
}
</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.15 |
| **Header** | ursdevice.h (include Urscx.h) |
| **Library** | Urscxstub.lib |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\wdfdevice\nc-wdfdevice-evt_wdfdevice_wdm_post_po_fx_register_device.md">EvtDeviceWdmPostPoFxRegisterDevice</a>



<i>EvtDeviceWdmPrePoFxUnregisterDevice</i>