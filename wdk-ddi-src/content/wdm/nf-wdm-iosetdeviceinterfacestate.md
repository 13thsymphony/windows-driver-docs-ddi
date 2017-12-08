---
UID: NF.wdm.IoSetDeviceInterfaceState
title: IoSetDeviceInterfaceState function
author: windows-driver-content
description: The IoSetDeviceInterfaceState routine enables or disables an instance of a previously registered device interface class.
old-location: kernel\iosetdeviceinterfacestate.htm
old-project: kernel
ms.assetid: 071b5f2a-7129-4de5-9577-f2aa22f23765
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: IoSetDeviceInterfaceState
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoSetDeviceInterfaceState
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: IrqlIoPassive1, LowerDriverReturn, PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL (see Remarks section)
req.product: Windows 10 or later.
---

# IoSetDeviceInterfaceState function



## -description
The <b>IoSetDeviceInterfaceState</b> routine enables or disables an instance of a previously registered device interface class. 


## -syntax

````
NTSTATUS IoSetDeviceInterfaceState(
  _In_ PUNICODE_STRING SymbolicLinkName,
  _In_ BOOLEAN         Enable
);
````


## -parameters

### -param SymbolicLinkName [in]

Pointer to a string that identifies the device interface instance that is being enabled or disabled. This string was obtained from a previous call to <a href="kernel.ioregisterdeviceinterface">IoRegisterDeviceInterface</a> or <a href="kernel.iogetdeviceinterfaces">IoGetDeviceInterfaces</a>. 

### -param Enable [in]

<b>TRUE</b> indicates that the device interface is being enabled. <b>FALSE</b> indicates that the device interface is being disabled. 

## -returns
<b>IoSetDeviceInterfaceState</b> returns STATUS_SUCCESS if the call was successful. This routine returns an informational status of STATUS_OBJECT_NAME_EXISTS if the caller requested to enable a device interface that was already enabled. Possible error return values are described following.
<dl>
<dt><b>STATUS_OBJECT_NAME_NOT_FOUND</b></dt>
</dl>The caller tried to disable a device interface that was not enabled.

 

## -remarks
<b>IoSetDeviceInterfaceState</b> enables an instance of a registered device interface for use by applications and other system components. The interface class must have been previously registered with <a href="kernel.ioregisterdeviceinterface">IoRegisterDeviceInterface</a> or from user mode. 

Applications and other system components can open only interfaces that are enabled.

A function or a filter driver typically calls this routine with <i>Enable</i> set to <b>TRUE</b> after it successfully starts a device in response to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a> IRP. Such a driver should disable the device interface instance (that is, call <b>IoSetDeviceInterfaceState</b> and set <i>Enable</i> to <b>FALSE</b>) when it removes the device in response to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551738">IRP_MN_REMOVE_DEVICE</a> IRP or an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551760">IRP_MN_SURPRISE_REMOVAL</a> IRP. If a driver does not disable a device interface when it processes these removal IRPs, the driver should not subsequently attempt to do so because the PnP manager will disable the interface when the PnP manager removes the device. 

If a device is removed suddenly (for example, by a surprise removal) but still has a valid device interface instance, a problem will occur if the device is reattached. This problem occurs when the PnP manager enumerates the newly attached device and enables a device interface instance, which will exist at the same registry path as the existing device interface instance.

Note that if the driver calls <b>IoSetDeviceInterfaceState</b> to disable a device interface instance in response to an <b>IRP_MN_SURPRISE_REMOVAL</b> IRP, the driver must not attempt to disable the same device interface instance in response to an <b>IRP_MN_REMOVE_DEVICE</b> IRP.

If a call to <b>IoSetDeviceInterfaceState</b> successfully exposes a device interface instance, the system notifies any components that registered for PnP notification of a device class change. Similarly, if a call to this routine disables an existing device interface instance, the system sends appropriate notifications.

The PnP manager does not send notification of interface instance arrivals until the <b>IRP_MN_START_DEVICE</b> IRP completes, indicating that all the drivers for the device have completed their start operations. In addition, the PnP manager fails create requests for the device until the <b>IRP_MN_START_DEVICE</b> IRP completes.

Callers of <b>IoSetDeviceInterfaceState</b> must be running at IRQL = PASSIVE_LEVEL in the context of a system thread.

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
Available starting with Windows 2000.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
PASSIVE_LEVEL (see Remarks section)
</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules
</th>
<td width="70%">
<a href="devtest.wdm_irqliopassive1">IrqlIoPassive1</a>, <a href="devtest.wdm_lowerdriverreturn">LowerDriverReturn</a>, <a href="devtest.wdm_powerirpddis">PowerIrpDDis</a>, <a href="devtest.storport_hwstorportprohibitedddis">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.iogetdeviceinterfaces">IoGetDeviceInterfaces</a>
</dt>
<dt>
<a href="kernel.ioregisterdeviceinterface">IoRegisterDeviceInterface</a>
</dt>
<dt>
<a href="kernel.ioregisterplugplaynotification">IoRegisterPlugPlayNotification</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551738">IRP_MN_REMOVE_DEVICE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551760">IRP_MN_SURPRISE_REMOVAL</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoSetDeviceInterfaceState routine%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
