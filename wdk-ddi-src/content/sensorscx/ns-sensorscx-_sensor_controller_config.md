---
UID: NS.SENSORSCX._SENSOR_CONTROLLER_CONFIG
title: _SENSOR_CONTROLLER_CONFIG
author: windows-driver-content
description: This structure contains pointers to callback functions that must be implemented by the driver, and passed on to the class extension to call.
old-location: sensors\sensor_controller_config.htm
old-project: sensors
ms.assetid: EEAC4D16-D0B8-4147-AD2D-7EE60853EBDD
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: _SENSOR_CONTROLLER_CONFIG, *PSENSOR_CONTROLLER_CONFIG, SENSOR_CONTROLLER_CONFIG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: sensorscx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SENSOR_CONTROLLER_CONFIG
req.alt-loc: SensorsCx.h
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

# _SENSOR_CONTROLLER_CONFIG structure



## -description
This structure contains pointers to callback functions that must be implemented by the driver, and passed on to the class extension to call.


## -syntax

````
typedef struct _SENSOR_CONTROLLER_CONFIG {
  ULONG                                       Size;
  WDF_TRI_STATE                               DriverIsPowerPolicyOwner;
  PFN_SENSOR_DRIVER_START_SENSOR {
    SENSOROBJECT Sensor;
  }             EvtSensorStart;
  PFN_SENSOR_DRIVER_STOP_SENSOR {
    SENSOROBJECT Sensor;
  }              EvtSensorStop;
  PFN_SENSOR_DRIVER_GET_SUPPORTED_DATA_FIELDS {
    SENSOROBJECT          Sensor;
    PSENSOR_PROPERTY_LIST pDataFields;
    PULONG                pSize;
  }EvtSensorGetSupportedDataFields;
  PFN_SENSOR_DRIVER_GET_DATA_FIELD_PROPERTIES {
    SENSOROBJECT            Sensor;
    PROPERTYKEY             pDataField;
    PSENSOR_COLLECTION_LIST pProperties;
    PULONG                  pSize;
  }EvtSensorGetDataFieldProperties;
  PFN_SENSOR_DRIVER_GET_DATA_INTERVAL {
    SENSOROBJECT Sensor;
    PULONG       pDataRateMs;
  }        EvtSensorGetDataInterval;
  PFN_SENSOR_DRIVER_SET_DATA_INTERVAL {
    SENSOROBJECT Sensor;
    ULONG        DataRateMs;
  }        EvtSensorSetDataInterval;
  PFN_SENSOR_DRIVER_GET_DATA_THRESHOLDS {
    SENSOROBJECT            Sensor;
    PSENSOR_COLLECTION_LIST pThresholds;
    PULONG                  pSize;
  }      EvtSensorGetDataThresholds;
  PFN_SENSOR_DRIVER_SET_DATA_THRESHOLDS {
    SENSOROBJECT            Sensor;
    PSENSOR_COLLECTION_LIST pThresholds;
  }      EvtSensorSetDataThresholds;
  PFN_SENSOR_DRIVER_GET_PROPERTIES {
    SENSOROBJECT            Sensor;
    PSENSOR_COLLECTION_LIST pProperties;
    PULONG                  pSize;
  }           EvtSensorGetProperties;
  PFN_SENSOR_DRIVER_DEVICE_IO_CONTROL {
    SENSOROBJECT Sensor;
    WDFREQUEST   Request;
    size_t       OutputBufferLength;
    size_t       InputBufferLength;
    ULONG        IoControlCode;
  }        EvtSensorDeviceIoControl;
  void                                        (jjjj *EvtSensorSetBatchLatency)(
       Sensor, 
       BatchLatencyMs);
} SENSOR_CONTROLLER_CONFIG, *PSENSOR_CONTROLLER_CONFIG;
````


## -struct-fields

### -field Size

The allocated size of this structure (in bytes).

### -field DriverIsPowerPolicyOwner

Indicates whether or not driver owns the power policy. This value must be either WdfFalse, WdfUseDefault, or WdfTrue. For partners to take advantage of pep-based power management, they must set this flag to WdfFalse or WdfUseDefault and remove any _PSx method in their ACPI tables.

### -field EvtSensorStart

This callback function starts the sensor based on the default properties specified by the driver, or properties set by the class extension.

<pre class="syntax">NTSTATUS EVT_SENSOR_DRIVER_START_SENSOR(
    _In_ SENSOROBJECT Sensor);</pre>


### -field Sensor

A reference to a sensor object.
</dd>
</dl>

### -field EvtSensorStop

This callback function stops the sensor.

<pre class="syntax">NTSTATUS EVT_SENSOR_DRIVER_STOP_SENSOR(
    _In_ SENSOROBJECT Sensor);</pre>


### -field Sensor

A reference to a sensor object.
</dd>
</dl>

### -field EvtSensorGetSupportedDataFields

This callback function returns a list of data fields supported by the specified sensor.

<pre class="syntax">NTSTATUS EVT_SENSOR_DRIVER_GET_SUPPORTED_DATA_FIELDS(
    _In_ SENSOROBJECT Sensor,
    _Inout_opt_ PSENSOR_PROPERTY_LIST pDataFields,
    _Out_ PULONG pSize);</pre>


### -field Sensor

A reference to a sensor object.

### -field pDataFields

A list of data fields that are supported by the given sensor.

### -field pSize

The size of pFields.
</dd>
</dl>

### -field EvtSensorGetDataFieldProperties

This callback function returns the properties of a given data field associated with a sensor.

<pre class="syntax">NTSTATUS EVT_SENSOR_DRIVER_GET_DATA_FIELD_PROPERTIES(
    _In_ SENSOROBJECT Sensor,
    _In_ const PROPERTYKEY *pDataField,
    _Inout_opt_ PSENSOR_COLLECTION_LIST pProperties,
    _Out_ PULONG pSize);</pre>


### -field Sensor

A reference to a sensor object.



### -field pDataField

A reference to a data field.

### -field pProperties

A list of properties associated with the pDataField.

### -field pSize

The size of pDataField.
</dd>
</dl>

### -field EvtSensorGetDataInterval

This callback function returns the data interval for a specified sensor.

<pre class="syntax">NTSTATUS EVT_SENSOR_DRIVER_GET_DATA_INTERVAL(
    _In_ SENSOROBJECT Sensor,
    _Out_ PULONG pDataRateMs);</pre>


### -field Sensor

A reference to a sensor object.



### -field pDataRateMs

The data interval for the specified sensor.
</dd>
</dl>

### -field EvtSensorSetDataInterval

This callback function sets the data interval for a specified sensor.

<pre class="syntax">NTSTATUS EVT_SENSOR_DRIVER_SET_DATA_INTERVAL(
    _In_ SENSOROBJECT Sensor,
    _In_ ULONG DataRateMs);</pre>


### -field Sensor

A reference to a sensor object.



### -field DataRateMs

The data interval for to set for the sensor.
</dd>
</dl>

### -field EvtSensorGetDataThresholds

This callback function returns the thresholds that are associated with a sensor.

<pre class="syntax">NTSTATUS EVT_SENSOR_DRIVER_GET_DATA_THRESHOLDS(
    _In_ SENSOROBJECT Sensor,
    _Inout_opt_ PSENSOR_COLLECTION_LIST pThresholds,
    _Out_ PULONG pSize);</pre>


### -field Sensor

A reference to a sensor object.



### -field pThresholds

A list of threshold properties and their values associated with the sensor.

### -field pSize

The size of pThresholds.
</dd>
</dl>

### -field EvtSensorSetDataThresholds

This callback function stops the sensor.

<pre class="syntax">NTSTATUS EVT_SENSOR_DRIVER_SET_DATA_THRESHOLDS(
    _In_ SENSOROBJECT Sensor,
    _In_ PSENSOR_COLLECTION_LIST pThresholds);</pre>


### -field Sensor

A reference to a sensor object.



### -field pThresholds

A list of threshold properties and their values associated with the sensor.
</dd>
</dl>

### -field EvtSensorGetProperties

This callback function returns the properties for a given sensor.

<pre class="syntax">NTSTATUS EVT_SENSOR_DRIVER_GET_PROPERTIES(
    _In_ SENSOROBJECT Sensor,
    _Inout_opt_ PSENSOR_COLLECTION_LIST pProperties,
    _Out_ PULONG pSize);</pre>


### -field Sensor

A reference to a sensor object.



### -field pProperties

A list of properties and their values for the specified sensor.

### -field pSize

The size of pProperties.
</dd>
</dl>

### -field EvtSensorDeviceIoControl

This callback function handles IOCTLs outside of the class extension.<div class="alert"><b>Note</b>  If the driver needs to queue the IRP, it must copy the IRP to an IoQueue that the driver owns. This will prevent all IRPs for the driver to be stalled until completion.</div>
<div> </div>


<pre class="syntax">NTSTATUS EVT_SENSOR_DRIVER_DEVICE_IO_CONTROL(
    _In_ SENSOROBJECT Sensor,
    _In_ WDFREQUEST Request,
    _In_ size_t OutputBufferLength,
    _In_ size_t InputBufferLength,
    _In_ ULONG IoControlCode);</pre>


### -field Sensor

A reference to a sensor object.



### -field Request

A handle to a framework request object that represents the I/O request.

### -field OutputBufferLength

The length of the output buffer (in bytes).



### -field InputBufferLength

The length of the input buffer (in bytes).



### -field IoControlCode

The code that indicates which device I/O control function is to be executed.


</dd>
</dl>

### -field EvtSensorSetBatchLatency

This callback function sets the batch latency for a specified sensor.<pre class="syntax">typedef _Function_class_(EVT_SENSOR_DRIVER_SET_BATCH_LATENCY)
_IRQL_requires_same_
_Check_return_
NTSTATUS EVT_SENSOR_DRIVER_SET_BATCH_LATENCY(
    _In_ SENSOROBJECT Sensor,
    _In_ ULONG BatchLatencyMs );

typedef EVT_SENSOR_DRIVER_SET_BATCH_LATENCY *PFN_SENSOR_DRIVER_SET_BATCH_LATENCY;</pre>


### -field Sensor

A reference to a sensor object.

### -field BatchLatencyMs

The batch latency, expressed in milliseconds.
</dd>
</dl>

## -remarks
This structure is given to the class extension using the <a href="sensors.sensorscxdeviceinitialize">SensorsCxDeviceInitialize</a> function. If any of the following function pointers are not set, the driver will fail to load:

Each function returns STATUS_SUCCESS when completed successfully.

<div class="alert"><b>Note</b>  The class extension (CX) only uses the NT_SUCCESS macro to determine if the call to the driver’s Evt function was successful, but does not take any action if the function failed or does not return STATUS_SUCCESS.

</div>
<div> </div>


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client
</th>
<td width="70%">
Windows 8.1
</td>
</tr>
<tr>
<th width="30%">
Minimum supported server
</th>
<td width="70%">
Windows Server 2012 R2
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>SensorsCx.h</dt>
</dl>
</td>
</tr>
</table>