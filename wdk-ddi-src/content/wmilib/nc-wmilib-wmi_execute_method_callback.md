---
UID: NC.wmilib.WMI_EXECUTE_METHOD_CALLBACK
title: WMI_EXECUTE_METHOD_CALLBACK
author: windows-driver-content
description: The DpWmiExecuteMethod routine executes a method associated with a data block. This routine is optional.
old-location: kernel\dpwmiexecutemethod.htm
old-project: kernel
ms.assetid: 3e671484-8f8d-4ba0-a763-37c3178487ca
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: _WMI_CHANGER_PROBLEM_DEVICE_ERROR, WMI_CHANGER_PROBLEM_DEVICE_ERROR, *PWMI_CHANGER_PROBLEM_DEVICE_ERROR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wmilib.h
req.include-header: Wmilib.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DpWmiExecuteMethod
req.alt-loc: Wmilib.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Called at PASSIVE_LEVEL.
req.product: Windows 10 or later.
---

# WMI_EXECUTE_METHOD_CALLBACK callback



## -description
The <i>DpWmiExecuteMethod</i> routine executes a method associated with a data block. This routine is optional.



## -prototype

````
WMI_EXECUTE_METHOD_CALLBACK DpWmiExecuteMethod;

NTSTATUS DpWmiExecuteMethod(
  _In_    PDEVICE_OBJECT DeviceObject,
  _In_    PIRP           Irp,
  _In_    ULONG          GuidIndex,
  _In_    ULONG          InstanceIndex,
  _In_    ULONG          MethodId,
  _In_    ULONG          InBufferSize,
  _In_    ULONG          OutBufferSize,
  _Inout_ PUCHAR         Buffer
)
{ ... }
````


## -parameters

### -param DeviceObject [in]

Pointer to the driver's WDM <a href="kernel.device_object">DEVICE_OBJECT</a> structure.


### -param Irp [in]

Pointer to the IRP.


### -param GuidIndex [in]

Specifies the data block by supplying a zero-based index into the list of GUIDs that the driver provided in the <a href="kernel.wmilib_context">WMILIB_CONTEXT</a> structure it passed to <a href="kernel.wmisystemcontrol">WmiSystemControl</a>. 


### -param InstanceIndex [in]

If the block specified by <i>GuidIndex</i> has multiple instances, <i>InstanceIndex</i> specifies a zero-based index value that identifies the instance.


### -param MethodId [in]

Specifies the ID of the method to execute. The driver defines the method ID as an item in a data block.


### -param InBufferSize [in]

Indicates the size in bytes of the input data. If there is no input data, <i>InBufferSize</i> is zero. 


### -param OutBufferSize [in]

Indicates the number of bytes available in the buffer for output data.


### -param Buffer [in, out]

Pointer to a buffer that holds input data, if any, and receives output data, if any, for the method. If the buffer is too small to receive all of the output data, the driver returns STATUS_BUFFER_TOO_SMALL and calls <a href="kernel.wmicompleterequest">WmiCompleteRequest</a> with the size required.


## -returns
<i>DpWmiExecuteMethod</i> returns STATUS_SUCCESS or an appropriate error code such as the following:
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
<dt><b>STATUS_WMI_INSTANCE_NOT_FOUND</b></dt>
<dt><b>STATUS_WMI_ITEMID_NOT_FOUND</b></dt>
</dl>

## -remarks
WMI calls a driver's <i>DpWmiExecuteMethod</i> routine after the driver calls <a href="kernel.wmisystemcontrol">WmiSystemControl</a> in response to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550868">IRP_MN_EXECUTE_METHOD</a> request.

If a driver implements a <i>DpWmiExecuteMethod</i> routine, the driver must place the routine's address in the <b>ExecuteWmiMethod</b> member of the <a href="kernel.wmilib_context">WMILIB_CONTEXT</a> structure that it passes to <a href="kernel.wmisystemcontrol">WmiSystemControl</a>. If a driver does not implement a <i>DpWmiExecuteMethod</i> routine, it must set <b>ExecuteWmiMethod</b> to <b>NULL</b>. In the latter case, WMI returns STATUS_INVALID_DEVICE_REQUEST to the caller in response to any <b>IRP_MN_EXECUTE_METHOD</b> request.

The driver is responsible for validating all input arguments. Specifically, the driver must do the following:

Verify that the <i>GuidIndex</i> value is between zero and GuidCount-1, based on the <b>GuidCount</b> member of the <a href="kernel.wmilib_context">WMILIB_CONTEXT</a> structure.

Verify that the driver has not flagged the specified data block for removal. If the driver recently specified the WMIREG_FLAG_REMOVE_GUID flag in a <a href="kernel.wmiguidreginfo">WMIGUIDREGINFO</a> structure that is contained in a <b>WMILIB_CONTEXT</b> structure, it is possible for an additional request to arrive before the removal occurs.

Verify that the <i>InstanceIndex</i> value is within the range of instance indexes that are supported by the driver for the data block. 

Verify that the method identifier supplied by <i>MethodId</i> is a valid identifier for the specified data block, and that the caller is allowed to execute the method.

Verify that <i>Buffer</i> and <i>InBufferSize</i> describe a buffer that is large enough to contain the specified method's input parameters, including padding if necessary, and verify that the input parameters are valid. 

Verify that <i>Buffer</i> and <i>OutBufferSize</i> describe a buffer that is large enough to receive the specified method's output data, including padding if necessary.

Do not assume the thread context is that of the initiating user-mode application—a higher-level driver might have changed it.

If the specified method performs an operation that causes data loss, such as fetching and resetting the contents of a set of counters, the driver should validate the output buffer size before performing the operation. That way, the driver can return STATUS_BUFFER_TOO_SMALL and allow the caller to resubmit the request with a larger buffer, without prematurely resetting the counters.

After executing the method and writing any output data to the buffer, the driver calls <a href="kernel.wmicompleterequest">WmiCompleteRequest</a> to complete the request.

This routine can be pageable.

For more information about implementing this routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540741">Calling WmiSystemControl to Handle WMI IRPs</a>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
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
IRQL

</th>
<td width="70%">
Called at PASSIVE_LEVEL.

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550868">IRP_MN_EXECUTE_METHOD</a>
</dt>
<dt>
<a href="kernel.wmilib_context">WMILIB_CONTEXT</a>
</dt>
<dt>
<a href="kernel.wmicompleterequest">WmiCompleteRequest</a>
</dt>
<dt>
<a href="kernel.wmisystemcontrol">WmiSystemControl</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20WMI_EXECUTE_METHOD_CALLBACK callback function%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

