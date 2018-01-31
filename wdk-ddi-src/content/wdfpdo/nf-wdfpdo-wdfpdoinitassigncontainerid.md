---
UID : NF:wdfpdo.WdfPdoInitAssignContainerID
title : WdfPdoInitAssignContainerID function
author : windows-driver-content
description : The WdfPdoInitAssignContainerID method updates the container ID for a child device.
old-location : wdf\wdfpdoinitassigncontainerid.htm
old-project : wdf
ms.assetid : 603bff9f-fd18-40bd-9b2b-8f013f99ec61
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : wdfpdo/WdfPdoInitAssignContainerID, PFN_WDFPDOINITASSIGNCONTAINERID, WdfPdoInitAssignContainerID method, kmdf.wdfpdoinitassigncontainerid, WdfPdoInitAssignContainerID, DFDeviceObjectFdoPdoRef_b744c1d7-e24f-4936-8921-cf5b7dd4ad68.xml, wdf.wdfpdoinitassigncontainerid
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdfpdo.h
req.include-header : Wdf.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.9
req.umdf-ver : 
req.ddi-compliance : DriverCreate
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Wdf01000.sys (see Framework Library Versioning.)
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WDF_OBJECT_CONTEXT_TYPE_INFO, *PWDF_OBJECT_CONTEXT_TYPE_INFO
req.product : Windows 10 or later.
---


# WdfPdoInitAssignContainerID function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfPdoInitAssignContainerID</b> method updates the container ID for a child device.

## Syntax

````
NTSTATUS WdfPdoInitAssignContainerID(
  _In_ PWDFDEVICE_INIT  DeviceInit,
  _In_ PCUNICODE_STRING ContainerID
);
````

## Parameters

`DeviceInit`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure.

`ContainerID`

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains a container ID string. The driver can allocate the string's buffer from paged pool.


## Return Value

If the operation succeeds, the method returns STATUS_SUCCESS. Additional return values include:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The driver is initializing an FDO instead of a PDO.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The driver could not allocate space to store the container ID string.

</td>
</tr>
</table> 

The method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

## Remarks

For more information about container IDs, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/install/device-identification-strings">Device Identification Strings</a>.

The driver must call <b>WdfPdoInitAssignContainerID</b> before calling <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>. For more information about calling <b>WdfDeviceCreate</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** | 1.9 |
| **Minimum UMDF version** |  |
| **Header** | wdfpdo.h (include Wdf.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | DriverCreate |

## See Also

<a href="..\wdfpdo\nf-wdfpdo-wdfpdoinitaddhardwareid.md">WdfPdoInitAddHardwareID</a>

<a href="..\wdfpdo\nf-wdfpdo-wdfpdoinitaddcompatibleid.md">WdfPdoInitAddCompatibleID</a>

<a href="..\wdfpdo\nf-wdfpdo-wdfpdoinitassigndeviceid.md">WdfPdoInitAssignDeviceID</a>

<a href="..\wdm\nf-wdm-rtlinitunicodestring.md">RtlInitUnicodeString</a>

<a href="..\wdfpdo\nf-wdfpdo-wdfpdoinitassigninstanceid.md">WdfPdoInitAssignInstanceID</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfPdoInitAssignContainerID method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>