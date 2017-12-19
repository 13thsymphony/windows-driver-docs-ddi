---
UID: NC.ndkpi.NDK_FN_ARM_CQ
title: NDK_FN_ARM_CQ
author: windows-driver-content
description: The NdkArmCq (NDK_FN_ARM_CQ) function arms an NDK completion queue (CQ) notification.
old-location: netvista\ndk_fn_arm_cq.htm
old-project: NetVista
ms.assetid: 8204EC7B-8F90-4F34-BFFB-9F1574AF69BC
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _NDIS_WWAN_VISIBLE_PROVIDERS, NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS, PNDIS_WWAN_VISIBLE_PROVIDERS
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
req.alt-api: NdkArmCq
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

# NDK_FN_ARM_CQ callback



## -description
The <i>NdkArmCq</i> (<i>NDK_FN_ARM_CQ</i>) function arms an NDK completion queue (CQ) notification. 



## -prototype

````
NDK_FN_ARM_CQ NdkArmCq;

VOID NdkArmCq(
  _In_ NDK_CQ *pNdkCq,
  _In_ ULONG  Type
)
{ ... }
````


## -parameters

### -param pNdkCq [in]

A pointer to an NDK completion queue object (<a href="netvista.ndk_cq">NDK_CQ</a>).



### -param Type [in]

The type of notification to arm. The following notification types are defined:



<table>
<tr>
<th>Term</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<a id="NDK_CQ_NOTIFY_ERRORS"></a><a id="ndk_cq_notify_errors"></a>NDK_CQ_NOTIFY_ERRORS

</td>
<td width="60%">
Notify if there are any completion queue errors such as a completion queue overrun or catastrophic failure.

</td>
</tr>
<tr>
<td width="40%">
<a id="NDK_CQ_NOTIFY_ANY"></a><a id="ndk_cq_notify_any"></a>NDK_CQ_NOTIFY_ANY

</td>
<td width="60%">
Notify of the next successful completion in the completion queue.

</td>
</tr>
<tr>
<td width="40%">
<a id="NDK_CQ_NOTIFY_SOLICITED"></a><a id="ndk_cq_notify_solicited"></a>NDK_CQ_NOTIFY_SOLICITED

</td>
<td width="60%">
Notify when the completion queue receives a send request that includes the ND_OP_FLAG_SEND_AND_SOLICIT_EVENT flag.

</td>
</tr>
</table>
 


## -returns
None


## -remarks
After the NDK consumer arms a completion queue (CQ) notification, the provider calls the <i>NdkCqNotificationCallback</i> callback function (the <a href="..\ndkpi\nc-ndkpi-ndk_fn_cq_notification_callback.md">NDK_FN_CQ_NOTIFICATION_CALLBACK</a> routine that the consumer  specified when the CQ was created with the <i>NdkCreateCq</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_cq.md">NDK_FN_CREATE_CQ</a>) function) when the specified type of notification is due.

If the CQ is closed while a call to <i>NdkCqNotificationCallback</i> is in-progress, the close request will remain pending until <i>NdkCqNotificationCallback</i> returns control  to the provider. After the close request is completed, the provider will not call  <i>NdkCqNotificationCallback</i>.


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

## -see-also
<dl>
<dt>
<a href="netvista.ndk_cq">NDK_CQ</a>
</dt>
<dt>
<a href="netvista.ndk_cq_dispatch">NDK_CQ_DISPATCH</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_cq_notification_callback.md">NDK_FN_CQ_NOTIFICATION_CALLBACK</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_cq.md">NDK_FN_CREATE_CQ</a>
</dt>
<dt>
<a href="netvista.ndkpi_completion_handling_requirements">NDKPI Completion Handling Requirements</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NDK_FN_ARM_CQ callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

