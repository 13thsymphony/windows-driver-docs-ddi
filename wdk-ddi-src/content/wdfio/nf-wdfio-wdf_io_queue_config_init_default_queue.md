---
UID: NF.wdfio.WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE
title: WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE function
author: windows-driver-content
description: The WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE function initializes a driver's WDF_IO_QUEUE_CONFIG structure.
old-location: wdf\wdf_io_queue_config_init_default_queue.htm
old-project: wdf
ms.assetid: c7d0c483-b534-471b-8172-174abdbb3c6a
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfio.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE
req.alt-loc: wdfio.h
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
req.product: Windows 10 or later.
---

# WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE</b> function initializes a driver's <a href="wdf.wdf_io_queue_config">WDF_IO_QUEUE_CONFIG</a> structure.



## -syntax

````
VOID WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE(
  _Out_ PWDF_IO_QUEUE_CONFIG       Config,
  _In_  WDF_IO_QUEUE_DISPATCH_TYPE DispatchType
);
````


## -parameters

### -param Config [out]

A pointer to the driver's <a href="wdf.wdf_io_queue_config">WDF_IO_QUEUE_CONFIG</a> structure.


### -param DispatchType [in]

A <a href="wdf.wdf_io_queue_dispatch_type">WDF_IO_QUEUE_DISPATCH_TYPE</a> enumerator that identifies the request dispatching type for the queue.


## -returns
None


## -remarks
Drivers should call <b>WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE</b> when creating a power-managed I/O queue that is a device's default queue. The <b>WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE</b> function zeros the specified <a href="wdf.wdf_io_queue_config">WDF_IO_QUEUE_CONFIG</a> structure and sets its <b>Size</b> member. It also sets the <b>PowerManaged</b> member to <b>WdfUseDefault</b>, sets the <b>DefaultQueue</b> member to <b>TRUE</b>, and stores the specified dispatching type in the <b>DispatchType</b> member.

Starting in KMDF version 1.9, if <i>DispatchType</i> is set to <b>WdfIoQueueDispatchParallel</b>, <b>WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE</b> sets the structure's <b>NumberOfPresentedRequests</b> member to -1. This value indicates that the framework can deliver an unlimited number of I/O requests to the driver.

For a code example that uses <b>WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE</b>, see <a href="wdf.wdfioqueuecreate">WdfIoQueueCreate</a>.


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
<dt>Wdfio.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdf_io_queue_config">WDF_IO_QUEUE_CONFIG</a>
</dt>
<dt>
<a href="wdf.wdf_io_queue_config_init">WDF_IO_QUEUE_CONFIG_INIT</a>
</dt>
<dt>
<a href="wdf.wdf_io_queue_dispatch_type">WDF_IO_QUEUE_DISPATCH_TYPE</a>
</dt>
<dt>
<a href="wdf.wdfioqueuecreate">WdfIoQueueCreate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE function%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

