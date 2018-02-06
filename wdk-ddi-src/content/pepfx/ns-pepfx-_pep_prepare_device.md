---
UID: NS:pepfx._PEP_PREPARE_DEVICE
title: "_PEP_PREPARE_DEVICE"
author: windows-driver-content
description: The PEP_PREPARE_DEVICE structure identifies a device that must be started up in preparation for its use by the operating system.
old-location: kernel\pep_prepare_device.htm
old-project: kernel
ms.assetid: 1D47C803-693B-4205-9D25-82489BFEC82C
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PPEP_PREPARE_DEVICE structure pointer [Kernel-Mode Driver Architecture], kernel.pep_prepare_device, PEP_PREPARE_DEVICE structure [Kernel-Mode Driver Architecture], pepfx/PPEP_PREPARE_DEVICE, PPEP_PREPARE_DEVICE, *PPEP_PREPARE_DEVICE, pepfx/PEP_PREPARE_DEVICE, PEP_PREPARE_DEVICE, _PEP_PREPARE_DEVICE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pepfx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pepfx.h
apiname:
-	PEP_PREPARE_DEVICE
product: Windows
targetos: Windows
req.typenames: "*PPEP_PREPARE_DEVICE, PEP_PREPARE_DEVICE"
---

# _PEP_PREPARE_DEVICE structure
The <b>PEP_PREPARE_DEVICE</b> structure identifies a device that must be started up in preparation for its use by the operating system.

## Syntax
````
typedef struct _PEP_PREPARE_DEVICE {
  PCUNICODE_STRING DeviceId;
  BOOLEAN          DeviceAccepted;
} PEP_PREPARE_DEVICE, *PPEP_PREPARE_DEVICE;
````

## Members


`DeviceAccepted`

[out] Whether the PEP claims ownership of the device. The PEP sets this member to TRUE to claim ownership of the device, or to FALSE to indicate that it does not own the device. The PEP that claims ownership is responsible for handling <a href="https://msdn.microsoft.com/library/windows/hardware/mt186631">device power management (DPM) notifications</a> for the device.

`DeviceId`

[in] A string that uniquely identifies the device. This member is a pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/install/device-identification-strings">device identification string</a>.

## Remarks
This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186832">PEP_DPM_PREPARE_DEVICE</a> notification. The <b>DeviceId</b> member of the structure contains an input value that is supplied by the Windows <a href="https://msdn.microsoft.com/9F2D8ACD-44D5-46E0-9FC7-1B38B99450FF">power management framework</a> (PoFx). The <b>DeviceAccepted</b> member contains an output value that the PEP writes to the structure in response to this notification.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10. Supported starting with Windows 10. |
| **Header** | pepfx.h |

## See Also

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186832">PEP_DPM_PREPARE_DEVICE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PREPARE_DEVICE structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>