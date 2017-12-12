---
UID: NF.wdfcontrol.WdfControlDeviceInitAllocate
title: WdfControlDeviceInitAllocate function
author: windows-driver-content
description: The WdfControlDeviceInitAllocate method allocates a WDFDEVICE_INIT structure that a driver uses when creating a new control device object.
old-location: wdf\wdfcontroldeviceinitallocate.htm
old-project: wdf
ms.assetid: 3d423861-4c4d-45f2-bc44-b7cf1b230458
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: WdfControlDeviceInitAllocate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfcontrol.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfControlDeviceInitAllocate
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: ControlDeviceInitAPI, CtlDeviceFinishInitDeviceAdd, CtlDeviceFinishInitDrEntry, DriverCreate, InitFreeDeviceCallback, InitFreeDeviceCreate, InitFreeDeviceCreateType2, InitFreeDeviceCreateType4, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# WdfControlDeviceInitAllocate function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfControlDeviceInitAllocate</b> method allocates a <a href="wdf.wdfdevice_init">WDFDEVICE_INIT</a> structure that a driver uses when creating a new control device object.



## -syntax

````
PWDFDEVICE_INIT WdfControlDeviceInitAllocate(
  _In_       WDFDRIVER      Driver,
  _In_ const UNICODE_STRING *SDDLString
);
````


## -parameters

### -param Driver [in]

A handle to a framework driver object.


### -param SDDLString [in]

A pointer to a <a href="kernel.unicode_string">UNICODE_STRING</a> structure that describes a Unicode string. This string is a Security Descriptor Definition Language (SDDL) representation of a security descriptor. For more information, see the following Remarks section.


## -returns
<b>WdfControlDeviceInitAllocate</b> returns a pointer to a framework-allocated <a href="wdf.wdfdevice_init">WDFDEVICE_INIT</a> structure, if the operation succeeds. Otherwise, the method returns <b>NULL</b>.


## -remarks
If you want your driver to create a control device object, the driver must call <b>WdfControlDeviceInitAllocate</b> to obtain a WDFDEVICE_INIT structure that it can pass to <a href="wdf.wdfdevicecreate">WdfDeviceCreate</a>. 

Your driver can specify a security setting by using a subset of SDDL. The <i>Wdmsec.h</i> file defines a set of SDDL_DEVOBJ_<i>Xxx</i>-formatted constants that you can use. For more information about security descriptors and SDDL, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563688">Securing Device Objects</a>.

The <a href="wdf.wdfdeviceinitassignsddlstring">WdfDeviceInitAssignSDDLString</a> method overwrites the security setting, if any, that <b>WdfControlDeviceInitAllocate</b> specifies.

For more information about calling <b>WdfControlDeviceInitAllocate</b>, see <a href="wdf.using_control_device_objects">Using Control Device Objects</a>.

The following code example allocates a DEVICE_INIT structure, assigns a device object name, registers a shutdown notification callback function, and creates a control device object. For a more complex example that uses <b>WdfControlDeviceInitAllocate</b>, see the <a href="wdf.sample_kmdf_drivers">NONPNP</a> sample driver or the <a href="wdf.sample_kmdf_drivers">NDISProt</a> sample driver.


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
Minimum KMDF version

</th>
<td width="70%">
1.0

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdfcontrol.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (see <a href="wdf.framework_library_versioning">Framework Library Versioning</a>.)</dt>
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
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.kmdf_controldeviceinitapi">ControlDeviceInitAPI</a>, <a href="devtest.kmdf_ctldevicefinishinitdeviceadd">CtlDeviceFinishInitDeviceAdd</a>, <a href="devtest.kmdf_ctldevicefinishinitdrentry">CtlDeviceFinishInitDrEntry</a>, <a href="devtest.kmdf_drivercreate">DriverCreate</a>, <a href="devtest.kmdf_initfreedevicecallback">InitFreeDeviceCallback</a>, <a href="devtest.kmdf_initfreedevicecreate">InitFreeDeviceCreate</a>, <a href="devtest.kmdf_initfreedevicecreatetype2">InitFreeDeviceCreateType2</a>, <a href="devtest.kmdf_initfreedevicecreatetype4">InitFreeDeviceCreateType4</a>, <a href="devtest.kmdf_kmdfirql">KmdfIrql</a>, <a href="devtest.kmdf_kmdfirql2">KmdfIrql2</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdf_object_attributes_init">WDF_OBJECT_ATTRIBUTES_INIT</a>
</dt>
<dt>
<a href="wdf.wdfdevice_init">WDFDEVICE_INIT</a>
</dt>
<dt>
<a href="wdf.wdfcontrolfinishinitializing">WdfControlFinishInitializing</a>
</dt>
<dt>
<a href="wdf.wdfdeviceinitassignname">WdfDeviceInitAssignName</a>
</dt>
<dt>
<a href="wdf.wdfcontroldeviceinitsetshutdownnotification">WdfControlDeviceInitSetShutdownNotification</a>
</dt>
<dt>
<a href="wdf.wdfdevicecreate">WdfDeviceCreate</a>
</dt>
<dt>
<a href="wdf.wdfdeviceinitassignsddlstring">WdfDeviceInitAssignSDDLString</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfControlDeviceInitAllocate method%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

