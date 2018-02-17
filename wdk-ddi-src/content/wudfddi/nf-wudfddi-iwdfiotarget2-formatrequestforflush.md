---
UID: NF:wudfddi.IWDFIoTarget2.FormatRequestForFlush
title: IWDFIoTarget2::FormatRequestForFlush method
author: windows-driver-content
description: The FormatRequestForFlush method builds an I/O request for a flush operation but does not send the request to an I/O target.
old-location: wdf\iwdfiotarget2_formatrequestforflush.htm
old-project: wdf
ms.assetid: 28509e28-0e81-4531-947c-9ce452564682
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IWDFIoTarget2 interface, FormatRequestForFlush method, IWDFIoTarget2::FormatRequestForFlush, UMDFIoTargetObjectRef_985162ca-fae2-408e-b4df-59add8e4a760.xml, wudfddi/IWDFIoTarget2::FormatRequestForFlush, FormatRequestForFlush method, FormatRequestForFlush method, IWDFIoTarget2 interface, IWDFIoTarget2, umdf.iwdfiotarget2_formatrequestforflush, FormatRequestForFlush, wdf.iwdfiotarget2_formatrequestforflush
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: wudfddi.h
req.dll: WUDFx.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WUDFx.dll
apiname:
-	IWDFIoTarget2.FormatRequestForFlush
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
req.product: Windows 10 or later.
---


# FormatRequestForFlush method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>FormatRequestForFlush</b> method builds an I/O request for a flush operation but does not send the request to an I/O target.

## Syntax

````
HRESULT FormatRequestForFlush(
  [in]           IWDFIoRequest *pRequest,
  [in, optional] IWDFFile      *pFile
);
````

## Parameters

`pRequest`

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a> interface of the request object that represents the I/O request.

`pFile`

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdffile.md">IWDFFile</a> interface of the file object that is associated with the I/O request. This parameter is optional and can be <b>NULL</b>, but it is required for the default I/O target.


## Return Value

<b>FormatRequestForFlush</b> returns S_OK if the operation succeeds. Otherwise, the method might return one of the following value:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
The framework was unable to allocate memory.

</td>
</tr>
</table>
 

This method might return one of the other values that Winerror.h contains.

## Remarks

Some drivers must flush cached buffers that exist in either a lower driver or the device. For example, drivers that exist in a driver stack for a serial device or a storage device might support this operation. 

Use the <b>FormatRequestForFlush</b> method, followed by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559149">IWDFIoRequest::Send</a> method, to send flush requests either synchronously or asynchronously. 


#### Examples

The following code example is part of an <a href="https://msdn.microsoft.com/library/windows/hardware/ff556847">IQueueCallbackDefaultIoHandler::OnDefaultIoHandler</a> callback function. If the callback function receives a flush request, it sends the request to the device's default I/O target.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>void
CMyQueue::OnDefaultIoHandler(
 IWDFIoQueue*  pQueue,
 IWDFIoRequest*  pRequest
    )
{
    HRESULT hr;
    IWDFDevice *pDevice;
    IWDFIoTarget *pTarget;
    IWDFFile *pFile;

    //
    // Obtain the device, default I/O target, and file object.
    //
    pQueue-&gt;GetDevice(&amp;pDevice);
    pDevice-&gt;GetDefaultIoTarget(&amp;pTarget);
    pRequest-&gt;GetFileObject(&amp;pFile);

    if (WdfRequestFlushBuffers==pRequest-&gt;GetType())
    {
        // 
        // Declare an IWDFIoTarget2 interface pointer and obtain the
        // IWDFIoTarget2 interface from the IWDFIoTarget interface.
        //
        CComQIPtr&lt;IWDFIoTarget2&gt; target2(pTarget);

        //
        // Format a flush request and send it to the I/O target.
        //
        hr = target2-&gt;FormatRequestForFlush(pRequest, 
                                            pFile);

        if (SUCCEEDED(hr))
        {
            hr = pRequest-&gt;Send(pTarget,
                                WDF_REQUEST_SEND_OPTION_SYNCHRONOUS,
                                0);
        }
    }
...
    //
    // Release objects.
    //
    SAFE_RELEASE(pDevice);
    SAFE_RELEASE(pTarget);
    SAFE_RELEASE(pFile);
}</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.9 |
| **Header** | wudfddi.h (include Wudfddi.h) |
| **Library** | wudfddi.h |
| **DLL** | WUDFx.dll |

## See Also

<a href="..\wudfddi\nn-wudfddi-iwdfiotarget2.md">IWDFIoTarget2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556847">IQueueCallbackDefaultIoHandler::OnDefaultIoHandler</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559149">IWDFIoRequest::Send</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoTarget2::FormatRequestForFlush method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>