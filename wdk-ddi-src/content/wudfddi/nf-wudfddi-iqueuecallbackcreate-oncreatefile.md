---
UID: NF.wudfddi.IQueueCallbackCreate.OnCreateFile
title: IQueueCallbackCreate::OnCreateFile method
author: windows-driver-content
description: The OnCreateFile method is called to handle an open file request when an application opens a device through the Microsoft Win32 CreateFile function.
old-location: wdf\iqueuecallbackcreate_oncreatefile.htm
old-project: wdf
ms.assetid: f569d306-4e1e-44b7-acb0-6b46abc26b37
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: IQueueCallbackCreate, IQueueCallbackCreate::OnCreateFile, OnCreateFile
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IQueueCallbackCreate.OnCreateFile
req.alt-loc: Wudfddi.h
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
req.product: Windows 10 or later.
---

# IQueueCallbackCreate::OnCreateFile method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnCreateFile</b> method is called to handle an open file request when an application opens a device through the Microsoft Win32 <b>CreateFile</b> function. 



## -syntax

````
void OnCreateFile(
  [in] IWDFIoQueue   *pWdfQueue,
  [in] IWDFIoRequest *pWdfRequest,
  [in] IWDFFile      *pWdfFileObject
);
````


## -parameters

### -param pWdfQueue [in]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfioqueue.md">IWDFIoQueue</a> interface for the I/O queue object that the request arrives from. 


### -param pWdfRequest [in]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a> interface that represents the framework request object. 


### -param pWdfFileObject [in]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdffile.md">IWDFFile</a> interface for the file object that is associated with the device. This information is provided for convenience because the driver can call the <a href="wdf.iwdfiorequest_getcreateparameters">IWDFIoRequest::GetCreateParameters</a> method to obtain the file object. 


## -returns
None


## -remarks
If the driver implements the <a href="..\wudfddi\nn-wudfddi-iqueuecallbackcreate.md">IQueueCallbackCreate</a> interface, the framework calls the <b>OnCreateFile</b> method when an application opens a device through the Win32 <b>CreateFile</b> function to perform an I/O operation, such as reading from or writing to a file. 

A driver registers the <a href="..\wudfddi\nn-wudfddi-iqueuecallbackcreate.md">IQueueCallbackCreate</a> interface when the driver calls the <a href="wdf.iwdfdevice_createioqueue">IWDFDevice::CreateIoQueue</a> method to create an I/O queue or to configure the default I/O queue.

A typical <b>OnCreateFile</b> method might call <a href="wdf.iwdfobject_assigncontext">IWDFObject::AssignContext</a> method on the file object to associate context with the file object, and then call <a href="wdf.iwdfiorequest_complete">IWDFIoRequest::Complete</a> to complete the request.

A UMDF driver might be required to open registry keys or files while it impersonates a client that sends the I/O requests. From its implementation of the <b>OnCreateFile</b> method, the driver calls the <a href="wdf.iwdfiorequest_impersonate">IWDFIoRequest::Impersonate</a> method to set a security impersonation level and to set the <a href="wdf.iimpersonatecallback_onimpersonate">IImpersonateCallback::OnImpersonate</a> method in which the driver handles the impersonation. To access necessary resources by using the credentials of the user, the framework calls the driver's <b>OnImpersonate</b> method. For any operations other than those that require impersonation, the framework calls driver methods that run under the default driver account. For more information about how UMDF and UMDF drivers handle impersonation, see <a href="wdf.handling_client_impersonation">Handling Impersonation</a>.

This example is based on the WpdWudfSampleDriver sample, and is from the Queue.cpp file.


## -requirements
<table>
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
</table>

## -see-also
<dl>
<dt>
<a href="wdf.iimpersonatecallback_onimpersonate">IImpersonateCallback::OnImpersonate</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iqueuecallbackcreate.md">IQueueCallbackCreate</a>
</dt>
<dt>
<a href="wdf.iwdfdevice_createioqueue">IWDFDevice::CreateIoQueue</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdffile.md">IWDFFile</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfioqueue.md">IWDFIoQueue</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a>
</dt>
<dt>
<a href="wdf.iwdfiorequest_getcreateparameters">IWDFIoRequest::GetCreateParameters</a>
</dt>
<dt>
<a href="wdf.iwdfiorequest_impersonate">IWDFIoRequest::Impersonate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IQueueCallbackCreate::OnCreateFile method%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

