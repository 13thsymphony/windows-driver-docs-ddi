---
UID: NN:wudfusb.IWDFUsbTargetFactory
title: IWDFUsbTargetFactory
author: windows-driver-content
description: The IWDFUsbTargetFactory interface is a factory interface that is used to create a USB target device object.
old-location: wdf\iwdfusbtargetfactory.htm
old-project: wdf
ms.assetid: 00f89160-b880-4882-bf2e-28e9ed15f844
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IWDFUsbTargetPipe2, IWDFUsbTargetPipe2::ConfigureContinuousReader, ConfigureContinuousReader
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: wudfusb.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.alt-api: IWDFUsbTargetFactory
req.alt-loc: WUDFx.dll
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
req.typenames: *PWDF_USB_REQUEST_TYPE, WDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# IWDFUsbTargetFactory interface



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IWDFUsbTargetFactory</b> interface is a factory interface that is used to create a USB target device object.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFUsbTargetFactory</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IWDFUsbTargetFactory</b> also has these types of members:

The <b>IWDFUsbTargetFactory</b> interface has these methods.

The <a href="https://msdn.microsoft.com/c5aeb5f4-be62-4418-981c-1dd4acdccf07">CreateUsbTargetDevice</a> method creates a USB device object that is also an I/O target.

 


## -members
The <b>IWDFUsbTargetFactory</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560390">IWDFUsbTargetFactory::CreateUsbTargetDevice</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/c5aeb5f4-be62-4418-981c-1dd4acdccf07">CreateUsbTargetDevice</a> method creates a USB device object that is also an I/O target.

</td>
</tr>
</table>The <a href="https://msdn.microsoft.com/c5aeb5f4-be62-4418-981c-1dd4acdccf07">CreateUsbTargetDevice</a> method creates a USB device object that is also an I/O target.

 


## -remarks
