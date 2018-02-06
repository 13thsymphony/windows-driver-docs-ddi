---
UID: NN:wudfddi.IWDFDriverCreatedFile
title: IWDFDriverCreatedFile
author: windows-driver-content
description: The IWDFDriverCreatedFile interface exposes a UMDF driver-created-file object for the driver to use.
old-location: wdf\iwdfdrivercreatedfile.htm
old-project: wdf
ms.assetid: ea74a539-d0a0-41ea-9fe1-8d7880a4187d
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.iwdfdrivercreatedfile, IWDFDriverCreatedFile interface, IWDFDriverCreatedFile interface, described, IWDFDriverCreatedFile, wudfddi/IWDFDriverCreatedFile, UMDFDriverCreatedFileObjectRef_5299de07-06ff-484c-a60f-4abe8828a725.xml, umdf.iwdfdrivercreatedfile
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: wudfddi.h
req.include-header: 
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
-	IWDFDriverCreatedFile
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFDriverCreatedFile interface

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IWDFDriverCreatedFile</b> interface exposes a UMDF driver-created-file object for the driver to use.

## Methods

<p>The <b>IWDFDriverCreatedFile</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [wudfddi.IWDFDriverCreatedFile.Close](nf-wudfddi-iwdfdrivercreatedfile-close.md) | The Close method closes an instance of a UMDF driver-created-file object that was created by calling the IWDFDevice::CreateWdfFile method. |

## Remarks

The driver can call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558828">IWDFDevice::CreateWdfFile</a> method to receive a pointer to a <b>IWDFDriverCreatedFile</b> interface.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.5 |
| **Header** | wudfddi.h |