---
UID: NN:wudfddi.IWDFFile3
title: IWDFFile3
author: windows-driver-content
description: Drivers obtain the IWDFFile3 interface by calling IWDFFile::QueryInterface.
old-location: wdf\iwdffile3.htm
old-project: wdf
ms.assetid: 67F55A00-2DE4-4ECE-8DAF-BBCBB156454E
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.iwdffile3, IWDFFile3 interface, IWDFFile3 interface, described, IWDFFile3, wudfddi/IWDFFile3, umdf.iwdffile3
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: wudfddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
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
-	Wudfddi.h
apiname:
-	IWDFFile3
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFFile3 interface

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

Drivers obtain the <b>IWDFFile3</b> interface by calling <b>IWDFFile::QueryInterface</b>.

## Methods

<p>The <b>IWDFFile3</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [wudfddi.IWDFFile3.GetInitiatorProcessId](nf-wudfddi-iwdffile3-getinitiatorprocessid.md) | The GetInitiatorProcessId method retrieves the initiator process ID associated with an IWDFFile interface. |

## Remarks



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.11 |
| **Header** | wudfddi.h |

## See Also

<a href="..\wudfddi\nn-wudfddi-iwdffile2.md">IWDFFile2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFFile3 interface%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>