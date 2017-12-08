---
UID: NF.sercx.SerCxInitialize
title: SerCxInitialize function
author: windows-driver-content
description: The SerCxInitialize method completes the initialization of the serial framework extension (SerCx) after this driver creates the associated device object.
old-location: serports\sercxinitialize.htm
old-project: serports
ms.assetid: 2837C3BE-71EB-4949-AB46-5333CF4575A8
ms.author: windowsdriverdev
ms.date: 10/23/2017
ms.keywords: SerCxInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: sercx.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SerCxInitialize
req.alt-loc: 1.0\Sercx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# SerCxInitialize function



## -description
The <b>SerCxInitialize</b> method completes the initialization of the serial framework extension (SerCx) after this driver creates the associated device object.


## -syntax

````
NTSTATUS SerCxInitialize(
  [in] WDFDEVICE     FxDevice,
  [in] PSERCX_CONFIG Config
);
````


## -parameters

### -param FxDevice [in]

A WDFDEVICE handle to the framework device object that represents the serial controller.

### -param Config [in]

A pointer to a caller-allocated <a href="serports.sercx_config">SERCX_CONFIG</a> structure that contains configuration information for SerCx. The caller previously called the <a href="serports.sercx_config_init">SERCX_CONFIG_INIT</a> function to initialize this structure.

## -returns
<b>SerCxInitialize</b> returns STATUS_SUCCESS if it is successful. Possible error return values include the following status codes.
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>The method was called at the wrong IRQL; or the WDFDEVICE handle is not valid; or either <i>FxDevice</i> or <i>Config</i> is NULL.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>Could not allocate system resources (typically memory).

 

## -remarks
The serial controller driver calls this method after it creates the associated device object.

<b>SerCxInitialize</b> registers the controller driver’s I/O callback functions with SerCx. In addition, this method defines the transfer mode for the I/O queue.  During the call, this method creates all of the internal structures required by SerCx (including the I/O queue for the serial controller).  After this method returns, SerCx is ready to process I/O.  However, the controller driver might configure controller hardware settings before it returns from the <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback or before it adds the PDO to the child list.

If the parameters are invalid (as described in <a href="serports.sercx_config">SERCX_CONFIG</a>), <a href="https://msdn.microsoft.com/library/windows/hardware/ff557262">Driver Verifier</a> will raise an error.

This routine must be called before committing the device (returning from <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> or adding the PDO to the child list).

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available starting with Windows 8.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>1.0\Sercx.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
PASSIVE_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a>
</dt>
<dt>
<a href="serports.sercx_config">SERCX_CONFIG</a>
</dt>
<dt>
<a href="serports.sercx_config_init">SERCX_CONFIG_INIT</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SerCxInitialize method%20 RELEASE:%20(10/23/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
