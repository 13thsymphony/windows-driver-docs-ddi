---
UID: NS:netdispumdddi.MIRACAST_STATISTIC_DATA
title: MIRACAST_STATISTIC_DATA
author: windows-driver-content
description: Contains Miracast statistics data that the user-mode display driver reports to the operating system.
old-location: display\miracast_statistic_data.htm
old-project: display
ms.assetid: 94D5C260-4076-4DB7-8ED3-E0549A872FEE
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.miracast_statistic_data, MIRACAST_STATISTIC_DATA, netdispumdddi/MIRACAST_STATISTIC_DATA, MIRACAST_STATISTIC_DATA structure [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: netdispumdddi.h
req.include-header: Netdispumdddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	Netdispumdddi.h
apiname:
-	MIRACAST_STATISTIC_DATA
product: Windows
targetos: Windows
req.typenames: MIRACAST_STATISTIC_DATA
---

# MIRACAST_STATISTIC_DATA structure
Contains Miracast statistics data that the user-mode display driver reports to the operating system.

## Syntax
````
typedef struct {
  MIRACAST_STATISTIC_TYPE StatisticType;
  union {
    struct {
      MIRACAST_CHUNK_INFO ChunkInfo;
    } EncodeComplete;
    struct {
      MIRACAST_CHUNK_ID ChunkId;
    } ChunkSent;
    struct {
      MIRACAST_PROTOCOL_EVENT Event;
    } ProtocolEvent;
  };
} MIRACAST_STATISTIC_DATA;
````

## Members


`StatisticType`

The type of statistics data from the <a href="..\netdispumdddi\ne-netdispumdddi-miracast_statistic_type.md">MIRACAST_STATISTIC_TYPE</a> enumeration.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows 8.1 |
| **Header** | netdispumdddi.h (include Netdispumdddi.h) |

## See Also

<a href="..\netdispumdddi\ns-netdispumdddi-miracast_chunk_id.md">MIRACAST_CHUNK_ID</a>



<a href="..\netdispumdddi\ne-netdispumdddi-miracast_statistic_type.md">MIRACAST_STATISTIC_TYPE</a>



<a href="..\netdispumdddi\ns-netdispumdddi-miracast_chunk_info.md">MIRACAST_CHUNK_INFO</a>



<a href="..\netdispumdddi\ne-netdispumdddi-miracast_protocol_event.md">MIRACAST_PROTOCOL_EVENT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20MIRACAST_STATISTIC_DATA structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>