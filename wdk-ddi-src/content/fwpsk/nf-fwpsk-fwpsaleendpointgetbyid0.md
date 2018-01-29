---
UID : NF:fwpsk.FwpsAleEndpointGetById0
title : FwpsAleEndpointGetById0 function
author : windows-driver-content
description : The FwpsAleEndpointGetById0 function retrieves information about an application layer enforcement (ALE) endpoint.Note  FwpsAleEndpointGetById0 is a specific version of FwpsAleEndpointGetById.
old-location : netvista\fwpsaleendpointgetbyid0.htm
old-project : netvista
ms.assetid : fa9a5078-d254-4b4a-bbfb-256491beff5f
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : fwpsk/FwpsAleEndpointGetById0, FwpsAleEndpointGetById0 function [Network Drivers Starting with Windows Vista], FwpsAleEndpointGetById0, wfp_ref_2_funct_3_fwps_A-B_3feb07cf-ae5a-4412-a51a-8e4d4d65c31d.xml, netvista.fwpsaleendpointgetbyid0
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : fwpsk.h
req.include-header : Fwpsk.h
req.target-type : Universal
req.target-min-winverclnt : Available starting with Windows 7.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Fwpkclnt.lib
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : FWPS_VSWITCH_EVENT_TYPE
---


# FwpsAleEndpointGetById0 function
The 
  <b>FwpsAleEndpointGetById0</b> function retrieves information about an application layer enforcement (ALE)
  endpoint.
<div class="alert"><b>Note</b>  <b>FwpsAleEndpointGetById0</b> is a specific version of <b>FwpsAleEndpointGetById</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## Syntax

````
NTSTATUS NTAPI FwpsAleEndpointGetById0(
  _In_  HANDLE                        engineHandle,
  _In_  UINT64                        endpointId,
  _Out_ FWPS_ALE_ENDPOINT_PROPERTIES0 **properties
);
````

## Parameters

`engineHandle`

A handle for an open session with the filter engine. This handle is obtained when a session is
     opened by calling 
     <a href="..\fwpmk\nf-fwpmk-fwpmengineopen0.md">FwpmEngineOpen0</a>.

`endpointId`

The unique endpoint identifier.

`properties`

A pointer to an 
     <mshelp:link keywords="netvista.fwps_ale_endpoint_properties0" tabindex="0"><b>
     FWPS_ALE_ENDPOINT_PROPERTIES0</b></mshelp:link> structure that contains the properties of the endpoint.


## Return Value

The 
     <b>FwpsAleEndpointGetById0</b> function returns one of the following NTSTATUS codes.
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The function succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
An error occurred.

</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | fwpsk.h (include Fwpsk.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<mshelp:link keywords="netvista.fwpsaleendpointsetsecurityinfo0" tabindex="0"><b>
   FwpsAleEndpointSetSecurityInfo0</b></mshelp:link>

<a href="..\fwpsk\nf-fwpsk-fwpsaleendpointenum0.md">FwpsAleEndpointEnum0</a>

<mshelp:link keywords="netvista.fwpsaleendpointgetsecurityinfo0" tabindex="0"><b>
   FwpsAleEndpointGetSecurityInfo0</b></mshelp:link>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsAleEndpointGetById0 function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>