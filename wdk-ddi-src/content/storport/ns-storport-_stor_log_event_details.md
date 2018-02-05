---
UID : NS:storport._STOR_LOG_EVENT_DETAILS
title : "_STOR_LOG_EVENT_DETAILS"
author : windows-driver-content
description : The STOR_LOG_EVENT_DETAILS structure provides details pertaining to Storport-specific error log events and system log events.
old-location : storage\stor_log_event_details.htm
old-project : storage
ms.assetid : 2370e730-6c35-45e6-a370-62adc10df53b
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : STOR_LOG_EVENT_DETAILS structure [Storage Devices], structs-storport_ba65fe62-1b9a-4234-b9a4-b145bf549699.xml, storport/STOR_LOG_EVENT_DETAILS, _STOR_LOG_EVENT_DETAILS, PSTOR_LOG_EVENT_DETAILS, STOR_LOG_EVENT_DETAILS, storport/PSTOR_LOG_EVENT_DETAILS, *PSTOR_LOG_EVENT_DETAILS, PSTOR_LOG_EVENT_DETAILS structure pointer [Storage Devices], storage.stor_log_event_details
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : storport.h
req.include-header : Storport.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PSTOR_LOG_EVENT_DETAILS, STOR_LOG_EVENT_DETAILS"
req.product : Windows 10 or later.
---

# _STOR_LOG_EVENT_DETAILS structure
The <b>STOR_LOG_EVENT_DETAILS</b> structure provides details pertaining to Storport-specific error log events and system  log events.

## Syntax
````
typedef struct _STOR_LOG_EVENT_DETAILS {
  ULONG                       InterfaceRevision;
  ULONG                       Size;
  ULONG                       Flags;
  STOR_EVENT_ASSOCIATION_ENUM EventAssociation;
  ULONG                       PathId;
  ULONG                       TargetId;
  ULONG                       LunId;
  BOOLEAN                     StorportSpecificErrorCode;
  ULONG                       ErrorCode;
  ULONG                       UniqueId;
  ULONG                       DumpDataSize;
  PVOID                       DumpData;
  ULONG                       StringCount;
  PWSTR                       *StringList;
} STOR_LOG_EVENT_DETAILS, *PSTOR_LOG_EVENT_DETAILS;
````

## Members


`DumpData`

Pointer to the miniport-specific data block that is to be appended to the log entry. If no data block is to be written, DumpDataSize should be set to 0, and this field is ignored.

`DumpDataSize`

The size of the miniport-specific data block that is to be appended to the log entry. If no data block is to be written, this should be set to 0.

`ErrorCode`

The event error code to log.

`EventAssociation`

Specifies whether the event should be associated with the adapter, the target, or the LUN. For adapter- and target-associated events, the event is logged against the adapter's device object. For LUN-associated events, the event is logged against the LUN's device object if it exists; otherwise, it is logged against the adapter's device object.

`Flags`

Not currently used. Must be zero.

`InterfaceRevision`

The revision number of this interface. Set to STOR_CURRENT_LOG_INTERFACE_REVISION to use the version of the interface that matches this structure. Both the constant and the data structure are defined in the same header file. This member is set to 0x00000100 for the first revision.

`LunId`

The SCSI logical unit number of the target device corresponding to this event.

`PathId`

The SCSI path/bus corresponding to this event.

`Size`

The size of this structure. Set before calling <a href="..\storport\nf-storport-storportlogsystemevent.md">StorPortLogSystemEvent</a>.

`StorportSpecificErrorCode`

If the <b>ErrorCode</b> value is specific to Storport and should be translated for use with IOLOGMSG.DLL, this value is set to <b>TRUE</b>. If the <b>ErrorCode</b> value is not specific to Storport and should be passed directly to the system event logging facility, this value is set to <b>FALSE</b>.

`StringCount`

The count of null-terminated Unicode strings contained in the StringList member. If no strings are to be written, this should be set to 0.

`StringList`

The list of null-terminated Unicode strings to be appended to the log entry for use in string substitution. These strings are substituted for the place holders "%2" through "%n" in the log message text when the log entry is being displayed. This list consists of an array of pointers to the null-terminated Unicode strings. StringCount contains the count of string pointers in this array, so no list termination entry is needed. If no strings are to be written, StringCount should be set to 0, and this field is ignored.

`TargetId`

The SCSI target controller or device on the bus corresponding to this event.

`UniqueId`

Specifies a unique identifier associated with the ErrorCode. Often this is used as a location code, referencing the location in the miniport that triggered the event. This value is passed directly to the event logging facility.

## Remarks
Although <a href="..\storport\nf-storport-storportlogerror.md">StorPortLogError</a> uses <b>PathId</b>, <b>TargetId</b>, and <b>LunId</b> values that are 8bits wide, for <a href="..\storport\nf-storport-storportlogsystemevent.md">StorPortLogSystemEvent</a> they are 32bits wide. The combined size of the miniport driver's dump data and string areas cannot exceed 150 bytes. This restriction is due to the &lt; 255 byte limit that the kernel enforces on the event log entries.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | storport.h (include Storport.h) |

## See Also

<a href="..\storport\nf-storport-storportlogsystemevent.md">StorPortLogSystemEvent</a>

<a href="..\storport\ne-storport-_stor_event_association_enum.md">STOR_EVENT_ASSOCIATION_ENUM</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STOR_LOG_EVENT_DETAILS structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>