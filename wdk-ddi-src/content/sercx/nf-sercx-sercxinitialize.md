---
UID: NF:sercx.SerCxInitialize
title: SerCxInitialize function
author: windows-driver-content
description: The SerCxInitialize method completes the initialization of the serial framework extension (SerCx) after this driver creates the associated device object.
old-location: serports\sercxinitialize.htm
old-project: serports
ms.assetid: 2837C3BE-71EB-4949-AB46-5333CF4575A8
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: serports.sercxinitialize, SerCxInitialize method [Serial Ports], 1/SerCxInitialize, SerCxInitialize
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	1.0\Sercx.h
apiname:
-	SerCxInitialize
product: Windows
targetos: Windows
req.typenames: "*PSERCX_STATUS, SERCX_STATUS"
req.product: Windows 10 or later.
---


# SerCxInitialize function
The <b>SerCxInitialize</b> method completes the initialization of the serial framework extension (SerCx) after this driver creates the associated device object.

## Syntax

````
NTSTATUS SerCxInitialize(
  [in] WDFDEVICE     FxDevice,
  [in] PSERCX_CONFIG Config
);
````

## Parameters

`FxDevice`

A WDFDEVICE handle to the framework device object that represents the serial controller.

`Config`

A pointer to a caller-allocated <a href="..\sercx\ns-sercx-_sercx_config.md">SERCX_CONFIG</a> structure that contains configuration information for SerCx. The caller previously called the <a href="..\sercx\nf-sercx-sercx_config_init.md">SERCX_CONFIG_INIT</a> function to initialize this structure.


## Return Value

<b>SerCxInitialize</b> returns STATUS_SUCCESS if it is successful. Possible error return values include the following status codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The method was called at the wrong IRQL; or the WDFDEVICE handle is not valid; or either <i>FxDevice</i> or <i>Config</i> is NULL.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Could not allocate system resources (typically memory).

</td>
</tr>
</table>

## Remarks

The serial controller driver calls this method after it creates the associated device object.

<b>SerCxInitialize</b> registers the controller driver’s I/O callback functions with SerCx. In addition, this method defines the transfer mode for the I/O queue.  During the call, this method creates all of the internal structures required by SerCx (including the I/O queue for the serial controller).  After this method returns, SerCx is ready to process I/O.  However, the controller driver might configure controller hardware settings before it returns from the <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback or before it adds the PDO to the child list.

If the parameters are invalid (as described in <a href="..\sercx\ns-sercx-_sercx_config.md">SERCX_CONFIG</a>), <a href="https://msdn.microsoft.com/library/windows/hardware/ff557262">Driver Verifier</a> will raise an error.

This routine must be called before committing the device (returning from <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> or adding the PDO to the child list).

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8.  |
| **Target Platform** | Universal |
| **Header** | sercx.h |
| **Library** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\sercx\ns-sercx-_sercx_config.md">SERCX_CONFIG</a>



<a href="..\sercx\ns-sercx-_sercx_config.md">SERCX_CONFIG</a>



<a href="..\sercx\nf-sercx-sercx_config_init.md">SERCX_CONFIG_INIT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SerCxInitialize method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>