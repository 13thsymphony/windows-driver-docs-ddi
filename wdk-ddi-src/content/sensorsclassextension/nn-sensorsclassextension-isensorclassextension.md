---
UID: NN:sensorsclassextension.ISensorClassExtension
title: ISensorClassExtension
author: windows-driver-content
description: The ISensorClassExtension interface provides methods that the sensor driver uses to communicate with the sensor platform (and, therefore, client applications) through the sensor class extension object.
old-location: sensors\isensorclassextension.htm
old-project: sensors
ms.assetid: db455be3-3aec-47c4-81a8-992aa4926138
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: sensors.isensorclassextension, ISensorClassExtension interface [Sensor Devices], ISensorClassExtension interface [Sensor Devices], described, ISensorClassExtension, sensorsclassextension/ISensorClassExtension, Sensor_IFaces_84ca9d2b-f0e3-4500-99a4-21054c7dc527.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: sensorsclassextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: SensorsClassExtension.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	SensorsClassExtension.lib
-	SensorsClassExtension.dll
apiname:
-	ISensorClassExtension
product: Windows
targetos: Windows
req.typenames: SensorConnectionType
req.product: Windows 10 or later.
---

# ISensorClassExtension interface

The ISensorClassExtension interface provides methods that the sensor driver uses to communicate with the sensor platform (and, therefore, client applications) through the sensor class extension object.

## Methods

<p>The <b>ISensorClassExtension</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [sensorsclassextension.ISensorClassExtension.CleanupFile](nf-sensorsclassextension-isensorclassextension-cleanupfile.md) | The ISensorClassExtension::CleanupFile method notifies the class extension about a file handle that closes and cancels all pending I/O requests, for the specified application. |
| [sensorsclassextension.ISensorClassExtension.Initialize](nf-sensorsclassextension-isensorclassextension-initialize.md) | The ISensorClassExtension::Initialize method initializes the sensor class extension object. |
| [sensorsclassextension.ISensorClassExtension.PostEvent](nf-sensorsclassextension-isensorclassextension-postevent.md) | The ISensorClassExtension::PostEvent method raises one or more driver events in the sensor class extension. |
| [sensorsclassextension.ISensorClassExtension.PostStateChange](nf-sensorsclassextension-isensorclassextension-poststatechange.md) | The ISensorClassExtension::PostStateChange method notifies the sensor class extension about a change in the operational state of the sensor. |
| [sensorsclassextension.ISensorClassExtension.ProcessIoControl](nf-sensorsclassextension-isensorclassextension-processiocontrol.md) | The ISensorClassExtension::ProcessControl method sends Windows Portable Devices (WPD) I/O control requests to the sensor class extension for processing. |
| [sensorsclassextension.ISensorClassExtension.Uninitialize](nf-sensorsclassextension-isensorclassextension-uninitialize.md) | The ISensorClassExtension::Uninitialize method uninitializes the sensor class extension object. |

## Remarks



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | sensorsclassextension.h |