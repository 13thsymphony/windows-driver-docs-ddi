---
UID: NC.wdm.POB_POST_OPERATION_CALLBACK
title: POB_POST_OPERATION_CALLBACK
author: windows-driver-content
description: The ObjectPostCallback routine is called by the operating system after a process or thread handle operation occurs.
old-location: kernel\objectpostcallback.htm
old-project: kernel
ms.assetid: cfa73359-58bb-4260-ac16-08f57ead67bb
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
req.alt-api: ObjectPostCallback
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

# POB_POST_OPERATION_CALLBACK callback



## -description
The <i>ObjectPostCallback</i> routine is called by the operating system after a process or thread handle operation occurs.



## -prototype

````
POB_POST_OPERATION_CALLBACK ObjectPostCallback;

VOID ObjectPostCallback(
  _In_ PVOID                          RegistrationContext,
  _In_ POB_POST_OPERATION_INFORMATION OperationInformation
)
{ ... }
````


## -parameters

### -param RegistrationContext [in]

The context that the driver specifies as the <i>CallBackRegistration</i>-&gt;<b>RegistrationContext</b> parameter of the <a href="kernel.obregistercallbacks">ObRegisterCallbacks</a> routine. The meaning of this value is driver-defined.


### -param OperationInformation [in]

A pointer to an <a href="kernel.ob_post_operation_information">OB_POST_OPERATION_INFORMATION</a> structure that specifies the parameters of the handle operation.


## -returns
None


## -remarks
Use the <a href="kernel.obregistercallbacks">ObRegisterCallbacks</a> routine to register an <i>ObjectPostCallback</i> routine, and use the <a href="kernel.obunregistercallbacks">ObUnRegisterCallbacks</a> routine to unregister the routine.

An <i>ObjectPostCallback</i> routine is called after an operation on a process handle or thread handle completes, whereas an <a href="..\wdm\nc-wdm-pob_pre_operation_callback.md">ObjectPreCallback</a> routine is called before the operation occurs. The <i>OperationInformation</i> parameter of the <i>ObjectPreCallback</i> routine is a pointer to an <a href="kernel.ob_pre_operation_information">OB_PRE_OPERATION_INFORMATION</a> structure, which contains information that you can modify. In contrast, the <i>OperationInformation</i> parameter of the <i>ObjectPostCallback</i> routine is a pointer to an <a href="kernel.ob_post_operation_information">OB_POST_OPERATION_INFORMATION</a> structure. The contents of this structure are informational and you cannot modify them.

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
<a href="kernel.ob_post_operation_information">OB_POST_OPERATION_INFORMATION</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-pob_pre_operation_callback.md">ObjectPreCallback</a>
</dt>
<dt>
<a href="kernel.obregistercallbacks">ObRegisterCallbacks</a>
</dt>
<dt>
<a href="kernel.obunregistercallbacks">ObUnRegisterCallbacks</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20POB_POST_OPERATION_CALLBACK callback function%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

