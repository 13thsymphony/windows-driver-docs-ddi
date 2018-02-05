---
UID : NF:fwpsk.FwpsAleEndpointEnum0
title : FwpsAleEndpointEnum0 function
author : windows-driver-content
description : The FwpsAleEndpointEnum0 function enumerates application layer enforcement (ALE) endpoints.Note  FwpsAleEndpointEnum0 is a specific version of FwpsAleEndpointEnum.
old-location : netvista\fwpsaleendpointenum0.htm
old-project : netvista
ms.assetid : 8b3257ea-9eeb-426b-8c82-a4f0242861a8
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : fwpsk/FwpsAleEndpointEnum0, netvista.fwpsaleendpointenum0, FwpsAleEndpointEnum0, wfp_ref_2_funct_3_fwps_A-B_daf596f9-09c1-4e1c-8869-8c6aec4da6cd.xml, FwpsAleEndpointEnum0 function [Network Drivers Starting with Windows Vista]
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


# FwpsAleEndpointEnum0 function
The 
  <b>FwpsAleEndpointEnum0</b> function enumerates application layer enforcement (ALE) endpoints.
<div class="alert"><b>Note</b>  <b>FwpsAleEndpointEnum0</b> is a specific version of <b>FwpsAleEndpointEnum</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## Syntax

````
NTSTATUS NTAPI FwpsAleEndpointEnum0(
  _In_  HANDLE                        engineHandle,
  _In_  HANDLE                        enumHandle,
  _In_  UINT32                        numEntriesRequested,
  _Out_ FWPS_ALE_ENDPOINT_PROPERTIES0 ***entries,
  _Out_ UINT32                        *numEntriesReturned
);
````

## Parameters

`engineHandle`

The handle for an open session with the filter engine. This handle is obtained when a session is
     opened by calling 
     <a href="..\fwpmk\nf-fwpmk-fwpmengineopen0.md">FwpmEngineOpen0</a>.

`enumHandle`

The enumeration handle created by a previous call to 
     <a href="..\fwpsk\nf-fwpsk-fwpsaleendpointdestroyenumhandle0.md">FwpsAleEndpointDestroyEnumHandle0</a>.

`numEntriesRequested`

The maximum number of endpoint property entries to return. The actual number of entries enumerated
     is returned in 
     <i>numEntriesReturned</i>. The actual number is less than the requested number only if fewer endpoints
     than the requested are present.

`entries`

A pointer to an array of 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff551218">FWPS_ALE_ENDPOINT_PROPERTIES0</a> structure pointers. Each structure contains the properties of a
     single endpoint. The array contains as many elements as the value returned in 
     <i>numEntriesReturned</i>.

`numEntriesReturned`

On return, the number of elements in the array of endpoint property structures pointed to by 
     <i>entries</i>.


## Return Value

The 
     <b>FwpsAleEndpointEnum0</b> function returns one of the following NTSTATUS codes.
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

## Remarks

To enumerate ALE endpoints, the callout driver must first obtain an enumeration handle by calling 
    <a href="..\fwpsk\nf-fwpsk-fwpsaleendpointcreateenumhandle0.md">FwpsAleEndpointCreateEnumHandle0</a>. The handle returned is associated with any parameters specified
    in the optional 
    <i>enumTemplate</i> parameter of 
    <b>FwpsAleEndpointCreateEnumHandle0</b>.

After obtaining a handle, the callout driver can call 
    <b>FwpsAleEndpointEnum0</b> to get information about the endpoints that match the enumeration parameters
    of the handle.

When finished examining endpoint properties, the callout driver must call 
    <a href="..\fwpsk\nf-fwpsk-fwpsaleendpointdestroyenumhandle0.md">FwpsAleEndpointDestroyEnumHandle0</a> to release the system resources associated with the enumeration
    handle.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 7. Available starting with Windows 7. |
| **Target Platform** | Universal |
| **Header** | fwpsk.h (include Fwpsk.h) |
| **Library** | Fwpkclnt.lib |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\fwpsk\nf-fwpsk-fwpsaleendpointcreateenumhandle0.md">
   FwpsAleEndpointCreateEnumHandle0</a>

<a href="..\fwpsk\nf-fwpsk-fwpsaleendpointgetsecurityinfo0.md">
   FwpsAleEndpointGetSecurityInfo0</a>

<a href="..\fwpsk\nf-fwpsk-fwpsaleendpointdestroyenumhandle0.md">
   FwpsAleEndpointDestroyEnumHandle0</a>

<a href="..\fwpsk\nf-fwpsk-fwpsaleendpointgetbyid0.md">FwpsAleEndpointGetById0</a>

<a href="..\fwpsk\nf-fwpsk-fwpsaleendpointsetsecurityinfo0.md">
   FwpsAleEndpointSetSecurityInfo0</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsAleEndpointEnum0 function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>