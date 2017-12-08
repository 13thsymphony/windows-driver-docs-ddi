---
UID: NF.wdfiotarget.WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN
title: WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN function
author: windows-driver-content
description: The WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN function initializes a driver's WDF_IO_TARGET_OPEN_PARAMS structure so the driver can reopen a remote I/O target.
old-location: wdf\wdf_io_target_open_params_init_reopen.htm
old-project: wdf
ms.assetid: 00f1e870-4c74-44d3-9ee9-c8b9e63e5f3b
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfiotarget.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN
req.alt-loc: wdfiotarget.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level
req.product: Windows 10 or later.
---

# WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]
The <b>WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN</b> function initializes a driver's <a href="wdf.wdf_io_target_open_params">WDF_IO_TARGET_OPEN_PARAMS</a> structure so the driver can reopen a remote I/O target. 


## -syntax

````
VOID WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN(
  _Out_ PWDF_IO_TARGET_OPEN_PARAMS Params
);
````


## -parameters

### -param Params [out]

A pointer to a driver-allocated <a href="wdf.wdf_io_target_open_params">WDF_IO_TARGET_OPEN_PARAMS</a> structure, which the function initializes.

## -returns
None

## -remarks
The <a href="wdf.wdf_io_target_open_params">WDF_IO_TARGET_OPEN_PARAMS</a> structure is used as input to the <a href="wdf.wdfiotargetopen">WdfIoTargetOpen</a> method. Your driver should call <b>WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN</b> to initialize a <b>WDF_IO_TARGET_OPEN_PARAMS</b> structure if the driver is calling <b>WdfIoTargetOpen</b> from within an <a href="..\wdfiotarget\nc-wdfiotarget-evt_wdf_io_target_remove_canceled.md">EvtIoTargetRemoveCanceled</a> callback function.

The <b>WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN</b> function zeros the specified <a href="wdf.wdf_io_target_open_params">WDF_IO_TARGET_OPEN_PARAMS</a> structure and sets the structure's <b>Size</b> member. Then, the function sets the <b>Type</b> member to <a href="wdf.wdf_io_target_open_type">WdfIoTargetOpenReopen</a>.

For more information about I/O targets, see <a href="wdf.using_i_o_targets">Using I/O Targets</a>.

The following code example is a segment of an <a href="..\wdfiotarget\nc-wdfiotarget-evt_wdf_io_target_remove_canceled.md">EvtIoTargetRemoveCanceled</a> callback function that reopens a remote I/O target.

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
Minimum KMDF version
</th>
<td width="70%">
1.0
</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version
</th>
<td width="70%">
2.0
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdfiotarget.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
Any level
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdfiotarget\nc-wdfiotarget-evt_wdf_io_target_remove_canceled.md">EvtIoTargetRemoveCanceled</a>
</dt>
<dt>
<a href="wdf.wdf_io_target_open_params">WDF_IO_TARGET_OPEN_PARAMS</a>
</dt>
<dt>
<a href="wdf.wdfiotargetopen">WdfIoTargetOpen</a>
</dt>
<dt>
<a href="wdf.wdf_io_target_open_type">WdfIoTargetOpenReopen</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
