---
UID: NC:wdfdevice.EVT_WDF_DEVICE_RELATIONS_QUERY
title: EVT_WDF_DEVICE_RELATIONS_QUERY function
author: windows-driver-content
description: A driver's EvtDeviceRelationsQuery event callback reports changes in the relationships among devices that are supported by the driver.
old-location: wdf\evtdevicerelationsquery.htm
old-project: wdf
ms.assetid: 3a156696-1dd5-4383-a0cc-8d07ec92bdbf
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: EVT_WDF_DEVICE_RELATIONS_QUERY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: EvtDeviceRelationsQuery
req.alt-loc: Wdfdevice.h
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
req.typenames: WDF_DEVICE_SHUTDOWN_FLAGS
req.product: Windows 10 or later.
---

# EVT_WDF_DEVICE_RELATIONS_QUERY function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtDeviceRelationsQuery</i> event callback reports changes in the relationships among devices that are supported by the driver.



## -syntax

````
EVT_WDF_DEVICE_RELATIONS_QUERY EvtDeviceRelationsQuery;

VOID EvtDeviceRelationsQuery(
  _In_ WDFDEVICE            Device,
  _In_ DEVICE_RELATION_TYPE RelationType
)
{ ... }
````


## -parameters

### -param Device [in]

A handle to a framework device object.


### -param RelationType [in]

A DEVICE_RELATION_TYPE-typed enumerator value. The DEVICE_RELATION_TYPE enumeration is defined in <i>wdm.h</i>.


## -returns
None


## -remarks
To register the <i>EvtDeviceRelationsQuery</i> callback function, a driver must call <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetpnppowereventcallbacks.md">WdfDeviceInitSetPnpPowerEventCallbacks</a>.

Most framework-based drivers do not need to provide this callback function.

During system initialization, the Plug and Play manager enumerates all of the devices on the system by sending an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551670">IRP_MN_QUERY_DEVICE_RELATIONS</a> request to the driver stack. If a framework-based driver has registered an <i>EvtDeviceRelationsQuery</i> callback function, the framework calls it. The function driver for the bus must report all of the child devices that are attached to the bus.

Additionally, after the framework calls the <a href="..\wdm\nf-wdm-ioinvalidatedevicerelations.md">IoInvalidateDeviceRelations</a> routine to report a changed relationship among the devices on the driver's bus, the Plug and Play manager sends another IRP_MN_QUERY_DEVICE_RELATIONS request to the driver stack. The framework then calls the driver's <i>EvtDeviceRelationsQuery</i> callback function so that the driver can provide details about the change. 

The type of work that a driver must do depends on the value received for the <i>RelationType</i> parameter. The value can be one of the following:



Most framework-based drivers do not report bus relations in an <i>EvtDeviceRelationsQuery</i> callback function. Instead, the drivers follow the guidelines that are described in <a href="https://msdn.microsoft.com/5731db82-2bc8-4a8d-98f1-3977845f572c">Enumerating the Devices on a Bus</a>.

Most framework-based drivers do not report ejection relations in an <i>EvtDeviceRelationsQuery</i> callback function. Instead, the driver for the device's bus calls <a href="..\wdfpdo\nf-wdfpdo-wdfpdoaddejectionrelationsphysicaldevice.md">WdfPdoAddEjectionRelationsPhysicalDevice</a> and <a href="..\wdfpdo\nf-wdfpdo-wdfpdoremoveejectionrelationsphysicaldevice.md">WdfPdoRemoveEjectionRelationsPhysicalDevice</a><i>.</i>

Most framework-based drivers do not report removal relations in an <i>EvtDeviceRelationsQuery</i> callback function. Instead, the drivers call <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceaddremovalrelationsphysicaldevice.md">WdfDeviceAddRemovalRelationsPhysicalDevice</a> and <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceremoveremovalrelationsphysicaldevice.md">WdfDeviceRemoveRemovalRelationsPhysicalDevice</a>.

Framework-based drivers do not have to report a device's target relation. Instead, the framework handles this request.

The framework can call the <i>EvtDeviceRelationsQuery</i> callback function with a <i>RelationType</i> value of <b>EjectionRelations</b> or <b>RemovalRelations</b> even if the device is being removed. 

To define an <i>EvtDeviceRelationsQuery</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDeviceRelationsQuery</i> callback function that is named <i>MyDeviceRelationsQuery</i>, use the <b>EVT_WDF_DEVICE_RELATIONS_QUERY</b> type as shown in this code example:

Then, implement your callback function as follows:

The <b>EVT_WDF_DEVICE_RELATIONS_QUERY</b> function type is defined in the Wdfdevice.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_RELATIONS_QUERY</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.</p>