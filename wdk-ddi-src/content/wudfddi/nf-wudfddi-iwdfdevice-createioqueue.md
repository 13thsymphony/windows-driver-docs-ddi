---
UID: NF:wudfddi.IWDFDevice.CreateIoQueue
title: IWDFDevice::CreateIoQueue method
author: windows-driver-content
description: The CreateIoQueue method configures the default I/O queue that is associated with a device or creates a secondary I/O queue for the device.
old-location: wdf\iwdfdevice_createioqueue.htm
old-project: wdf
ms.assetid: 54c19d8c-59eb-44b2-b406-8fe33cdfcd63
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: IWDFDevice, IWDFDevice::CreateIoQueue, CreateIoQueue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.alt-api: IWDFDevice.CreateIoQueue
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

# IWDFDevice::CreateIoQueue method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>CreateIoQueue</b> method configures the default I/O queue that is associated with a device or creates a secondary I/O queue for the device.



## -syntax

````
HRESULT CreateIoQueue(
  [in, optional] IUnknown                   *pCallbackInterface,
  [in]           BOOL                       bDefaultQueue,
  [in]           WDF_IO_QUEUE_DISPATCH_TYPE DispatchType,
  [in]           BOOL                       bPowerManaged,
  [in]           BOOL                       bAllowZeroLengthRequests,
  [out]          IWDFIoQueue                **ppIoQueue
);
````


## -parameters

### -param pCallbackInterface [in, optional]

A pointer to the <b>IUnknown</b> interface that the framework uses to determine the event callback functions that the driver subscribes to on the queue. These are the functions that the framework calls when the relevant events occur.

 For UMDF versions 1.9 and later, this parameter is required for I/O queues that use the sequential or parallel <a href="wdf.configuring_dispatch_mode_for_an_i_o_queue">dispatching method</a><u>,</u> and it is optional (can be <b>NULL</b>) for I/O queues that use the manual dispatching method. For UMDF versions earlier than 1.9, this parameter is required for all dispatching methods.


### -param bDefaultQueue [in]

A BOOL value that specifies whether to configure the default I/O queue or create a secondary I/O queue for the device. <b>TRUE</b> indicates to configure the default I/O queue; <b>FALSE</b> indicates to create a secondary I/O queue.


### -param DispatchType [in]

A <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_io_queue_dispatch_type.md">WDF_IO_QUEUE_DISPATCH_TYPE</a>-typed value that identifies how the driver must receive requests from the I/O queue.


### -param bPowerManaged [in]

A BOOL value that specifies whether the I/O queue is power managed. <b>TRUE</b> indicates the framework automatically coordinates dispatching for the I/O queue with Plug and Play (PnP) and the power state of the device; <b>FALSE</b> indicates no automatically coordinated dispatching.


### -param bAllowZeroLengthRequests [in]

A BOOL value that specifies whether the framework puts zero-length I/O requests directly in the I/O queue for the driver to handle. <b>TRUE</b> indicates that the driver should receive read and write requests that have zero-length buffers--that is, the framework automatically puts these request types directly in the I/O queue for the driver. <b>FALSE</b> indicates that the framework completes zero-length I/O requests instead of putting them in the I/O queue.


### -param ppIoQueue [out]

A pointer to a variable that receives a pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfioqueue.md">IWDFIoQueue</a> interface for the newly created I/O queue object or the default I/O queue object.


## -returns
<b>CreateIoQueue</b> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The I/O queue was successfully created.
<dl>
<dt><b>HRESULT_FROM_WIN32(ERROR_BAD_CONFIGURATION)</b></dt>
</dl>The I/O queue is configured in one of the following ways:

The <i>DispatchType</i> parameter specifies a nonmanual queue and none of the I/O queue callback interfaces that are specified in the Remarks section are supported through the <i>pCallbackInterface</i> parameter.

The <i>DispatchType</i> parameter specifies a manual queue and one or more of the I/O queue callback interfaces that are specified in the Remarks section are supported through the <i>pCallbackInterface</i> parameter.

For more information about these configurations, see the Remarks section. 

 

<b>CreateIoQueue</b> might also return other HRESULT values.




## -remarks
The <b>IUnknown</b> interface that the driver supplies for the <i>pCallbackInterface</i> parameter can support several queue callback functions. The framework calls the <b>QueryInterface</b> method on the supplied <b>IUnknown</b> interface multiple times to retrieve the interface methods that the driver supports. When applications perform actions that are related to the methods of the supported interfaces (such as, an I/O read request), the framework calls the methods (such as, the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556875">IQueueCallbackRead::OnRead</a> method) to notify the driver. The framework calls <b>QueryInterface</b> for the following interfaces:


<a href="..\wudfddi\nn-wudfddi-iqueuecallbackcreate.md">IQueueCallbackCreate</a>



<a href="..\wudfddi\nn-wudfddi-iqueuecallbackdefaultiohandler.md">IQueueCallbackDefaultIoHandler</a>



<a href="..\wudfddi\nn-wudfddi-iqueuecallbackdeviceiocontrol.md">IQueueCallbackDeviceIoControl</a>



<a href="..\wudfddi\nn-wudfddi-iqueuecallbackread.md">IQueueCallbackRead</a>



<a href="..\wudfddi\nn-wudfddi-iqueuecallbackwrite.md">IQueueCallbackWrite</a>


When the driver passes either <b>WdfIoQueueDispatchSequential</b> or <b>WdfIoQueueDispatchParallel</b> for the <i>DispatchType</i> parameter of <b>CreateIoQueue</b> to create a nonmanual queue, <b>CreateIoQueue</b> can return S_OK only if the driver's queue callback object implements at least one of the preceding interfaces and indicates support of such interfaces through the <b>IUnknown</b> interface that <i>pCallbackInterface</i> points to. 

When the driver passes <b>WdfIoQueueDispatchManual</b> for <i>DispatchType</i> to create a manual queue, <b>CreateIoQueue</b> can return S_OK only if the driver's queue callback object does not implement or indicate support of any of the preceding callback interfaces. For more information about the driver's callback objects, see <a href="https://msdn.microsoft.com/bbae1458-911f-4a48-8bf2-0997e8f98826">Creating Callback Objects</a>.

For more information about configuring dispatch mode, see <a href="https://msdn.microsoft.com/7603c3fd-a4cb-4174-ad14-f57efedfe9de">Configuring Dispatch Mode for an I/O Queue</a>.

The framework also calls <b>QueryInterface</b> on the supplied <b>IUnknown</b> interface to determine if the driver supports any of the following interfaces:


<a href="..\wudfddi\nn-wudfddi-iobjectcleanup.md">IObjectCleanup</a>



<a href="..\wudfddi\nn-wudfddi-iqueuecallbackioresume.md">IQueueCallbackIoResume</a>



<a href="..\wudfddi\nn-wudfddi-iqueuecallbackiostop.md">IQueueCallbackIoStop</a>


The framework also calls <b>QueryInterface</b> on the supplied <b>IUnknown</b> interface to determine if the driver supports the <a href="..\wudfddi\nn-wudfddi-iqueuecallbackstatechange.md">IQueueCallbackStateChange</a> interface. The driver's queue callback object can optionally implement and indicate support of <b>IQueueCallbackStateChange</b> only for a manual queue. The driver's queue callback object must not implement and indicate support of <b>IQueueCallbackStateChange</b> for a sequential or parallel queue. 

For a code example of how to use the <b>CreateIoQueue</b> method, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a>.


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

## -see-also
<dl>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfdevice.md">IWDFDevice</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iobjectcleanup.md">IObjectCleanup</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iqueuecallbackcreate.md">IQueueCallbackCreate</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iqueuecallbackdefaultiohandler.md">IQueueCallbackDefaultIoHandler</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iqueuecallbackdeviceiocontrol.md">IQueueCallbackDeviceIoControl</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iqueuecallbackioresume.md">IQueueCallbackIoResume</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iqueuecallbackiostop.md">IQueueCallbackIoStop</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iqueuecallbackread.md">IQueueCallbackRead</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iqueuecallbackstatechange.md">IQueueCallbackStateChange</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iqueuecallbackwrite.md">IQueueCallbackWrite</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfioqueue.md">IWDFIoQueue</a>
</dt>
<dt>
<a href="..\wudfddi_types\ne-wudfddi_types-_wdf_io_queue_dispatch_type.md">WDF_IO_QUEUE_DISPATCH_TYPE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFDevice::CreateIoQueue method%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

