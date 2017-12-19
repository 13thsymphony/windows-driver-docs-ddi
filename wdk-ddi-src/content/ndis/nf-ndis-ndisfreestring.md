---
UID: NF.ndis.NdisFreeString
title: NdisFreeString macro
author: windows-driver-content
description: The NdisFreeString function releases storage that was allocated by NdisInitializeString for a buffered string.
old-location: netvista\ndisfreestring.htm
old-project: NetVista
ms.assetid: 62b4318a-b883-44fc-a2a5-86a7a884f039
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: NdisFreeString
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for existing drivers in  NDIS 6.0 and later, but new drivers should use RtlFreeAnsiString or RtlFreeUnicodeString  instead.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisFreeString
req.alt-loc: ndis.h
req.ddi-compliance: Irql_Miscellaneous_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
---

# NdisFreeString macro



## -description
The 
  <b>NdisFreeString</b> function releases storage that was allocated by 
  <a href="netvista.ndisinitializestring">NdisInitializeString</a> for a buffered
  string.



## -syntax

````
VOID NdisFreeString(
  [in] NDIS_STRING String
);
````


## -parameters

### -param String [in]

An NDIS_STRING type value that describes the string to free. For Windows 2000 and later, NDIS
     defines the NDIS_STRING type as a 
     <a href="kernel.unicode_string">UNICODE_STRING</a> type.


## -remarks
An NDIS driver typically calls the 
    <a href="netvista.ndisinitializestring">NdisInitializeString</a> function during
    initialization--for example, to set up names passed to the 
    <b>Ndis<i>Xxx</i>Configuration</b> functions. For each call that the driver makes to 
    <b>NdisInitializeString</b>, the driver must make a corresponding call to 
    <b>NdisFreeString</b>. When releasing string buffers that were allocated during initialization, a driver
    must call 
    <b>NdisFreeString</b> before the driver's initialization function returns control.

<b>NdisFreeString</b> must be used only for freeing buffers that were allocated with 
    <b>NdisInitializeString</b>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported for existing drivers in  NDIS 6.0 and later, but new drivers should use <a href="kernel.rtlfreeansistring">RtlFreeAnsiString</a> or <a href="kernel.rtlfreeunicodestring">RtlFreeUnicodeString</a>  instead.

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
<a href="devtest.ndis_irql_miscellaneous_function">Irql_Miscellaneous_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.ansi_string">ANSI_STRING</a>
</dt>
<dt>
<a href="netvista.driverentry_of_ndis_protocol_drivers">DriverEntry of NDIS Protocol
   Drivers</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="netvista.ndisopenadapterex">NdisOpenAdapterEx</a>
</dt>
<dt>
<a href="netvista.ndisregisterprotocoldriver">NdisRegisterProtocolDriver</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a>
</dt>
<dt>
<a href="kernel.rtlinitstring">RtlInitString</a>
</dt>
<dt>
<a href="kernel.rtlinitunicodestring">RtlInitUnicodeString</a>
</dt>
<dt>
<a href="kernel.rtlunicodestringtoansistring">RtlUnicodeStringToAnsiString</a>
</dt>
<dt>
<a href="kernel.unicode_string">UNICODE_STRING</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NdisFreeString macro%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

