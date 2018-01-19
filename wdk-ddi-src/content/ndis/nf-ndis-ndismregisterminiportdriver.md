---
UID : NF:ndis.NdisMRegisterMiniportDriver
title : NdisMRegisterMiniportDriver function
author : windows-driver-content
description : A miniport driver calls the NdisMRegisterMiniportDriver function to register MiniportXxx entry points with NDIS as the first step in initialization.
old-location : netvista\ndismregisterminiportdriver.htm
old-project : netvista
ms.assetid : bed68aa8-499d-41fd-997b-a46316913cc8
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : NdisMRegisterMiniportDriver
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Universal
req.target-min-winverclnt : Supported in NDIS 6.0 and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : NdisMRegisterMiniportDriver
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


# NdisMRegisterMiniportDriver function
A miniport driver calls the 
  <b>NdisMRegisterMiniportDriver</b> function to register 
  <i>MiniportXxx</i> entry points with NDIS as the first step in initialization.

## Syntax

````
NDIS_STATUS NdisMRegisterMiniportDriver(
  _In_     PDRIVER_OBJECT                        DriverObject,
  _In_     PUNICODE_STRING                       RegistryPath,
  _In_opt_ NDIS_HANDLE                           MiniportDriverContext,
  _In_     PNDIS_MINIPORT_DRIVER_CHARACTERISTICS MiniportDriverCharacteristics,
  _Out_    PNDIS_HANDLE                          NdisMiniportDriverHandle
);
````

## Parameters

`DriverObject`

A pointer to an opaque driver object that the miniport driver received in its 
     <a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a> routine at the 
     <i>Argument1</i> parameter (see 
     <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff548818">DriverEntry of NDIS
     Miniport Drivers</a>).

`RegistryPath`

A pointer to an opaque registry path that the miniport driver received in its 
     <a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a> routine at the 
     <i>Argument2</i> parameter.

`MiniportDriverContext`

A handle to a driver-allocated context area where the driver maintains state and configuration
     information.

`MiniportDriverCharacteristics`

A pointer to an 
     <a href="..\ndis\ns-ndis-_ndis_miniport_driver_characteristics.md">
     NDIS_MINIPORT_DRIVER_CHARACTERISTICS</a> structure that the caller initialized.

`NdisMiniportDriverHandle`

A pointer to a caller-supplied handle variable. NDIS writes a handle to this variable that
     uniquely identifies this driver. The driver must save this handle for use in subsequent 
     <b>Ndis<i>Xxx</i></b> function calls.


## Return Value

<b>NdisMRegisterMiniportDriver</b> returns one of the following status values:
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
<a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a> registered the miniport driver successfully.
<dl>
<dt><b>NDIS_STATUS_BAD_CHARACTERISTICS</b></dt>
</dl>The 
       <i>CharacteristicsLength</i> parameter is incorrect for the NDIS version that is specified at the 
       <b>MajorNdisVersion</b> member in the structure at 
       <i>MiniportDriverCharacteristics</i> .
<dl>
<dt><b>NDIS_STATUS_BAD_VERSION</b></dt>
</dl>The 
       <b>MajorNdisVersion</b> or 
       <b>MinorNdisVersion</b> specified in the characteristics structure is invalid.
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>A shortage of resources, possibly memory, prevented NDIS from registering the caller.
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>This is a default error status, returned when none of the preceding errors caused the
       registration to fail.

## Remarks

An NDIS driver calls 
    <b>NdisMRegisterMiniportDriver</b> from its 
    <a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a> routine. For more information, see 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff548818">DriverEntry of NDIS
    Miniport Drivers</a>.

Every miniport driver exports a set of standard 
    <i>MiniportXxx</i> functions by setting up the characteristics structure and calling 
    <b>NdisMRegisterMiniportDriver</b>. NDIS copies the characteristics structure to NDIS internal storage.
    Therefore, after it has registered, a driver cannot change its 
    <i>MiniportXxx</i> entry points.

To register its virtual miniport interface, an NDIS intermediate drivers must call 
    <b>NdisMRegisterMiniportDriver</b> with the NDIS_INTERMEDIATE_DRIVER flag set in the structure at 
    <i>MiniportDriverCharacteristics</i> . NDIS drivers that have a WDM lower edge must call 
    <b>NdisMRegisterMiniportDriver</b> with the NDIS_WDM_DRIVER flag set in the structure at 
    <i>MiniportDriverCharacteristics</i> .

Drivers can register as a combined miniport driver and intermediate driver. To register its physical
    miniport driver, a miniport-intermediate driver calls 
    <b>NdisMRegisterMiniportDriver</b> with appropriate parameters just as for any miniport driver. To
    register its virtual miniport interface, the driver calls 
    <b>NdisMRegisterMiniportDriver</b> again, but with the NDIS_INTERMEDIATE_DRIVER flag set in the 
    <i>MiniportDriverCharacteristics</i> parameter.

To enable miniport drivers to register optional services, NDIS calls the 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff570269">MiniportSetOptions</a> function within
    the context of 
    <b>NdisMRegisterMiniportDriver</b>.

After a driver calls 
    <b>NdisMRegisterMiniportDriver</b>, the driver should be prepared to be called back at the 
    <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function that
    is specified in the 
    <i>MiniportDriverCharacteristics</i> parameter.

If an error occurs in 
    <a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a> after 
    <b>NdisMRegisterMiniportDriver</b> returns successfully, the driver must call the 
    <a href="..\ndis\nf-ndis-ndismderegisterminiportdriver.md">
    NdisMDeregisterMiniportDriver</a> function before 
    <b>DriverEntry</b> returns. If 
    <b>DriverEntry</b> succeeds, the driver must call 
    <b>NdisMDeregisterMiniportDriver</b> from its 
    <a href="..\ndis\nc-ndis-miniport_unload.md">MiniportDriverUnload</a> function.

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
<a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_unload.md">MiniportDriverUnload</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff570269">MiniportSetOptions</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_ndis_miniport_driver_characteristics.md">
   NDIS_MINIPORT_DRIVER_CHARACTERISTICS</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismderegisterminiportdriver.md">
   NdisMDeregisterMiniportDriver</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMRegisterMiniportDriver function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>