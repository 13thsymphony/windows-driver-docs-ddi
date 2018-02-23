---
UID: NC:hwnclx.HWN_CLIENT_START_DEVICE
title: HWN_CLIENT_START_DEVICE
author: windows-driver-content
description: Implemented by the client driver to start the hardware notification component. It is invoked as a result of a call to EVT_WDF_DEVICE_D0_ENTRY.
old-location: gpiobtn\hwn_client_start_device.htm
old-project: gpiobtn
ms.assetid: 79ad880a-74a2-48e8-b16b-0d488003889f
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: gpiobtn.hwn_client_start_device, HwnClientStartDevice callback function, HwnClientStartDevice, HWN_CLIENT_START_DEVICE, HWN_CLIENT_START_DEVICE, hwnclx/HwnClientStartDevice, *PHWN_CLIENT_START_DEVICE callback function pointer, *PHWN_CLIENT_START_DEVICE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: hwnclx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Hwnclx.h
apiname:
-	*PHWN_CLIENT_START_DEVICE
product: Windows
targetos: Windows
req.typenames: "*PHPMI_QUERY_CAPABILITIES_RESPONSE, HPMI_QUERY_CAPABILITIES_RESPONSE"
---


# HWN_CLIENT_START_DEVICE function
Implemented by the client driver to start the hardware notification component. It is invoked as a result of a call to <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_entry.md">EVT_WDF_DEVICE_D0_ENTRY</a>.

## Syntax

```
HWN_CLIENT_START_DEVICE HwnClientStartDevice;

NTSTATUS HwnClientStartDevice(
  PVOID Context
)
{...}
```

## Parameters

`Context`

Pointer to the client driver's context information. This memory space is available for use by the client driver. It is allocated as part of the framework object context space by <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>. For more information, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/gpiobtn/create-a-hardware-notification-client-driver">HWN_CLIENT_REGISTRATION_PACKET</a> and <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/framework-object-context-space">Framework Object Context Space</a>.


## Return Value

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.

## Remarks

Register your implementation of this callback function by setting the appropriate member of <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/gpiobtn/create-a-hardware-notification-client-driver">HWN_CLIENT_REGISTRATION_PACKET</a> and then calling <a href="..\hwnclx\nf-hwnclx-hwnregisterclient.md">HwNRegisterClient</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1709 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | hwnclx.h |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/405ff6db-9bc0-42f3-a740-49dd3967a8b3">Hardware notifications reference</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/dn789335">Hardware notifications support</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [gpiobtn\gpiobtn]:%20HWN_CLIENT_START_DEVICE callback function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>