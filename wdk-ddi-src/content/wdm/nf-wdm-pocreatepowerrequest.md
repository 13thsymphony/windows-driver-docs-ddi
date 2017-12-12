---
UID: NF.wdm.PoCreatePowerRequest
title: PoCreatePowerRequest function
author: windows-driver-content
description: The PoCreatePowerRequest routine creates a power request object.
old-location: kernel\pocreatepowerrequest.htm
old-project: kernel
ms.assetid: 67986bf8-b070-44e9-95a2-eea35100b0e7
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: PoCreatePowerRequest
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 7.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PoCreatePowerRequest
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
req.product: Windows 10 or later.
---

# PoCreatePowerRequest function



## -description
The <b>PoCreatePowerRequest</b> routine creates a power request object.



## -syntax

````
NTSTATUS PoCreatePowerRequest(
  _Out_ PVOID                   *PowerRequest,
  _In_  PDEVICE_OBJECT          DeviceObject,
  _In_  PCOUNTED_REASON_CONTEXT Context
);
````


## -parameters

### -param PowerRequest [out]

A pointer to a location into which the routine writes a pointer to the newly created power request object. If the call fails, the routine writes <b>NULL</b> to this location.


### -param DeviceObject [in]

A pointer to the device object of the caller (a <a href="kernel.device_object">DEVICE_OBJECT</a> structure).


### -param Context [in]

A pointer to a <a href="kernel.counted_reason_context">COUNTED_REASON_CONTEXT</a> structure that describes why the caller is creating the power request object. This parameter is optional and can be set to <b>NULL</b>.


## -returns
<b>PoCreatePowerRequest</b> returns STATUS_SUCCESS if the call is successful. If the call fails, possible error return codes include the following:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The <i>DeviceObject</i> parameter is <b>NULL</b>.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>There is not enough memory available to create a power request object.

 


## -remarks
This routine creates a power request object. To enable power requests, the caller should create one power request object and use that object for all calls to the <a href="kernel.posetpowerrequest">PoSetPowerRequest</a> and <a href="kernel.poclearpowerrequest">PoClearPowerRequest</a> routines.

A driver can use power requests to override certain aspects of the computer's default power behavior. For example, a driver for a TV receiver device can use power requests to prevent the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559829">power manager</a> from automatically blanking the display during extended periods of time in which no user interaction occurs.

When the power request object is no longer needed, the caller must delete the object by calling the <a href="kernel.podeletepowerrequest">PoDeletePowerRequest</a> routine. The driver must delete the power request object before it deletes the device object that was used to create the power request object.


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
Available starting with Windows 7.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= APC_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.poclearpowerrequest">PoClearPowerRequest</a>
</dt>
<dt>
<a href="kernel.podeletepowerrequest">PoDeletePowerRequest</a>
</dt>
<dt>
<a href="kernel.posetpowerrequest">PoSetPowerRequest</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PoCreatePowerRequest routine%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

