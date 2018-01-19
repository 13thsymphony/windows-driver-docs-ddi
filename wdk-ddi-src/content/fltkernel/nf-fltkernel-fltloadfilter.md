---
UID : NF:fltkernel.FltLoadFilter
title : FltLoadFilter function
author : windows-driver-content
description : The FltLoadFilter routine dynamically loads a minifilter driver into the currently running system.
old-location : ifsk\fltloadfilter.htm
old-project : ifsk
ms.assetid : aecf5f5f-c0b7-487a-9db0-d01212aef094
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : FltLoadFilter
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : fltkernel.h
req.include-header : Fltkernel.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : FltLoadFilter
req.alt-loc : fltmgr.sys
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : FltMgr.lib
req.dll : Fltmgr.sys
req.irql : PASSIVE_LEVEL
req.typenames : EXpsFontRestriction
---


# FltLoadFilter function
The <b>FltLoadFilter</b> routine dynamically loads a minifilter driver into the currently running system.

## Syntax

````
NTSTATUS FltLoadFilter(
  _In_ PCUNICODE_STRING FilterName
);
````

## Parameters

`FilterName`

Pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure containing the service name for the minifilter driver.


## Return Value

<b>FltLoadFilter</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as one of the following: 
<dl>
<dt><b>STATUS_DRIVER_FAILED_PRIOR_UNLOAD</b></dt>
</dl>The minifilter driver could not be loaded because a previous version of the driver is still in memory. This is an error code. 
<dl>
<dt><b>STATUS_FAILED_DRIVER_ENTRY</b></dt>
</dl>The minifilter driver's <b>DriverEntry</b> routine returned an NTSTATUS value that was not a success code. This is an error code. 
<dl>
<dt><b>STATUS_IMAGE_ALREADY_LOADED</b></dt>
</dl>The minifilter driver is already running. This is an error code. 
<dl>
<dt><b>STATUS_OBJECT_NAME_NOT_FOUND</b></dt>
</dl>No matching minifilter driver was found. This is an error code.

## Remarks

A minifilter driver that has a dependency on another minifilter driver can load that minifilter driver by calling <b>FltLoadFilter</b>. 

To unload the supporting minifilter driver, call <a href="..\fltkernel\nf-fltkernel-fltunloadfilter.md">FltUnloadFilter</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltunloadfilter.md">FltUnloadFilter</a>
</dt>
<dt>
<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltLoadFilter routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>