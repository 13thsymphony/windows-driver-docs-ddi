---
UID: NC.mrx.PMRX_GET_CONNECTION_ID
title: PMRX_GET_CONNECTION_ID
author: windows-driver-content
description: TheMRxGetConnectionId routine is called by RDBSS to request that a network mini-redirector return a connection ID, which can be used for handling multiple sessions.
old-location: ifsk\mrxgetconnectionid.htm
old-project: ifsk
ms.assetid: c994060c-d8b3-4daa-a0dd-a734ffe34229
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: _SetDSMCounters_IN, *PSetDSMCounters_IN, SetDSMCounters_IN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: mrx.h
req.include-header: Mrx.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MRxGetConnectionId
req.alt-loc: mrx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
---

# PMRX_GET_CONNECTION_ID callback



## -description
The<i>MRxGetConnectionId</i> routine is called by <a href="ifsk.the_rdbss_driver_and_library">RDBSS</a> to request that a network mini-redirector return a connection ID, which can be used for handling multiple sessions. 


## -prototype

````
PMRX_GET_CONNECTION_ID MRxGetConnectionId;

NTSTATUS MRxGetConnectionId(
  _Inout_ PRX_CONTEXT       RxContext,
  _Inout_ PRX_CONNECTION_ID UniqueId
)
{ ... }
````


## -parameters

### -param RxContext [in, out]

A pointer to the RX_CONTEXT structure. This parameter contains the IRP that is requesting the operation. 

### -param UniqueId [in, out]

A pointer to the connection ID when the routine returns. 

## -returns
<i>MRxGetConnectionId</i> returns STATUS_SUCCESS on success or an appropriate NTSTATUS value, such as the following: 
<dl>
<dt><b>STATUS_NOT_IMPLEMENTED</b></dt>
</dl>This routine is not implemented. 

 

## -remarks
<i>MRxGetConnectionId</i> is called by RDBSS when trying to find or construct a V_NET_ROOT structure. 

If connection IDs are supported by the network mini-redirector, then the returned connection ID is appended to the NET_ROOT structure name stored in the NetName table used by RDBSS for storing network names. RDBSS considers the connection ID as an opaque blob, and does a byte-by-byte comparison of the connection ID blob while looking up the NetName table for a given name with a connection ID. 

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
Header
</th>
<td width="70%">
<dl>
<dt>Mrx.h (include Mrx.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.mrxcompletebufferingstatechangerequest">MRxCompleteBufferingStateChangeRequest</a>
</dt>
<dt>
<a href="ifsk.mrxcomputenewbufferingstate">MRxComputeNewBufferingState</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20MRxGetConnectionId routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
