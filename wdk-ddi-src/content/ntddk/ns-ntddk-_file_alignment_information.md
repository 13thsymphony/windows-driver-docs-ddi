---
UID: NS.NTDDK._FILE_ALIGNMENT_INFORMATION
title: _FILE_ALIGNMENT_INFORMATION
author: windows-driver-content
description: The FILE_ALIGNMENT_INFORMATION structure is used as an argument to the ZwQueryInformationFile routine.
old-location: kernel\file_alignment_information.htm
old-project: kernel
ms.assetid: d3990d67-aa0c-4d17-9126-80fdcebbd306
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _FILE_ALIGNMENT_INFORMATION, *PFILE_ALIGNMENT_INFORMATION, FILE_ALIGNMENT_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FILE_ALIGNMENT_INFORMATION
req.alt-loc: Ntddk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
---

# _FILE_ALIGNMENT_INFORMATION structure



## -description
The <b>FILE_ALIGNMENT_INFORMATION</b> structure is used as an argument to the <a href="kernel.zwqueryinformationfile">ZwQueryInformationFile</a> routine.


## -syntax

````
typedef struct _FILE_ALIGNMENT_INFORMATION {
  ULONG AlignmentRequirement;
} FILE_ALIGNMENT_INFORMATION, *PFILE_ALIGNMENT_INFORMATION;
````


## -struct-fields

### -field AlignmentRequirement

The buffer alignment required by the underlying device. For a list of system-defined values, see <a href="kernel.device_object">DEVICE_OBJECT</a>. The value must be one of the FILE_<i>XXX</i>_ALIGNMENT values defined in Wdm.h. For more information, see <a href="kernel.device_object">DEVICE_OBJECT</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff547807">Initializing a Device Object</a>.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h or Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.device_object">DEVICE_OBJECT</a>
</dt>
<dt>
<a href="kernel.zwqueryinformationfile">ZwQueryInformationFile</a>
</dt>
<dt>
<a href="kernel.zwsetinformationfile">ZwSetInformationFile</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20FILE_ALIGNMENT_INFORMATION structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
