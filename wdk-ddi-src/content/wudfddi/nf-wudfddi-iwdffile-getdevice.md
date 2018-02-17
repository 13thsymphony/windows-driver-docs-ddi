---
UID: NF:wudfddi.IWDFFile.GetDevice
title: IWDFFile::GetDevice method
author: windows-driver-content
description: The GetDevice method returns the interface to the device object that a file object is associated with.
old-location: wdf\iwdffile_getdevice.htm
old-project: wdf
ms.assetid: 914cc125-076e-40e1-baef-a12cba427b37
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wudfddi/IWDFFile::GetDevice, UMDFFileObjectRef_67417dd5-53be-487b-a93f-711bbcd6b0dd.xml, GetDevice, IWDFFile, wdf.iwdffile_getdevice, IWDFFile interface, GetDevice method, umdf.iwdffile_getdevice, GetDevice method, GetDevice method, IWDFFile interface, IWDFFile::GetDevice
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
-	IWDFFile.GetDevice
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
req.product: Windows 10 or later.
---


# GetDevice method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetDevice</b> method returns the interface to the device object that a file object is associated with.

## Syntax

````
void GetDevice(
  [out] IWDFDevice **ppWdfDevice
);
````

## Parameters

`ppWdfDevice`

A pointer to a variable that receives a pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfdevice.md">IWDFDevice</a> interface for the device object that is associated with the file object.


## Return Value

None


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

<a href="..\wudfddi\nn-wudfddi-iwdffile.md">IWDFFile</a>



<a href="..\wudfddi\nn-wudfddi-iwdfdevice.md">IWDFDevice</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFFile::GetDevice method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>