---
UID : NF:ndis.NdisMDeregisterIoPortRange
title : NdisMDeregisterIoPortRange function
author : windows-driver-content
description : NdisMDeregisterIoPortRange releases a mapping that was set up with NdisMRegisterIoPortRange during driver initialization.
old-location : netvista\ndismderegisterioportrange.htm
old-project : netvista
ms.assetid : b5b6a608-af1f-4030-b83a-a6f64ff3a264
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : NdisMDeregisterIoPortRange
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Universal
req.target-min-winverclnt : Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMDeregisterIoPortRange   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMDeregisterIoPortRange   (NDIS 5.1)) in Windows XP.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : NdisMDeregisterIoPortRange
req.alt-loc : ndis.lib,ndis.dll
req.ddi-compliance : Irql_Miniport_Driver_Function
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ndis.lib
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisMDeregisterIoPortRange function
<b>NdisMDeregisterIoPortRange</b> releases a mapping that was set up with 
  <a href="..\ndis\nf-ndis-ndismregisterioportrange.md">NdisMRegisterIoPortRange</a> during
  driver initialization.

## Syntax

````
VOID NdisMDeregisterIoPortRange(
  _In_ NDIS_HANDLE MiniportAdapterHandle,
  _In_ UINT        InitialPort,
  _In_ UINT        NumberOfPorts,
  _In_ PVOID       PortOffset
);
````

## Parameters

`MiniportAdapterHandle`

Specifies the handle input to 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>.

`InitialPort`

Specifies the bus-relative address of the first port in the range of ports.

`NumberOfPorts`

Specifies the number of ports in the range.

`PortOffset`

Specifies the mapped base port address returned by 
     <b>NdisMRegisterIoPortRange</b>.


## Return Value

None

## Remarks

The miniport driver must pass the same 
    <i>InitialPort</i> and 
    <i>NumberOfPorts</i> to 
    <b>NdisMDeregisterIoPortRange</b> that were passed when 
    <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> called 
    <a href="..\ndis\nf-ndis-ndismregisterioportrange.md">NdisMRegisterIoPortRange</a> to get
    the mapped 
    <i>PortOffset</i> value. That is, a miniport driver cannot call 
    <b>NdisMDeregisterIoPortRange</b> to release a subrange of a mapped port range.

<b>NdisMDeregisterIoPortRange</b> can be called from the 
    <i>MiniportInitializeEx</i> or 
    <a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a> functions only if 
    <i>MiniportInitializeEx</i> previously made a successful call to 
    <b>NdisMRegisterIoPortRange</b>.

<b>NdisMDeregisterIoPortRange</b> also releases the driver's claim on the I/O port range in the
    registry.

After it calls 
    <b>NdisMRegisterIoPortRange</b>, the miniport driver can no longer access the NIC's port range with calls
    to the 
    <b>NdisRaw..Port<i>Xxx</i></b> functions.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndis.h (include Ndis.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | Irql_Miniport_Driver_Function |

## See Also

<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismregisterioportrange.md">NdisMRegisterIoPortRange</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMDeregisterIoPortRange function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>