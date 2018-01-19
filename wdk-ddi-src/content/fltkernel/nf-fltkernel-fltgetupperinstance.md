---
UID : NF:fltkernel.FltGetUpperInstance
title : FltGetUpperInstance function
author : windows-driver-content
description : The FltGetUpperInstance routine returns an opaque instance pointer for the next higher minifilter driver instance, if there is one, that is attached above a given minifilter driver instance on the same volume.
old-location : ifsk\fltgetupperinstance.htm
old-project : ifsk
ms.assetid : 01e7760c-b10c-497e-9cab-4d839c2ce5ff
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : FltGetUpperInstance
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
req.alt-api : FltGetUpperInstance
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


# FltGetUpperInstance function
The <b>FltGetUpperInstance</b> routine returns an opaque instance pointer for the next higher minifilter driver instance, if there is one, that is attached above a given minifilter driver instance on the same volume.

## Syntax

````
NTSTATUS FltGetUpperInstance(
  _In_  PFLT_INSTANCE CurrentInstance,
  _Out_ PFLT_INSTANCE *UpperInstance
);
````

## Parameters

`CurrentInstance`

Opaque instance pointer for the instance for which the next higher instance is requested.

`UpperInstance`

Pointer to a caller-allocated variable that receives an opaque instance pointer for the next higher instance. This parameter is required and cannot be <b>NULL</b>.


## Return Value

<b>FltGetUpperInstance</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as the following: 
<dl>
<dt><b>STATUS_NO_MORE_ENTRIES</b></dt>
</dl>No higher instance was found. This is a warning code.

## Remarks

One instance is said to be <i>above</i> another if it is attached at a higher altitude on the same volume. The term "altitude" refers to the position that an instance occupies (or should occupy) in the minifilter driver instance stack for a volume. The higher the altitude, the farther the instance is from the base file system in the stack. Only one instance can be attached at a given altitude on a given volume. 

Altitude is specified by an <i>altitude string</i>, which is a counted Unicode string consisting of one or more decimal digits in the range of 0 through 9, and it can include a single decimal point. For example, "100.123456" and "03333" are valid altitude strings. 

The string "03333" represents a higher altitude than "100.123456". (Leading and trailing zeros are ignored.) In other words, an instance whose altitude is "03333" is farther from the base file system than an instance whose altitude is "100.123456". However, this comparison is only meaningful if both instances are attached to the same volume. 

<b>FltGetUpperInstance</b> adds a rundown reference to the opaque instance pointer returned in the <i>UpperInstance</i> parameter. When this pointer is no longer needed, the caller must release it by calling <a href="..\fltkernel\nf-fltkernel-fltobjectdereference.md">FltObjectDereference</a>. Thus every successful call to <b>FltGetUpperInstance</b> must be matched by a subsequent call to <b>FltObjectDereference</b>.

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
<a href="..\fltkernel\nf-fltkernel-fltattachvolume.md">FltAttachVolume</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltattachvolumeataltitude.md">FltAttachVolumeAtAltitude</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltcompareinstancealtitudes.md">FltCompareInstanceAltitudes</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetbottominstance.md">FltGetBottomInstance</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetlowerinstance.md">FltGetLowerInstance</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgettopinstance.md">FltGetTopInstance</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltobjectdereference.md">FltObjectDereference</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltGetUpperInstance routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>