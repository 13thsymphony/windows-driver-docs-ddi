---
UID: NC.ndkpi.NDK_FN_READ
title: NDK_FN_READ
author: windows-driver-content
description: The NdkRead (NDK_FN_READ) function posts a read request on an NDK queue pair (QP).
old-location: netvista\ndk_fn_read.htm
old-project: netvista
ms.assetid: A6D2C017-0D50-4AD7-9241-110C97F5FE92
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: NDIS_WWAN_VISIBLE_PROVIDERS, NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS
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
req.alt-api: NdkRead
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
req.iface: 
---

# NDK_FN_READ callback



## -description
<p>The <i>NdkRead</i> (<i>NDK_FN_READ</i>) function posts a read request on an NDK queue pair (QP).</p>


## -prototype

````
NDK_FN_READ NdkRead;

NTSTATUS NdkRead(
  _In_     NDK_QP                         *pNdkQp,
  _In_opt_ PVOID                          RequestContext,
           _In_reads_(nSge) CONST NDK_SGE *pSgl,
  _In_     ULONG                          nSge,
  _In_     UINT64                         RemoteAddress,
  _In_     UINT32                         RemoteToken,
  _In_     ULONG                          Flags
)
{ ... }
````


## -parameters
<dl>

### -param <i>pNdkQp</i> [in]

<dd>
<p>A pointer to an NDK queue pair (QP) object (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439933">NDK_QP</a>).</p>
</dd>

### -param <i>RequestContext</i> [in, optional]

<dd>
<p>A context value to be returned in the <b>RequestContext</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439935">NDK_RESULT</a> structure for this request.
</p>
</dd>

### -param <i>pSgl</i> 

<dd>
<p>An array of SGE structures (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439936">NDK_SGE</a>) that represent the buffers to place incoming data into.</p>
</dd>

### -param <i>nSge</i> [in]

<dd>
<p>The number of SGE structures in the array  that is specified in the <i>pSgl</i>
parameter.</p>
</dd>

### -param <i>RemoteAddress</i> [in]

<dd>
<p>A remote address to read from that is presented in the local host's byte order. The NDK consumer can   add  an offset  to the remotely-provided value.
</p>
</dd>

### -param <i>RemoteToken</i> [in]

<dd>
<p>A remotely-provided memory token that  is an opaque array of bytes from the NDK consumer.</p>
</dd>

### -param <i>Flags</i> [in]

<dd>
<p>A bitwise OR of flags which specifies the operations that are allowed. The following flags are supported:</p>
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="NDK_OP_FLAG_SILENT_SUCCESS"></a><a id="ndk_op_flag_silent_success"></a><dl>

### -param <b>NDK_OP_FLAG_SILENT_SUCCESS</b>


### -param 0x00000001

</dl>
</td>
<td width="60%">
<p>Indicates the successful completion of this request does not generate a completion event in the outbound completion queue. However, requests that fail do generate an event in the completion queue.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="NDK_OP_FLAG_READ_FENCE"></a><a id="ndk_op_flag_read_fence"></a><dl>

### -param <b>NDK_OP_FLAG_READ_FENCE</b>


### -param 0x00000002

</dl>
</td>
<td width="60%">
<p>Indicates that all prior read requests must be complete before the hardware begins processing this request.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="NDK_OP_FLAG_RDMA_READ_LOCAL_INVALIDATE"></a><a id="ndk_op_flag_rdma_read_local_invalidate"></a><dl>

### -param <b>NDK_OP_FLAG_RDMA_READ_LOCAL_INVALIDATE</b>


### -param 0x00000200

</dl>
</td>
<td width="60%">
<p>If this flag is set and the provider also reports <b>NDK_ADAPTER_FLAG_RDMA_READ_LOCAL_INVALIDATE_SUPPORTED</b> adapter capability in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439851">NDK_ADAPTER_INFO</a> structure, successful completion of the <i>NdkRead</i> function means that the first buffer specified in the <i>pSgl</i> parameter is invalidated. Unsuccessful completion leaves the buffer and token in an undefined state. This flag is ignored if the provider does not report <b>NDK_ADAPTER_FLAG_RDMA_READ_LOCAL_INVALIDATE_SUPPORTED</b> adapter capability in the <b>NDK_ADAPTER_INFO</b> structure.</p>
<p><b>Note</b>  This flag is supported only in NDKPI 1.2 (Windows Server 2012 R2) and later.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="NDK_OP_FLAG_DEFER"></a><a id="ndk_op_flag_defer"></a><dl>

### -param <b>NDK_OP_FLAG_DEFER</b>


### -param 0x00000200

</dl>
</td>
<td width="60%">
<p>Indicates to the NDK provider that it may defer indicating the request to hardware for processing. For more information about this flag, see <a href="NULL">NDKPI Deferred Processing Scheme</a>.</p>
<p><b>Note</b>  This flag is supported only in NDKPI 1.2 (Windows Server 2012 R2) and later.</p>
</td>
</tr>
</table>
<p> </p>
</dd>
</dl>

## -returns
<p>The 
     <i>NdkRead</i> function returns one of the following NTSTATUS codes.</p><dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl><p>The request was posted successfully. A completion entry will be queued to the CQ when the work request is completed.
</p><dl>
<dt><b>STATUS_CONNECTION_INVALID</b></dt>
</dl><p>The QP is not connected.</p><dl>
<dt><b>STATUS_REMOTE_RESOURCES</b></dt>
</dl><p>	The request tried to read beyond the size of the remote memory.
</p><dl>
<dt><b>Other status codes</b></dt>
</dl><p>An error occurred. </p>

<p> </p>

## -remarks
<p><i>NdkRead</i> posts a read request on a queue pair (QP).</p>

<p><i>NdkRead</i> posts a read request on a queue pair (QP).</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>None supported</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in NDIS 6.30 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndkpi.h (include Ndkpi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;=DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439858">NDK_FN_ARM_CQ</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439851">NDK_ADAPTER_INFO</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439933">NDK_QP</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439935">NDK_RESULT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439936">NDK_SGE</a>
</dt>
<dt>
<a href="NULL">NDKPI Deferred Processing Scheme</a>
</dt>
<dt>
<a href="NULL">NDKPI Work Request Posting Requirements</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_FN_READ callback function%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
