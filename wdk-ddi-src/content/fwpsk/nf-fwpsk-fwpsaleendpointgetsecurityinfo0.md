---
UID : NF:fwpsk.FwpsAleEndpointGetSecurityInfo0
title : FwpsAleEndpointGetSecurityInfo0 function
author : windows-driver-content
description : The FwpsAleEndpointGetSecurityInfo0 function retrieves security information about the application layer enforcement (ALE) endpoint enumeration session.Note  FwpsAleEndpointGetSecurityInfo0 is a specific version of FwpsAleEndpointGetSecurityInfo.
old-location : netvista\fwpsaleendpointgetsecurityinfo0.htm
old-project : netvista
ms.assetid : 0c825695-7fef-4eb1-8615-f41c526aa32d
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : fwpsk/FwpsAleEndpointGetSecurityInfo0, wfp_ref_2_funct_3_fwps_A-B_83803cc6-94be-4b32-8b33-2d12cec31e9e.xml, FwpsAleEndpointGetSecurityInfo0 function [Network Drivers Starting with Windows Vista], netvista.fwpsaleendpointgetsecurityinfo0, FwpsAleEndpointGetSecurityInfo0
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


# FwpsAleEndpointGetSecurityInfo0 function
The 
  <b>FwpsAleEndpointGetSecurityInfo0</b> function retrieves security information about the application layer
  enforcement (ALE) endpoint enumeration session.
<div class="alert"><b>Note</b>  <b>FwpsAleEndpointGetSecurityInfo0</b> is a specific version of <b>FwpsAleEndpointGetSecurityInfo</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## Syntax

````
NTSTATUS NTAPI FwpsAleEndpointGetSecurityInfo0(
  _In_  HANDLE               engineHandle,
  _In_  SECURITY_INFORMATION securityInfo,
  _Out_ PSID                 *sidOwner,
  _Out_ PSID                 *sidGroup,
  _Out_ PACL                 *dacl,
  _Out_ PACL                 *sacl,
  _Out_ PSECURITY_DESCRIPTOR *securityDescriptor
);
````

## Parameters

`engineHandle`

A handle for an open session with the filter engine. This handle is obtained when a session is
     opened by calling 
     <a href="..\fwpmk\nf-fwpmk-fwpmengineopen0.md">FwpmEngineOpen0</a>.

`securityInfo`

A set of security information flags. For more information, see the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff556635">SECURITY_INFORMATION</a> description in the
     Installable File Systems driver documentation.

`sidOwner`

The security identifier of the security owner.

`sidGroup`

The security identifier of the security group.

`dacl`

The discretionary access control list.

`sacl`

The system access control list.

`securityDescriptor`

The security descriptor structure.


## Return Value

The 
     <b>FwpsAleEndpointGetSecurityInfo0</b> function returns one of the following NTSTATUS codes.
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

<a href="..\fwpsk\nf-fwpsk-fwpsaleendpointgetbyid0.md">FwpsAleEndpointGetById0</a>

<a href="..\fwpsk\nf-fwpsk-fwpsaleendpointenum0.md">FwpsAleEndpointEnum0</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsAleEndpointGetSecurityInfo0 function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>