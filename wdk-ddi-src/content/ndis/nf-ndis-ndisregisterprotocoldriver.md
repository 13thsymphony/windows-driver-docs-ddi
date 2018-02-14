---
UID: NF:ndis.NdisRegisterProtocolDriver
title: NdisRegisterProtocolDriver function
author: windows-driver-content
description: A protocol driver calls the NdisRegisterProtocolDriver function to register its ProtocolXxx functions with NDIS.
old-location: netvista\ndisregisterprotocoldriver.htm
old-project: netvista
ms.assetid: b48571eb-13a2-4541-80ac-c8d31f378d37
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: protocol_ndis_functions_ref_023b338a-65cf-4ccb-bce8-d1506f37f632.xml, NdisRegisterProtocolDriver, netvista.ndisregisterprotocoldriver, ndis/NdisRegisterProtocolDriver, NdisRegisterProtocolDriver function [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Protocol_Driver_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisRegisterProtocolDriver
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---


# NdisRegisterProtocolDriver function
A protocol driver calls the
  <b>NdisRegisterProtocolDriver</b> function to register its 
  <i>ProtocolXxx</i> functions with NDIS.

## Syntax

````
NDIS_STATUS NdisRegisterProtocolDriver(
  _In_opt_ NDIS_HANDLE                           ProtocolDriverContext,
  _In_     PNDIS_PROTOCOL_DRIVER_CHARACTERISTICS ProtocolCharacteristics,
  _Out_    PNDIS_HANDLE                          NdisProtocolHandle
);
````

## Parameters

`ProtocolDriverContext`

A handle to a driver-allocated context area where the driver maintains state and configuration
     information.

`ProtocolCharacteristics`

A pointer to an 
     <a href="..\ndis\ns-ndis-_ndis_protocol_driver_characteristics.md">
     NDIS_PROTOCOL_DRIVER_CHARACTERISTICS</a> structure that the protocol driver created and initialized
     with its 
     <i>ProtocolXxx</i> function entry points.

`NdisProtocolHandle`

A pointer to a caller-supplied handle variable. NDIS writes a handle to this variable that
     uniquely identifies the driver that is registering. The driver must save this handle for use in
     subsequent 
     <b>Ndis<i>Xxx</i></b> function calls.


## Return Value

<b>NdisRegisterProtocolDriver</b> returns one of the following status values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">

<a href="..\ndis\nf-ndis-ndisregisterprotocoldriver.md">NdisRegisterProtocolDriver</a> returns NDIS_STATUS_SUCCESS if it registered the protocol
       driver.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_BAD_VERSION</b></dt>
</dl>
</td>
<td width="60%">
The version specified in the 
       <b>MajorNdisVersion</b> member of the structure at 
       <i>ProtocolCharacteristics</i> is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_BAD_CHARACTERISTICS</b></dt>
</dl>
</td>
<td width="60%">
Some members of the structure at the 
       <i>ProtocolCharacteristics</i> parameter are invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">

<a href="..\ndis\nf-ndis-ndisregisterprotocoldriver.md">NdisRegisterProtocolDriver</a> failed due to insufficient resources.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">

<a href="..\ndis\nf-ndis-ndisregisterprotocoldriver.md">NdisRegisterProtocolDriver</a> returns NDIS_STATUS_FAILURE if none of the preceding values
       applies.

</td>
</tr>
</table>

## Remarks

A protocol driver calls the 
    <b>NdisRegisterProtocolDriver</b> function from its 
    <a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a> routine. For more information about 
    <b>DriverEntry</b>, see 
    <a href="https://msdn.microsoft.com/en-us/library/gg156036.aspx">DriverEntry of NDIS
    Protocol Drivers</a>.

Drivers that call <b>
    NdisRegisterProtocolDriver</b> must be prepared for an immediate call to any of their <i>ProtocolXxx</i> functions.

Every protocol driver exports a set of 
    <i>ProtocolXxx</i> functions by setting up the 
    <a href="..\ndis\ns-ndis-_ndis_protocol_driver_characteristics.md">
    NDIS_PROTOCOL_DRIVER_CHARACTERISTICS</a> structure and calling 
    <b>NdisRegisterProtocolDriver</b>. NDIS copies this structure to the NDIS library's internal storage.

To allow protocol drivers to register optional services, NDIS calls the 
    <a href="..\ndis\nc-ndis-set_options.md">ProtocolSetOptions</a> function within
    the context of 
    <b>NdisRegisterProtocolDriver</b>.

Protocol drivers call the 
    <a href="..\ndis\nf-ndis-ndisderegisterprotocoldriver.md">
    NdisDeregisterProtocolDriver</a> function to release resources that were previously allocated with 
    <b>NdisRegisterProtocolDriver</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.0 and later. Supported in NDIS 6.0 and later. |
| **Target Platform** | Desktop |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | Irql_Protocol_Driver_Function |

## See Also

<a href="https://msdn.microsoft.com/en-us/library/gg156036.aspx">DriverEntry of NDIS Protocol
   Drivers</a>



<a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a>



<a href="..\ndis\ns-ndis-_ndis_protocol_driver_characteristics.md">
   NDIS_PROTOCOL_DRIVER_CHARACTERISTICS</a>



<a href="..\ndis\nf-ndis-ndisderegisterprotocoldriver.md">NdisDeregisterProtocolDriver</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisRegisterProtocolDriver function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>