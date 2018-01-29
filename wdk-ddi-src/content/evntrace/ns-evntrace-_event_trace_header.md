---
UID : NS:evntrace._EVENT_TRACE_HEADER
title : _EVENT_TRACE_HEADER
author : windows-driver-content
description : The EVENT_TRACE_HEADER structure is used to pass a WMI event to the WMI event logger.
old-location : kernel\event_trace_header.htm
old-project : kernel
ms.assetid : faddcf82-1025-458f-ab33-c96cd5699ca5
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : _EVENT_TRACE_HEADER, evntrace/PEVENT_TRACE_HEADER, PEVENT_TRACE_HEADER, kernel.event_trace_header, evntrace/EVENT_TRACE_HEADER, kstruct_a_9a7cc863-6913-427c-8756-4c62c20f5b60.xml, EVENT_TRACE_HEADER structure [Kernel-Mode Driver Architecture], *PEVENT_TRACE_HEADER, PEVENT_TRACE_HEADER structure pointer [Kernel-Mode Driver Architecture], EVENT_TRACE_HEADER
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : evntrace.h
req.include-header : Wdm.h, Ntddk.h
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
req.typenames : EVENT_TRACE_HEADER, *PEVENT_TRACE_HEADER
---

# _EVENT_TRACE_HEADER structure
The <b>EVENT_TRACE_HEADER</b> structure is used to pass a WMI event to the WMI event logger. It is overlaid on the <a href="..\wmistr\ns-wmistr-_wnode_header.md">WNODE_HEADER</a> portion of the <a href="..\wmistr\ns-wmistr-tagwnode_event_item.md">WNODE_EVENT_ITEM</a> passed to <a href="..\wdm\nf-wdm-iowmiwriteevent.md">IoWMIWriteEvent</a>. Information contained in the <b>EVENT_TRACE_HEADER</b> is written to the WMI log file.

## Syntax
````
typedef struct _EVENT_TRACE_HEADER {
  USHORT        Size;
  union {
    USHORT FieldTypeFlags;
    struct {
      UCHAR HeaderType;
      UCHAR MarkerFlags;
    };
  };
  union {
    ULONG  Version;
    struct {
      UCHAR  Type;
      UCHAR  Level;
      USHORT Version;
    } Class;
  };
  ULONG         ThreadId;
  ULONG         ProcessId;
  LARGE_INTEGER TimeStamp;
  union {
    GUID      Guid;
    ULONGLONG GuidPtr;
  };
  union {
    struct {
      ULONG KernelTime;
      ULONG UserTime;
    };
    ULONG64 ProcessorTime;
    struct {
      ULONG ClientContext;
      ULONG Flags;
    };
  };
} EVENT_TRACE_HEADER, *PEVENT_TRACE_HEADER;
````

## Members


`DUMMYUNIONNAME`



`DUMMYUNIONNAME2`



`DUMMYUNIONNAME3`



`DUMMYUNIONNAME4`



`ProcessId`

Process identifier.

`Size`

Specifies the size, in bytes, of the buffer that is allocated to hold event tracing information. The value that is specified must include both the size of the <b>EVENT_TRACE_HEADER</b> structure and the size of any driver-specific data. (<b>EVENT_TRACE_HEADER</b> is overlaid on a <a href="..\wmistr\ns-wmistr-_wnode_header.md">WNODE_HEADER</a> structure, but the <b>Size</b> member of <b>EVENT_TRACE_HEADER</b> and the <b>BufferSize</b> member of <b>WNODE_HEADER</b> do not specify the same size. Do not use the <b>BufferSize</b> member of <b>WNODE_HEADER</b> to set the <b>Size</b> member.)

`ThreadId`

Thread identifier.

`TimeStamp`

The time at which the driver event occurred. This time value is expressed in absolute system time format. Absolute system time is the number of 100-nanosecond intervals since the start of the year 1601 in the Gregorian calendar. If the WNODE_FLAG_USE_TIMESTAMP is set in <b>Flags,</b> the system logger will leave the value of <b>TimeStamp</b> unchanged. Otherwise, the system logger will set the value of <b>TimeStamp</b> at the time it receives the event. A driver can call <b>KeQuerySystemTime</b> to set the value of <b>TimeStamp</b>.

## Remarks
A driver that supports trace events will use this structure to report events to the WMI event logger. Trace events should not be reported until the driver receives a request to enable events and the control GUID is one the driver supports. The driver should initialize an <b>EVENT_TRACE_HEADER</b> structure, fill in any user-defined event data at the end, and pass a pointer to the <b>EVENT_TRACE_HEADER</b> to <b>IoWMIWriteEvent</b>. The driver should continue reporting trace events until it receives a request to disable the control GUID for the trace events.

If the driver does not specify the WNODE_FLAG_USE_MOF_PTR flag in the <b>Flags</b> member of <b>EVENT_TRACE_HEADER</b>, the <b>EVENT_TRACE_HEADER</b> structure is followed in memory by event-specific data. In this case, the <b>Size</b> member must be <b>sizeof</b>(<b>EVENT_TRACE_HEADER</b>) plus the size of the event-specific data. 

If the driver does specify the WNODE_FLAG_USE_MOF_PTR flag, the <b>EVENT_TRACE_HEADER</b> structure is followed in memory by an array of <b>MOF_FIELD</b> structures (which are defined in Evntrace.h) that contain pointers to the data and sizes rather than the event tracing data itself. In this case, the <b>Size</b> member must be <b>sizeof</b>(<b>EVENT_TRACE_HEADER</b>) plus the size of the array of <b>MOF_FIELD</b> structures.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | evntrace.h (include Wdm.h, Ntddk.h) |

## See Also

<a href="..\wdm\nf-wdm-iowmiwriteevent.md">IoWMIWriteEvent</a>

<a href="..\wmistr\ns-wmistr-tagwnode_event_item.md">WNODE_EVENT_ITEM</a>

<a href="..\wmistr\ns-wmistr-_wnode_header.md">WNODE_HEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20EVENT_TRACE_HEADER structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>