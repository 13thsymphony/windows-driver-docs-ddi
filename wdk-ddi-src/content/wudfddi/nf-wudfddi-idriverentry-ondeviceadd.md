---
UID: NF.wudfddi.IDriverEntry.OnDeviceAdd
title: IDriverEntry::OnDeviceAdd
author: windows-driver-content
description: The OnDeviceAdd method adds a new device to a system.
old-location: wdf\idriverentry_ondeviceadd.htm
old-project: wdf
ms.assetid: f2953b0d-6745-4804-bcda-47c7ddfb901f
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IDriverEntry, OnDeviceAdd, IDriverEntry::OnDeviceAdd
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDriverEntry.OnDeviceAdd
req.alt-loc: Wudfddi.h
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
req.iface: IDriverEntry
req.product: Windows 10 or later.
---

# IDriverEntry::OnDeviceAdd method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]</p>
<p>The <b>OnDeviceAdd</b> method adds a new device to a system.</p>


## -syntax

````
HRESULT OnDeviceAdd(
  [in] IWDFDriver           *pWdfDriver,
  [in] IWDFDeviceInitialize *pWdfDeviceInit
);
````


## -parameters
<dl>

### -param pWdfDriver [in]

<dd>
<p>A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfdriver.md">IWDFDriver</a> interface for the parent driver object that the new device belongs to.</p>
</dd>

### -param pWdfDeviceInit [in]

<dd>
<p>A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfdeviceinitialize.md">IWDFDeviceInitialize</a> interface that the driver uses to initialize the newly created device.</p>
</dd>
</dl>

## -returns
<p><b>OnDeviceAdd</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h. The driver should return S_OK only if it successfully called the <a href="wdf.iwdfdriver_createdevice">IWDFDriver::CreateDevice</a> method to create the <a href="wdf.framework_device_object">framework device object</a>. If the driver returns an error code, UMDF tears down the entire device stack regardless of whether the driver is a filter driver or a function driver.</p>

## -remarks
<p>A new device object is created for each device that is loaded in the driver host process. When a new device arrives in the system, the framework calls <b>OnDeviceAdd</b> to notify the driver of the arrival and passes the <a href="..\wudfddi\nn-wudfddi-iwdfdriver.md">IWDFDriver</a> and <a href="..\wudfddi\nn-wudfddi-iwdfdeviceinitialize.md">IWDFDeviceInitialize</a> interfaces in the call. The driver can call the <a href="wdf.iwdfdeviceinitialize_retrievedevicepropertystore">IWDFDeviceInitialize::RetrieveDevicePropertyStore</a> method to query for the device information that is provided as part of device installation. The driver must call the <a href="wdf.iwdfdriver_createdevice">IWDFDriver::CreateDevice</a> method to configure and create the device. If the driver does not successfully call <b>IWDFDriver::CreateDevice</b> before it returns S_OK, UMDF determines that the driver's behavior is incorrect and terminates the host process.</p>

<p>Any driver whose <b>OnDeviceAdd</b> method returns S_OK will subsequently receive a call to its <a href="wdf.ipnpcallbackhardware_onreleasehardware">IPnpCallbackHardware::OnReleaseHardware</a> method when the UMDF tears down the device stack.</p>

<p>Do not use the <a href="..\wudfddi\nn-wudfddi-iwdfdeviceinitialize.md">IWDFDeviceInitialize</a> interface that the <i>pWdfDeviceInit</i> parameter points to after the driver has called <a href="wdf.iwdfdriver_createdevice">IWDFDriver::CreateDevice</a>.</p>

<p>For more information, see <a href="wdf.adding_a_device">Adding a Device</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wudfddi.h (include Wudfddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wudfddi\nn-wudfddi-idriverentry.md">IDriverEntry</a>
</dt>
<dt>
<a href="wdf.ipnpcallbackhardware_onreleasehardware">IPnpCallbackHardware::OnReleaseHardware</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfdeviceinitialize.md">IWDFDeviceInitialize</a>
</dt>
<dt>
<a href="wdf.iwdfdeviceinitialize_retrievedevicepropertystore">IWDFDeviceInitialize::RetrieveDevicePropertyStore</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfdriver.md">IWDFDriver</a>
</dt>
<dt>
<a href="wdf.iwdfdriver_createdevice">IWDFDriver::CreateDevice</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IDriverEntry::OnDeviceAdd method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
