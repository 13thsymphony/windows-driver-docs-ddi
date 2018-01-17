---
UID: NF:wudfddi.IWDFDevice.PostEvent
title: IWDFDevice::PostEvent method
author: windows-driver-content
description: The PostEvent method asynchronously notifies applications that are waiting for the specified event from a driver.
old-location: wdf\iwdfdevice_postevent.htm
old-project: wdf
ms.assetid: 3df25c91-d421-48fe-958c-48bce3bc78b8
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IWDFDevice, IWDFDevice::PostEvent, PostEvent
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
req.alt-api: IWDFDevice.PostEvent
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

# IWDFDevice::PostEvent method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>PostEvent</b> method asynchronously notifies applications that are waiting for the specified event from a driver.



## -syntax

````
HRESULT PostEvent(
  [in] REFGUID        EventGuid,
  [in] WDF_EVENT_TYPE EventType,
  [in] BYTE           *pbData,
  [in] DWORD          cbDataSize
);
````


## -parameters

### -param EventGuid [in]

The GUID for the event. The GUID is determined by the application and the driver and is opaque to the framework.


### -param EventType [in]

A <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_event_type.md">WDF_EVENT_TYPE</a>-typed value that identifies the type of event. In the current version of UMDF, the driver must set <i>EventType</i> to <b>WdfEventBroadcast</b> (1). <b>WdfEventBroadcast</b> indicates that the event is broadcast. Applications can subscribe to <b>WdfEventBroadcast</b>-type events. To receive broadcast events, the application must register for notification through the Microsoft Win32 <b>RegisterDeviceNotification</b> function. <b>WdfEventBroadcast</b>-type events are exposed as DBT_CUSTOMEVENT-type events to applications.


### -param pbData [in]

A pointer to a buffer that contains data that is associated with the event. <b>NULL</b> is a valid value. 


### -param cbDataSize [in]

The size, in bytes, of data that <i>pbData</i> points to. Zero is a valid size value if <i>pbData</i> is set to <b>NULL</b>. 

The maximum size of the event data is slightly less than MAXUSHORT (64 KB). The precise upper limit is (0xFFFF - <a href="..\wdm\nf-wdm-field_offset.md">FIELD_OFFSET</a>(<a href="..\wdm\ns-wdm-_target_device_custom_notification.md">TARGET_DEVICE_CUSTOM_NOTIFICATION</a>, CustomDataBuffer)). 


## -returns
<b>PostEvent</b> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The event data was successfully sent to the operating system.
<dl>
<dt><b>HRESULT_FROM_WIN32(ERROR_NOT_ENOUGH_MEMORY)</b></dt>
</dl>The data size that the <i>cbDataSize</i> parameter specifies is larger than the maximum allowable size. 
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>The <i>EventType</i> parameter is not set to <b>WdfEventBroadcast</b> (1). 
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
<a href="https://msdn.microsoft.com/3df25c91-d421-48fe-958c-48bce3bc78b8">PostEvent</a> could not allocate memory that was required for it to complete.

 

<b>PostEvent</b> might also return other HRESULT values.


## -remarks
When the driver calls <b>IWDFDevice::PostEvent</b> to notify the requesting application about an event, UMDF sends the event to the operating system. The operating system sends the event on to the requesting application in an asynchronous operation. If the operating system initially returns no error, the driver receives no error (S_OK). However, later, if the operating system receives an error while it attempts to deliver the event (possibly because of a low memory condition), the operating system is unable to inform the driver about the error. Because of the asynchronous nature of this event notification, delivery of the event to the requesting application is not guaranteed. If event information is lost on its way up to the requesting application, the application should be able to recover from the lost event. 

For information about creating device events, see <a href="https://msdn.microsoft.com/acb6da80-bd04-48f0-b42a-96463f091b0a">Using Device Interfaces in UMDF Drivers</a>.


## -see-also
<dl>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfdevice.md">IWDFDevice</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-field_offset.md">FIELD_OFFSET</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_target_device_custom_notification.md">TARGET_DEVICE_CUSTOM_NOTIFICATION</a>
</dt>
<dt>
<a href="..\wdfdevice\nf-wdfdevice-wdfdevicepostevent.md">WdfDevicePostEvent</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFDevice::PostEvent method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

