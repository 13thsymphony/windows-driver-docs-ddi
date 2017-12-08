---
UID: NS.NTDDDUMP._FILTER_INITIALIZATION_DATA
title: _FILTER_INITIALIZATION_DATA
author: windows-driver-content
description: The filter driver fills in a FILTER_INITIALIZATION_DATA structure and returns it to the crash dump driver.
old-location: storage\filter_initialization_data.htm
old-project: storage
ms.assetid: 71f9d0c2-ffc9-4fe1-ae95-f38a1d1e82df
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: _FILTER_INITIALIZATION_DATA, *PFILTER_INITIALIZATION_DATA, FILTER_INITIALIZATION_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntdddump.h
req.include-header: Ntdddump.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista and Windows Server 2008.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FILTER_INITIALIZATION_DATA
req.alt-loc: ntdddump.h
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
---

# _FILTER_INITIALIZATION_DATA structure



## -description
The filter driver fills in a <b>FILTER_INITIALIZATION_DATA</b> structure and returns it to the crash dump driver.


## -syntax

````
typedef struct _FILTER_INITIALIZATION_DATA {
  ULONG        MajorVersion;
  ULONG        MinorVersion;
  PDUMP_START  DumpStart;
  PDUMP_WRITE  DumpWrite;
  PDUMP_FINISH DumpFinish;
  PDUMP_UNLOAD DumpUnload;
  PVOID        DumpData;
  ULONG        MaxPagesPerWrite;
  ULONG        Flags;
  PDUMP_READ   DumpRead;
} FILTER_INITIALIZATION_DATA, *PFILTER_INITIALIZATION_DATA;
````


## -struct-fields

### -field MajorVersion

Set to one of the following major version values:

### -field DUMP_FILTER_MAJOR_VERSION_1 (0x1)
### -field DUMP_FILTER_MAJOR_VERSION (0x2)


### -field MinorVersion

Set to <b>DUMP_FILTER_MINOR_VERSION</b>.

### -field DumpStart

A pointer to the dump initialization routine. This routine is called when the crash dump starts.

### -field DumpWrite

A pointer to the write routine. This routine is called before every crash dump write request.

### -field DumpFinish

A pointer to the dump finish routine.  This routine is called when the crash dump is finished.

### -field DumpUnload

A pointer to the dump unload routine. This routine is called before the driver is unloaded.

### -field DumpData

The filter driver can pass a pointer to internal context data in this member. This pointer is passed back to the filter driver in a <a href="storage.filter_extension">FILTER_EXTENSION</a> structure during each callback.

### -field MaxPagesPerWrite

The maximum number of pages for each dump read or write request.

### -field Flags

A set of flags for  dump filter initialization. This value is set to either 0 or the following:
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -field DUMP_FILTER_FLAG_SYSTEM_SUPPORT_READ

</td>
<td width="60%">
The dump filter supports filtering reads, and a read callback routine is set for <b>DumpRead</b>. This flag is supported starting in Windows 8.
</td>
</tr>
<tr>

### -field DUMP_FILTER_CRITICAL

</td>
<td width="60%">
Fail the filter initialization  immediately if the  dump filter driver's <b>DriverEntry</b> routine does not return STATUS_SUCCESS. This flag is supported starting in Windows 8.
</td>
</tr>
</table>
 

### -field DumpRead

A pointer to the read routine. This routine is called after every crash dump read request. This member is available starting in Windows 8.

## -remarks
For a dump filter driver to support read filtering, the following settings are required:

If any of these members are not set, the dump filter driver will be marked as not supporting dump reads by the crashdump stack.

## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available starting with Windows Vista and Windows Server 2008.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntdddump.h (include Ntdddump.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntdddump\nc-ntdddump-dump_finish.md">Dump_Finish</a>
</dt>
<dt>
<a href="..\ntdddump\nc-ntdddump-dump_read.md">Dump_Read</a>
</dt>
<dt>
<a href="..\ntdddump\nc-ntdddump-dump_start.md">Dump_Start</a>
</dt>
<dt>
<a href="..\ntdddump\nc-ntdddump-dump_write.md">Dump_Write</a>
</dt>
<dt>
<a href="..\ntdddump\nc-ntdddump-dump_unload.md">Dump_Unload</a>
</dt>
<dt>
<a href="storage.filter_extension">FILTER_EXTENSION</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FILTER_INITIALIZATION_DATA structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
