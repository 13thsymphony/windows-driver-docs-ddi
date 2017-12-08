---
UID: NC.ndkpi.NDK_FN_SRQ_NOTIFICATION_CALLBACK
title: NDK_FN_SRQ_NOTIFICATION_CALLBACK
author: windows-driver-content
description: The NdkSrqNotificationCallback (NDK_FN_SRQ_NOTIFICATION_CALLBACK) function provides NDK shared receive queue (SRQ) notifications from an NDK provider.
old-location: netvista\ndk_fn_srq_notification_callback.htm
old-project: netvista
ms.assetid: 3063F991-DDC5-4E52-979B-6CFCD11A604C
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS, NDIS_WWAN_VISIBLE_PROVIDERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndkpi.h
req.include-header: Ndkpi.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdkSrqNotificationCallback
req.alt-loc: ndkpi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
---

# NDK_FN_SRQ_NOTIFICATION_CALLBACK callback



## -description
The <i>NdkSrqNotificationCallback</i> (<i>NDK_FN_SRQ_NOTIFICATION_CALLBACK</i>) function provides NDK shared receive queue (SRQ) notifications from an NDK provider.


## -prototype

````
NDK_FN_SRQ_NOTIFICATION_CALLBACK NdkSrqNotificationCallback;

VOID NdkSrqNotificationCallback(
  _In_opt_ PVOID    SrqNotificationContext,
  _In_     NTSTATUS SrqStatus
)
{ ... }
````


## -parameters

### -param SrqNotificationContext [in, optional]

A context area that was specified in the <i>SrqNotificationContext</i> parameter of the <i>NdkCreateSrq</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_srq.md">NDK_FN_CREATE_SRQ</a>) function when the SRQ  object was created.

### -param SrqStatus [in]

Indicates if a fatal SRQ error occurred. The following status codes are defined:


<table>
<tr>
<th>Term</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<a id="STATUS_SUCCESS"></a><a id="status_success"></a>STATUS_SUCCESS
</td>
<td width="60%">
The SRQ is operating normally.

</td>
</tr>
<tr>
<td width="40%">
<a id="STATUS_INTERNAL_ERROR"></a><a id="status_internal_error"></a>STATUS_INTERNAL_ERROR
</td>
<td width="60%">
A catastrophic error occurred on the SRQ. The SRQ is unusable. All of the associated queue pairs (QPs) are also unusable. No future completions will be reported. This error usually indicates a hardware error.
</td>
</tr>
</table>
 

## -returns
None

## -remarks
An NDK provider calls the <i>NdkSrqNotificationCallback</i> function when the number of receive requests that are queued on the SRQ falls below the minimum number of queued receive requests (<i>NotifyThreshold</i>). The   <i>NotifyThreshold</i> is an input parameter to the <i>NdkCreateSrq</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_srq.md">NDK_FN_CREATE_SRQ</a>)  and <i>NdkModifySrq</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_modify_srq.md">NDK_FN_MODIFY_SRQ</a>)  functions.

## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client
</th>
<td width="70%">
None supported
</td>
</tr>
<tr>
<th width="30%">
Minimum supported server
</th>
<td width="70%">
Windows Server 2012
</td>
</tr>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Supported in NDIS 6.30 and later.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ndkpi.h (include Ndkpi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
&lt;=DISPATCH_LEVEL
</td>
</tr>
</table>