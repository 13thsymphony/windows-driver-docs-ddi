---
UID: NF.ndis.NdisIMInitializeDeviceInstanceEx
title: NdisIMInitializeDeviceInstanceEx
author: windows-driver-content
description: The NdisIMInitializeDeviceInstanceEx function initiates the initialization operation for a virtual miniport and optionally sets up state information about the virtual miniport for subsequently bound protocol drivers.
old-location: netvista\ndisiminitializedeviceinstanceex.htm
old-project: netvista
ms.assetid: f65c2974-4bf4-4948-ac07-527e69c96303
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: NdisIMInitializeDeviceInstanceEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisIMInitializeDeviceInstanceEx (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       NdisIMInitializeDeviceInstanceEx (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisIMInitializeDeviceInstanceEx
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_IM_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.iface: 
---

# NdisIMInitializeDeviceInstanceEx function



## -description
<p>The
  <b>NdisIMInitializeDeviceInstanceEx</b> function initiates the initialization operation for a virtual
  miniport and optionally sets up state information about the virtual miniport for subsequently bound
  protocol drivers.</p>


## -syntax

````
NDIS_STATUS NdisIMInitializeDeviceInstanceEx(
  _In_     NDIS_HANDLE  DriverHandle,
  _In_     PNDIS_STRING DriverInstance,
  _In_opt_ NDIS_HANDLE  DeviceContext
);
````


## -parameters
<dl>

### -param <i>DriverHandle</i> [in]

<dd>
<p>The miniport driver handle that the 
     <a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">
     NdisMRegisterMiniportDriver</a> function returns at 
     <i>NdisMiniportDriverHandle</i> .</p>
</dd>

### -param <i>DriverInstance</i> [in]

<dd>
<p>A pointer to an NDIS_STRING type that describes a caller-initialized counted string in the
     system-default character set. The string contains the name of the registry key in which the driver
     stores information about a virtual miniport and, possibly, binding-specific information. For Microsoft
     Windows 2000 and later drivers, this string contains Unicode characters. That is, for Windows 2000 and
     later, NDIS defines the NDIS_STRING type as a 
     <a href="..\wudfwdm\ns-wudfwdm--unicode-string.md">UNICODE_STRING</a> type.</p>
</dd>

### -param <i>DeviceContext</i> [in, optional]

<dd>
<p>A pointer to caller-supplied memory to be set up with driver-defined device context information
     about the virtual miniport, which still higher level protocol drivers that subsequently bind themselves
     to this virtual miniport can use. This parameter can be <b>NULL</b> if the intermediate driver has no such
     device context area.</p>
</dd>
</dl>

## -returns
<p><b>NdisIMInitializeDeviceInstanceEx</b> can return either of the following:</p><dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl><p>NDIS initiated the initialization operation for the intermediate driver's virtual
       miniport.</p><dl>
<dt><b>NDIS_STATUS_NOT_ACCEPTED</b></dt>
</dl><p><b>NdisIMInitializeDeviceInstanceEx</b> failed because the device specified by 
       <i>DriverHandle</i> has already been initialized.</p>

<p> </p>

## -remarks
<p>An NDIS intermediate driver should call 
    <b>NdisIMInitializeDeviceInstanceEx</b> from its 
    <a href="..\ndis\nc-ndis-protocol-bind-adapter-ex.md">ProtocolBindAdapterEx</a> function. A
    failure to call 
    <b>NdisIMInitializeDeviceInstanceEx</b> from an NDIS intermediate driver effectively prevents that driver
    from loading successfully.</p>

<p>Before it calls 
    <b>NdisIMInitializeDeviceInstanceEx</b>, the intermediate driver's 
    <i>ProtocolBindAdapterEx</i> function should bind to any underlying miniport drivers that are required for
    the intermediate driver to function. The 
    <i>ProtocolBindAdapterEx</i> function can allocate an area at 
    <i>DeviceContext</i> as well, possibly setting it up with intermediate driver-determined information about
    the capabilities of the underlying miniport adapter and that was collected by 
    <i>ProtocolBindAdapterEx</i>. The intermediate driver's 
    <a href="..\ndis\nc-ndis-miniport-initialize.md">MiniportInitializeEx</a> function
    might use such information subsequently to set up this context area with information about the driver's
    virtual miniport.</p>

<p>The intermediate driver's call to 
    <b>NdisIMInitializeDeviceInstanceEx</b> causes NDIS to call the intermediate driver's 
    <i>MiniportInitializeEx</i> function, if NDIS receives an 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a> IRP to start the device.
    If NDIS does not receive such an IRP, NDIS will not call the intermediate driver's 
    <i>MiniportInitializeEx</i> function.</p>

<p>The call to 
    <i>MiniportInitializeEx</i> can happen at a later time and therefore is not necessarily within the context
    of the call to 
    <b>NdisIMInitializeDeviceInstanceEx</b>. If NDIS never calls 
    <i>MiniportInitializeEx</i> for the virtual miniport that is referenced in a call to 
    <b>NdisIMInitializeDeviceInstanceEx</b> and the intermediate driver no longer requires the virtual
    miniport, the intermediate driver should call the 
    <a href="..\ndis\nf-ndis-ndisimcancelinitializedeviceinstance.md">
    NdisIMCancelInitializeDeviceInstance</a> function to cancel the initialization of the virtual miniport.
    For example, suppose that an intermediate driver creates a virtual miniport in response to a successful
    binding to an underlying miniport adapter. If that binding is removed before NDIS calls 
    <i>MiniportInitializeEx</i>, the intermediate driver should call 
    <b>NdisIMCancelInitializeDeviceInstance</b> to cancel the initialization of the virtual miniport.</p>

<p><i>MiniportInitializeEx</i> allocates any resources that the driver requires to carry out network I/O
    operations, such as calling the 
    <a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">
    NdisMSetMiniportAttributes</a> function, and to initialize the driver's virtual miniport to an
    operational state. Then, higher-level protocol drivers can bind themselves to its virtual miniport when
    the intermediate driver's initialization is completed successfully.</p>

<p>After 
    <i>MiniportInitializeEx</i> returns control, the intermediate driver's device context area, if any, can
    contain any intermediate-driver-defined data that subsequently enables all higher-level protocol drivers
    that are bound to the same virtual miniport to access information in that context area. Such a
    higher-level protocol driver can query the intermediate-driver-supplied device context with the 
    <a href="..\ndis\nf-ndis-ndisimgetbindingcontext.md">
    NdisIMGetBindingContext</a> function.</p>

<p>Before NDIS calls an intermediate driver's 
    <i>MiniportInitializeEx</i> function, the driver can call 
    <a href="..\ndis\nf-ndis-ndisimcancelinitializedeviceinstance.md">
    NdisIMCancelInitializeDeviceInstance</a> to cancel the initialization operation.</p>

<p>After NDIS calls an intermediate driver's 
    <i>MiniportInitializeEx</i> function, the driver must call 
    <a href="..\ndis\nf-ndis-ndisimdeinitializedeviceinstance.md">
    NdisIMDeInitializeDeviceInstance</a> to reverse the initialization operation.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   <a href="https://msdn.microsoft.com/7d51b25b-41d1-49df-a5a1-b116bb14e3be">
   NdisIMInitializeDeviceInstanceEx (NDIS 5.1)</a>) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   <b>
   NdisIMInitializeDeviceInstanceEx (NDIS 5.1)</b>) in Windows XP.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="devtest.ndis_irql_im_function">Irql_IM_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport-initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisallocatememorywithtagpriority.md">
   NdisAllocateMemoryWithTagPriority</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisimcancelinitializedeviceinstance.md">
   NdisIMCancelInitializeDeviceInstance</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisimdeinitializedeviceinstance.md">
   NdisIMDeInitializeDeviceInstance</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisimgetbindingcontext.md">NdisIMGetBindingContext</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisiminitializedeviceinstanceex.md">
   NdisIMInitializeDeviceInstanceEx</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisinitializestring.md">NdisInitializeString</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">NdisMSetMiniportAttributes</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol-bind-adapter-ex.md">ProtocolBindAdapterEx</a>
</dt>
<dt>
<a href="..\wudfwdm\ns-wudfwdm--unicode-string.md">UNICODE_STRING</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisIMInitializeDeviceInstanceEx function%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
