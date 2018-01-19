---
UID : NF:fltkernel.FltGetVolumeFromName
title : FltGetVolumeFromName function
author : windows-driver-content
description : The FltGetVolumeFromName routine returns an opaque pointer for the volume whose name matches the value of the VolumeName parameter.
old-location : ifsk\fltgetvolumefromname.htm
old-project : ifsk
ms.assetid : 813b914a-05d6-4e5a-9420-f87e94ee9e96
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : FltGetVolumeFromName
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
req.alt-api : FltGetVolumeFromName
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


# FltGetVolumeFromName function
The <b>FltGetVolumeFromName</b> routine returns an opaque pointer for the volume whose name matches the value of the <i>VolumeName</i> parameter.

## Syntax

````
NTSTATUS FltGetVolumeFromName(
  _In_  PFLT_FILTER      Filter,
  _In_  PCUNICODE_STRING VolumeName,
  _Out_ PFLT_VOLUME      *RetVolume
);
````

## Parameters

`Filter`

Opaque filter pointer for the caller. This parameter is required and cannot be <b>NULL</b>.

`VolumeName`

Pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains the volume name (for example, "\Device\HarddiskVolume1", "\DosDevices\D:", "\??\D:", or "D:"). This parameter is required and cannot be <b>NULL</b>.

`RetVolume`

Pointer to a caller-allocated variable that receives an opaque pointer for the volume. This parameter is required and cannot be <b>NULL</b>.


## Return Value

<b>FltGetVolumeFromName</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as one of the following: 
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>The caller did not have FILE_READ_DATA access to the volume. This is an error code. 
<dl>
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl>The volume is being torn down. This is an error code. 
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An invalid value was specified for the <i>VolumeName</i> parameter. This is an error code. 
<dl>
<dt><b>STATUS_FLT_VOLUME_NOT_FOUND</b></dt>
</dl>No matching volume was found. This is an error code.

## Remarks

<b>FltGetVolumeFromName</b> searches the Filter Manager's global list of volumes for a volume whose name matches <i>VolumeName</i>. The caller must have FILE_READ_DATA access to the volume. To locate the volume structure, <b>FltGetVolumeFromName</b> must first open the volume.

<b>FltGetVolumeFromName</b> adds a rundown reference to the opaque volume pointer returned in the <i>RetVolume</i> parameter. When this pointer is no longer needed, the caller must release it by calling <a href="..\fltkernel\nf-fltkernel-fltobjectdereference.md">FltObjectDereference</a>. Thus every successful call to <b>FltGetVolumeFromName</b> must be matched by a subsequent call to <b>FltObjectDereference</b>. 

To get the volume name for a given volume, call <a href="..\fltkernel\nf-fltkernel-fltgetvolumename.md">FltGetVolumeName</a>. 

To get the volume GUID name for a given volume, call <a href="..\fltkernel\nf-fltkernel-fltgetvolumeguidname.md">FltGetVolumeGuidName</a>.

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
<a href="..\fltkernel\nf-fltkernel-fltgetfilterfromname.md">FltGetFilterFromName</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetvolumeguidname.md">FltGetVolumeGuidName</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetvolumeinstancefromname.md">FltGetVolumeInstanceFromName</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetvolumename.md">FltGetVolumeName</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltobjectdereference.md">FltObjectDereference</a>
</dt>
<dt>
<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltGetVolumeFromName routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>