---
UID : NF:ndis.NdisWriteEventLogEntry
title : NdisWriteEventLogEntry function
author : windows-driver-content
description : NdisWriteEventLogEntry logs an event to the Win32 event log.
old-location : netvista\ndiswriteeventlogentry.htm
old-project : netvista
ms.assetid : 1f3fbcf1-e6f4-4117-a795-f4b14ef9fc96
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : netvista.ndiswriteeventlogentry, miniport_logging_ref_435a14ad-ae5a-4ff9-80a9-2c41966ed8ba.xml, NdisWriteEventLogEntry function [Network Drivers Starting with Windows Vista], ndis/NdisWriteEventLogEntry, NdisWriteEventLogEntry
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Universal
req.target-min-winverclnt : Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisWriteEventLogEntry (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisWriteEventLogEntry (NDIS   5.1)) in Windows XP.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : Irql_Miscellaneous_Function
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ndis.lib
req.dll : 
req.irql : "<= DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisWriteEventLogEntry function
<b>NdisWriteEventLogEntry</b> logs an event to the Win32 event log.

## Syntax

````
NDIS_STATUS NdisWriteEventLogEntry(
  _In_     PVOID       LogHandle,
  _In_     NDIS_STATUS EventCode,
  _In_     ULONG       UniqueEventValue,
  _In_     USHORT      NumStrings,
  _In_opt_ PVOID       StringsList,
  _In_     ULONG       DataSize,
  _In_opt_ PVOID       Data
);
````

## Parameters

`LogHandle`

Pointer to the driver object of the protocol that is logging this event.

`EventCode`

Specifies the NDIS_STATUS_<i>XXX</i> code describing the event.

`UniqueEventValue`

Identifies this instance of the error message.

`NumStrings`

Specifies the number of pointers to Unicode strings in the optional 
     <i>StringsList</i>. If 
     <i>StringsList</i> is <b>NULL</b>, 
     <i>NumStrings</i> must be zero.

`StringsList`

Either <b>NULL</b> or points to buffered Unicode strings. These strings, which describe the event, are
     inserted into the Win32 event log and can be examined with the Win32 event viewer. Each string must be a
     NUL-terminated Unicode string.

`DataSize`

Specifies the number of bytes in the buffer for the binary data at 
     <i>Data</i> . If 
     <i>Data</i> is <b>NULL</b>, 
     <i>DataSize</i> must be zero.

`Data`

Either <b>NULL</b> or points to buffered binary dump data that is useful for understanding the event.
     This data can be examined with the Win32 event viewer.


## Return Value

<b>NdisWriteEventLogEntry</b> can return one of the following values:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The event was successfully logged.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_BUFFER_TOO_SHORT</b></dt>
</dl>
</td>
<td width="60%">
The optionally supplied Unicode strings and binary dump data exceed the maximum-allowed size
       (MAX_EVENT_LOG_DATA_SIZE).

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
NDIS was unable to allocate memory for the I/O error log record.

</td>
</tr>
</table>

## Remarks

<b>NdisWriteEventLogEntry</b> allocates an I/O error log record, fills in the record with the supplied
    information about the event, and then writes the record to the I/O error log file. A user can view the
    logged event, including an optional description of the event and/or optional binary dump data, with the
    Win32 event viewer.

The NT error-logging thread uses any strings supplied in the optional 
    <i>StringsList</i> to fill in messages written into the Win32 event log. Each string must be a
    NUL-terminated Unicode string. The I/O manager assumes that the initial string is either the name of the
    driver reporting the error or the name of the device that caused the error.

The Unicode strings supplied by the caller should be read from the registry or should be
    language-independent (that is, the strings should be the same in any language -- for example, the string
    could be a file name).

Caller-supplied dump data can be any binary data (such as register values) that is useful in
    understanding the event. The caller does not have to pad the binary data. If necessary, 
    <b>NdisWriteEventLogEntry</b> pads the binary dump data so that the final data size is a multiple integral
    of 
    <b>sizeof</b>(ULONG).

The system limits the total size of the optional data supplied to 
    <b>NdisWriteEventLogEntry</b>. The combined size of the strings list and the (possibly padded) binary
    dump must be less than or equal to MAX_EVENT_LOG_DATA_SIZE.

<b>NdisWriteEventLogEntry</b> is called only by protocol drivers. Miniport drivers should call 
    <b>NdisWriteErrorLogEntry</b> to log events and errors.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisWriteEventLogEntry (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisWriteEventLogEntry (NDIS   5.1)) in Windows XP. Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisWriteEventLogEntry (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisWriteEventLogEntry (NDIS   5.1)) in Windows XP. |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | Irql_Miscellaneous_Function |

## See Also

<a href="..\ndis\nc-ndis-miniport_reset.md">MiniportResetEx</a>

<a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">NdisMSetMiniportAttributes</a>

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>

<a href="..\ndis\nf-ndis-ndiswriteerrorlogentry.md">NdisWriteErrorLogEntry</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisWriteEventLogEntry function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>