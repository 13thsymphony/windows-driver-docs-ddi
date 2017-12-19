---
UID: NF.ndis.NdisMRegisterIoPortRange
title: NdisMRegisterIoPortRange function
author: windows-driver-content
description: NdisMRegisterIoPortRange sets up driver access to device I/O ports with the NdisRawReadPortXxx and NdisRawWritePortXxx functions and claims the range of I/O port addresses in the registry for that driver's NIC.
old-location: netvista\ndismregisterioportrange.htm
old-project: NetVista
ms.assetid: 3e7fc02b-9562-44b9-8659-793a1d96d1e9
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: NdisMRegisterIoPortRange
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMRegisterIoPortRange (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMRegisterIoPortRange (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisMRegisterIoPortRange
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_Miniport_Driver_Function, NdisMRegisterIoPortRange
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
---

# NdisMRegisterIoPortRange function



## -description
<b>NdisMRegisterIoPortRange</b> sets up driver access to device I/O ports with the 
  <b>NdisRawReadPort<i>Xxx</i></b> and 
  <b>NdisRawWritePort<i>Xxx</i></b> functions and claims the range of I/O port addresses in the registry for that driver's
  NIC.



## -syntax

````
NDIS_STATUS NdisMRegisterIoPortRange(
  _Out_ PVOID       *PortOffset,
  _In_  NDIS_HANDLE MiniportAdapterHandle,
  _In_  UINT        InitialPort,
  _In_  UINT        NumberOfPorts
);
````


## -parameters

### -param PortOffset [out]

Specifies a caller-supplied variable in which this function returns the mapped base virtual
     address for the given bus-relative I/O port range specified by 
     <i>InitialPort</i> and 
     <i>NumberOfPorts</i> .


### -param MiniportAdapterHandle [in]

Specifies the handle input to 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>.


### -param InitialPort [in]

Specifies the bus-relative base port address for a range of ports to be mapped.


### -param NumberOfPorts [in]

Specifies the number of ports in the range to be mapped.


## -returns
<b>NdisMRegisterIoPortRange</b> can return one of the following:
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>The given range of I/O ports was mapped successfully so the value at 
       <i>PortOffset</i> is valid and the mapped range has been claimed in the registry for the NIC.
<dl>
<dt><b>NDIS_STATUS_RESOURCE_CONFLICT</b></dt>
</dl>An attempt to claim the I/O port range in the registry has failed, possibly because another
       driver already claimed the range for its device. 
       <b>NdisMRegisterIoPortRange</b> logs an error if this occurs.
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>The port range could not be mapped or NDIS could not allocate resources to check the registry
       for hardware-resource conflicts.
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>Either the bus type or bus number is out of range or the given 
       <i>InitialPort</i> and 
       <i>NumberOfPorts</i> were invalid (possibly not within the I/O port space of the current
       platform).

 


## -remarks
A miniport driver calls 
    <b>NdisMRegisterIoPortRange</b> from its 
    <i>MiniportInitializeEx</i> function. 
    <i>MiniportInitializeEx</i> must call 
    <a href="netvista.ndismsetminiportattributes">
    NdisMSetMiniportAttributes</a> before calling 
    <b>NdisMRegisterIoPortRange</b>.

<b>NdisMRegisterIoPortRange</b> maps a bus-relative device address range that the miniport driver can use
    subsequently to access an I/O port range on a NIC by calling the 
    <b>NdisRaw<i>Xxx</i></b> functions. A successful call claims the specified range of I/O ports in the registry for the
    caller's NIC.

Because the parameters passed to the 
    <b>NdisRaw<i>Xxx</i></b> have been mapped, these functions run significantly faster than the corresponding 
    <b>NdisImmediate..Port<i>Xxx</i></b>. After a successful call to 
    <b>NdisMRegisterIoPortRange</b>, a miniport driver cannot call any of the 
    <b>NdisImmediate..Port<i>Xxx</i></b> functions with either bus-relative addresses or mapped virtual addresses within such an I/O
    port range.

If its call to 
    <b>NdisMRegisterIoPortRange</b> fails, 
    <i>MiniportInitializeEx</i> should release all resources it already allocated for a NIC and, then, fail
    initialization for that NIC.

Drivers of NICs with device registers in the host memory space call 
    <b>NdisMMapIoSpace</b> and, subsequently, the 
    <b>NdisRead/WriteRegister<i>Xxx</i></b> functions to access the NIC registers.


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
Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   <a href="https://msdn.microsoft.com/5b57d289-0438-410c-81a5-9a8940988b5f">NdisMRegisterIoPortRange (NDIS
   5.1)</a>) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   <b>NdisMRegisterIoPortRange (NDIS
   5.1)</b>) in Windows XP.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Ndis.lib</dt>
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
<a href="devtest.ndis_irql_miniport_driver_function">Irql_Miniport_Driver_Function</a>, <a href="devtest.ndis_ndismregisterioportrange">NdisMRegisterIoPortRange</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="netvista.ndismderegisterioportrange">NdisMDeregisterIoPortRange</a>
</dt>
<dt>
<a href="netvista.ndismmapiospace">NdisMMapIoSpace</a>
</dt>
<dt>
<a href="netvista.ndisrawreadportbufferuchar">NdisRawReadPortBufferUchar</a>
</dt>
<dt>
<a href="netvista.ndisrawreadportbufferulong">NdisRawReadPortBufferUlong</a>
</dt>
<dt>
<a href="netvista.ndisrawreadportbufferushort">NdisRawReadPortBufferUshort</a>
</dt>
<dt>
<a href="netvista.ndisrawreadportuchar">NdisRawReadPortUchar</a>
</dt>
<dt>
<a href="netvista.ndisrawreadportulong">NdisRawReadPortUlong</a>
</dt>
<dt>
<a href="netvista.ndisrawreadportushort">NdisRawReadPortUshort</a>
</dt>
<dt>
<a href="netvista.ndisrawwriteportbufferuchar">NdisRawWritePortBufferUchar</a>
</dt>
<dt>
<a href="netvista.ndisrawwriteportbufferulong">NdisRawWritePortBufferUlong</a>
</dt>
<dt>
<a href="netvista.ndisrawwriteportbufferushort">NdisRawWritePortBufferUshort</a>
</dt>
<dt>
<a href="netvista.ndisrawwriteportuchar">NdisRawWritePortUchar</a>
</dt>
<dt>
<a href="netvista.ndisrawwriteportulong">NdisRawWritePortUlong</a>
</dt>
<dt>
<a href="netvista.ndisrawwriteportushort">NdisRawWritePortUshort</a>
</dt>
<dt>
<a href="netvista.ndisreadregisteruchar">NdisReadRegisterUchar</a>
</dt>
<dt>
<a href="netvista.ndisreadregisterulong">NdisReadRegisterUlong</a>
</dt>
<dt>
<a href="netvista.ndisreadregisterushort">NdisReadRegisterUshort</a>
</dt>
<dt>
<a href="netvista.ndiswriteregisteruchar">NdisWriteRegisterUchar</a>
</dt>
<dt>
<a href="netvista.ndiswriteregisterulong">NdisWriteRegisterUlong</a>
</dt>
<dt>
<a href="netvista.ndiswriteregisterushort">NdisWriteRegisterUshort</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NdisMRegisterIoPortRange function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

