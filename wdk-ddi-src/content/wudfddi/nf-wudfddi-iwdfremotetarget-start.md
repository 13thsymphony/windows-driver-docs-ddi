---
UID: NF.wudfddi.IWDFRemoteTarget.Start
title: IWDFRemoteTarget::Start method
author: windows-driver-content
description: The IWDFRemoteTarget::Start method restarts a remote I/O target that is stopped.
old-location: wdf\iwdfremotetarget_start.htm
old-project: wdf
ms.assetid: f0f21d34-21f2-48ac-994f-e050f4447745
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: IWDFRemoteTarget, IWDFRemoteTarget::Start, Start
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
req.alt-api: IWDFRemoteTarget.Start
req.alt-loc: WUDFx.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
req.product: Windows 10 or later.
---

# IWDFRemoteTarget::Start method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IWDFRemoteTarget::Start</b> method restarts a <a href="wdf.general_i_o_targets_in_umdf">remote I/O target</a> that is stopped.



## -syntax

````
HRESULT Start();
````


## -parameters


## -returns
<b>Start</b> returns S_OK if the operation succeeds. Otherwise, the method might return the following value:
<dl>
<dt><b>HRESULT_FROM_NT (STATUS_INVALID_DEVICE_STATE)</b></dt>
</dl>The remote I/O target object was deleted.

 

This method might return one of the other values that Winerror.h contains.



<b>Start</b> returns S_OK if the operation succeeds. Otherwise, the method might return the following value:
<dl>
<dt><b>HRESULT_FROM_NT (STATUS_INVALID_DEVICE_STATE)</b></dt>
</dl>The remote I/O target object was deleted.

 

This method might return one of the other values that Winerror.h contains.



<b>Start</b> returns S_OK if the operation succeeds. Otherwise, the method might return the following value:
<dl>
<dt><b>HRESULT_FROM_NT (STATUS_INVALID_DEVICE_STATE)</b></dt>
</dl>The remote I/O target object was deleted.

 

This method might return one of the other values that Winerror.h contains.




## -remarks
The <b>Start</b> method resumes processing any I/O requests that are in queued to the remote I/O target. After a driver calls <a href="wdf.iwdfremotetarget_stop">IWDFRemoteTarget::Stop</a>, the driver must call <b>Start</b> so the framework can resume sending I/O requests to the I/O target.

For more information about <b>Start</b>, and how to use remote I/O targets in UMDF-based drivers, see <a href="wdf.controlling_a_general_i_o_target_s_state_in_umdf">Controlling a General I/O Target's State in UMDF</a>.

The following code example restarts a remote I/O target.


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
End of support

</th>
<td width="70%">
Unavailable in UMDF 2.0 and later.

</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
1.9

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wudfddi.h (include Wudfddi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>WUDFx.dll</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfremotetarget.md">IWDFRemoteTarget</a>
</dt>
<dt>
<a href="wdf.iwdfremotetarget_stop">IWDFRemoteTarget::Stop</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFRemoteTarget::Start method%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

