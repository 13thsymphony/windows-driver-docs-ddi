---
UID: NF:wudfddi.IWDFIoRequest2.GetRequestorMode
title: IWDFIoRequest2::GetRequestorMode method
author: windows-driver-content
description: The GetRequestorMode method indicates whether an I/O request came from a kernel-mode driver or a user-mode component (either an application or a user-mode driver).
old-location: wdf\iwdfiorequest2_getrequestormode.htm
old-project: wdf
ms.assetid: 8f918bc4-d2d0-4d5b-93c8-89f02c81a701
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetRequestorMode method, GetRequestorMode method, IWDFIoRequest2 interface, GetRequestorMode,IWDFIoRequest2.GetRequestorMode, IWDFIoRequest2, IWDFIoRequest2 interface, GetRequestorMode method, IWDFIoRequest2::GetRequestorMode, UMDFRequestObjectRef_ab2c358c-de7c-4bc3-b0cf-a598a1c69bd1.xml, umdf.iwdfiorequest2_getrequestormode, wdf.iwdfiorequest2_getrequestormode, wudfddi/IWDFIoRequest2::GetRequestorMode
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
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFIoRequest2.GetRequestorMode
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---


# GetRequestorMode method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetRequestorMode</b> method indicates whether an I/O request came from a kernel-mode driver or a user-mode component (either an application or a user-mode driver).

## Syntax

````
WDF_KPROCESSOR_MODE GetRequestorMode();
````

## Parameters

This function has no parameters.

## Return Value

<b>GetRequestorMode</b> returns a <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_kprocessor_mode.md">WDF_KPROCESSOR_MODE</a>-typed value that indicates whether the current I/O request came from a kernel-mode driver or a user-mode component.

## Remarks

A UMDF-based driver can receive an I/O request from a kernel-mode driver only if the UMDF-based driver supports <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-kernel-mode-clients-in-umdf-1-x-drivers">kernel-mode clients</a>. 

If <b>GetRequestorMode</b> returns <b>WdfUserMode</b>, the driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff559021">IWDFIoRequest2::IsFromUserModeDriver</a> to determine if the I/O request came from an application or a user-mode driver.


#### Examples

The following code example shows how an <a href="https://msdn.microsoft.com/library/windows/hardware/ff556885">IQueueCallbackWrite::OnWrite</a> callback function can determine whether an I/O request is from kernel mode or user mode. If the request is from user mode, the example determines whether the request is from an application or another user-mode driver.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
STDMETHODCALLTYPE
  CMyQueue::OnWrite(
    __in IWDFIoQueue *pWdfQueue,
    __in IWDFIoRequest *pWdfRequest,
    __in SIZE_T BytesToWrite
    )
{
 WDF_KPROCESSOR_MODE processorMode;
    BOOL fromApp = FALSE;
    //
    // Declare an IWDFIoRequest2 interface pointer and obtain the
    // IWDFIoRequest2 interface from the IWDFIoRequest interface.
    //
    CComQIPtr&lt;IWDFIoRequest2&gt; r2 = pWdfRequest;

    processorMode = r2-&gt;GetRequestorMode();
    if (processorMode == WdfUserMode)
    {
        fromApp = r2-&gt;IsFromUserModeDriver();
    }
...
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
| **DLL** | WUDFx.dll |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559021">IWDFIoRequest2::IsFromUserModeDriver</a>



<a href="..\wudfddi\nn-wudfddi-iwdfiorequest2.md">IWDFIoRequest2</a>