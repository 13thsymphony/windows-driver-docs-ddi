---
UID: NF.ndis.NdisInitUnicodeString
title: NdisInitUnicodeString macro
author: windows-driver-content
description: The NdisInitUnicodeString function initializes a counted Unicode string.
old-location: netvista\ndisinitunicodestring.htm
old-project: NetVista
ms.assetid: 073feb91-48ae-4ad5-9061-117e6541021c
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: NdisInitUnicodeString
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisInitUnicodeString (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisInitUnicodeString (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisInitUnicodeString
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_Miscellaneous_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: See Remarks section
---

# NdisInitUnicodeString macro



## -description
The 
  <b>NdisInitUnicodeString</b> function initializes a counted Unicode string.



## -syntax

````
VOID NdisInitUnicodeString(
  [in, out] PNDIS_STRING DestinationString,
  [in]      PCWSTR       SourceString
);
````


## -parameters

### -param DestinationString [in, out]

A pointer to a caller-allocated NDIS_STRING type in which 
     <b>NdisInitUnicodeString</b> should store the counted Unicode string. For Windows 2000 and later, NDIS
     defines the NDIS_STRING type as a 
     <a href="kernel.unicode_string">UNICODE_STRING</a> type.


### -param SourceString [in]

A pointer to a null-terminated string with which to initialize the counted string.


## -remarks
The 
    <i>DestinationString</i> is initialized to point to the 
    <i>SourceString</i> . The 
    <b>Length</b> and 
    <b>MaximumLength</b> members of NDIS_STRING for the 
    <i>DestinationString</i> are initialized to the length of the string at 
    <i>SourceString</i>. If 
    <i>SourceString</i> is <b>NULL</b>, the length is zero.

Callers of 
    <b>NdisInitUnicodeString</b> must be running at IRQL &lt;= DISPATCH_LEVEL if the 
    <i>DestinationString</i> buffer is allocated from nonpaged memory. Usually, callers are running at IRQL =
    PASSIVE_LEVEL during driver initialization.


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
   <a href="https://msdn.microsoft.com/9eec98d4-3e4f-4e2c-9f8c-ff612d5de603">NdisInitUnicodeString (NDIS
   5.1)</a>) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   <b>NdisInitUnicodeString (NDIS
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
See Remarks section

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.ndis_irql_miscellaneous_function">Irql_Miscellaneous_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.driverentry_of_ndis_protocol_drivers">DriverEntry of NDIS Protocol
   Drivers</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="netvista.ndisansistringtounicodestring">
   NdisAnsiStringToUnicodeString</a>
</dt>
<dt>
<a href="netvista.ndisinitansistring">NdisInitAnsiString</a>
</dt>
<dt>
<a href="netvista.ndisinitializestring">NdisInitializeString</a>
</dt>
<dt>
<a href="netvista.ndisunicodestringtoansistring">
   NdisUnicodeStringToAnsiString</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a>
</dt>
<dt>
<a href="kernel.unicode_string">UNICODE_STRING</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NdisInitUnicodeString macro%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

