---
UID: NS.STORPORT._STOR_POFX_DEVICE_V3
title: _STOR_POFX_DEVICE_V3
author: windows-driver-content
description: The STOR_POFX_DEVICE_V3 structure describes the power attributes of a storage device to the power management framework (PoFx).
old-location: storage\stor_pofx_device_v3.htm
old-project: storage
ms.assetid: 49B03A5F-9F96-4F0B-AC52-ADBDC8ED03B2
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _STOR_POFX_DEVICE_V3, PSTOR_POFX_DEVICE_V3, STOR_POFX_DEVICE_V3, *PSTOR_POFX_DEVICE_V3
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: storport.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STOR_POFX_DEVICE_V3
req.alt-loc: storport.h
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

# _STOR_POFX_DEVICE_V3 structure



## -description
The <b>STOR_POFX_DEVICE_V3</b> structure describes the power attributes of a storage device to the power management framework (PoFx). This structure is similar to <a href="storage.stor_pofx_device_v2">STOR_POFX_DEVICE</a> but allows the caller to specify an idle timeout value



## -syntax

````
typedef struct _STOR_POFX_DEVICE_V3 {
  ULONG               Version;
  USHORT              Size;
  ULONG               ComponentCount;
  ULONG               Flags;
  union {
    ULONG UnitMinIdleTimeoutInMS;
    ULONG AdapterIdleTimeoutInMS;
  };
  ULONG               MinimumPowerCyclePeriodInMS;
  STOR_POFX_COMPONENT Components[ANYSIZE_ARRAY];
} STOR_POFX_DEVICE_V3, *PSTOR_POFX_DEVICE_V3;
````


## -struct-fields

### -field Version

The version number of this structure. Set this member to <b>STOR_POFX_DEVICE_VERSION_V3</b>.


### -field Size

The size of this structure. Set this value to <b>STOR_POFX_DEVICE_V3_SIZE</b>.


### -field ComponentCount

The number of elements in the <b>Components</b> array. Set this member to 1. Currently, only a single component is supported for either a storage adapter or logical unit.


### -field Flags

The device power state capabilities flags. The miniport sets one or more of the PoFx device flags to enable or disable power state capabilities.


<b>Flags</b> is a bitwise OR combination of the following.



<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -field STOR_POFX_DEVICE_FLAG_NO_D0

</td>
<td width="60%">
Requests that a  power up IRP not be sent to the device object for the adapter or unit.

</td>
</tr>
<tr>

### -field STOR_POFX_DEVICE_FLAG_NO_D3

</td>
<td width="60%">
Requests that a  power down IRP not be sent to the device object for the adapter or unit.

</td>
</tr>
<tr>

### -field STOR_POFX_DEVICE_FLAG_ENABLE_D3_COLD

</td>
<td width="60%">
Enables Storport to set the D3 Cold state for the adapter if
  it supports it. This flag applies to adapters only.

</td>
</tr>
<tr>

### -field STOR_POFX_DEVICE_FLAG_NO_DUMP_ACTIVE

</td>
<td width="60%">
The miniport is not able to bring the storage device active in dump mode if the device has entered the idle state or the power off when idle state.
This flag indicates whether a device is available for dump when it is idle.

</td>
</tr>
<tr>

### -field STOR_POFX_DEVICE_FLAG_IDLE_TIMEOUT

</td>
<td width="60%">
If the <b>STOR_POFX_DEVICE_V3</b> represents a unit, this indicates the UnitMinIdleTimeoutInMS field should be honored. If the <b>STOR_POFX_DEVICE_V3</b> represents an adapter, this indicates the AdapterIdleTimeoutInMS field should be honored.

</td>
</tr>
<tr>

### -field STOR_POFX_DEVICE_FLAG_ADAPTIVE_D3_IDLE_TIMEOUT

</td>
<td width="60%">
Indicates that Storport should dynamically adjust the D3 idle timeout such that the device can aggressively enter D3 when necessary. This is valid only when <b>STOR_POFX_DEVICE_V3</b> is used.

</td>
</tr>
<tr>

### -field STOR_POFX_DEVICE_FLAG_NO_UNIT_REGISTRATION

</td>
<td width="60%">
Specifies that none of the units exposed by this adapter should be registered for runtime power management. This is valid only for STOR_POFX_DEVICE structures that represent an adapter.

</td>
</tr>
</table>
 


### -field UnitMinIdleTimeoutInMS

The minimum idle time in milliseconds for an unit. This value is only valid when STOR_POFX_DEVICE_FLAG_IDLE_TIMEOUT is set in <b>Flags</b>.


### -field AdapterIdleTimeoutInMS

The adapter idle timeout value in milliseconds. This value is only valid when STOR_POFX_DEVICE_FLAG_IDLE_TIMEOUT is set in <b>Flags</b>.


### -field MinimumPowerCyclePeriodInMS

Indicates that the device should not be power cycled (D0 -&gt; D3 -&gt; D0) more than once per the given period in Milliseconds. This member is only valid when the STOR_POFX_DEVICE_FLAG_ADAPTIVE_D3_IDLE_TIMEOUT flag has been set.


### -field Components

This member is the first element in an array of one or more <a href="kernel.po_fx_component">STOR_POFX_COMPONENT</a> elements. If the array contains more than one element, the additional elements immediately follow the <b>STOR_POFX_DEVICE</b> structure. The array contains one element for each component in the device.  Currently, storage devices have only  one component so additional component structures are unnecessary.


## -remarks
To register a storage adapter for Storport PoFx support, the miniport driver calls <a href="storage.storportenablepassiveinitialization">StorPortEnablePassiveInitialization</a> in its <a href="storage.hwstorinitialize">HwStorInitialize</a> routine and implements a <a href="storage.hwstorpassiveinitializeroutine">HwStorPassiveInitializeRoutine</a>. The miniport calls <a href="storage.storportinitializepofxpower">StorPortInitializePoFxPower</a> within it's <b>HwStorPassiveInitializeRoutine</b> to provide information about the adapter component.

To register a storage unit for Storport PoFx support, the miniport driver implements the <a href="storage.hwstorunitcontrol">HwStorUnitControl</a> callback routine and provides handling of the <b>ScsiUnitPoFxPowerInfo</b> unit control code. When the handling the <b>ScsiUnitPoFxPowerInfo</b> control code, the miniport calls <a href="storage.storportinitializepofxpower">StorPortInitializePoFxPower</a> if idle power management for the unit component is enabled.

The component for the storage device identified by its <b>Components</b> array index. Storage devices have only one component so the index of 0 is used.  Routines such as  <a href="storage.storportpofxactivatecomponent">StorPortPoFxActivateComponent</a> and <a href="storage.storportpofxidlecomponent">StorPortPoFxIdleComponent</a> use the array index of a component to identify the component.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported starting with Windows 10.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Storport.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.po_fx_component">STOR_POFX_COMPONENT</a>
</dt>
<dt>
<a href="storage.stor_pofx_device">STOR_POFX_DEVICE</a>
</dt>
<dt>
<a href="storage.storportinitializepofxpower">StorPortInitializePoFxPower</a>
</dt>
<dt>
<a href="storage.storportpofxactivatecomponent">StorPortPoFxActivateComponent</a>
</dt>
<dt>
<a href="storage.storportpofxidlecomponent">StorPortPoFxIdleComponent</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STOR_POFX_DEVICE_V3 structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

