---
UID: NF.ndis.NdisMCmDeleteVc
title: NdisMCmDeleteVc function
author: windows-driver-content
description: NdisMCmDeleteVc destroys a caller-created VC.
old-location: netvista\ndismcmdeletevc.htm
old-project: NetVista
ms.assetid: b55d0995-efd8-4a61-85e9-970559e21a88
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: NdisMCmDeleteVc
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMCmDeleteVc (NDIS 5.1)) in   Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMCmDeleteVc (NDIS 5.1)) in   Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisMCmDeleteVc
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_MCM_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
---

# NdisMCmDeleteVc function



## -description
<b>NdisMCmDeleteVc</b> destroys a caller-created VC.



## -syntax

````
NDIS_STATUS NdisMCmDeleteVc(
  _In_ NDIS_HANDLE NdisVcHandle
);
````


## -parameters

### -param NdisVcHandle [in]

Specifies the handle identifying the VC to be deleted. The caller originally obtained this handle
     from 
     <a href="netvista.ndismcmcreatevc">NdisMCmCreateVc</a>.


## -returns
<b>NdisMCmDeleteVc</b> can return one of the following:
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>NDIS deleted the VC.
<dl>
<dt><b>NDIS_STATUS_NOT_ACCEPTED</b></dt>
</dl>The VC is still active, so it could not be deleted.

 


## -remarks
When an MCM driver calls 
    <b>NdisMCmDeleteVc</b>, there must be no outstanding calls on the given VC and that VC must have been
    deactivated. To meet these requirements implies that the MCM driver has already called 
    <a href="netvista.ndismcmdeactivatevc">NdisMCmDeactivateVc</a> with the given 
    <i>NdisVcHandle</i> successfully.

Only the driver that created a particular VC can delete that VC. A call to 
    <b>NdisMCmDeleteVc</b> causes NDIS to call the 
    <a href="..\ndis\nc-ndis-protocol_co_delete_vc.md">ProtocolCoDeleteVc</a> function of the
    client with which the caller shares the 
    <i>NdisVcHandle</i> .

When 
    <b>NdisMCmDeleteVc</b> returns control, the 
    <i>NdisVcHandle</i> is no longer valid. The MCM driver can release the resources it allocated to maintain
    state about the deleted VC or prepare them for reuse in a subsequent incoming-call notification after it
    calls 
    <a href="netvista.ndismcmcreatevc">NdisMCmCreateVc</a>.

The driver writer determines whether an MCM driver has an (internal) 
    <a href="..\ndis\nc-ndis-miniport_co_delete_vc.md">MiniportCoDeleteVc</a> function that the
    driver calls in the context of tearing down connections for outgoing and incoming calls.

Only connection-oriented miniport drivers that provide integrated call-management support can call 
    <b>NdisMCmDeleteVc</b>. Stand-alone call managers and clients, which register themselves with NDIS as
    protocol drivers, call 
    <b>NdisCoDeleteVc</b> instead.


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
Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   <a href="https://msdn.microsoft.com/library/windows/hardware/ff553362">NdisMCmDeleteVc (NDIS 5.1)</a>) in
   Windows Vista. Supported for NDIS 5.1 drivers (see 
   <b>NdisMCmDeleteVc (NDIS 5.1)</b>) in
   Windows XP.

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
&lt;= DISPATCH_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.ndis_irql_mcm_function">Irql_MCM_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport_co_delete_vc.md">MiniportCoDeleteVc</a>
</dt>
<dt>
<a href="netvista.ndisclclosecall">NdisClCloseCall</a>
</dt>
<dt>
<a href="netvista.ndiscodeletevc">NdisCoDeleteVc</a>
</dt>
<dt>
<a href="netvista.ndismcmdeactivatevc">NdisMCmDeactivateVc</a>
</dt>
<dt>
<a href="netvista.ndismcmcreatevc">NdisMCmCreateVc</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_co_delete_vc.md">ProtocolCoDeleteVc</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NdisMCmDeleteVc function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

