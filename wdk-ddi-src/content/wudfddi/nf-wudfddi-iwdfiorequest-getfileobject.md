---
UID: NF:wudfddi.IWDFIoRequest.GetFileObject
title: IWDFIoRequest::GetFileObject method
author: windows-driver-content
description: The GetFileObject method retrieves a pointer to the IWDFFile interface that is associated with an I/O request.
old-location: wdf\iwdfiorequest_getfileobject.htm
old-project: wdf
ms.assetid: 2d6567f1-9e2a-405f-ae8d-eb531cc29275
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: GetFileObject method, IWDFIoRequest interface, IWDFIoRequest interface, GetFileObject method, umdf.iwdfiorequest_getfileobject, UMDFRequestObjectRef_50a8506d-039a-448a-8459-30e89ac1021c.xml, GetFileObject, wudfddi/IWDFIoRequest::GetFileObject, IWDFIoRequest::GetFileObject, GetFileObject method, wdf.iwdfiorequest_getfileobject, IWDFIoRequest
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
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
-	IWDFIoRequest.GetFileObject
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
req.product: Windows 10 or later.
---


# GetFileObject method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetFileObject</b> method retrieves a pointer to the <a href="..\wudfddi\nn-wudfddi-iwdffile.md">IWDFFile</a> interface that is associated with an I/O request.

## Syntax

````
void GetFileObject(
  [out] IWDFFile **ppFileObject
);
````

## Parameters

`ppFileObject`

A pointer to a buffer that receives a pointer to the <a href="..\wudfddi\nn-wudfddi-iwdffile.md">IWDFFile</a> interface for the file object. Note that returning <b>NULL</b> is valid.


## Return Value

None

## Remarks

When your driver calls <b>GetFileObject</b>, the framework increments the reference count on the interface.  Your driver is responsible for releasing the reference when finished with the interface pointer. To do so, either use a smart pointer that automatically decrements the reference count when the object goes out of context, or call  <a href="https://msdn.microsoft.com/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a">Release</a> on the interface when finished with it.


#### Examples

The following code example is taken from the WpdMultiTransportDriver sample in the WDK. The example declares a smart pointer to an <a href="..\wudfddi\nn-wudfddi-iwdffile.md">IWDFFile</a> interface, calls <b>GetFileObject</b>, and then calls <a href="https://msdn.microsoft.com/b76acae1-3c37-4095-bf8b-1785dc90f378">RetrieveContext</a> on the file object.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>  CComPtr&lt;IWDFFile&gt;   pFileObject;

  ...

  // Get the Context map for this client

  pRequest-&gt;GetFileObject(&amp;pFileObject);

  if (pFileObject != NULL)
  {
      hr = pFileObject-&gt;RetrieveContext((void**)&amp;pClientContextMap);
      CHECK_HR(hr, "Failed to get Contextmap from WDF File Object");
  }
  </pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.5 |
| **Header** | wudfddi.h (include Wudfddi.h) |
| **Library** | wudfddi.h |
| **DLL** | WUDFx.dll |

## See Also

<a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a>



<a href="..\wudfddi\nn-wudfddi-iwdffile.md">IWDFFile</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoRequest::GetFileObject method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>