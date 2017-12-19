---
UID: NF.wmilib.WmiSystemControl
title: WmiSystemControl function
author: windows-driver-content
description: The WmiSystemControl routine is a dispatch routine for drivers that use WMI library support routines to handle WMI IRPs.
old-location: kernel\wmisystemcontrol.htm
old-project: kernel
ms.assetid: 6226e75e-b744-46cd-b14b-e93ece1c2f61
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: WmiSystemControl
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wmilib.h
req.include-header: Wmilib.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WmiSystemControl
req.alt-loc: Wmilib.lib,Wmilib.dll
req.ddi-compliance: WmiComplete
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wmilib.lib
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
req.product: Windows 10 or later.
---

# WmiSystemControl function



## -description
The <b>WmiSystemControl</b> routine is a dispatch routine for drivers that use <a href="kernel.wmi_library_callback_routines">WMI library support routines</a> to handle WMI IRPs.



## -syntax

````
NTSTATUS WmiSystemControl(
  _In_    PWMILIB_CONTEXT         WmiLibInfo,
  _In_    PDEVICE_OBJECT          DeviceObject,
  _Inout_ PIRP                    Irp,
  _Out_   PSYSCTL_IRP_DISPOSITION IrpDisposition
);
````


## -parameters

### -param WmiLibInfo [in]

A pointer to a <a href="kernel.wmilib_context">WMILIB_CONTEXT</a> structure that contains registration information for a driver's data blocks and event blocks and defines entry points for the driver's WMI library callback routines. 


### -param DeviceObject [in]

A pointer to the driver's <a href="kernel.device_object">DEVICE_OBJECT</a>. 


### -param Irp [in, out]

A pointer to the <a href="kernel.irp">IRP</a>.


### -param IrpDisposition [out]


      A pointer to an enumeration value of type <b>SYSCTL_IRP_DISPOSITION</b> that indicates how the IRP was handled. <b>WmiSystemControl</b> always sets this value, even when it returns a non-success NTSTATUS code.

<b>SYSCTL_IRP_DISPOSITION</b> is an enumeration in Wmilib.h and contains the following values:




### -param IrpProcessed

The IRP was processed and possibly completed. If the driver's <i>DpWmi</i>Xxx routine called by <b>WmiSystemControl</b> did not complete the IRP, the driver must call <a href="kernel.wmicompleterequest">WmiCompleteRequest</a> to complete the IRP after <b>WmiSystemControl</b> returns.


### -param IrpNotCompleted

The IRP was processed but not completed, either because WMI detected an error and set up the IRP with an appropriate error code, or processed an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551731">IRP_MN_REGINFO</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff551734">IRP_MN_REGINFO_EX</a> request. The driver must complete the IRP by calling <a href="kernel.iocompleterequest">IoCompleteRequest</a>.


### -param IrpNotWmi

The IRP is not a WMI request (that is, WMI does not recognize the IRP's minor code). If the driver handles <a href="https://msdn.microsoft.com/library/windows/hardware/ff550813">IRP_MJ_SYSTEM_CONTROL</a> requests with this <b>IRP_MN_<i>XXX</i></b>, it should handle the IRP; otherwise, the driver should forward the IRP to the next lower driver. If the driver is the lowest-level driver, then it must complete the IRP.


### -param IrpForward

The IRP is targeted to another device object (that is, the device object pointer at <b>Parameters.WMI.ProviderId</b> in the IRP does not match the pointer passed by the driver in its call to <a href="kernel.iowmiregistrationcontrol">IoWMIRegistrationControl</a>). The driver must forward the IRP to the next lower driver. If the driver is the lowest-level driver, then it must complete the IRP.

</dd>
</dl>

## -returns
<b>WmiSystemControl</b> returns STATUS_SUCCESS or one of the following error codes:
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
<dt><b>STATUS_WMI_GUID_NOT_FOUND</b></dt>
<dt><b>STATUS_WMI_INSTANCE_NOT_FOUND</b></dt>
</dl>

## -remarks
When a driver receives an <b>IRP_MJ_SYSTEM_CONTROL</b> request with a WMI IRP minor code, it calls <b>WmiSystemControl</b> with a pointer to the driver's <b>WMILIB_CONTEXT</b> structure, a pointer to its device object, and a pointer to the IRP. The <b>WMILIB_CONTEXT</b> structure contains registration information for the driver's data blocks and event blocks and defines entry points for its WMI library callback routines.

<b>WmiSystemControl</b> confirms that the IRP is a WMI request and determines whether the block specified by the request is valid for the driver. If so, it processes the IRP by calling the appropriate <i>DpWmi</i>Xxx entry point in the driver's <b>WMILIB_CONTEXT</b> structure. WMI is running at IRQL PASSIVE_LEVEL when it calls the driver's <i>DpWmi</i>Xxx routine.

A driver must be running at IRQL PASSIVE_LEVEL when it forwards an <b>IRP_MJ_SYSTEM_CONTROL</b> request to the next-lower driver.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows 2000 and later versions of Windows.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wmilib.h (include Wmilib.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Wmilib.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL (see Remarks section)

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.wdm_wmicomplete">WmiComplete</a>
</td>
</tr>
</table>

## -see-also
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
<a href="kernel.iocompleterequest">IoCompleteRequest</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550813">IRP_MJ_SYSTEM_CONTROL</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551734">IRP_MN_REGINFO_EX</a>
</dt>
<dt>
<a href="kernel.wmilib_context">WMILIB_CONTEXT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20WmiSystemControl routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

