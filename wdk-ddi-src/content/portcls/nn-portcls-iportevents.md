---
UID: NN:portcls.IPortEvents
title: IPortEvents
author: windows-driver-content
description: The IPortEvents interface is used by miniport drivers to notify clients of hardware events.
old-location: audio\iportevents.htm
old-project: audio
ms.assetid: bbbb5486-1217-4c4d-9421-96994a5fec82
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PcUnregisterIoTimeout
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: portcls.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPortEvents
req.alt-loc: portcls.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: *PPC_EXIT_LATENCY, PC_EXIT_LATENCY
---

# IPortEvents interface



## -description
The <code>IPortEvents</code> interface is used by miniport drivers to notify clients of <a href="https://msdn.microsoft.com/b91e02dd-0de4-4de3-ade6-778339ce47a8">hardware events</a>. In Windows 98/Me and in Windows 2000 and later, all port drivers in portcls.sys implement this interface and expose it to miniport drivers. To determine whether a port driver supports the <code>IPortEvents</code> interface, the miniport driver calls the IPort<i>Xxx</i> object's <b>QueryInterface</b> method with REFIID <b>IID_IPortEvents</b>. <code>IPortEvents</code> inherits from the <b>IUnknown</b> interface.

Drivers typically use the <code>IPortEvents</code> interface to notify the system of hardware-generated volume or mute changes, although <code>IPortEvents</code> can be used for any type of event notification. <code>IPortEvents</code> interface is an optional lower-edge port driver interface. It can be used, for example, to notify <b>mixer</b> applications of control or mixer-line changes. For information about the <b>mixer</b> API, see the Microsoft Windows SDK documentation.

A miniport driver exposes an event in the same way that it exposes properties: through an automation table (see <a href="..\portcls\ns-portcls-__unnamed_struct_0c93_6.md">PCAUTOMATION_TABLE</a>). The following objects, all of which are exposed by the miniport driver, can specify an automation table that contains properties and/or events:

The filter that the miniport driver implements

Each pin that the filter exposes

Each node that the filter exposes

Each event entry in an automation table is a structure of type <a href="..\portcls\ns-portcls-__unnamed_struct_0c93_5.md">PCEVENT_ITEM</a> that specifies the following:

An event set

An event within the set

Flags indicating support options

A function pointer to the handler for the event

Once the adapter driver is started and its port/miniport driver pairs have been registered as filters with the system, the <a href="audio.user_mode_wdm_audio_components#wdmaud_system_driver#wdmaud_system_driver">WDMAud system driver</a>, which translates <b>mixer</b> API calls into KS commands to WDM audio drivers, will open each port/miniport driver pair and interrogate its capabilities. During this process, WDMAud will traverse the miniport driver's filter topology in search of a control node that supports a hardware event. The event is represented by the combination of event-set GUID <a href="https://msdn.microsoft.com/library/windows/hardware/ff537122">KSEVENTSETID_AudioControlChange</a> and event ID <a href="https://msdn.microsoft.com/library/windows/hardware/ff537128">KSEVENT_CONTROL_CHANGE</a>. When WdmAud finds these, it enables the event, effectively registering itself as a client of the event. Subsequently, each time the miniport driver signals the event, this notifies WDMAud, which generates the appropriate windows messages for its clients.

In addition to exposing the event in the automation table, a miniport driver that needs to expose events should query the port driver for its <code>IPortEvents</code> interface.

This section also describes the following routine for handling event requests:


<a href="..\portcls\nc-portcls-pcpfnevent_handler.md">EventHandler</a>




## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPortEvents</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface but does not have additional members.


## -remarks
