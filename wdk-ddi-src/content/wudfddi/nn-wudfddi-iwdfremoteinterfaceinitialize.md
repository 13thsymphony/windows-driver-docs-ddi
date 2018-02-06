---
UID: NN:wudfddi.IWDFRemoteInterfaceInitialize
title: IWDFRemoteInterfaceInitialize
author: windows-driver-content
description: UMDF-based drivers receive the IWDFRemoteInterfaceInitialize interface as input to an IPnpCallbackRemoteInterfaceNotification::OnRemoteInterfaceArrival callback function.
old-location: wdf\iwdfremoteinterfaceinitialize.htm
old-project: wdf
ms.assetid: 54954874-d67a-4e8b-b791-105e8018f8ca
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.iwdfremoteinterfaceinitialize, IWDFRemoteInterfaceInitialize interface, IWDFRemoteInterfaceInitialize interface, described, IWDFRemoteInterfaceInitialize, wudfddi/IWDFRemoteInterfaceInitialize, UMDFIoTargetObjectRef_0536631b-c316-41e7-856b-94a3c991c318.xml, umdf.iwdfremoteinterfaceinitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: wudfddi.h
req.include-header: 
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
-	IWDFRemoteInterfaceInitialize
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFRemoteInterfaceInitialize interface

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

UMDF-based drivers receive the <b>IWDFRemoteInterfaceInitialize</b> interface as input to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff556775">IPnpCallbackRemoteInterfaceNotification::OnRemoteInterfaceArrival</a> callback function.

## Methods

<p>The <b>IWDFRemoteInterfaceInitialize</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [wudfddi.IWDFRemoteInterfaceInitialize.GetInterfaceGuid](nf-wudfddi-iwdfremoteinterfaceinitialize-getinterfaceguid.md) | The GetInterfaceGuid method retrieves the GUID that identifies a device interface. |
| [wudfddi.IWDFRemoteInterfaceInitialize.RetrieveSymbolicLink](nf-wudfddi-iwdfremoteinterfaceinitialize-retrievesymboliclink.md) | The RetrieveSymbolicLink method retrieves the symbolic link name that the operating system assigned to a device interface. |

## Remarks



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.9 |
| **Header** | wudfddi.h |