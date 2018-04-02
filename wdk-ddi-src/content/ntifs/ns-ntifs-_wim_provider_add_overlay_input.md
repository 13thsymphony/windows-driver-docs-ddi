---
UID: NS:ntifs._WIM_PROVIDER_ADD_OVERLAY_INPUT
title: "_WIM_PROVIDER_ADD_OVERLAY_INPUT"
author: windows-driver-content
description: A new Windows Image File (WIM) data source is added to the WIM provider with the WIM_PROVIDER_ADD_OVERLAY_INPUT structure.
old-location: ifsk\wim_provider_add_overlay_input.htm
old-project: ifsk
ms.assetid: 75C95941-367D-4A7F-A121-AF2BF9EFE28E
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PWIM_PROVIDER_ADD_OVERLAY_INPUT, PWIM_PROVIDER_ADD_OVERLAY_INPUT, PWIM_PROVIDER_ADD_OVERLAY_INPUT structure pointer [Installable File System Drivers], WIM_BOOT_NOT_OS_WIM, WIM_BOOT_OS_WIM, WIM_PROVIDER_ADD_OVERLAY_INPUT, WIM_PROVIDER_ADD_OVERLAY_INPUT structure [Installable File System Drivers], _WIM_PROVIDER_ADD_OVERLAY_INPUT, ifsk.wim_provider_add_overlay_input, ntifs/PWIM_PROVIDER_ADD_OVERLAY_INPUT, ntifs/WIM_PROVIDER_ADD_OVERLAY_INPUT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.1 Update.
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntifs.h
api_name:
-	WIM_PROVIDER_ADD_OVERLAY_INPUT
product: Windows
targetos: Windows
req.typenames: WIM_PROVIDER_ADD_OVERLAY_INPUT, *PWIM_PROVIDER_ADD_OVERLAY_INPUT
---

# _WIM_PROVIDER_ADD_OVERLAY_INPUT structure
A new Windows Image File (WIM) data source is added to the WIM provider with the <b>WIM_PROVIDER_ADD_OVERLAY_INPUT</b> structure.

## Syntax
```
typedef struct _WIM_PROVIDER_ADD_OVERLAY_INPUT {
  ULONG WimType;
  ULONG WimIndex;
  ULONG WimFileNameOffset;
  ULONG WimFileNameLength;
} WIM_PROVIDER_ADD_OVERLAY_INPUT, *PWIM_PROVIDER_ADD_OVERLAY_INPUT;
```

## Members


`WimType`

The type of WIM file set as a backing source. The WIM file type is set to one of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="_WIM_BOOT_OS_WIM"></a><a id="_wim_boot_os_wim"></a><dl>
<dt><b> WIM_BOOT_OS_WIM</b></dt>
</dl>
</td>
<td width="60%">
The WIM file contains Windows system files.

</td>
</tr>
<tr>
<td width="40%"><a id="_WIM_BOOT_NOT_OS_WIM"></a><a id="_wim_boot_not_os_wim"></a><dl>
<dt><b> WIM_BOOT_NOT_OS_WIM</b></dt>
</dl>
</td>
<td width="60%">
The WIM file contains non-operating system files.

</td>
</tr>
</table>

`WimIndex`

The index of the image in the WIM file whose filename is specified at <b>WimFileNameOffset</b>.

`WimFileNameOffset`

The offset, in bytes, from the beginning of this structure of the file name for the WIM file to add as a backing source. The file name is a string of <b>WCHAR</b> character values.

`WimFileNameLength`

The length, in bytes, of the file name at found at  <b>WimFileNameOffset</b>.

## Remarks
The WIM file name is included immediately following <b>WIM_PROVIDER_ADD_OVERLAY_INPUT</b> in the system buffer for a <a href="https://msdn.microsoft.com/library/windows/hardware/dn632437">FSCTL_ADD_OVERLAY</a> control request. The <b>WimFileNameOffset</b> member is set to <b>sizeof</b>(WIM_PROVIDER_ADD_OVERLAY_INPUT).

The WIM file name includes a terminating NULL character. <b>WimFileNameLength</b> contains the length of the file name excluding the terminating NULL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8.1 Update. Available starting with Windows 8.1 Update. |
| **Header** | ntifs.h (include Ntifs.h, Fltkernel.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn632437">FSCTL_ADD_OVERLAY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn632442">FSCTL_REMOVE_OVERLAY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt426735">FSCTL_SUSPEND_OVERLAY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn632445">FSCTL_UPDATE_OVERLAY</a>