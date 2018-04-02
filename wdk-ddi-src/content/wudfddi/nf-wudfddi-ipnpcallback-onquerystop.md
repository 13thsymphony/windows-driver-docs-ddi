---
UID: NF:wudfddi.IPnpCallback.OnQueryStop
title: IPnpCallback::OnQueryStop method
author: windows-driver-content
description: The OnQueryStop method notifies a driver before a device is stopped.
old-location: wdf\ipnpcallback_onquerystop.htm
old-project: wdf
ms.assetid: e0cb14fa-82d0-4ce3-8672-801e7f04d522
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPnpCallback, IPnpCallback interface, OnQueryStop method, IPnpCallback::OnQueryStop, OnQueryStop method, OnQueryStop method, IPnpCallback interface, OnQueryStop,IPnpCallback.OnQueryStop, UMDFDeviceObjectRef_9215c39e-2cb9-4de6-9fb3-f228dad51f6d.xml, umdf.ipnpcallback_onquerystop, wdf.ipnpcallback_onquerystop, wudfddi/IPnpCallback::OnQueryStop
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Wudfddi.h
api_name:
-	IPnpCallback.OnQueryStop
product:
- Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---


# IPnpCallback::OnQueryStop method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnQueryStop</b> method notifies a driver before a device is stopped.

## Syntax

```
HRESULT OnQueryStop(
  IWDFDevice *pWdfDevice
);
```

## Parameters

`pWdfDevice`

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556917">IWDFDevice</a> interface for the device object of the device that will be stopped.


## Return Value

If the driver determines that the device can be stopped, the <b>OnQueryStop</b> callback method must return S_OK or another status code for which SUCCEEDED(status) equals <b>TRUE</b>. Otherwise it must return a status code for which SUCCEEDED(status) equals <b>FALSE</b>.   HRESULT error codes are defined in Winerror.h. Do not return HRESULT_FROM_NT(STATUS_NOT_SUPPORTED).

This method must use the HRESULT_FROM_NT macro to return a specific HRESULT value to  return status to a kernel-mode client. For more information, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-kernel-mode-clients-in-umdf-1-x-drivers">Supporting Kernel-mode Clients</a>.

## Remarks

A driver registers the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556762">IPnpCallback</a> interface when it calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a> method to create a device object. 

The framework does not synchronize the <b>OnQueryStop</b> callback function with other PnP and power management callback functions.  

<b>OnQueryStop</b> is not called in framework versions 1.7 and earlier.

For more information about the <b>OnQueryStop</b> callback method, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/the-pnp-manager-redistributes-system-resources">The PnP Manager Redistributes System Resources</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | wudfddi.h (include Wudfddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556762">IPnpCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556917">IWDFDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a>