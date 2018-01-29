---
UID : NF:storport.StorPortIsDeviceOperationAllowed
title : StorPortIsDeviceOperationAllowed function
author : windows-driver-content
description : A miniport driver can call the StorPortIsDeviceOperationAllowedminiport routine to determine if operations for a certain device management class are allowed.
old-location : storage\storportisdeviceoperationallowed.htm
old-project : storage
ms.assetid : 2FA71DC1-8068-42E3-A5C0-903858E496FA
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : storage.storportisdeviceoperationallowed, StorPortIsDeviceOperationAllowed routine [Storage Devices], storport/StorPortIsDeviceOperationAllowed, STORPORT_DEVICEOPERATION_SECURE_REPROVISION_GUID, StorPortIsDeviceOperationAllowed
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : storport.h
req.include-header : 
req.target-type : Universal
req.target-min-winverclnt : Available in starting with Windows 8.1.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.exe
req.dll : 
req.irql : IRQL == PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : STOR_SPINLOCK
req.product : Windows 10 or later.
---


# StorPortIsDeviceOperationAllowed function
A miniport driver can call the <b>StorPortIsDeviceOperationAllowedminiport</b> routine to determine if operations for a certain device management      class are allowed. A status value is set in the return parameter to indicate whether such operations are allowed or not allowed for the device in its current operating environment.

## Syntax

````
ULONG StorPortIsDeviceOperationAllowed(
  _In_  PVOID         HwDeviceExtension,
  _In_  PSTOR_ADDRESS Address,
  _In_  LPCGUID       DeviceOperation,
  _Out_ ULONG         *AllowedFlag
);
````

## Parameters

`HwDeviceExtension`

A pointer to the hardware device extension for the host bus adapter (HBA).

`Address`

The address of a storage device unit.

`DeviceOperation`

A pointer to a GUID specifying a device management operation class. The following GUID is valid.
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="STORPORT_DEVICEOPERATION_SECURE_REPROVISION_GUID"></a><a id="storport_deviceoperation_secure_reprovision_guid"></a><dl>
<dt><b>STORPORT_DEVICEOPERATION_SECURE_REPROVISION_GUID</b></dt>
</dl>
</td>
<td width="60%">
The device is enabled to receive secured provisioning commands.

</td>
</tr>
</table>

`AllowedFlag`

TRUE when the operation specified in <i>DeviceOperation</i> is allowed. Otherwise, FALSE.


## Return Value

The <b>StorPortIsDeviceOperationAllowed</b> routine returns one of these status codes:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
A valid value for <i>AllowedFlag</i> was returned.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
<i>Address</i> points to an invalid unit address structure.

-or-

The storage device specified by <i>Address</i> is not found.

-or-

The pointer value in <i>AllowedFlag</i> is NULL.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_IRQL</b></dt>
</dl>
</td>
<td width="60%">
The current IRQL &gt; PASSIVE_LEVEL.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">
The management class specified in <i>DeviceOperation</i> is not available or invalid.

</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | storport.h |
| **Library** |  |
| **IRQL** | IRQL == PASSIVE_LEVEL |
| **DDI compliance rules** |  |