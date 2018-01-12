---
UID: NN:wudfddi.IWDFFileHandleTargetFactory
title: IWDFFileHandleTargetFactory
author: windows-driver-content
description: The IWDFFileHandleTargetFactory interface is a factory interface that is used to create a file-handle-based target device object.
old-location: wdf\iwdffilehandletargetfactory.htm
old-project: wdf
ms.assetid: b4754176-53a2-4ee4-a441-5d9a4a4a17e2
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: IWDFWorkItem, IWDFWorkItem::GetParentObject, GetParentObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.alt-api: IWDFFileHandleTargetFactory
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
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFFileHandleTargetFactory interface



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IWDFFileHandleTargetFactory</b> interface is a factory interface that is used to create a file-handle-based target device object.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFFileHandleTargetFactory</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IWDFFileHandleTargetFactory</b> also has these types of members:

The <b>IWDFFileHandleTargetFactory</b> interface has these methods.

The <a href="https://msdn.microsoft.com/579a2cef-1e37-426c-9f69-8766dc9011ba">CreateFileHandleTarget</a> method creates a file-handle-based I/O target object.

 


## -members
The <b>IWDFFileHandleTargetFactory</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558930">IWDFFileHandleTargetFactory::CreateFileHandleTarget</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/579a2cef-1e37-426c-9f69-8766dc9011ba">CreateFileHandleTarget</a> method creates a file-handle-based I/O target object.

</td>
</tr>
</table>The <a href="https://msdn.microsoft.com/579a2cef-1e37-426c-9f69-8766dc9011ba">CreateFileHandleTarget</a> method creates a file-handle-based I/O target object.

 


## -remarks
Drivers obtain the <b>IWDFFileHandleTargetFactory</b> interface by calling <b>IWDFDevice::QueryInterface</b>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
End of support

</th>
<td width="70%">
Unavailable in UMDF 2.0 and later.

</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
1.5

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wudfddi.h (include Wudfddi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>WUDFx.dll</dt>
</dl>
</td>
</tr>
</table>