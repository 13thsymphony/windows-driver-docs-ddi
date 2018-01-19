---
UID : NF:fltkernel.FltGetVolumeFromInstance
title : FltGetVolumeFromInstance function
author : windows-driver-content
description : The FltGetVolumeFromInstance routine returns an opaque pointer for the volume that a given minifilter driver instance is attached to.
old-location : ifsk\fltgetvolumefrominstance.htm
old-project : ifsk
ms.assetid : 2c38ab6a-c583-45a5-93a5-6a5882411b6c
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : FltGetVolumeFromInstance
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
req.alt-api : FltGetVolumeFromInstance
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
req.irql : <= APC_LEVEL
req.typenames : EXpsFontRestriction
---


# FltGetVolumeFromInstance function
The <b>FltGetVolumeFromInstance</b> routine returns an opaque pointer for the volume that a given minifilter driver instance is attached to.

## Syntax

````
NTSTATUS FltGetVolumeFromInstance(
  _In_  PFLT_INSTANCE Instance,
  _Out_ PFLT_VOLUME   *RetVolume
);
````

## Parameters

`Instance`

Opaque instance pointer for the instance.

`RetVolume`

Pointer to a caller-allocated variable that receives an opaque pointer for the volume. This parameter is required and cannot be <b>NULL</b>.


## Return Value

<b>FltGetVolumeFromInstance</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as the following: 
<dl>
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl>The volume that the minifilter driver instance is attached to is being torn down. This is an error code.

## Remarks

<b>FltGetVolumeFromInstance</b> adds a rundown reference to the opaque volume pointer returned in the <i>RetVolume</i> parameter. When this pointer is no longer needed, the caller must release it by calling <a href="..\fltkernel\nf-fltkernel-fltobjectdereference.md">FltObjectDereference</a>. Thus every successful call to <b>FltGetVolumeFromInstance</b> must be matched by a subsequent call to <b>FltObjectDereference</b>. 

To get an opaque filter pointer for the minifilter driver that created a given instance, call <a href="..\fltkernel\nf-fltkernel-fltgetfilterfrominstance.md">FltGetFilterFromInstance</a>. 

To get a pointer to the device object for a given volume, call <a href="..\fltkernel\nf-fltkernel-fltgetdeviceobject.md">FltGetDeviceObject</a>. 

To get detailed information about the volume that a given instance is attached to, call <a href="..\fltkernel\nf-fltkernel-fltqueryvolumeinformation.md">FltQueryVolumeInformation</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** |  |
| **IRQL** | <= APC_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetdeviceobject.md">FltGetDeviceObject</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetfilterfrominstance.md">FltGetFilterFromInstance</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltobjectdereference.md">FltObjectDereference</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltqueryvolumeinformation.md">FltQueryVolumeInformation</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltGetVolumeFromInstance routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>