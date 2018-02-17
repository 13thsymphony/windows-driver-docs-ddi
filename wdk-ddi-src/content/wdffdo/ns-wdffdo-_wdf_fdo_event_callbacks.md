---
UID: NS:wdffdo._WDF_FDO_EVENT_CALLBACKS
title: "_WDF_FDO_EVENT_CALLBACKS"
author: windows-driver-content
description: The WDF_FDO_EVENT_CALLBACKS structure contains pointers to a function driver's PnP event callback functions.
old-location: wdf\wdf_fdo_event_callbacks.htm
old-project: wdf
ms.assetid: 61e268aa-782a-42d5-8965-b935156033cb
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdffdo/PWDF_FDO_EVENT_CALLBACKS, _WDF_FDO_EVENT_CALLBACKS, DFDeviceObjectFdoPdoRef_ed4f99d4-cc25-4275-b523-36cd439cac86.xml, kmdf.wdf_fdo_event_callbacks, *PWDF_FDO_EVENT_CALLBACKS, WDF_FDO_EVENT_CALLBACKS structure, wdf.wdf_fdo_event_callbacks, PWDF_FDO_EVENT_CALLBACKS structure pointer, WDF_FDO_EVENT_CALLBACKS, wdffdo/WDF_FDO_EVENT_CALLBACKS, PWDF_FDO_EVENT_CALLBACKS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdffdo.h
req.include-header: Wdf.h
req.target-type: Windows
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdffdo.h
apiname:
-	WDF_FDO_EVENT_CALLBACKS
product: Windows
targetos: Windows
req.typenames: "*PWDF_FDO_EVENT_CALLBACKS, WDF_FDO_EVENT_CALLBACKS"
req.product: Windows 10 or later.
---

# _WDF_FDO_EVENT_CALLBACKS structure
<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_FDO_EVENT_CALLBACKS</b> structure contains pointers to a function driver's PnP event callback functions.

## Syntax
````
typedef struct _WDF_FDO_EVENT_CALLBACKS {
  ULONG                                       Size;
  PFN_WDF_DEVICE_FILTER_RESOURCE_REQUIREMENTS EvtDeviceFilterAddResourceRequirements;
  PFN_WDF_DEVICE_FILTER_RESOURCE_REQUIREMENTS EvtDeviceFilterRemoveResourceRequirements;
  PFN_WDF_DEVICE_REMOVE_ADDED_RESOURCES       EvtDeviceRemoveAddedResources;
} WDF_FDO_EVENT_CALLBACKS, *PWDF_FDO_EVENT_CALLBACKS;
````

## Members


`EvtDeviceFilterAddResourceRequirements`

A pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff540870">EVT_WDF_DEVICE_FILTER_RESOURCE_REQUIREMENTS</a> event callback function, or <b>NULL</b>.

`EvtDeviceFilterRemoveResourceRequirements`

A pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff540870">EVT_WDF_DEVICE_FILTER_RESOURCE_REQUIREMENTS</a> event callback function, or <b>NULL</b>.

`EvtDeviceRemoveAddedResources`

A pointer to the driver's <a href="..\wdffdo\nc-wdffdo-evt_wdf_device_remove_added_resources.md">EvtDeviceRemoveAddedResources</a> event callback function, or <b>NULL</b>.

`Size`

The size, in bytes, of this structure.

## Remarks
The <b>WDF_FDO_EVENT_CALLBACKS</b> structure is used as input to the <a href="..\wdffdo\nf-wdffdo-wdffdoinitseteventcallbacks.md">WdfFdoInitSetEventCallbacks</a> method.

Drivers must call <a href="..\wdffdo\nf-wdffdo-wdf_fdo_event_callbacks_init.md">WDF_FDO_EVENT_CALLBACKS_INIT</a> to initialize the structure.

A driver that specifies an <a href="https://msdn.microsoft.com/7d9b38b5-989d-45a3-8771-57a8d1f98725">EvtDeviceFilterAddResourceRequirements</a> event callback function must also specify an <a href="..\wdffdo\nc-wdffdo-evt_wdf_device_remove_added_resources.md">EvtDeviceRemoveAddedResources</a> event callback function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum KMDF version** | 1.0 |
| **Header** | wdffdo.h (include Wdf.h) |

## See Also

<a href="..\wdffdo\nf-wdffdo-wdffdoinitseteventcallbacks.md">WdfFdoInitSetEventCallbacks</a>



<a href="..\wdffdo\nf-wdffdo-wdf_fdo_event_callbacks_init.md">WDF_FDO_EVENT_CALLBACKS_INIT</a>



<a href="..\wdfpdo\ns-wdfpdo-_wdf_pdo_event_callbacks.md">WDF_PDO_EVENT_CALLBACKS</a>



<a href="..\wdfpdo\nf-wdfpdo-wdfpdoinitseteventcallbacks.md">WdfPdoInitSetEventCallbacks</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_FDO_EVENT_CALLBACKS structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>