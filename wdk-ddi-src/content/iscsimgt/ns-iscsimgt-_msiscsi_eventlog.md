---
UID: NS:iscsimgt._MSiSCSI_Eventlog
title: "_MSiSCSI_Eventlog"
author: windows-driver-content
description: This MSiSCSI_EventLog method is used to log any messages to the event log.
old-location: storage\msiscsi_eventlog.htm
old-project: storage
ms.assetid: a31a8688-6002-4ad7-b135-0a8111e2c849
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.msiscsi_eventlog, MSiSCSI_EventLog, iscsimgt/MSiSCSI_EventLog, iscsimgt/PMSiSCSI_EventLog, *PMSiSCSI_Eventlog, _MSiSCSI_Eventlog, PMSiSCSI_EventLog structure pointer [Storage Devices], PMSiSCSI_EventLog, MSiSCSI_EventLog structure [Storage Devices], structs-iSCSI_d2419ba1-4f36-42c6-8a21-164dadb50263.xml, MSiSCSI_Eventlog
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsimgt.h
req.include-header: Iscsimgt.h
req.target-type: Windows
req.target-min-winverclnt: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Iscsimgt.h
apiname:
-	MSiSCSI_EventLog
product: Windows
targetos: Windows
req.typenames: MSiSCSI_Eventlog, *PMSiSCSI_Eventlog
---

# _MSiSCSI_Eventlog structure
This MSiSCSI_EventLog method is used to log any messages to the event log.

## Syntax
````
typedef struct _MSiSCSI_EventLog {
  ULONG Type;
  ULONG LogToEventLog;
  ULONG Size;
  UCHAR AdditionalData[1];
} MSiSCSI_EventLog, *PMSiSCSI_EventLog;
````

## Members


`AdditionalData`



`LogToEventlog`



`Size`

This specifies the size of the Additional Data field.

`Type`

This specifies the EVENTLOG_MESSAGE_QUALIFIERS type of event log message.

## Remarks
We recommend that you implement this class.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iscsimgt.h (include Iscsimgt.h) |