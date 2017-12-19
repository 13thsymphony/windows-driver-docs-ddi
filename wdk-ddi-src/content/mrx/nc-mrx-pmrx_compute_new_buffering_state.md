---
UID: NC.mrx.PMRX_COMPUTE_NEW_BUFFERING_STATE
title: PMRX_COMPUTE_NEW_BUFFERING_STATE
author: windows-driver-content
description: TheMRxComputeNewBufferingState routine is called by RDBSS to request that the network mini-redirector compute a new buffering state change.
old-location: ifsk\mrxcomputenewbufferingstate.htm
old-project: ifsk
ms.assetid: d47cbcab-8682-4c7f-b651-3d1e0f78dc0c
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _SetDSMCounters_IN, *PSetDSMCounters_IN, SetDSMCounters_IN, PSetDSMCounters_IN
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
req.alt-api: MRxComputeNewBufferingState
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

# PMRX_COMPUTE_NEW_BUFFERING_STATE callback



## -description
The<i>MRxComputeNewBufferingState</i> routine is called by <a href="ifsk.the_rdbss_driver_and_library">RDBSS</a> to request that the network mini-redirector compute a new buffering state change. 



## -prototype

````
PMRX_COMPUTE_NEW_BUFFERING_STATE MRxComputeNewBufferingState;

NTSTATUS MRxComputeNewBufferingState(
  _Inout_ PMRX_SRV_OPEN SrvOpen,
  _In_    PVOID         MRxContext,
  _Out_   PULONG        NewBufferingState
)
{ ... }
````


## -parameters

### -param SrvOpen [in, out]

A pointer to the SRV_OPEN structure and the associated FCB structure.


### -param MRxContext [in]

A pointer to a context parameter for use by the network mini-redirector callback.


### -param NewBufferingState [out]

A pointer to where the new buffering state is stored when the routine returns. 


## -returns
<i>MRxComputeNewBufferingState</i> returns STATUS_SUCCESS on success or an appropriate NTSTATUS value, such as the following: 
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>A feature that is requested is not supported. 

 


## -remarks
Before calling <i>MRxComputeNewBufferingState</i>, RDBSS sets the <b>FcbState</b> member of <i>SrvOpen</i><i>-&gt;Fcb</i> to FCB_STATE_BUFFERSTATE_CHANGING. 

The Server Message Block (SMB) redirector uses <i>MRxComputeNewBufferingState</i> to map the SMB-specific oplock levels into the appropriate RDBSS buffering state flags. The oplock level is passed in the <i>MrxContext</i> parameter.


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
<a href="ifsk.mrxgetconnectionid">MRxGetConnectionId</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20MRxComputeNewBufferingState routine%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

