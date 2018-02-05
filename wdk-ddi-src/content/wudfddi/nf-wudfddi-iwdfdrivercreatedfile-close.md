---
UID : NF:wudfddi.IWDFDriverCreatedFile.Close
title : IWDFDriverCreatedFile::Close method
author : windows-driver-content
description : The Close method closes an instance of a UMDF driver-created-file object that was created by calling the IWDFDevice::CreateWdfFile method.
old-location : wdf\iwdfdrivercreatedfile_close.htm
old-project : wdf
ms.assetid : a9c1d1d7-4222-4c8c-92eb-497d13952bed
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : wdf.iwdfdrivercreatedfile_close, IWDFDriverCreatedFile::Close, Close method, wudfddi/IWDFDriverCreatedFile::Close, UMDFDriverCreatedFileObjectRef_52a9f370-6f1d-4d62-84de-0b56a61b95fc.xml, IWDFDriverCreatedFile, Close method, IWDFDriverCreatedFile interface, umdf.iwdfdrivercreatedfile_close, IWDFDriverCreatedFile interface, Close method, Close
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : wudfddi.h
req.include-header : Wudfddi.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 1.5
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : Unavailable in UMDF 2.0 and later.
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : wudfddi.h
req.dll : WUDFx.dll
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : POWER_ACTION, *PPOWER_ACTION
req.product : Windows 10 or later.
---


# Close method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>Close</b> method closes an instance of a UMDF driver-created-file object that was created by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558828">IWDFDevice::CreateWdfFile</a> method.

## Syntax

````
void  Close();
````

## Parameters

This function has no parameters.

## Return Value

None

## Remarks

For more information, see <a href="https://msdn.microsoft.com/84b677b4-fddf-4f06-9ea6-e4642c3f1b2d">Creating and Using Driver-Created File Objects</a>.

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

<a href="..\wudfddi\nn-wudfddi-iwdfdrivercreatedfile.md">IWDFDriverCreatedFile</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558828">IWDFDevice::CreateWdfFile</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFDriverCreatedFile::Close method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>