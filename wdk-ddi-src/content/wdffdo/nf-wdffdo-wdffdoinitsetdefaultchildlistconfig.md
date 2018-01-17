---
UID: NF:wdffdo.WdfFdoInitSetDefaultChildListConfig
title: WdfFdoInitSetDefaultChildListConfig function
author: windows-driver-content
description: The WdfFdoInitSetDefaultChildListConfig method configures a bus driver's default child list.
old-location: wdf\wdffdoinitsetdefaultchildlistconfig.htm
old-project: wdf
ms.assetid: 656a0c58-dd12-4417-a781-464d1670592c
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfFdoInitSetDefaultChildListConfig
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdffdo.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfFdoInitSetDefaultChildListConfig
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: ChildListConfiguration, DeviceInitAPI, DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: *PWDF_DRIVER_VERSION_AVAILABLE_PARAMS, WDF_DRIVER_VERSION_AVAILABLE_PARAMS
req.product: Windows 10 or later.
---

# WdfFdoInitSetDefaultChildListConfig function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfFdoInitSetDefaultChildListConfig</b> method configures a bus driver's default child list.



## -syntax

````
VOID WdfFdoInitSetDefaultChildListConfig(
  _Inout_  PWDFDEVICE_INIT        DeviceInit,
  _In_     PWDF_CHILD_LIST_CONFIG Config,
  _In_opt_ PWDF_OBJECT_ATTRIBUTES DefaultChildListAttributes
);
````


## -parameters

### -param DeviceInit [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure that the driver obtained from its <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function.


### -param Config [in]

A pointer to a driver-allocated <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_list_config.md">WDF_CHILD_LIST_CONFIG</a> structure.


### -param DefaultChildListAttributes [in, optional]

A pointer to a caller-allocated <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that contains object attributes for the child-list object that represents the driver's default child list. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


## -returns
None


## -remarks
A bus driver must call <b>WdfFdoInitSetDefaultChildListConfig</b> before calling <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a> for the functional device object (FDO). For more information about calling <b>WdfDeviceCreate</b>, see <a href="https://msdn.microsoft.com/25023c19-a153-4bd4-9fb6-3a1bf85860aa">Creating a Framework Device Object</a>.

For more information about the <b>WdfFdoInitSetDefaultChildListConfig</b> method, see <a href="https://msdn.microsoft.com/5731db82-2bc8-4a8d-98f1-3977845f572c">Enumerating the Devices on a Bus</a>.

The following code example initializes a <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_list_config.md">WDF_CHILD_LIST_CONFIG</a> structure and then calls <b>WdfFdoInitSetDefaultChildListConfig</b>. 


## -see-also
<dl>
<dt>
<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistcreate.md">WdfChildListCreate</a>
</dt>
<dt>
<a href="..\wdfchildlist\nf-wdfchildlist-wdf_child_list_config_init.md">WDF_CHILD_LIST_CONFIG_INIT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfFdoInitSetDefaultChildListConfig method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

