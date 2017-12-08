---
UID: NF.wdm.PoFxUnregisterDevice
title: PoFxUnregisterDevice function
author: windows-driver-content
description: The PoFxUnregisterDevice routine removes the registration of a device from the power management framework (PoFx).
old-location: kernel\pofxunregisterdevice.htm
old-project: kernel
ms.assetid: FC4B1B4D-31D8-4E63-A3A5-07A1099997A8
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: PoFxUnregisterDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PoFxUnregisterDevice
req.alt-loc: Ntoskrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ntoskrnl.lib
req.dll: Ntoskrnl.exe
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# PoFxUnregisterDevice function



## -description
The <b>PoFxUnregisterDevice</b> routine removes the registration of a device from the power management framework (PoFx).


## -syntax

````
VOID PoFxUnregisterDevice(
  _In_ POHANDLE Handle
);
````


## -parameters

### -param Handle [in]

A handle that represents the registration of the device with PoFx. The device driver previously received this handle from the <a href="kernel.pofxregisterdevice">PoFxRegisterDevice</a> routine.

## -returns
None.

## -remarks
The driver that owns the power policy for a device must unregister the device from PoFx when the device is removed. The Plug and Play (PnP) manager can remove the device stack from the PnP tree only after the device is unregistered.

To unregister the device, the driver calls <b>PoFxUnregisterDevice</b> during the handling of an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551738">IRP_MN_REMOVE_DEVICE</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff551760">IRP_MN_SURPRISE_REMOVAL</a> request, whichever is received first. This call should occur after the driver no longer requires access to the device's hardware.

A device driver that calls this routine must previously have called the <a href="kernel.pofxregisterdevice">PoFxRegisterDevice</a> routine to register the device with PoFx.

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
Available starting with Windows 8.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdm.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Ntoskrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL
</th>
<td width="70%">
<dl>
<dt>Ntoskrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
PASSIVE_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551738">IRP_MN_REMOVE_DEVICE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551760">IRP_MN_SURPRISE_REMOVAL</a>
</dt>
<dt>
<a href="kernel.pofxregisterdevice">PoFxRegisterDevice</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PoFxUnregisterDevice routine%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
