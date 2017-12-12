---
UID: NN.wudfddi.IQueueCallbackDeviceIoControl
title: IQueueCallbackDeviceIoControl
author: windows-driver-content
description: An I/O queue object notifies a driver when a device I/O control request is available for the driver.
old-location: wdf\iqueuecallbackdeviceiocontrol.htm
old-project: wdf
ms.assetid: efb33bc5-2a9b-40c7-9584-c762daf016f6
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: __MIDL___MIDL_itf_wudfddi_0000_0000_0001, POWER_ACTION, *PPOWER_ACTION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: wudfddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IQueueCallbackDeviceIoControl
req.alt-loc: wudfddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# IQueueCallbackDeviceIoControl interface



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

An I/O queue object notifies a driver when a device I/O control request is available for the driver. The I/O queue object notifies the driver in response to an application calling the Microsoft Win32 <b>DeviceIoControl</b> function. The driver can handle the notification by registering the <b>IQueueCallbackDeviceIoControl</b> interface.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IQueueCallbackDeviceIoControl</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IQueueCallbackDeviceIoControl</b> also has these types of members:

The <b>IQueueCallbackDeviceIoControl</b> interface has these methods.

The <a href="wdf.iqueuecallbackdeviceiocontrol_ondeviceiocontrol">OnDeviceIoControl</a> method is called to handle a device I/O control request when an application performs a specific operation on a device through the Microsoft Win32 <b>OnDeviceIoControl</b> function. 

 


## -members
The <b>IQueueCallbackDeviceIoControl</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="wdf.iqueuecallbackdeviceiocontrol_ondeviceiocontrol">IQueueCallbackDeviceIoControl::OnDeviceIoControl</a>
</td>
<td align="left" width="63%">
The <a href="wdf.iqueuecallbackdeviceiocontrol_ondeviceiocontrol">OnDeviceIoControl</a> method is called to handle a device I/O control request when an application performs a specific operation on a device through the Microsoft Win32 <b>OnDeviceIoControl</b> function. 

</td>
</tr>
</table>The <a href="wdf.iqueuecallbackdeviceiocontrol_ondeviceiocontrol">OnDeviceIoControl</a> method is called to handle a device I/O control request when an application performs a specific operation on a device through the Microsoft Win32 <b>OnDeviceIoControl</b> function. 

 


## -remarks
A driver registers the <b>IQueueCallbackDeviceIoControl</b> interface when it calls the <a href="wdf.iwdfdevice_createioqueue">IWDFDevice::CreateIoQueue</a> method to create an I/O queue or to configure the default I/O queue. For more information about creating or configuring an I/O queue, see <a href="wdf.configuring_dispatch_mode_for_an_i_o_queue">Configuring Dispatch Mode for an I/O Queue</a>.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wudfddi.h</dt>
</dl>
</td>
</tr>
</table>