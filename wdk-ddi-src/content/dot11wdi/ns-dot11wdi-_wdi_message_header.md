---
UID: NS:dot11wdi._WDI_MESSAGE_HEADER
title: "_WDI_MESSAGE_HEADER"
author: windows-driver-content
description: The WDI_MESSAGE_HEADER structure defines the WDI message header. All WDI command messages must start with this header.
old-location: netvista\wdi_message_header.htm
old-project: netvista
ms.assetid: 69c3ebf5-8805-47d0-a507-d2e3e1d1b0df
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PWDI_MESSAGE_HEADER, PWDI_MESSAGE_HEADER, PWDI_MESSAGE_HEADER structure pointer [Network Drivers Starting with Windows Vista], WDI_MESSAGE_HEADER, WDI_MESSAGE_HEADER structure [Network Drivers Starting with Windows Vista], _WDI_MESSAGE_HEADER, dot11wdi/PWDI_MESSAGE_HEADER, dot11wdi/WDI_MESSAGE_HEADER, netvista.wdi_message_header"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dot11wdi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	dot11wdi.h
api_name:
-	WDI_MESSAGE_HEADER
product: Windows
targetos: Windows
req.typenames: WDI_MESSAGE_HEADER, *PWDI_MESSAGE_HEADER
---

# _WDI_MESSAGE_HEADER structure
The 
  WDI_MESSAGE_HEADER structure defines the WDI message header. All WDI  command messages must start with this header.

## Syntax
````
typedef struct _WDI_MESSAGE_HEADER {
  UINT16      PortId;
  UINT16      Reserved;
  NDIS_STATUS Status;
  UINT32      TransactionId;
  UINT32      IhvSpecificId;
} WDI_MESSAGE_HEADER, *PWDI_MESSAGE_HEADER;
````

## Members


`IhvSpecificId`

Specifies an IHV-specific ID for this message. This can be used by IHVs for debugging purpose.

`PortId`

Specifies the identifier for the Port object that this command is targeted for. For commands on the Adapter object, this is 0xFFFF.

`Reserved`

This member is reserved.

`Status`

Specifies the operation completion status for output messages. For input messages, this field is reserved.

`TransactionId`

Specifies the transaction ID. This value is used to match host-sent messages with function responses.  This value must be unique among all outstanding transactions.  For notifications, the TransactionId must be set to 0 by the function.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | dot11wdi.h |