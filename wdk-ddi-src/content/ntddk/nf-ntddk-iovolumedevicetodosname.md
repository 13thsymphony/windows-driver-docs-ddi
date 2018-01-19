---
UID : NF:ntddk.IoVolumeDeviceToDosName
title : IoVolumeDeviceToDosName function
author : windows-driver-content
description : The IoVolumeDeviceToDosName routine returns the MS-DOS path for a specified device object that represents a file system volume.
old-location : kernel\iovolumedevicetodosname.htm
old-project : kernel
ms.assetid : f860d0ad-f971-4ba7-93fb-20fe8831fc90
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : IoVolumeDeviceToDosName
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntddk.h
req.include-header : Ntddk.h
req.target-type : Universal
req.target-min-winverclnt : Available starting with Windows XP. Drivers that must work in earlier versions of Windows NT-based operating systems can use RtlVolumeDeviceToDosName, which behaves identically.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IoVolumeDeviceToDosName
req.alt-loc : NtosKrnl.exe
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : PASSIVE_LEVEL
req.typenames : WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# IoVolumeDeviceToDosName function
The <b>IoVolumeDeviceToDosName</b> routine returns the MS-DOS path for a specified device object that represents a file system volume.

## Syntax

````
NTSTATUS IoVolumeDeviceToDosName(
  _In_  PVOID           VolumeDeviceObject,
  _Out_ PUNICODE_STRING DosName
);
````

## Parameters

`VolumeDeviceObject`

A pointer to a device object that represents a volume device object created by a storage class driver.

`DosName`

A pointer to a caller-allocated <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure. If the call is successful, <b>IoVolumeDeviceToDosName</b> sets the values of the <b>Length</b>, <b>MaximumLength</b>, and <b>Buffer</b> members of this structure. On exit, the <b>Buffer</b> member points to a wide-character, null-terminated string that contains the MS-DOS path of the volume device object specified by <i>VolumeDeviceObject</i>. For more information, see Remarks.


## Return Value

<b>IoVolumeDeviceToDosName</b> returns STATUS_SUCCESS if the call is successful. Possible error return values include the following status codes.
<dl>
<dt>STATUS_INVALID_PARAMETER</dt>
</dl>The routine failed due to invalid parameter values passed by the caller.
<dl>
<dt>STATUS_INSUFFICIENT_RESOURCES</dt>
</dl>The routine failed to allocate resources required for this operation.

## Remarks

<b>IoVolumeDeviceToDosName</b> allocates the string buffer pointed to by the <b>Buffer</b> member of the <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that the <i>DosName</i> parameter points to. After this buffer is no longer required, a caller of this routine should call the <a href="..\ntddk\nf-ntddk-exfreepool.md">ExFreePool</a> routine to free the buffer.

Starting with Windows Vista, you must ensure that APCs are <u>not</u> disabled before calling this routine. The <a href="..\wdm\nf-wdm-keareallapcsdisabled.md">KeAreAllApcsDisabled</a> routine can be used to verify that APCs are not disabled.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddk.h (include Ntddk.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\ntddk\nf-ntddk-exfreepool.md">ExFreePool</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-keareallapcsdisabled.md">KeAreAllApcsDisabled</a>
</dt>
<dt>
<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoVolumeDeviceToDosName routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>