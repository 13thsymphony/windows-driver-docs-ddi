---
UID: NF.wudfddi.IWDFIoRequest2.Requeue
title: IWDFIoRequest2::Requeue method
author: windows-driver-content
description: The Requeue method returns an I/O request to the head of the I/O queue from which it was delivered to the driver.
old-location: wdf\iwdfiorequest2_requeue.htm
old-project: wdf
ms.assetid: 1e33f284-6cb9-426f-a900-76b827341927
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: IWDFIoRequest2, IWDFIoRequest2::Requeue, Requeue
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
req.alt-api: IWDFIoRequest2.Requeue
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

# IWDFIoRequest2::Requeue method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>Requeue</b> method returns an I/O request to the head of the I/O queue from which it was delivered to the driver.



## -syntax

````
HRESULT Requeue();
````


## -parameters


## -returns
<b>Requeue</b> returns S_OK if the operation succeeds. Otherwise, this method might return one of the following values:
<dl>
<dt><b>HRESULT_FROM_WIN32 (ERROR_INVALID_OPERATION)</b></dt>
</dl>This value is returned if one of the following occurs:

The specified I/O request did not come from an I/O queue.

The driver does not own the I/O request.

The request is cancelable.

The queue's dispatching method is not manual.

 

This method might return one of the other values that Winerror.h contains.





<b>Requeue</b> returns S_OK if the operation succeeds. Otherwise, this method might return one of the following values:
<dl>
<dt><b>HRESULT_FROM_WIN32 (ERROR_INVALID_OPERATION)</b></dt>
</dl>This value is returned if one of the following occurs:

The specified I/O request did not come from an I/O queue.

The driver does not own the I/O request.

The request is cancelable.

The queue's dispatching method is not manual.

 

This method might return one of the other values that Winerror.h contains.





<b>Requeue</b> returns S_OK if the operation succeeds. Otherwise, this method might return one of the following values:
<dl>
<dt><b>HRESULT_FROM_WIN32 (ERROR_INVALID_OPERATION)</b></dt>
</dl>This value is returned if one of the following occurs:

The specified I/O request did not come from an I/O queue.

The driver does not own the I/O request.

The request is cancelable.

The queue's dispatching method is not manual.

 

This method might return one of the other values that Winerror.h contains.






## -remarks
A driver can call <b>Requeue</b> only if it uses the <a href="wdf.configuring_dispatch_mode_for_an_i_o_queue">manual dispatching method</a> for the I/O queue.

The following code example shows a segment of an <a href="wdf.iqueuecallbackstatechange_onstatechange">IQueueCallbackStateChange::OnStateChange</a> callback function. The segment obtains an I/O request from the I/O and then returns the request to the queue.


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
<a href="..\wudfddi\nn-wudfddi-iwdfiorequest2.md">IWDFIoRequest2</a>
</dt>
<dt>
<a href="wdf.iwdfioqueue_retrievenextrequest">IWDFIoQueue::RetrieveNextRequest</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoRequest2::Requeue method%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

