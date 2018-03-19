---
UID: NF:fltkernel.FltRegisterFilter
title: FltRegisterFilter function
author: windows-driver-content
description: FltRegisterFilter registers a minifilter driver.
old-location: ifsk\fltregisterfilter.htm
old-project: ifsk
ms.assetid: 46e96f85-d368-40cd-9530-81959d20b750
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltApiRef_p_to_z_41e3002c-d720-4e0f-81cb-36cbc215cdba.xml, FltRegisterFilter, FltRegisterFilter function [Installable File System Drivers], fltkernel/FltRegisterFilter, ifsk.fltregisterfilter
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltRegisterFilter
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# FltRegisterFilter function
<b>FltRegisterFilter</b> registers a minifilter driver.

## Syntax

````
NTSTATUS FltRegisterFilter(
  _In_        PDRIVER_OBJECT   Driver,
  _In_  const FLT_REGISTRATION *Registration,
  _Out_       PFLT_FILTER      *RetFilter
);
````

## Parameters

`Driver`

A pointer to the driver object for the minifilter driver. This should be the same driver object pointer that was passed as input to the minifilter driver's <b>DriverEntry</b> routine.

`Registration`

A pointer to a caller-allocated minifilter driver registration structure (<a href="..\fltkernel\ns-fltkernel-_flt_registration.md">FLT_REGISTRATION</a>).

`RetFilter`

A pointer to a caller-allocated variable that receives an opaque filter pointer for the caller.


## Return Value

<b>FltRegisterFilter</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<b>FltRegisterFilter</b> encountered a pool allocation failure. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
One of the following: 

<ul>
<li>
The <b>Version</b> member of the <i>Registration</i> structure was not set to FLT_REGISTRATION_VERSION. 

</li>
<li>
One of the non-NULL name-provider routines in the <i>Registration</i> structure was set to an invalid value. The <b>GenerateFileNameCallback</b>, <b>NormalizeNameComponentCallback</b>, and <b>NormalizeNameComponentExCallback</b> members of <a href="..\fltkernel\ns-fltkernel-_flt_registration.md">FLT_REGISTRATION</a> point to the name-provider routines. 

</li>
</ul>
STATUS_INVALID_PARAMETER is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_NOT_INITIALIZED</b></dt>
</dl>
</td>
<td width="60%">
The Filter Manager was not initialized when the filter tried to register. Make sure that the Filter Manager is loaded as a driver. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NAME_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The filter service key is not found in the registry.

-or-

The filter instance is not registered.

</td>
</tr>
</table>

## Remarks

Every minifilter driver must call <b>FltRegisterFilter</b> from its <b>DriverEntry</b> routine to add itself to the global list of registered minifilter drivers and to provide the Filter Manager with a list of callback functions and other information about the minifilter driver. 

<b>FltRegisterFilter</b> returns an opaque filter pointer for the minifilter driver in *<i>RetFilter</i>. This pointer value uniquely identifies the minifilter driver and remains constant as long as the minifilter driver is loaded. The minifilter driver should save this pointer, because it is a required parameter for <a href="..\fltkernel\nf-fltkernel-fltstartfiltering.md">FltStartFiltering</a> and <a href="..\fltkernel\nf-fltkernel-fltunregisterfilter.md">FltUnregisterFilter</a>. 

After calling <b>FltRegisterFilter</b>, a minifilter driver typically calls <a href="..\fltkernel\nf-fltkernel-fltstartfiltering.md">FltStartFiltering</a> to begin filtering I/O operations. 

A minifilter driver can only call <b>FltRegisterFilter</b> to register itself, not another minifilter driver. 

To unregister itself, a minifilter driver calls <a href="..\fltkernel\nf-fltkernel-fltunregisterfilter.md">FltUnregisterFilter</a>..

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** | FltMgr.lib |
| **DLL** | Fltmgr.sys |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\fltkernel\ns-fltkernel-_flt_registration.md">FLT_REGISTRATION</a>



<a href="..\fltkernel\nf-fltkernel-fltstartfiltering.md">FltStartFiltering</a>



<a href="..\fltkernel\nf-fltkernel-fltunregisterfilter.md">FltUnregisterFilter</a>