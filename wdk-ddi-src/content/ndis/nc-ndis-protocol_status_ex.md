---
UID: NC.ndis.PROTOCOL_STATUS_EX
title: PROTOCOL_STATUS_EX
author: windows-driver-content
description: The ProtocolStatusEx function indicates status-changes from underlying connectionless drivers or NDIS.Note  You must declare the function by using the PROTOCOL_STATUS_EX type.
old-location: netvista\protocolstatusex.htm
old-project: NetVista
ms.assetid: 5bc5a24f-5f28-4502-8776-b1cf15fd8283
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: RxNameCacheInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ProtocolStatusEx
req.alt-loc: Ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
---

# PROTOCOL_STATUS_EX callback



## -description
The 
  <i>ProtocolStatusEx</i> function indicates status-changes from underlying connectionless drivers or
  NDIS.



## -prototype

````
PROTOCOL_STATUS_EX ProtocolStatusEx;

VOID ProtocolStatusEx(
  _In_ NDIS_HANDLE             ProtocolBindingContext,
  _In_ PNDIS_STATUS_INDICATION StatusIndication
)
{ ... }
````


## -parameters

### -param ProtocolBindingContext [in]

A handle to a context area that the protocol driver allocated. The protocol driver maintains the
     per-binding context information in this context area. The driver supplied this handle to NDIS when the
     driver called the 
     <a href="netvista.ndisopenadapterex">NdisOpenAdapterEx</a> function.


### -param StatusIndication [in]

A pointer to an 
     <a href="netvista.ndis_status_indication">NDIS_STATUS_INDICATION</a> structure
     that contains the status information.


## -returns
None


## -remarks
A call to 
    <i>ProtocolStatusEx</i> notifies the protocol driver about changes in status of an underlying driver.

To determine link status, use the status indications from underlying drivers instead of OID queries.
    These status indications will improve system performance and avoid possible race conditions.

NDIS calls the 
    <i>ProtocolStatusEx</i> function of all bound protocol drivers when an underlying driver is resetting a
    NIC. First NDIS specifies the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff567420">NDIS_STATUS_RESET_START</a> code and
    later, when the reset operation is complete, NDIS specifies the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff567419">NDIS_STATUS_RESET_END</a> code.

NDIS will not accept send requests and OID requests for a miniport adapter while a reset operation is
    in progress, the NDIS_STATUS_RESET_START notification warns bound protocol drivers to stop such requests
    on the affected binding until they receive the corresponding NDIS_STATUS_RESET_END notification.

NDIS calls 
    <i>ProtocolStatusEx</i> at IRQL &lt;= DISPATCH_LEVEL.

To define a <i>ProtocolStatusEx</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolStatusEx</i> function that is named "MyStatusEx", use the <b>PROTOCOL_STATUS_EX</b> type as shown in this code example:

Then, implement your function as follows:

The <b>PROTOCOL_STATUS_EX</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_STATUS_EX</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported in NDIS 6.0 and later.

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
&lt;= DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport_reset.md">MiniportResetEx</a>
</dt>
<dt>
<a href="netvista.ndis_status_indication">NDIS_STATUS_INDICATION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567419">NDIS_STATUS_RESET_END</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567420">NDIS_STATUS_RESET_START</a>
</dt>
<dt>
<a href="netvista.ndisopenadapterex">NdisOpenAdapterEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20PROTOCOL_STATUS_EX callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

