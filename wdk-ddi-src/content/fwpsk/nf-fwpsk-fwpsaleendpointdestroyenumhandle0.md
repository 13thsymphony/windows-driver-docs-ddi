---
UID: NF:fwpsk.FwpsAleEndpointDestroyEnumHandle0
title: FwpsAleEndpointDestroyEnumHandle0 function
author: windows-driver-content
description: The FwpsAleEndpointDestroyEnumHandle0 function destroys an endpoint enumeration handle that was created by calling FwpsAleEndpointCreateEnumHandle0.Note  FwpsAleEndpointDestroyEnumHandle0 is a specific version of FwpsAleEndpointDestroyEnumHandle.
old-location: netvista\fwpsaleendpointdestroyenumhandle0.htm
old-project: netvista
ms.assetid: 45ec429e-d324-40c9-bedc-acd75ccb160e
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: FwpsAleEndpointDestroyEnumHandle0, FwpsAleEndpointDestroyEnumHandle0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsAleEndpointDestroyEnumHandle0, netvista.fwpsaleendpointdestroyenumhandle0, wfp_ref_2_funct_3_fwps_A-B_3230abaf-8185-43b4-b46f-b1c1688ede2d.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 7.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Fwpkclnt.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	fwpkclnt.lib
-	fwpkclnt.dll
api_name:
-	FwpsAleEndpointDestroyEnumHandle0
product: Windows
targetos: Windows
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---


# FwpsAleEndpointDestroyEnumHandle0 function
The 
  <b>FwpsAleEndpointDestroyEnumHandle0</b> function destroys an endpoint enumeration handle that was created
  by calling 
  <a href="..\fwpsk\nf-fwpsk-fwpsaleendpointcreateenumhandle0.md">
  FwpsAleEndpointCreateEnumHandle0</a>.
<div class="alert"><b>Note</b>  <b>FwpsAleEndpointDestroyEnumHandle0</b> is a specific version of <b>FwpsAleEndpointDestroyEnumHandle</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## Syntax

````
NTSTATUS NTAPI FwpsAleEndpointDestroyEnumHandle0(
  _In_    HANDLE engineHandle,
  _Inout_ HANDLE enumHandle
);
````

## Parameters

`engineHandle`

The handle for an open session with the filter engine. This handle is obtained when a session is
     opened by calling 
     <a href="..\fwpmk\nf-fwpmk-fwpmengineopen0.md">FwpmEngineOpen0</a>.

`enumHandle`

The enumeration handle created by a previous call to 
     <a href="..\fwpsk\nf-fwpsk-fwpsaleendpointcreateenumhandle0.md">
     FwpsAleEndpointCreateEnumHandle0</a>.


## Return Value

The 
     <b>FwpsAleEndpointDestroyEnumHandle0</b> function returns one of the following NTSTATUS codes.

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

When endpoint enumeration is complete, the enumeration handle must be destroyed by calling 
    <b>FwpsAleEndpointDestroyEnumHandle0</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 7.  |
| **Target Platform** | Universal |
| **Header** | fwpsk.h (include Fwpsk.h) |
| **Library** | Fwpkclnt.lib |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\fwpsk\nf-fwpsk-fwpsaleendpointcreateenumhandle0.md">
     FwpsAleEndpointCreateEnumHandle0</a>