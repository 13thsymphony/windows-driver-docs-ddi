---
UID: NS.PEPFX._PEP_CRASHDUMP_INFORMATION
title: _PEP_CRASHDUMP_INFORMATION
author: windows-driver-content
description: The PEP_CRASHDUMP_INFORMATION structure contains information about a crash-dump device.
old-location: kernel\pep_crashdump_information.htm
old-project: kernel
ms.assetid: B1F680CB-8F82-4B31-A62E-23804FEB0107
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: _PEP_CRASHDUMP_INFORMATION, PEP_CRASHDUMP_INFORMATION, *PPEP_CRASHDUMP_INFORMATION
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
req.alt-api: PEP_CRASHDUMP_INFORMATION
req.alt-loc: pepfx.h
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
---

# _PEP_CRASHDUMP_INFORMATION structure



## -description
The <b>PEP_CRASHDUMP_INFORMATION</b> structure contains information about a crash-dump device.



## -syntax

````
typedef struct _PEP_CRASHDUMP_INFORMATION {
  PEPHANDLE DeviceHandle;
  PVOID     DeviceContext;
} PEP_CRASHDUMP_INFORMATION, *PPEP_CRASHDUMP_INFORMATION;
````


## -struct-fields

### -field DeviceHandle

[in] A PEPHANDLE value that identifies the crash-dump device. The platform extension plug-in (PEP) supplied this handle in response to a previous <a href="kernel.pep_dpm_register_device">PEP_DPM_REGISTER_DEVICE</a> notification.


### -field DeviceContext

[in] A pointer to a device-specific context. This pointer is the <i>Context</i> parameter value that the device driver previously passed to the <a href="kernel.pofxpoweroncrashdumpdevice">PoFxPowerOnCrashdumpDevice</a> routine. The context contains information in a format that is defined by the device driver and is understood by the PEP. The context is opaque to the operating system. This member value can be NULL if the PEP does not require a context.


## -remarks
The <i>CrashdumpInformation</i> parameter to the <a href="kernel.powerondumpdevicecallback">PowerOnDumpDeviceCallback</a> routine is a pointer to a <b>PEP_CRASHDUMP_INFORMATION</b> structure.

When a fatal system error occurs, the devices in the crash-dump device chain (storage controller, PCI controller, and so on) need to be turned on so that the Windows kernel can write a crash-dump file to disk.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported starting with Windows 10.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Pepfx.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.pep_dpm_register_device">PEP_DPM_REGISTER_DEVICE</a>
</dt>
<dt>
<a href="kernel.pofxpoweroncrashdumpdevice">PoFxPowerOnCrashdumpDevice</a>
</dt>
<dt>
<a href="kernel.powerondumpdevicecallback">PowerOnDumpDeviceCallback</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_CRASHDUMP_INFORMATION structure%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

