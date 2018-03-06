---
UID: NF:fltkernel.FltGetVolumeInstanceFromName
title: FltGetVolumeInstanceFromName function
author: windows-driver-content
description: The FltGetVolumeInstanceFromName routine returns an opaque instance pointer for the given minifilter driver instance on the given volume.
old-location: ifsk\fltgetvolumeinstancefromname.htm
old-project: ifsk
ms.assetid: 25455faa-2197-4b2a-bce8-db9764153e51
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltApiRef_e_to_o_78e7987d-7f24-4c51-b263-502005595c6d.xml, FltGetVolumeInstanceFromName, FltGetVolumeInstanceFromName routine [Installable File System Drivers], fltkernel/FltGetVolumeInstanceFromName, ifsk.fltgetvolumeinstancefromname
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
-	FltGetVolumeInstanceFromName
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# FltGetVolumeInstanceFromName function
The <b>FltGetVolumeInstanceFromName</b> routine returns an opaque instance pointer for the given minifilter driver instance on the given volume.

## Syntax

````
NTSTATUS FltGetVolumeInstanceFromName(
  _In_opt_ PFLT_FILTER      Filter,
  _In_     PFLT_VOLUME      Volume,
  _In_opt_ PCUNICODE_STRING InstanceName,
  _Out_    PFLT_INSTANCE    *RetInstance
);
````

## Parameters

`Filter`

Opaque filter pointer for the minifilter driver that owns the instance. This parameter is optional and can be <b>NULL</b>.

`Volume`

Opaque pointer for the volume that the instance is attached to. Must be a valid volume handle. This parameter is required and cannot be <b>NULL</b>. (Setting this parameter to an invalid value causes the system to ASSERT on a checked build.)

`InstanceName`

Pointer to a caller-allocated <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains the instance name for the instance on the volume. (This is the <i>InstanceName</i> value that was passed to <a href="..\fltkernel\nf-fltkernel-fltattachvolume.md">FltAttachVolume</a> or <a href="..\fltkernel\nf-fltkernel-fltattachvolumeataltitude.md">FltAttachVolumeAtAltitude</a> when the instance was created.) This parameter is optional and can be <b>NULL</b>. If it is <b>NULL</b>, <b>FltGetVolumeInstanceFromName</b> returns the highest matching instance that is found.

`RetInstance`

Pointer to a caller-allocated variable that receives an opaque instance pointer for the instance that matches the values for <i>Filter</i>, <i>Volume</i>, and <i>InstanceName</i>. This parameter is required and cannot be <b>NULL</b>.


## Return Value

<b>FltGetVolumeInstanceFromName</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as one of the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl>
</td>
<td width="60%">
The instance is being torn down. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_INSTANCE_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
No matching instance was found. This is an error code. 

</td>
</tr>
</table>

## Remarks

<b>FltGetVolumeInstanceFromName</b> searches the list of minifilter driver instances attached to the volume specified in the <i>Volume</i> parameter in order of decreasing altitude, beginning with the topmost instance. If more than one instance matches the given values for the <i>Filter</i>, <i>Volume</i>, and <i>InstanceName</i> parameters, <b>FltGetVolumeInstanceFromName</b> returns the highest matching instance that is found. 

The term "altitude" refers to the position that an instance occupies (or should occupy) in the minifilter driver instance stack for a volume. The higher the altitude, the farther the instance is from the base file system in the stack. Only one instance can be attached at a given altitude on a given volume. 

Altitude is specified by an <i>altitude string</i>, which is a counted Unicode string consisting of one or more decimal digits from 0 through 9, and it can include a single decimal point. For example, "100.123456" and "03333" are valid altitude strings. 

The string "03333" represents a higher altitude than "100.123456". (Leading and trailing zeros are ignored.) In other words, an instance whose altitude is "03333" is farther from the base file system than an instance whose altitude is "100.123456". However, this comparison is only meaningful if both instances are attached to the same volume. 

<b>FltGetVolumeInstanceFromName</b> adds a rundown reference to the opaque instance pointer returned in the <i>RetInstance</i> parameter. When this pointer is no longer needed, the caller must release it by calling <a href="..\fltkernel\nf-fltkernel-fltobjectdereference.md">FltObjectDereference</a>. Thus every successful call to <b>FltGetVolumeInstanceFromName</b> must be matched by a subsequent call to <b>FltObjectDereference</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** | FltMgr.lib |
| **DLL** | Fltmgr.sys |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\fltkernel\nf-fltkernel-fltattachvolume.md">FltAttachVolume</a>



<a href="..\fltkernel\nf-fltkernel-fltobjectdereference.md">FltObjectDereference</a>



<a href="..\fltkernel\nf-fltkernel-fltattachvolumeataltitude.md">FltAttachVolumeAtAltitude</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltGetVolumeInstanceFromName routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>