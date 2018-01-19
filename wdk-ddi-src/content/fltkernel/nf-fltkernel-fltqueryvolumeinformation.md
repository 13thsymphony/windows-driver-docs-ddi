---
UID : NF:fltkernel.FltQueryVolumeInformation
title : FltQueryVolumeInformation function
author : windows-driver-content
description : The FltQueryVolumeInformation routine retrieves information about the volume that the given instance is attached to.
old-location : ifsk\fltqueryvolumeinformation.htm
old-project : ifsk
ms.assetid : 57b65e87-7f2d-44fc-84b9-e029c8075be3
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : FltQueryVolumeInformation
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : fltkernel.h
req.include-header : FltKernel.h
req.target-type : Universal
req.target-min-winverclnt : Available and supported in Microsoft Windows 2000 Update Rollup 1 for SP4, Windows XP with Service Pack 2 (SP2), Windows Server 2003 SP1 and later  Windows operating systems. Not available or supported in Windows 2000 SP4 and earlier Windows operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : FltQueryVolumeInformation
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


# FltQueryVolumeInformation function
The <b>FltQueryVolumeInformation</b> routine retrieves information about the volume that the given instance is attached to.

## Syntax

````
NTSTATUS FltQueryVolumeInformation(
  _In_  PFLT_INSTANCE        Instance,
  _Out_ PIO_STATUS_BLOCK     Iosb,
  _Out_ PVOID                FsInformation,
  _In_  ULONG                Length,
  _In_  FS_INFORMATION_CLASS FsInformationClass
);
````

## Parameters

`Instance`

An opaque instance pointer for a minifilter driver instance that is attached to the volume.

`Iosb`

A pointer to caller-allocated IO_STATUS_BLOCK structure that receives the final completion status and information about the query operation. For successful calls that return data, the number of bytes written to the <i>FsInformation</i> buffer is returned in the structure's <b>Information</b> member.

`FsInformation`

A pointer to a caller-allocated buffer that receives the desired information about the volume. The structure of the information returned in the buffer is defined by the <i>FsInformationClass</i> parameter.

`Length`

The size in bytes of the buffer that <i>FsInformation</i> points to. The caller should set this parameter according to the given <i>FsInformationClass</i>. For example, if the value of <i>FsInformationClass</i> is FileFsControlInformation, <i>Length</i> must be at least <b>sizeof</b>(FILE_FS_CONTROL_INFORMATION).

`FsInformationClass`

The type of information requested. One of the following value. 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>


## Return Value

The <b>FltQueryVolumeInformation</b> routine returns <b>STATUS_SUCCESS</b> or an appropriate <b>NTSTATUS</b> value such as one of the following: 
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
<a href="..\fltkernel\nf-fltkernel-fltqueryvolumeinformation.md">FltQueryVolumeInformation</a> encountered a pool allocation failure. This is an error code. 
<dl>
<dt><b>STATUS_INVALID_INFO_CLASS</b></dt>
</dl>An invalid value was specified for <i>FsInformationClass</i>. This is an error code. 
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The <i>Instance</i> is attached to a network volume. <a href="..\fltkernel\nf-fltkernel-fltqueryvolumeinformation.md">FltQueryVolumeInformation</a> cannot be used to query network volume information. This is an error code.

## Remarks

Fields in the FILE_<i>XXX</i>_INFORMATION structure that are not supported by the underlying file system are set to zero. 

To change information about a volume, call <a href="..\fltkernel\nf-fltkernel-fltsetvolumeinformation.md">FltSetVolumeInformation</a>. 

To get volume property information for the given volume, call <a href="..\fltkernel\nf-fltkernel-fltgetvolumeproperties.md">FltGetVolumeProperties</a>. 

To get the volume name for a given volume, call <a href="..\fltkernel\nf-fltkernel-fltgetvolumename.md">FltGetVolumeName</a>. 

To get the volume GUID name for a given volume, call <a href="..\fltkernel\nf-fltkernel-fltgetvolumeguidname.md">FltGetVolumeGuidName</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | fltkernel.h (include FltKernel.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\ntifs\ns-ntifs-_file_fs_attribute_information.md">FILE_FS_ATTRIBUTE_INFORMATION</a>
</dt>
<dt>
<a href="..\ntifs\ns-ntifs-_file_fs_control_information.md">FILE_FS_CONTROL_INFORMATION</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_file_fs_device_information.md">FILE_FS_DEVICE_INFORMATION</a>
</dt>
<dt>
<a href="..\ntifs\ns-ntifs-_file_fs_driver_path_information.md">FILE_FS_DRIVER_PATH_INFORMATION</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk-_file_fs_full_size_information.md">FILE_FS_FULL_SIZE_INFORMATION</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk-_file_fs_objectid_information.md">FILE_FS_OBJECTID_INFORMATION</a>
</dt>
<dt><b>FILE_FS_SECTOR_SIZE_INFORMATION</b></dt>
<dt>
<a href="..\ntddk\ns-ntddk-_file_fs_size_information.md">FILE_FS_SIZE_INFORMATION</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk-_file_fs_volume_information.md">FILE_FS_VOLUME_INFORMATION</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetvolumeguidname.md">FltGetVolumeGuidName</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetvolumename.md">FltGetVolumeName</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetvolumeproperties.md">FltGetVolumeProperties</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltsetvolumeinformation.md">FltSetVolumeInformation</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltQueryVolumeInformation routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>