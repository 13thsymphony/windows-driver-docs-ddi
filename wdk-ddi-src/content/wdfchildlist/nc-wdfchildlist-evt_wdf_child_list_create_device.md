---
UID: NC:wdfchildlist.EVT_WDF_CHILD_LIST_CREATE_DEVICE
title: EVT_WDF_CHILD_LIST_CREATE_DEVICE
author: windows-driver-content
description: A bus driver'sEvtChildListCreateDevice event callback function creates a framework device object for a new device that has been dynamically enumerated.
old-location: wdf\evtchildlistcreatedevice.htm
old-project: wdf
ms.assetid: 296fbe06-1680-43a8-b5c3-1a1faa19c6c3
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evtchildlistcreatedevice, EvtChildListCreateDevice callback function, EvtChildListCreateDevice, EVT_WDF_CHILD_LIST_CREATE_DEVICE, EVT_WDF_CHILD_LIST_CREATE_DEVICE, wdfchildlist/EvtChildListCreateDevice, DFDeviceObjectChildListRef_e3abb118-d40f-46f5-9b70-80d0fc8c531f.xml, kmdf.evtchildlistcreatedevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfchildlist.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	WdfChildlist.h
apiname:
-	EvtChildListCreateDevice
product: Windows
targetos: Windows
req.typenames: "*PWDBGEXTS_THREAD_OS_INFO, WDBGEXTS_THREAD_OS_INFO"
req.product: Windows 10 or later.
---


# EVT_WDF_CHILD_LIST_CREATE_DEVICE function
<p class="CCE_Message">[Applies to KMDF only]

A bus driver's<i>EvtChildListCreateDevice</i> event callback function creates a framework device object for a new device that has been dynamically enumerated.

## Syntax

```
EVT_WDF_CHILD_LIST_CREATE_DEVICE EvtWdfChildListCreateDevice;

NTSTATUS EvtWdfChildListCreateDevice(
  WDFCHILDLIST ChildList,
  PWDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER IdentificationDescription,
  PWDFDEVICE_INIT ChildInit
)
{...}
```

## Parameters

`ChildList`

A handle to the framework child-list object that the driver specified when it called <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistaddorupdatechilddescriptionaspresent.md">WdfChildListAddOrUpdateChildDescriptionAsPresent</a>.

`IdentificationDescription`

A pointer to a copy of the <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_identification_description_header.md">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a> structure that the driver specified when it called <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistaddorupdatechilddescriptionaspresent.md">WdfChildListAddOrUpdateChildDescriptionAsPresent</a>.

`ChildInit`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure.


## Return Value

The <i>EvtChildListCreateDevice</i> callback function must return STATUS_SUCCESS, or another status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>, if the operation succeeds. Otherwise, this function must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>.

If the operation failed but you think your driver should try again later, and if the driver's <i>EvtChildListCreateDevice</i> callback function has not called <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>, the driver can return STATUS_RETRY. As a result, the framework calls the <i>EvtChildListCreateDevice</i> callback function again later. If your driver returns STATUS_RETRY more than a few times, the framework will stop calling the callback function for the failing device.

## Remarks

If a bus driver is using <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dynamic-enumeration">dynamic enumeration</a>, it can register an <i>EvtChildListCreateDevice</i> callback function by calling <a href="..\wdffdo\nf-wdffdo-wdffdoinitsetdefaultchildlistconfig.md">WdfFdoInitSetDefaultChildListConfig</a> or <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistcreate.md">WdfChildListCreate</a>.

After a driver calls <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistaddorupdatechilddescriptionaspresent.md">WdfChildListAddOrUpdateChildDescriptionAsPresent</a> or <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistupdateallchilddescriptionsaspresent.md">WdfChildListUpdateAllChildDescriptionsAsPresent</a>, the framework calls the driver's <i>EvtChildListCreateDevice</i> callback function. The callback function must call <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a> to create a framework device object (a PDO).

Before calling <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>, the driver must call framework-supplied functions that initialize the WDFDEVICE_INIT structure. For more information about these functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a>.

For more information about calling <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.

For more information about dynamic enumeration, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/enumerating-the-devices-on-a-bus">Enumerating the Devices on a Bus</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Header** | wdfchildlist.h (include Wdf.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_identification_description_header.md">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a>

<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistupdateallchilddescriptionsaspresent.md">WdfChildListUpdateAllChildDescriptionsAsPresent</a>

<a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>

<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistaddorupdatechilddescriptionaspresent.md">WdfChildListAddOrUpdateChildDescriptionAsPresent</a>

<a href="..\wdffdo\nf-wdffdo-wdffdoinitsetdefaultchildlistconfig.md">WdfFdoInitSetDefaultChildListConfig</a>

<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistcreate.md">WdfChildListCreate</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_CHILD_LIST_CREATE_DEVICE callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>