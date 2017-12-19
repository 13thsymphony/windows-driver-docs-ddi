---
UID: NC.wdm.POB_PRE_OPERATION_CALLBACK
title: POB_PRE_OPERATION_CALLBACK
author: windows-driver-content
description: The ObjectPreCallback routine is called by the operating system when a process or thread handle operation occurs.
old-location: kernel\objectprecallback.htm
old-project: kernel
ms.assetid: 257c6c7d-be79-43bf-b2cd-f561e1741f90
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _WDI_TYPE_PMK_NAME, WDI_TYPE_PMK_NAME, PWDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows Server 2008.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ObjectPreCallback
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Called at PASSIVE_LEVEL (see Remarks section).
req.product: Windows 10 or later.
---

# POB_PRE_OPERATION_CALLBACK callback



## -description
The <i>ObjectPreCallback</i> routine is called by the operating system when a process or thread handle operation occurs.



## -prototype

````
POB_PRE_OPERATION_CALLBACK ObjectPreCallback;

OB_PREOP_CALLBACK_STATUS ObjectPreCallback(
  _In_ PVOID                         RegistrationContext,
  _In_ POB_PRE_OPERATION_INFORMATION OperationInformation
)
{ ... }
````


## -parameters

### -param RegistrationContext [in]

The context that the driver specifies as the <i>CallBackRegistration</i>-&gt;<b>RegistrationContext</b> parameter of the <a href="kernel.obregistercallbacks">ObRegisterCallbacks</a> routine. The meaning of this value is driver-defined.


### -param OperationInformation [in]

A pointer to an <a href="kernel.ob_pre_operation_information">OB_PRE_OPERATION_INFORMATION</a> structure that specifies the parameters of the handle operation. 


## -returns
<i>ObjectPreCallback</i> returns an OB_PREOP_CALLBACK_STATUS value. Drivers must return OB_PREOP_SUCCESS.


## -remarks
Use the <a href="kernel.obregistercallbacks">ObRegisterCallbacks</a> routine to register an <i>ObjectPreCallback</i> routine, and use the <a href="kernel.obunregistercallbacks">ObUnRegisterCallbacks</a> routine to unregister the routine.

This routine is called at PASSIVE_LEVEL in an arbitrary thread context with normal kernel APCs disabled. Special kernel APCs are not disabled. For more information about APCs, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff564853">Types of APCs</a>.


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
Version

</th>
<td width="70%">
Available starting with Windows Server 2008.

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
IRQL

</th>
<td width="70%">
Called at PASSIVE_LEVEL (see Remarks section).

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.ob_pre_operation_information">OB_PRE_OPERATION_INFORMATION</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-pob_post_operation_callback.md">ObjectPostCallback</a>
</dt>
<dt>
<a href="kernel.obregistercallbacks">ObRegisterCallbacks</a>
</dt>
<dt>
<a href="kernel.obunregistercallbacks">ObUnRegisterCallbacks</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20POB_PRE_OPERATION_CALLBACK callback function%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

