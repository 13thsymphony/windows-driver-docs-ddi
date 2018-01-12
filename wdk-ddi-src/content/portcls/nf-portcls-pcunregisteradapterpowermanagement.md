---
UID: NF:portcls.PcUnregisterAdapterPowerManagement
title: PcUnregisterAdapterPowerManagement function
author: windows-driver-content
description: The PcUnregisterAdapterPowerManagement function unregisters the audio adapter's power management interface from the PortCls class driver. The PcUnregisterAdapterPowerManagement function is available in Windows 7 and later versions of Windows.
old-location: audio\pcunregisteradapterpowermanagement.htm
old-project: audio
ms.assetid: a25ee83f-e267-4966-9be2-ddcbc44b5c15
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PcUnregisterAdapterPowerManagement
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PcUnregisterAdapterPowerManagement
req.alt-loc: Portcls.lib,Portcls.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL.
req.typenames: *PPC_EXIT_LATENCY, PC_EXIT_LATENCY
---

# PcUnregisterAdapterPowerManagement function



## -description
The <b>PcUnregisterAdapterPowerManagement</b> function unregisters the audio adapter's power management interface from the PortCls class driver. The <b>PcUnregisterAdapterPowerManagement</b> function is available in Windows 7 and later versions of Windows.



## -syntax

````
PORTCLASSAPI NTSTATUS NTAPI PcUnregisterAdapterPowerManagement(
  _In_ PDEVICE_OBJECT pDeviceObject
);
````


## -parameters

### -param pDeviceObject [in]

Specifies a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> structure that represents the functional device object of the adapter.


## -returns
The <b>PcUnregisterAdapterPowerManagement</b> function returns STATUS_SUCCESS if the function call was successful. Otherwise, it returns the appropriate error code.


## -remarks
The <b>PcUnregisterAdapterPowerManagement</b> function unregisters a driver's power management interface that was registered with PortCls by using the <a href="..\portcls\nf-portcls-pcregisteradapterpowermanagement.md">PcRegisterAdapterPowerManagement</a> function. <b>PcUnregisterAdapterPowerManagement</b> helps the system to avoid making a power change request while the adapter driver is being unloaded. This function must only be called if the power management interface for the adapter was previously registered with PortCls.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows 7 and later versions of Windows.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Portcls.h (include Portcls.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Portcls.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL.

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>
</dt>
<dt>
<a href="..\portcls\nf-portcls-pcregisteradapterpowermanagement.md">PcRegisterAdapterPowerManagement</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PcUnregisterAdapterPowerManagement function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

