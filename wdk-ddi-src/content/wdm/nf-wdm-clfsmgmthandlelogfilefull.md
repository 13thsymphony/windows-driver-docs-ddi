---
UID: NF.wdm.ClfsMgmtHandleLogFileFull
title: ClfsMgmtHandleLogFileFull
author: windows-driver-content
description: The ClfsMgmtHandleLogFileFull routine attempts to make more space available in a log. It might make more space available by adding containers to the log, or it might ask clients to move their log tails.
old-location: kernel\clfsmgmthandlelogfilefull.htm
old-project: kernel
ms.assetid: acfd28c9-c6d5-4768-b095-488f174d78c0
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: ClfsMgmtHandleLogFileFull
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ClfsMgmtHandleLogFileFull
req.alt-loc: Clfs.sys,Ext-MS-Win-fs-clfs-l1-1-0.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Clfs.lib
req.dll: Clfs.sys
req.irql: <= APC_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# ClfsMgmtHandleLogFileFull function



## -description
<p>The <b>ClfsMgmtHandleLogFileFull</b> routine attempts to make more space available in a log. It might make more space available by adding containers to the log, or it might ask clients to move their log tails.</p>


## -syntax

````
NTSTATUS ClfsMgmtHandleLogFileFull(
  _In_ CLFS_MGMT_CLIENT Client
);
````


## -parameters
<dl>

### -param <i>Client</i> [in]

<dd>
<p>The client that is requesting CLFS management to make space available in the log. The value of this parameter should be the <b>CLFS_MGMT_CLIENT</b> structure that is obtained through a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541642">ClfsMgmtRegisterManagedClient</a> routine.</p>
</dd>
</dl>

## -returns
<p>The <b>ClfsMgmtHandleLogFileFull</b> routine returns one of the following NTSTATUS values:</p><dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl><p>The client is not managing a log.</p><dl>
<dt><b>STATUS_INVALID_PARAMETER_1</b></dt>
</dl><p>The value that was supplied for the <i>Client</i> parameter either was <b>NULL</b> or does not represent a valid client.</p><dl>
<dt><b>STATUS_LOG_FULL_HANDLER_IN_PROGRESS</b></dt>
</dl><p>CLFS management is already attempting to resolve a log file full condition for this client.</p><dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl><p>CLFS management was not able to process the request.</p><dl>
<dt><b>STATUS_PENDING</b></dt>
</dl><p>CLFS management is processing the request to create space in the log. </p><dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl><p>The requested amount of space is available in the log.</p>

<p> </p>

## -remarks
<p>To make more space available in the log, the <b>ClfsMgmtHandleLogFileFull</b> routine first tries to add more containers to the log in accordance with the growth rate, new container size, and maximum size policies. If more containers cannot be added, then the <b>ClfsMgmtHandleLogFileFull</b> routine tries to free existing space by invoking one or more clients' <a href="https://msdn.microsoft.com/library/windows/hardware/ff540776">ClfsAdvanceTailCallback</a> functions.</p>

<p>If the <b>ClfsMgmtHandleLogFileFull</b> routine returns STATUS_PENDING, the client's <a href="https://msdn.microsoft.com/library/windows/hardware/ff541562">ClfsLogGrowthCompleteCallback</a> function will be called when the request to make space in the log has been completed.</p>

<p>If the <b>ClfsMgmtHandleLogFileFull</b> routine returns STATUS_LOG_FULL_HANDLER_IN_PROGRESS, the client has already requested CLFS management to handle a log file full condition. The client's <a href="https://msdn.microsoft.com/library/windows/hardware/ff541562">ClfsLogGrowthCompleteCallback</a> function will not be called a second time.</p>

<p>If the <b>ClfsMgmtHandleLogFileFull</b> routine returns STATUS_SUCCESS, the call completed synchronously, and the client's <a href="https://msdn.microsoft.com/library/windows/hardware/ff541562">ClfsLogGrowthCompleteCallback</a> function will not be invoked.</p>

<p>If the <b>ClfsMgmtHandleLogFileFull</b> routine returns STATUS_PENDING, then CLFS management is in the process of trying to free space in the log, and will call the client's <a href="https://msdn.microsoft.com/library/windows/hardware/ff541562">ClfsLogGrowthCompleteCallback</a> function when the log file full condition has been handled. If the log is pinned, CLFS management will call the client's <i>ClfsLogGrowthCompleteCallback</i> function with the <i>LogIsPinned</i> parameter set to <b>TRUE</b> before the <b>ClfsMgmtHandleLogFileFull</b> routine returns STATUS_PENDING.</p>

<p>To make more space available in the log, the <b>ClfsMgmtHandleLogFileFull</b> routine first tries to add more containers to the log in accordance with the growth rate, new container size, and maximum size policies. If more containers cannot be added, then the <b>ClfsMgmtHandleLogFileFull</b> routine tries to free existing space by invoking one or more clients' <a href="https://msdn.microsoft.com/library/windows/hardware/ff540776">ClfsAdvanceTailCallback</a> functions.</p>

<p>If the <b>ClfsMgmtHandleLogFileFull</b> routine returns STATUS_PENDING, the client's <a href="https://msdn.microsoft.com/library/windows/hardware/ff541562">ClfsLogGrowthCompleteCallback</a> function will be called when the request to make space in the log has been completed.</p>

<p>If the <b>ClfsMgmtHandleLogFileFull</b> routine returns STATUS_LOG_FULL_HANDLER_IN_PROGRESS, the client has already requested CLFS management to handle a log file full condition. The client's <a href="https://msdn.microsoft.com/library/windows/hardware/ff541562">ClfsLogGrowthCompleteCallback</a> function will not be called a second time.</p>

<p>If the <b>ClfsMgmtHandleLogFileFull</b> routine returns STATUS_SUCCESS, the call completed synchronously, and the client's <a href="https://msdn.microsoft.com/library/windows/hardware/ff541562">ClfsLogGrowthCompleteCallback</a> function will not be invoked.</p>

<p>If the <b>ClfsMgmtHandleLogFileFull</b> routine returns STATUS_PENDING, then CLFS management is in the process of trying to free space in the log, and will call the client's <a href="https://msdn.microsoft.com/library/windows/hardware/ff541562">ClfsLogGrowthCompleteCallback</a> function when the log file full condition has been handled. If the log is pinned, CLFS management will call the client's <i>ClfsLogGrowthCompleteCallback</i> function with the <i>LogIsPinned</i> parameter set to <b>TRUE</b> before the <b>ClfsMgmtHandleLogFileFull</b> routine returns STATUS_PENDING.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Clfs.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>Clfs.sys</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= APC_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541642">ClfsMgmtRegisterManagedClient</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540776">ClfsAdvanceTailCallback</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541562">ClfsLogGrowthCompleteCallback</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ClfsMgmtHandleLogFileFull routine%20 RELEASE:%20(11/20/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
