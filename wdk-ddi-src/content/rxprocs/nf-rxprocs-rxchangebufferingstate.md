---
UID: NF:rxprocs.RxChangeBufferingState
title: RxChangeBufferingState function
author: windows-driver-content
description: RxChangeBufferingState is called to process a buffering state change request.
old-location: ifsk\rxchangebufferingstate.htm
old-project: ifsk
ms.assetid: 83e181cd-bbec-4142-8d97-4f67285b6bb4
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: RxChangeBufferingState
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rxprocs.h
req.include-header: Rxprocs.h, Struchdr.h, Fcb.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RxChangeBufferingState
req.alt-loc: rxprocs.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= APC_LEVEL
req.typenames: RX_CONTEXT, *PRX_CONTEXT
req.product: Windows 10 or later.
---

# RxChangeBufferingState function



## -description
<b>RxChangeBufferingState</b> is called to process a buffering state change request.



## -syntax

````
NTSTATUS RxChangeBufferingState(
   PSRV_OPEN SrvOpen,
   PVOID     Context,
   BOOLEAN   ComputeNewState
);
````


## -parameters

### -param SrvOpen 

A pointer to the SRV_OPEN data structure to be changed.


### -param Context 

A pointer to the context parameter for use by the network mini-redirector callback. 


### -param ComputeNewState 

The value that indicates if the new buffering state is to be computed. When this value is set to <b>TRUE</b>, the new buffering state is determined by calling the network mini-redirector to compute the new buffering state. When this value is <b>FALSE</b>, the new buffering state is determined by the <i>BufferingFlags</i> member of the passed in <i>SrvOpen</i> structure.


## -returns
<b>RxChangeBufferingState</b> always returns STATUS_SUCCESS whether this routine was successful or if an error occurs. If an error occurs, the buffering state is changed so that no buffering is enabled.


## -remarks
If local buffering is disabled for this FCB (FCB_STATE_DISABLE_LOCAL_BUFFERING is set in the FcbState structure member of the FCB), this will disable local buffering independent of the open mode on the FCB and any default buffering options. When FCB_STATE_DISABLE_LOCAL_BUFFERING is set, the new buffering state set by <b>RxChangeBufferingState</b> will be to disable all buffering.

If <i>ComputeNewState</i> is <b>TRUE</b>, then the <b>MRxComputeNewBufferingState</b> routine exported by the network mini-redirector is called to compute the new buffering state to use.

If the FCB is acquired exclusively and <i>ComputeNewState</i> is <b>FALSE</b>. then <b>RxChangeBufferingState</b> will set the following buffering state options:

FCB_STATE_WRITECACHING_ENABLED

FCB_STATE_FILESIZECACHEING_ENABLED

FCB_STATE_FILETIMECACHEING_ENABLED

FCB_STATE_WRITEBUFFERING_ENABLED

FCB_STATE_LOCK_BUFFERING_ENABLED

FCB_STATE_READBUFFERING_ENABLED

FCB_STATE_READCACHING_ENABLED

To acquire the FCB exclusively requires that the FCB must not be opened with any of the following values:

ShareAccess.SharedRead

ShareAccess.SharedWrite

ShareAccess.SharedDelete

RDBSS does not currently use a number of possible buffering options, so these options are ignored internally by RDBSS when they are set off using <b>RxChangeBufferingState</b>. These ignored buffering options include the following:

FCB_STATE_OPENSHARING_ENABLED

FCB_STATE_COLLAPSING_ENABLED

If the FCB_STATE_WRITECACHING_ENABLED buffering state is changed to off, any FCB in the system cache is flushed. 

On exit from <b>RxChangeBufferingState</b>, there is no change in resource ownership. 


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
<dt>Rxprocs.h (include Rxprocs.h, Struchdr.h, or Fcb.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= APC_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\rxprocs\nf-rxprocs-rxindicatechangeofbufferingstate.md">RxIndicateChangeOfBufferingState</a>
</dt>
<dt>
<a href="..\rxprocs\nf-rxprocs-rxindicatechangeofbufferingstateforsrvopen.md">RxIndicateChangeOfBufferingStateForSrvOpen</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/6cf4c6f6-a21f-4919-92b5-2403b650d8d0">The SRV_OPEN Structure</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxChangeBufferingState function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

