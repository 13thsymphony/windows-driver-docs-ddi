---
UID: NC.wdm.PCLFS_CLIENT_LOG_UNPINNED_CALLBACK
title: PCLFS_CLIENT_LOG_UNPINNED_CALLBACK
author: windows-driver-content
description: The ClfsLogUnpinnedCallback function implements any actions that the client will take when a log that had previously been pinned becomes unpinned.
old-location: kernel\clfslogunpinnedcallback.htm
old-project: kernel
ms.assetid: f28a1ad6-4946-4d1e-b430-2cdee3dfd835
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _WDI_TYPE_PMK_NAME, WDI_TYPE_PMK_NAME, PWDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in Windows Server 2003 R2, Windows Vista, and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ClfsLogUnpinnedCallback
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Called at IRQL <= APC_LEVEL
req.product: Windows 10 or later.
---

# PCLFS_CLIENT_LOG_UNPINNED_CALLBACK callback



## -description
The <i>ClfsLogUnpinnedCallback</i> function implements any actions that the client will take when a log that had previously been pinned becomes unpinned.



## -prototype

````
VOID ClfsLogUnpinnedCallback(
  _In_ PLOG_FILE_OBJECT LogFile,
  _In_ PVOID            ClientData
);
````


## -parameters

### -param LogFile [in]

A pointer to a <a href="kernel.log_file_object">LOG_FILE_OBJECT</a> structure that represents the CLFS log stream whose tail has become unpinned.


### -param ClientData [in]

A pointer to client-supplied information. You specify this data in the <b>LogUnpinnedCallbackData</b> member of the <a href="kernel.clfs_mgmt_client_registration">CLFS_MGMT_CLIENT_REGISTRATION</a> structure.


## -returns
None


## -remarks
If a client called the <a href="kernel.clfsmgmthandlelogfilefull">ClfsMgmtHandleLogFileFull</a> routine and CLFS management subsequently called the client's <a href="..\wdm\nc-wdm-pclfs_client_lff_handler_complete_callback.md">ClfsLogGrowthCompleteCallback</a> function with a value of <b>TRUE</b> for the <i>LogIsPinned</i> parameter, then the <i>ClfsLogUnpinnedCallback</i> function will be invoked when the log becomes unpinned. 

When a client uses the <a href="kernel.clfsmgmtregistermanagedclient">ClfsMgmtRegisterManagedClient</a> routine to register with CLFS management, the client provides both a pointer to the <i>ClfsLogUnpinnedCallback</i> function and the custom data that will be passed as a parameter to the <i>ClfsLogUnpinnedCallback</i> function when this function is called.

The <i>ClfsLogUnpinnedCallback</i> function should only perform a minimal amount of processing before returning. For example, it might create and queue a work item to inform the client that it can resume processing.

The <i>ClfsLogGrowthCompleteCallback</i> function is called before the <i>ClfsLogUnpinnedCallback</i> function.


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
Supported in Windows Server 2003 R2, Windows Vista, and later versions of Windows.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
Called at IRQL &lt;= APC_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.clfs_mgmt_client_registration">CLFS_MGMT_CLIENT_REGISTRATION</a>
</dt>
<dt>
<a href="kernel.clfsmgmthandlelogfilefull">ClfsMgmtHandleLogFileFull</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PCLFS_CLIENT_LOG_UNPINNED_CALLBACK callback function%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

