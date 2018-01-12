---
UID: NS:ntifs._FSCTL_OFFLOAD_WRITE_OUTPUT
title: _FSCTL_OFFLOAD_WRITE_OUTPUT
author: windows-driver-content
description: The FSCTL_OFFLOAD_WRITE_OUTPUT structure contains the output for the FSCTL_OFFLOAD_WRITE control code request.
old-location: ifsk\fsctl_offload_write_output.htm
old-project: ifsk
ms.assetid: 7293940B-A316-43C5-A5E8-6ED70EC6FDF8
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _FSCTL_OFFLOAD_WRITE_OUTPUT, *PFSCTL_OFFLOAD_WRITE_OUTPUT, FSCTL_OFFLOAD_WRITE_OUTPUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FSCTL_OFFLOAD_WRITE_OUTPUT
req.alt-loc: ntifs.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.typenames: *PFSCTL_OFFLOAD_WRITE_OUTPUT, FSCTL_OFFLOAD_WRITE_OUTPUT
---

# _FSCTL_OFFLOAD_WRITE_OUTPUT structure



## -description
The <b>FSCTL_OFFLOAD_WRITE_OUTPUT</b> structure contains the output for the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451122">FSCTL_OFFLOAD_WRITE</a> control code request.



## -syntax

````
typedef struct _FSCTL_OFFLOAD_WRITE_OUTPUT {
  ULONG     Size;
  ULONG     Flags;
  ULONGLONG LengthWritten;
} FSCTL_OFFLOAD_WRITE_OUTPUT, *PFSCTL_OFFLOAD_WRITE_OUTPUT;
````


## -struct-fields

### -field Size

The size of this structure. Set this member to <b>sizeof</b>(FSCTL_OFFLOAD_WRITE_OUTPUT).


### -field Flags

 Result flags for the offload write operation. This value is either 0 or the following:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -field OFFLOAD_READ_FLAG_FILE_TOO_SMALL
### -field 0x00000001

</td>
<td width="60%">
The file to write to is too small for an offload operation.

</td>
</tr>
</table>
 


### -field LengthWritten

The length of data written for the transfer specified in <a href="..\ntifs\ns-ntifs-_fsctl_offload_write_input.md">FSCTL_OFFLOAD_WRITE_INPUT</a>.


## -remarks
 The resulting length written, <b>LengthWritten</b>, may be smaller than what was originally specified in the <b>CopyLength</b> member of <a href="..\ntifs\ns-ntifs-_fsctl_offload_write_input.md">FSCTL_OFFLOAD_WRITE_INPUT</a>. A smaller value indicates that less data was able to be logically written with the specified <b>Token</b> than was requested.

 If less data than requested was written, the write operation  may be completed by performing another <a href="https://msdn.microsoft.com/library/windows/hardware/hh451122">FSCTL_OFFLOAD_WRITE</a> request. The next request uses an updated <b>FileOffset</b> member in the <a href="..\ntifs\ns-ntifs-_fsctl_offload_write_input.md">FSCTL_OFFLOAD_WRITE_INPUT</a> structure with the value in <b>LengthWritten</b> and an adjusted write length of the previous length minus the value in <b>LengthWritten</b>. Also, an incomplete write operation can be completed through a non-offloaded write method, using the <a href="..\wdm\nf-wdm-zwwritefile.md">ZwWriteFile</a> routine, for example.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows 8.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h or Fltkernel.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451122">FSCTL_OFFLOAD_WRITE</a>
</dt>
<dt>
<a href="..\ntifs\ns-ntifs-_fsctl_offload_write_input.md">FSCTL_OFFLOAD_WRITE_INPUT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FSCTL_OFFLOAD_WRITE_OUTPUT structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

