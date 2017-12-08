---
UID: NF.wdm.IoOpenDeviceInterfaceRegistryKey
title: IoOpenDeviceInterfaceRegistryKey function
author: windows-driver-content
description: The IoOpenDeviceInterfaceRegistryKey routine returns a handle to a registry key for storing information about a particular device interface instance.
old-location: kernel\ioopendeviceinterfaceregistrykey.htm
old-project: kernel
ms.assetid: d9ca4b9d-dacc-4164-9198-a71a771b145b
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: IoOpenDeviceInterfaceRegistryKey
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
req.alt-api: IoOpenDeviceInterfaceRegistryKey
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
req.product: Windows 10 or later.
---

# IoOpenDeviceInterfaceRegistryKey function



## -description
The <b>IoOpenDeviceInterfaceRegistryKey</b> routine returns a handle to a registry key for storing information about a particular device interface instance.


## -syntax

````
NTSTATUS IoOpenDeviceInterfaceRegistryKey(
  _In_  PUNICODE_STRING SymbolicLinkName,
  _In_  ACCESS_MASK     DesiredAccess,
  _Out_ PHANDLE         DeviceInterfaceKey
);
````


## -parameters

### -param SymbolicLinkName [in]

Pointer to a string identifying the device interface instance. This string was obtained from a previous call to <a href="kernel.iogetdeviceinterfaces">IoGetDeviceInterfaces</a>, <a href="kernel.iogetdeviceinterfacealias">IoGetDeviceInterfaceAlias</a>, or <a href="kernel.ioregisterdeviceinterface">IoRegisterDeviceInterface</a>. 

### -param DesiredAccess [in]

Specifies the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> value that represents the access the caller requires to the key, such as KEY_READ, KEY_WRITE, or KEY_ALL_ACCESS. See <a href="kernel.zwcreatekey">ZwCreateKey</a> for a description of each KEY_<i>XXX</i> access right. 

### -param DeviceInterfaceKey [out]

Pointer to a returned handle to the requested registry key if the call is successful. 

## -returns
<b>IoOpenDeviceInterfaceRegistryKey</b> returns STATUS_SUCCESS if the call was successful. Possible error return values include the following.
<dl>
<dt><b>STATUS_OBJECT_NAME_NOT_FOUND</b></dt>
</dl>The routine was not able to locate a registry key for the device interface instance, probably due to an error in the <i>SymbolicLinkName</i>. 
<dl>
<dt><b>STATUS_OBJECT_PATH_NOT_FOUND</b></dt>
</dl>The routine was not able to locate a registry key for the device interface instance, probably due to an error in the <i>SymbolicLinkName</i>. 
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>Possibly indicates an error in the <i>SymbolicLinkName</i>.

 

## -remarks
<b>IoOpenDeviceInterfaceRegistryKey</b> opens a nonvolatile subkey of the registry key for the device interface instance specified by <i>SymbolicLinkName</i>. Drivers can store information in this subkey that is specific to this instance of the device interface, such as the default resolution for a camera. User-mode applications can access this subkey using <b>SetupDi<i>Xxx</i></b> routines.

The driver must call <a href="kernel.zwclose">ZwClose</a> to close the handle returned from this routine when access is no longer required.

Callers of <b>IoOpenDeviceInterfaceRegistryKey</b> must be running at IRQL = PASSIVE_LEVEL in the context of a system thread.

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
<a href="devtest.wdm_powerirpddis">PowerIrpDDis</a>, <a href="devtest.storport_hwstorportprohibitedddis">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>
</dt>
<dt>
<a href="kernel.iogetdeviceinterfaces">IoGetDeviceInterfaces</a>
</dt>
<dt>
<a href="kernel.iogetdeviceinterfacealias">IoGetDeviceInterfaceAlias</a>
</dt>
<dt>
<a href="kernel.ioregisterdeviceinterface">IoRegisterDeviceInterface</a>
</dt>
<dt>
<a href="kernel.zwclose">ZwClose</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoOpenDeviceInterfaceRegistryKey routine%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
