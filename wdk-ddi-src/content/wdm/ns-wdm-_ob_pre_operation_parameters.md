---
UID: NS.WDM._OB_PRE_OPERATION_PARAMETERS
title: _OB_PRE_OPERATION_PARAMETERS
author: windows-driver-content
description: The OB_PRE_OPERATION_PARAMETERS union describes the operation-specific parameters for an ObjectPreCallback routine.
old-location: kernel\ob_pre_operation_parameters.htm
old-project: kernel
ms.assetid: 211bd3b1-34ca-414d-9167-0587c90cb56a
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: _OB_PRE_OPERATION_PARAMETERS, OB_PRE_OPERATION_PARAMETERS, *POB_PRE_OPERATION_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Server 2008 and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: OB_PRE_OPERATION_PARAMETERS
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
req.irql: PASSIVE_LEVEL (see Remarks section)
req.product: Windows 10 or later.
---

# _OB_PRE_OPERATION_PARAMETERS structure



## -description
The <b>OB_PRE_OPERATION_PARAMETERS</b> union describes the operation-specific parameters for an <a href="kernel.objectprecallback">ObjectPreCallback</a> routine.



## -syntax

````
typedef union _OB_PRE_OPERATION_PARAMETERS {
  OB_PRE_CREATE_HANDLE_INFORMATION    CreateHandleInformation;
  OB_PRE_DUPLICATE_HANDLE_INFORMATION DuplicateHandleInformation;
} OB_PRE_OPERATION_PARAMETERS, *POB_PRE_OPERATION_PARAMETERS;
````


## -struct-fields

### -field CreateHandleInformation

An <a href="kernel.ob_pre_create_handle_information">OB_PRE_CREATE_HANDLE_INFORMATION</a> structure that contains information that is specific to a handle that is being opened. 


### -field DuplicateHandleInformation

An <a href="kernel.ob_pre_duplicate_handle_information">OB_PRE_DUPLICATE_HANDLE_INFORMATION </a> structure that contains information that is specific to a handle that is being duplicated. 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Server 2008 and later versions of the Windows operating system.

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
</table>

## -see-also
<dl>
<dt>
<a href="kernel.ob_pre_create_handle_information">OB_PRE_CREATE_HANDLE_INFORMATION</a>
</dt>
<dt>
<a href="kernel.ob_pre_duplicate_handle_information">OB_PRE_DUPLICATE_HANDLE_INFORMATION</a>
</dt>
<dt>
<a href="kernel.objectprecallback">ObjectPreCallback</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20OB_PRE_OPERATION_PARAMETERS union%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

