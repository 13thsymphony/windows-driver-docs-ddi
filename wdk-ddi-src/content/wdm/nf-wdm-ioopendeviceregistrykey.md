---
UID: NF:wdm.IoOpenDeviceRegistryKey
title: IoOpenDeviceRegistryKey function
author: windows-driver-content
description: The IoOpenDeviceRegistryKey routine returns a handle to a device-specific or a driver-specific registry key for a particular device instance.
old-location: kernel\ioopendeviceregistrykey.htm
old-project: kernel
ms.assetid: c3b67c73-446b-42a8-bc41-2ca42fde3513
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: IoOpenDeviceRegistryKey
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
req.alt-api: IoOpenDeviceRegistryKey
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL (see Remarks section)
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoOpenDeviceRegistryKey function



## -description
The <b>IoOpenDeviceRegistryKey</b> routine returns a handle to a device-specific or a driver-specific registry key for a particular device instance. 



## -syntax

````
NTSTATUS IoOpenDeviceRegistryKey(
  _In_  PDEVICE_OBJECT DeviceObject,
  _In_  ULONG          DevInstKeyType,
  _In_  ACCESS_MASK    DesiredAccess,
  _Out_ PHANDLE        DevInstRegKey
);
````


## -parameters

### -param DeviceObject [in]

Pointer to the PDO of the device instance for which the registry key is to be opened.


### -param DevInstKeyType [in]

Specifies flags indicating whether to open a device-specific hardware key or a driver-specific software key. The flags also indicate whether the key is relative to the current hardware profile. For more information about hardware and software keys, see <a href="devinst.overview_of_registry_trees_and_keys">Registry Keys for Drivers</a>.

The flags are defined as follows:




### -param PLUGPLAY_REGKEY_DEVICE

Open the <b>Device Parameters</b> subkey under the device's <a href="wdkgloss.h#wdkgloss.hardware_key#wdkgloss.hardware_key"><i>hardware key</i></a>. The key is located under the key for the device instance specified by <i>DeviceObject</i>. This flag cannot be specified with PLUGPLAY_REGKEY_DRIVER.


### -param PLUGPLAY_REGKEY_DRIVER

Open a <a href="wdkgloss.s#wdkgloss.software_key#wdkgloss.software_key"><i>software key</i></a> for storing driver-specific information. This flag cannot be specified with PLUGPLAY_REGKEY_DEVICE.


### -param PLUGPLAY_REGKEY_CURRENT_HWPROFILE

Open a key relative to the current hardware profile for device or driver information. This allows the driver to access configuration information that is hardware-profile-specific. The caller must specify either PLUGPLAY_REGKEY_DEVICE or PLUGPLAY_REGKEY_DRIVER with this flag. 

</dd>
</dl>

### -param DesiredAccess [in]

Specifies the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> value that represents the access the caller needs to the key. See the <a href="..\wdm\nf-wdm-zwcreatekey.md">ZwCreateKey</a> routine for a description of each KEY_<i>XXX</i> access right.


### -param DevInstRegKey [out]

Pointer to a caller-allocated buffer that, on successful return, contains a handle to the requested registry key. 


## -returns
<b>IoOpenDeviceRegistryKey</b> returns STATUS_SUCCESS if the call was successful. Possible error return values include the following.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>Possibly indicates that the caller specified an illegal set of <i>DevInstKeyType</i> flags.
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>Possibly indicates that the <i>DeviceObject</i> is not a valid PDO.

 


## -remarks
The driver must call <a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a> to close the handle returned from this routine when access is no longer required.

The registry keys opened by this routine are nonvolatile.

User-mode setup applications, such as <a href="wdkgloss.c#wdkgloss.class_installer#wdkgloss.class_installer"><i>class installers</i></a>, can access these registry keys using <a href="https://msdn.microsoft.com/library/windows/hardware/ff541299">device installation functions</a> such as <a href="https://msdn.microsoft.com/library/windows/hardware/ff552079">SetupDiOpenDevRegKey</a>.

To create registry keys, use <a href="devinst.inf_addreg_directive">INF AddReg directives</a> in an INF file or use <a href="https://msdn.microsoft.com/library/windows/hardware/ff550973">SetupDiCreateDevRegKey</a> in a setup application.

Callers of <b>IoOpenDeviceRegistryKey</b> must be running at IRQL = PASSIVE_LEVEL in the context of a system thread. 


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
<a href="https://msdn.microsoft.com/library/windows/hardware/hh975204">PowerIrpDDis</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh454220">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoOpenDeviceRegistryKey routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

