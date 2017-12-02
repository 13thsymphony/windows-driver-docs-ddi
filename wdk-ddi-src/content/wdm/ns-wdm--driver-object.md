---
UID: NS.wdm._DRIVER_OBJECT
title: DRIVER_OBJECT
author: windows-driver-content
description: Each driver object represents the image of a loaded kernel-mode driver.
old-location: kernel\driver_object.htm
old-project: kernel
ms.assetid: 512e3fd5-7ea5-423c-a628-0db6b30fd708
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: DRIVER_OBJECT,
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DRIVER_OBJECT
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
req.iface: 
req.product: Windows 10 or later.
---

# DRIVER_OBJECT structure



## -description
<p>Each driver object represents the image of a loaded kernel-mode driver. A pointer to the driver object is an input parameter to a driver's <a href="..\wdm\nc-wdm-driver-initialize.md">DriverEntry</a>, <a href="kernel.adddevice">AddDevice</a>, and optional <a href="..\ntddk\nc-ntddk-driver-reinitialize.md">Reinitialize</a> routines and to its <a href="kernel.unload">Unload</a> routine, if any.</p>
<p>A driver object is partially opaque. Driver writers must know about certain members of a driver object to initialize a driver and to unload it if the driver is unloadable. The following members of the driver object are accessible to drivers.</p>


## -syntax

````
typedef struct _DRIVER_OBJECT {
  PDEVICE_OBJECT     DeviceObject;
  PDRIVER_EXTENSION  DriverExtension;
  PUNICODE_STRING    HardwareDatabase;
  PFAST_IO_DISPATCH  FastIoDispatch;
  PDRIVER_INITIALIZE DriverInit;
  PDRIVER_STARTIO    DriverStartIo;
  PDRIVER_UNLOAD     DriverUnload;
  PDRIVER_DISPATCH   MajorFunction[IRP_MJ_MAXIMUM_FUNCTION+1];
} DRIVER_OBJECT, *PDRIVER_OBJECT;
````


## -struct-fields
<dl>

### -field DeviceObject

<dd>
<p>Pointer to the device objects created by the driver. This member is automatically updated when the driver calls <a href="..\wdm\nf-wdm-iocreatedevice.md">IoCreateDevice</a> successfully. A driver can use this member and the <b>NextDevice</b> member of <a href="..\wdm\ns-wdm--device-object.md">DEVICE_OBJECT</a> to step through a list of all the device objects that the driver created.</p>
</dd>

### -field DriverExtension

<dd>
<p>Pointer to the driver extension. The only accessible member of the driver extension is <b>DriverExtension-&gt;AddDevice</b>, into which a driver's <b>DriverEntry</b> routine stores the driver's <a href="kernel.adddevice">AddDevice</a> routine.</p>
</dd>

### -field HardwareDatabase

<dd>
<p>Pointer to the <b>\Registry\Machine\Hardware</b> path to the hardware configuration information in the registry.</p>
</dd>

### -field FastIoDispatch

<dd>
<p>Pointer to a structure defining the driver's fast I/O entry points. This member is used only by FSDs and network transport drivers.</p>
</dd>

### -field DriverInit

<dd>
<p>The entry point for the <a href="..\wdm\nc-wdm-driver-initialize.md">DriverEntry</a> routine, which is set up by the I/O manager.</p>
</dd>

### -field DriverStartIo

<dd>
<p>The entry point for the driver's <a href="kernel.startio">StartIo</a> routine, if any, which is set by the <b>DriverEntry</b> routine when the driver initializes. If a driver has no <i>StartIo</i> routine, this member is <b>NULL</b>.</p>
</dd>

### -field DriverUnload

<dd>
<p>The entry point for the driver's <a href="kernel.unload">Unload</a> routine, if any, which is set by the <b>DriverEntry</b> routine when the driver initializes. If a driver has no <i>Unload</i> routine, this member is <b>NULL</b>.</p>
</dd>

### -field MajorFunction

<dd>
<p>A dispatch table consisting of an array of entry points for the driver's <i>DispatchXxx</i> routines. The array's index values are the <b>IRP_MJ_<i>XXX</i></b> values representing each <a href="https://msdn.microsoft.com/11c5b1a9-74c0-47fb-8cce-a008ece9efae">IRP major function code</a>. Each driver must set entry points in this array for the <b>IRP_MJ_<i>XXX</i></b> requests that the driver handles. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff566407">Writing Dispatch Routines</a>.</p>
<p>To help <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools, each <i>DispatchXxx</i> routine is declared using the DRIVER_DISPATCH type, as shown in this code example:</p>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
DRIVER_DISPATCH DispatchXxx;</pre>
</td>
</tr>
</table></span></div>
<p>Then, the callback routine is implemented as follows:</p>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
_Use_decl_annotations_
NTSTATUS
  DispatchXxx(
    struct _DEVICE_OBJECT  *DeviceObject,
    struct _IRP  *Irp
    )
  {
      // Function body
  }</pre>
</td>
</tr>
</table></span></div>
<p>The DRIVER_DISPATCH function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the DRIVER_DISPATCH function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/3260b53e-82be-4dbc-8ac5-d0e52de77f9d">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.</p>
</dd>
</dl>

## -remarks
<p>Each kernel-mode driver's initialization routine should be named <a href="..\wdm\nc-wdm-driver-initialize.md">DriverEntry</a> so the system will load the driver automatically. If this routine's name is something else, the driver writer must define the name of the initialization routine for the linker; otherwise, the system loader or I/O manager cannot find the driver's transfer address. The names of other standard driver routines can be chosen at the discretion of the driver writer.</p>

<p>A driver must set its <i>DispatchXxx</i> entry points in the driver object that is passed in to the <b>DriverEntry</b> routine when the driver is loaded. A device driver must set one or more <i>DispatchXxx</i> entry points for the <b>IRP_MJ_<i>XXX</i></b> that any driver of the same type of device is required to handle. A higher-level driver must set one or more <i>DispatchXxx</i> entry points for all the <b>IRP_MJ_<i>XXX</i></b> that it must pass on to the underlying device driver. Otherwise, a driver is not sent IRPs for any <b>IRP_MJ_<i>XXX</i></b> for which it does not set up a <i>DispatchXxx</i> routine in the driver object. For more information about the set of <b>IRP_MJ_<i>XXX</i></b> that drivers for different types of underlying devices are required to handle, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff550710">IRP Major Function Codes</a>.</p>

<p>The <b>DriverEntry</b> routine also sets the driver's <i>AddDevice</i>, <i>StartIo</i> and/or <a href="kernel.unload">Unload</a> entry points, if any, in the driver object.</p>

<p>The <b>HardwareDatabase</b> string can be used by device drivers to get hardware configuration information from the registry when the driver is loaded. A driver is given read-only access to this string.</p>

<p>The <i>RegistryPath</i> input to the <b>DriverEntry</b> routine points to the <b>\Registry\Machine\System\CurrentControlSet\Services\<i>DriverName</i></b> key, where the value entry of <i>DriverName</i> identifies the driver. As for the <b>HardwareDatabase</b> in the input driver object, a driver is given read-only access to this string.</p>

<p>Undocumented members within a driver object should be considered inaccessible. Drivers with dependencies on object member locations or on access to undocumented members might not remain portable and interoperable with other drivers over time.</p>

## -requirements
<table>
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
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nc-wdm-driver-initialize.md">DriverEntry</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iocreatedevice.md">IoCreateDevice</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iodeletedevice.md">IoDeleteDevice</a>
</dt>
<dt>
<a href="kernel.startio">StartIo</a>
</dt>
<dt>
<a href="kernel.unload">Unload</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20DRIVER_OBJECT structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
