---
UID: NF:wudfddi.IQueueCallbackCreate.OnCreateFile
title: IQueueCallbackCreate::OnCreateFile method
author: windows-driver-content
description: The OnCreateFile method is called to handle an open file request when an application opens a device through the Microsoft Win32 CreateFile function.
old-location: wdf\iqueuecallbackcreate_oncreatefile.htm
old-project: wdf
ms.assetid: f569d306-4e1e-44b7-acb0-6b46abc26b37
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IQueueCallbackCreate interface, OnCreateFile method, UMDFQueueObjectRef_db0b57a0-6086-4e2a-87bd-71e5a1e4f46d.xml, wdf.iqueuecallbackcreate_oncreatefile, OnCreateFile method, IQueueCallbackCreate::OnCreateFile, umdf.iqueuecallbackcreate_oncreatefile, IQueueCallbackCreate, OnCreateFile, OnCreateFile method, IQueueCallbackCreate interface, wudfddi/IQueueCallbackCreate::OnCreateFile
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: wudfddi.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Wudfddi.h
apiname:
-	IQueueCallbackCreate.OnCreateFile
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---


# OnCreateFile method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnCreateFile</b> method is called to handle an open file request when an application opens a device through the Microsoft Win32 <b>CreateFile</b> function.

## Syntax

````
void OnCreateFile(
  [in] IWDFIoQueue   *pWdfQueue,
  [in] IWDFIoRequest *pWdfRequest,
  [in] IWDFFile      *pWdfFileObject
);
````

## Parameters

`pWdfQueue`

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfioqueue.md">IWDFIoQueue</a> interface for the I/O queue object that the request arrives from.

`pWDFRequest`



`pWdfFileObject`

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdffile.md">IWDFFile</a> interface for the file object that is associated with the device. This information is provided for convenience because the driver can call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559088">IWDFIoRequest::GetCreateParameters</a> method to obtain the file object.


## Return Value

None

## Remarks

If the driver implements the <a href="..\wudfddi\nn-wudfddi-iqueuecallbackcreate.md">IQueueCallbackCreate</a> interface, the framework calls the <b>OnCreateFile</b> method when an application opens a device through the Win32 <b>CreateFile</b> function to perform an I/O operation, such as reading from or writing to a file. 

A driver registers the <a href="..\wudfddi\nn-wudfddi-iqueuecallbackcreate.md">IQueueCallbackCreate</a> interface when the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557020">IWDFDevice::CreateIoQueue</a> method to create an I/O queue or to configure the default I/O queue.

A typical <b>OnCreateFile</b> method might call <a href="https://msdn.microsoft.com/library/windows/hardware/ff560208">IWDFObject::AssignContext</a> method on the file object to associate context with the file object, and then call <a href="https://msdn.microsoft.com/library/windows/hardware/ff559070">IWDFIoRequest::Complete</a> to complete the request.

A UMDF driver might be required to open registry keys or files while it impersonates a client that sends the I/O requests. From its implementation of the <b>OnCreateFile</b> method, the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559136">IWDFIoRequest::Impersonate</a> method to set a security impersonation level and to set the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554916">IImpersonateCallback::OnImpersonate</a> method in which the driver handles the impersonation. To access necessary resources by using the credentials of the user, the framework calls the driver's <b>OnImpersonate</b> method. For any operations other than those that require impersonation, the framework calls driver methods that run under the default driver account. For more information about how UMDF and UMDF drivers handle impersonation, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/handling-client-impersonation-in-umdf-drivers">Handling Impersonation</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | wudfddi.h (include Wudfddi.h) |
| **Library** | wudfddi.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557020">IWDFDevice::CreateIoQueue</a>

<a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a>

<a href="..\wudfddi\nn-wudfddi-iwdfioqueue.md">IWDFIoQueue</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559088">IWDFIoRequest::GetCreateParameters</a>

<a href="..\wudfddi\nn-wudfddi-iqueuecallbackcreate.md">IQueueCallbackCreate</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554916">IImpersonateCallback::OnImpersonate</a>

<a href="..\wudfddi\nn-wudfddi-iwdffile.md">IWDFFile</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559136">IWDFIoRequest::Impersonate</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IQueueCallbackCreate::OnCreateFile method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>