---
UID: NF:wdfpdo.WdfPdoInitAllowForwardingRequestToParent
title: WdfPdoInitAllowForwardingRequestToParent function
author: windows-driver-content
description: The WdfPdoInitAllowForwardingRequestToParent method enables a driver's ability to call WdfRequestForwardToParentDeviceIoQueue.
old-location: wdf\wdfpdoinitallowforwardingrequesttoparent.htm
old-project: wdf
ms.assetid: fc8e4484-4059-4274-bb61-5d3b2f965b19
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfPdoInitAllowForwardingRequestToParent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfpdo.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.9
req.umdf-ver: 
req.alt-api: WdfPdoInitAllowForwardingRequestToParent
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: *PWDF_OBJECT_CONTEXT_TYPE_INFO, WDF_OBJECT_CONTEXT_TYPE_INFO
req.product: Windows 10 or later.
---

# WdfPdoInitAllowForwardingRequestToParent function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfPdoInitAllowForwardingRequestToParent</b> method enables a driver's ability to call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestforwardtoparentdeviceioqueue.md">WdfRequestForwardToParentDeviceIoQueue</a>.



## -syntax

````
VOID WdfPdoInitAllowForwardingRequestToParent(
  _In_ PWDFDEVICE_INIT DeviceInit
);
````


## -parameters

### -param DeviceInit [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure.


## -returns
None.


## -remarks
If your driver uses <a href="..\wdfrequest\nf-wdfrequest-wdfrequestforwardtoparentdeviceioqueue.md">WdfRequestForwardToParentDeviceIoQueue</a> to requeue I/O requests from a child device's I/O queue to a parent device's I/O queue, the driver must call <b>WdfPdoInitAllowForwardingRequestToParent</b> before it calls <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a> to create a physical device object (PDO) for the child device. For more information about calling <b>WdfDeviceCreate</b>, see <a href="https://msdn.microsoft.com/25023c19-a153-4bd4-9fb6-3a1bf85860aa">Creating a Framework Device Object</a>.

For more information about <b>WdfPdoInitAllowForwardingRequestToParent</b> and <a href="..\wdfrequest\nf-wdfrequest-wdfrequestforwardtoparentdeviceioqueue.md">WdfRequestForwardToParentDeviceIoQueue</a>, see <a href="https://msdn.microsoft.com/b509959c-b2ab-4f04-9c08-5c5e90726b73">Requeuing I/O Requests</a>.

The following code example enables a driver's ability to call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestforwardtoparentdeviceioqueue.md">WdfRequestForwardToParentDeviceIoQueue</a>.


## -see-also
<dl>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestforwardtoparentdeviceioqueue.md">WdfRequestForwardToParentDeviceIoQueue</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfPdoInitAllowForwardingRequestToParent method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

