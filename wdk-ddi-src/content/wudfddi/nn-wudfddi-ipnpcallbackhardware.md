---
UID: NN:wudfddi.IPnpCallbackHardware
title: IPnpCallbackHardware
author: windows-driver-content
description: The IPnpCallbackHardware interface is a Plug and Play (PnP) and power management (PM) interface.
old-location: wdf\ipnpcallbackhardware.htm
old-project: wdf
ms.assetid: 2746e7ab-690c-4382-be9a-124a7d68cf72
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.ipnpcallbackhardware, IPnpCallbackHardware interface, IPnpCallbackHardware interface, described, IPnpCallbackHardware, wudfddi/IPnpCallbackHardware, UMDFDeviceObjectRef_4b39ad3c-6fa6-4c47-aba8-676a6f628f1b.xml, umdf.ipnpcallbackhardware
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
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
-	IPnpCallbackHardware
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
req.product: Windows 10 or later.
---

# IPnpCallbackHardware interface

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IPnpCallbackHardware</b> interface is a Plug and Play (PnP) and power management (PM) interface.

## Methods

<p>The <b>IPnpCallbackHardware</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [wudfddi.IPnpCallbackHardware.OnPrepareHardware](nf-wudfddi-ipnpcallbackhardware-onpreparehardware.md) | The OnPrepareHardware method notifies a driver to make the specified hardware accessible. |
| [wudfddi.IPnpCallbackHardware.OnReleaseHardware](nf-wudfddi-ipnpcallbackhardware-onreleasehardware.md) | The OnReleaseHardware method notifies a driver to perform operations that are necessary when the specified hardware is no longer accessible. |

## Remarks

A driver registers the <b>IPnpCallbackHardware</b> interface when the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a> method to create a device object.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | wudfddi.h (include Wudfddi.h) |

## See Also

<a href="..\wudfddi\nn-wudfddi-ipnpcallbackhardware2.md">IPnpCallbackHardware2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IPnpCallbackHardware interface%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>