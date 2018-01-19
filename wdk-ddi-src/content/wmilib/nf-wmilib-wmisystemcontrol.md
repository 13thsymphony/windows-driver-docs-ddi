---
UID : NF:wmilib.WmiSystemControl
title : WmiSystemControl function
author : windows-driver-content
description : The WmiSystemControl routine is a dispatch routine for drivers that use WMI library support routines to handle WMI IRPs.
old-location : kernel\wmisystemcontrol.htm
old-project : kernel
ms.assetid : 6226e75e-b744-46cd-b14b-e93ece1c2f61
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : WmiSystemControl
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wmilib.h
req.include-header : Wmilib.h
req.target-type : Universal
req.target-min-winverclnt : Available in Windows 2000 and later versions of Windows.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : WmiSystemControl
req.alt-loc : Wmilib.lib,Wmilib.dll
req.ddi-compliance : WmiComplete
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Wmilib.lib
req.dll : 
req.irql : PASSIVE_LEVEL (see Remarks section)
req.typenames : WMI_CHANGER_PROBLEM_DEVICE_ERROR, *PWMI_CHANGER_PROBLEM_DEVICE_ERROR
req.product : Windows 10 or later.
---


# WmiSystemControl function
The <b>WmiSystemControl</b> routine is a dispatch routine for drivers that use <a href="https://msdn.microsoft.com/e0920c72-97bd-45c2-ad3f-03117dddc81b">WMI library support routines</a> to handle WMI IRPs.

## Syntax

````
NTSTATUS WmiSystemControl(
  _In_    PWMILIB_CONTEXT         WmiLibInfo,
  _In_    PDEVICE_OBJECT          DeviceObject,
  _Inout_ PIRP                    Irp,
  _Out_   PSYSCTL_IRP_DISPOSITION IrpDisposition
);
````

## Parameters

`WmiLibInfo`

A pointer to a <a href="..\wmilib\ns-wmilib-_wmilib_context.md">WMILIB_CONTEXT</a> structure that contains registration information for a driver's data blocks and event blocks and defines entry points for the driver's WMI library callback routines.

`DeviceObject`

A pointer to the driver's <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>.

`Irp`

A pointer to the <a href="..\wdm\ns-wdm-_irp.md">IRP</a>.

`IrpDisposition`

A pointer to an enumeration value of type <b>SYSCTL_IRP_DISPOSITION</b> that indicates how the IRP was handled. <b>WmiSystemControl</b> always sets this value, even when it returns a non-success NTSTATUS code.

<b>SYSCTL_IRP_DISPOSITION</b> is an enumeration in Wmilib.h and contains the following values:


## Return Value

<b>WmiSystemControl</b> returns STATUS_SUCCESS or one of the following error codes:
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
<dt><b>STATUS_WMI_GUID_NOT_FOUND</b></dt>
<dt><b>STATUS_WMI_INSTANCE_NOT_FOUND</b></dt>
</dl>

## Remarks

When a driver receives an <b>IRP_MJ_SYSTEM_CONTROL</b> request with a WMI IRP minor code, it calls <b>WmiSystemControl</b> with a pointer to the driver's <b>WMILIB_CONTEXT</b> structure, a pointer to its device object, and a pointer to the IRP. The <b>WMILIB_CONTEXT</b> structure contains registration information for the driver's data blocks and event blocks and defines entry points for its WMI library callback routines.

<b>WmiSystemControl</b> confirms that the IRP is a WMI request and determines whether the block specified by the request is valid for the driver. If so, it processes the IRP by calling the appropriate <i>DpWmi</i>Xxx entry point in the driver's <b>WMILIB_CONTEXT</b> structure. WMI is running at IRQL PASSIVE_LEVEL when it calls the driver's <i>DpWmi</i>Xxx routine.

A driver must be running at IRQL PASSIVE_LEVEL when it forwards an <b>IRP_MJ_SYSTEM_CONTROL</b> request to the next-lower driver.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wmilib.h (include Wmilib.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL (see Remarks section) |
| **DDI compliance rules** | WmiComplete |

## See Also

<dl>
<dt>
<a href="..\wmilib\nc-wmilib-wmi_execute_method_callback.md">DpWmiExecuteMethod</a>
</dt>
<dt>
<a href="..\wmilib\nc-wmilib-wmi_function_control_callback.md">DpWmiFunctionControl</a>
</dt>
<dt>
<a href="..\wmilib\nc-wmilib-wmi_query_datablock_callback.md">DpWmiQueryDataBlock</a>
</dt>
<dt>
<a href="..\wmilib\nc-wmilib-wmi_query_reginfo_callback.md">DpWmiQueryReginfo</a>
</dt>
<dt>
<a href="..\wmilib\nc-wmilib-wmi_set_datablock_callback.md">DpWmiSetDataBlock</a>
</dt>
<dt>
<a href="..\wmilib\nc-wmilib-wmi_set_dataitem_callback.md">DpWmiSetDataItem</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iocompleterequest.md">IoCompleteRequest</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550813">IRP_MJ_SYSTEM_CONTROL</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551734">IRP_MN_REGINFO_EX</a>
</dt>
<dt>
<a href="..\wmilib\ns-wmilib-_wmilib_context.md">WMILIB_CONTEXT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20WmiSystemControl routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>