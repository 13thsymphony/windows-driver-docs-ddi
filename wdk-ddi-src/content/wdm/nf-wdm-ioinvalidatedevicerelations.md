---
UID: NF.wdm.IoInvalidateDeviceRelations
title: IoInvalidateDeviceRelations
author: windows-driver-content
description: The IoInvalidateDeviceRelations routine notifies the PnP manager that the relations for a device (such as bus relations, ejection relations, removal relations, and the target device relation) have changed.
old-location: kernel\ioinvalidatedevicerelations.htm
old-project: kernel
ms.assetid: f312afec-10b3-4049-a4c1-154c11b4a869
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: IoInvalidateDeviceRelations
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
req.alt-api: IoInvalidateDeviceRelations
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# IoInvalidateDeviceRelations function



## -description
<p>The <b>IoInvalidateDeviceRelations</b> routine notifies the PnP manager that the relations for a device (such as bus relations, ejection relations, removal relations, and the target device relation) have changed.</p>


## -syntax

````
VOID IoInvalidateDeviceRelations(
  _In_ PDEVICE_OBJECT       DeviceObject,
  _In_ DEVICE_RELATION_TYPE Type
);
````


## -parameters
<dl>

### -param DeviceObject [in]

<dd>
<p>Pointer to the PDO for the device.</p>
</dd>

### -param Type [in]

<dd>
<p>Specifies a <b>DEVICE_RELATION_TYPE</b> enumeration value that describes the type of relations that have changed. Possible values include <b>BusRelations</b>, <b>EjectionRelations</b>, <b>RemovalRelations</b>, and <b>TargetDeviceRelation</b>. Starting with Windows 7, the <b>PowerRelations</b> value is also supported.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>For some relation types, such as <b>BusRelations</b>, this routine causes the PnP manager or power manager to gather updated relations information by sending an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551670">IRP_MN_QUERY_DEVICE_RELATIONS</a> request to the drivers for the device. For other relation types, such as <b>EjectionRelations</b>, the PnP manager does not need to gather new relation information immediately; the PnP manager queries drivers for ejection relations only when it is preparing to eject a device.</p>

<p>After a bus driver calls <b>IoInvalidateDeviceRelations</b> to inform the PnP manager that a device has disappeared, the bus driver must continue to handle PnP IRPs for that device until it receives an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551738">IRP_MN_REMOVE_DEVICE</a> request. In response to this IRP, the bus driver returns STATUS_NO_SUCH_DEVICE. Until the bus driver successfully completes the <b>IRP_MN_REMOVE_DEVICE</b> request, the bus driver can access the device extension to check its flags for the device.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with Windows 2000.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= DISPATCH_LEVEL</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="devtest.storport_hwstorportprohibitedddis">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551670">IRP_MN_QUERY_DEVICE_RELATIONS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551738">IRP_MN_REMOVE_DEVICE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoInvalidateDeviceRelations routine%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
