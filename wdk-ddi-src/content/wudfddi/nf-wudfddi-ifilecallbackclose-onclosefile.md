---
UID: NF:wudfddi.IFileCallbackClose.OnCloseFile
title: IFileCallbackClose::OnCloseFile method
author: windows-driver-content
description: The OnCloseFile method is called when the last reference count on a file object goes down to zero and before the file object is released.
old-location: wdf\ifilecallbackclose_onclosefile.htm
old-project: wdf
ms.assetid: ca3bd7af-b270-497e-a90a-6d79ce66d968
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: IFileCallbackClose, IFileCallbackClose interface, OnCloseFile method, IFileCallbackClose::OnCloseFile, OnCloseFile method, OnCloseFile method, IFileCallbackClose interface, OnCloseFile,IFileCallbackClose.OnCloseFile, UMDFFileObjectRef_8aa60206-80e0-4c49-b2fd-c79f5e703c18.xml, umdf.ifilecallbackclose_onclosefile, wdf.ifilecallbackclose_onclosefile, wudfddi/IFileCallbackClose::OnCloseFile
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Wudfddi.h
api_name:
-	IFileCallbackClose.OnCloseFile
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---


# OnCloseFile method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnCloseFile</b> method is called when the last reference count on a file object goes down to zero and before the file object is released.

## Syntax

````
void OnCloseFile(
  [in] IWDFFile *pWdfFileObject
);
````

## Parameters

`pWdfFileObject`

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdffile.md">IWDFFile</a> interface for the file object that is associated with the device.


## Return Value

None

## Remarks

A driver registers the <a href="..\wudfddi\nn-wudfddi-ifilecallbackclose.md">IFileCallbackClose</a> interface when the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a> method to create a device object. 

For information about when the framework calls <b>OnCloseFile</b>, see <a href="https://msdn.microsoft.com/f81ae0ed-a29c-476e-9b16-ff554eef1de9">Driver-Created Versus Application-Created File Objects</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | wudfddi.h (include Wudfddi.h) |
| **Library** | wudfddi.h |

## See Also

<a href="..\wudfddi\nn-wudfddi-iwdffile.md">IWDFFile</a>



<a href="..\wudfddi\nn-wudfddi-ifilecallbackclose.md">IFileCallbackClose</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IFileCallbackClose::OnCloseFile method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>