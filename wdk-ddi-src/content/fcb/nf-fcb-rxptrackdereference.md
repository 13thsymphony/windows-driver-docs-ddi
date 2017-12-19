---
UID: NF.fcb.RxpTrackDereference
title: RxpTrackDereference function
author: windows-driver-content
description: RxpTrackDereference is used in checked builds to track requests to dereference SRV_CALL, NET_ROOT, V_NET_ROOT, FOBX, FCB, and SRV_OPEN structures in checked builds. A log of these dereference requests can be accessed by the logging system and WMI.
old-location: ifsk\rxptrackdereference.htm
old-project: ifsk
ms.assetid: eaff92d2-d866-4096-8528-0672255ced60
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: RxpTrackDereference
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fcb.h
req.include-header: Fcb.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RxpTrackDereference
req.alt-loc: fcb.h
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
---

# RxpTrackDereference function



## -description
<b>RxpTrackDereference</b> is used in checked builds to track requests to dereference SRV_CALL, NET_ROOT, V_NET_ROOT, FOBX, FCB, and SRV_OPEN structures in checked builds. A log of these dereference requests can be accessed by the logging system and WMI. 



## -syntax

````
BOOLEAN RxpTrackDereference(
  _In_ ULONG TraceType,
  _In_ PCSTR FileName,
  _In_ ULONG Line,
  _In_ PVOID pInstance
);
````


## -parameters

### -param TraceType [in]

The value that determines which dereference request type is tracked. This value can be one of the following macros defined in <i>fcb.h</i>:




### -param RDBSS_REF_TRACK_SRVCALL

A dereference request on a SRV_CALL structure.


### -param RDBSS_REF_TRACK_NETROOT

A dereference request on a NET_ROOT structure.


### -param RDBSS_REF_TRACK_VNETROOT

A dereference request on a V_NET_ROOT structure.


### -param RDBSS_REF_TRACK_NETFOBX

A dereference request on an FOBX structure.


### -param RDBSS_REF_TRACK_NETFCB

A dereference request on an FCB structure.


### -param RDBSS_REF_TRACK_SRVOPEN

A dereference request on a SRV_OPEN structure.

</dd>
</dl>

### -param FileName [in]

The name of the source file where this routine was called.


### -param Line [in]

The line number in the source file where this routine was called.


### -param pInstance [in]

A pointer to the structure to be dereferenced.


## -returns
<b>RxpTrackDereference</b> always returns <b>TRUE</b> on checked builds. 


## -remarks
In checked builds, <b>RxpTrackDereference</b> is used to track requests to dereference SRV_CALL, NET_ROOT, V_NET_ROOT, FOBX, FCB, and SRV_OPEN structures. For retail builds, this function does nothing.

If WMI is enabled, a log of the dereference requests is sent as a WMI event to user-mode WMI components that have requested notification. The deference request is also logged to the RDBSS logging system by calling the <b>_RxLog</b> routine to record an I/O error log entry if logging is enabled. 

Note that this routine does not actually dereference the structure passed (decrement the reference count on the structure).

A number of macros are defined in <i>fcb.h</i> for debugging that are the preferred way to call this routine. These macros provide a wrapper around the <b>RxReference</b> or <b>RxDereference</b> routines used for file structure management operations on SRV_CALL, NET_ROOT, V_NET_ROOT, FOBX, FCB, and SRV_OPEN structures. These macros first call the corresponding <b>RxpTrackDereference</b> routine to log diagnostic information about the request before calling the corresponding <b>RxDereference</b> routine.


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
<dt>Fcb.h (include Fcb.h)</dt>
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
<a href="ifsk.rxassert">RxAssert</a>
</dt>
<dt>
<a href="ifsk.rxdbgbreakpoint">RxDbgBreakPoint</a>
</dt>
<dt>
<a href="ifsk.rxdereference">RxDereference</a>
</dt>
<dt>
<a href="ifsk.rxreference">RxReference</a>
</dt>
<dt>
<a href="ifsk.rxptrackreference">RxpTrackReference</a>
</dt>
<dt>
<a href="ifsk._rxlog">_RxLog</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxpTrackDereference function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

