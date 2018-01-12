---
UID: NF:fwpsk.FwpsAleEndpointSetSecurityInfo0
title: FwpsAleEndpointSetSecurityInfo0 function
author: windows-driver-content
description: The FwpsAleEndpointSetSecurityInfo0 function sets security information about the application layer enforcement (ALE) endpoint enumeration session.Note  FwpsAleEndpointSetSecurityInfo0 is a specific version of FwpsAleEndpointSetSecurityInfo.
old-location: netvista\fwpsaleendpointsetsecurityinfo0.htm
old-project: netvista
ms.assetid: 7b7fed83-dcf8-466d-8bd7-42a5ed15cced
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: FwpsAleEndpointSetSecurityInfo0
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
req.alt-api: FwpsAleEndpointSetSecurityInfo0
req.alt-loc: fwpkclnt.lib,fwpkclnt.dll
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
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---

# FwpsAleEndpointSetSecurityInfo0 function



## -description
The 
  <b>FwpsAleEndpointSetSecurityInfo0</b> function sets security information about the application layer
  enforcement (ALE) endpoint enumeration session.



## -syntax

````
NTSTATUS NTAPI FwpsAleEndpointSetSecurityInfo0(
  _In_           HANDLE               engineHandle,
  _In_           SECURITY_INFORMATION securityInfo,
  _In_opt_ const SID                  *sidOwner,
  _In_opt_ const SID                  *sidGroup,
  _In_opt_ const ACL                  *dacl,
  _In_opt_ const ACL                  *sacl
);
````


## -parameters

### -param engineHandle [in]

A handle for an open session with the filter engine. This handle is obtained when a session is
     opened by calling 
     <a href="..\fwpmk\nf-fwpmk-fwpmengineopen0.md">FwpmEngineOpen0</a>.


### -param securityInfo [in]

A set of security information flags. For more information, see the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff556635">SECURITY_INFORMATION</a> description in the
     Installable File Systems driver documentation.


### -param sidOwner [in, optional]

The security identifier of the security owner.


### -param sidGroup [in, optional]

The security identifier of the security group.


### -param dacl [in, optional]

The discretionary access control list.


### -param sacl [in, optional]

The system access control list.


## -returns
The 
     <b>FwpsAleEndpointSetSecurityInfo0</b> function returns one of the following NTSTATUS codes.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The function succeeded.
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred.

 


## -remarks


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
Available starting with Windows 7.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Fwpsk.h (include Fwpsk.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Fwpkclnt.lib</dt>
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
</table>

## -see-also
<dl>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpsaleendpointenum0.md">FwpsAleEndpointEnum0</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpsaleendpointgetbyid0.md">FwpsAleEndpointGetById0</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpsaleendpointgetsecurityinfo0.md">
   FwpsAleEndpointGetSecurityInfo0</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsAleEndpointSetSecurityInfo0 function%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

