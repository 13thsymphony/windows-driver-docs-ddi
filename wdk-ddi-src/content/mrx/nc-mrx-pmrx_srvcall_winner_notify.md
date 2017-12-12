---
UID: NC.mrx.PMRX_SRVCALL_WINNER_NOTIFY
title: PMRX_SRVCALL_WINNER_NOTIFY
author: windows-driver-content
description: The MRxSrvCallWinnerNotify routine is called by RDBSS to notify a network mini-redirector that it was chosen when multiple redirectors could fulfill the request.
old-location: ifsk\mrxsrvcallwinnernotify.htm
old-project: ifsk
ms.assetid: 6853b73e-5516-485e-ade4-54b7faf6bb1d
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
req.alt-api: MRxSrvCallWinnerNotify
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

# PMRX_SRVCALL_WINNER_NOTIFY callback



## -description
The<i> MRxSrvCallWinnerNotify</i> routine is called by <a href="ifsk.the_rdbss_driver_and_library">RDBSS</a> to notify a network mini-redirector that it was chosen when multiple redirectors could fulfill the request. 



## -prototype

````
PMRX_SRVCALL_WINNER_NOTIFY MRxSrvCallWinnerNotify;

NTSTATUS MRxSrvCallWinnerNotify(
  _Inout_ PMRX_SRV_CALL pSrvCall,
  _In_    BOOLEAN       ThisMinirdrIsTheWinner,
  _Inout_ PVOID         pSrvCallContext
)
{ ... }
````


## -parameters

### -param pSrvCall [in, out]

A pointer to the SRV_CALL structure. 


### -param ThisMinirdrIsTheWinner [in]

A Boolean value that indicates that this network mini-redirector was chosen.


### -param pSrvCallContext [in, out]

A pointer to an SRV_CALL structure that is created by the network mini-redirector.


## -returns
<i>MRxSmbSrvCallWinnerNotify</i> returns STATUS_SUCCESS on success. 


## -remarks
<i>MRxSrvCallWinnerNotify</i> was originally designed to be called by RDBSS to notify a network mini-redirector that it was chosen when multiple redirectors could fulfill the request. The chosen network mini-redirector is expected to create the SRV_CALL structure and establish a connection with the server.

The network mini-redirector should complete the context for the SRV_CALL structure. If the network mini-redirector supports case-insensitive names for NET_ROOT structures and for filenames, then the SRV_CALL <b>Flags</b> member should set the bits for SRVCALL_FLAG_CASE_INSENSITIVE_NETROOTS and SRVCALL_FLAG_CASE_INSENSITIVE_FILENAMES.

Under the current implementation of RDBSS, each network mini-redirector has its own copy of RDBSS, so there are no competing network redirectors at the RDBSS layer. All network mini-redirectors will receive a call to <i>MRxSrvCallWinnerNotify</i> with the <i>ThisMinirdrIsTheWinner</i> parameter set to <b>TRUE</b> after receiving a call to <a href="ifsk.mrxcreatesrvcall">MRxCreateSrvCall</a> to create the SRV_CALL structure. 

When multiple redirectors are installed for handling the same UNC namespace, the redirector to service a request is chosen by multiple UNC provider (MUP) based on the order of redirectors specified in the registry. 


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
<a href="ifsk.mrxcreatesrvcall">MRxCreateSrvCall</a>
</dt>
<dt>
<a href="ifsk.mrxcreatevnetroot">MRxCreateVNetRoot</a>
</dt>
<dt>
<a href="ifsk.mrxextractnetrootname">MRxExtractNetRootName</a>
</dt>
<dt>
<a href="ifsk.mrxfinalizenetroot">MRxFinalizeNetRoot</a>
</dt>
<dt>
<a href="ifsk.mrxfinalizevnetroot">MRxFinalizeVNetRoot</a>
</dt>
<dt>
<a href="ifsk.rxfinalizesrvcall">RxFinalizeSrvCall</a>
</dt>
<dt>
<a href="ifsk.mrxpreparsename">MRxPreparseName</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20MRxSrvCallWinnerNotify routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

