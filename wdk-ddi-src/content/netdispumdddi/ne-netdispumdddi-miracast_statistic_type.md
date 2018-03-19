---
UID: NE:netdispumdddi.MIRACAST_STATISTIC_TYPE
title: MIRACAST_STATISTIC_TYPE
author: windows-driver-content
description: Specifies types of Miracast statistics data that the user-mode display driver generates.
old-location: display\miracast_statistic_type.htm
old-project: display
ms.assetid: 1062e816-f10d-42eb-b0b5-4596b7b543f9
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: MIRACAST_STATISTIC_TYPE, MIRACAST_STATISTIC_TYPE enumeration [Display Devices], MIRACAST_STATISTIC_TYPE_CHUNK_PROCESSING_COMPLETE, MIRACAST_STATISTIC_TYPE_CHUNK_SENT, MIRACAST_STATISTIC_TYPE_EVENT, MIRACAST_STATISTIC_TYPE_FORCE_UINT32, display.miracast_statistic_type, netdispumdddi/MIRACAST_STATISTIC_TYPE, netdispumdddi/MIRACAST_STATISTIC_TYPE_CHUNK_PROCESSING_COMPLETE, netdispumdddi/MIRACAST_STATISTIC_TYPE_CHUNK_SENT, netdispumdddi/MIRACAST_STATISTIC_TYPE_EVENT, netdispumdddi/MIRACAST_STATISTIC_TYPE_FORCE_UINT32
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Netdispumdddi.h
api_name:
-	MIRACAST_STATISTIC_TYPE
product: Windows
targetos: Windows
req.typenames: MIRACAST_STATISTIC_TYPE
---

# MIRACAST_STATISTIC_TYPE Enumeration
Specifies  types of Miracast statistics data that the user-mode display driver generates.

## Syntax
````
typedef enum  { 
  MIRACAST_STATISTIC_TYPE_CHUNK_PROCESSING_COMPLETE  = 0,
  MIRACAST_STATISTIC_TYPE_CHUNK_SENT                 = 1,
  MIRACAST_STATISTIC_TYPE_EVENT                      = 2,
  MIRACAST_STATISTIC_TYPE_FORCE_UINT32               = 0xffffffff
} MIRACAST_STATISTIC_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>MIRACAST_STATISTIC_TYPE_CHUNK_PROCESSING_COMPLETE</td>
                    <td>The user-mode display driver has completed its processing of the encode chunk.</td>
                </tr>
            
                <tr>
                    <td>MIRACAST_STATISTIC_TYPE_CHUNK_SENT</td>
                    <td>The driver has successfully sent the encode chunk to the network.</td>
                </tr>
            
                <tr>
                    <td>MIRACAST_STATISTIC_TYPE_EVENT</td>
                    <td>Used by the user-mode display driver to report certain Miracast protocol events to the operating system for diagnostic purposes.</td>
                </tr>
            
                <tr>
                    <td>MIRACAST_STATISTIC_TYPE_FORCE_UINT32</td>
                    <td>Forces this enumeration to compile to 32 bits in size. Without this value, some compilers would allow this enumeration to compile to a size other than 32 bits. You should not use this value.</td>
                </tr>
</table>

## Remarks

For more info on how the driver uses these enumeration values with reporting calls to the <a href="..\netdispumdddi\nc-netdispumdddi-pfn_report_statistic.md">ReportStatistic</a> callback function, see <a href="https://msdn.microsoft.com/E1CE637F-42ED-4BEB-A2FF-04B4B88469DC">Reporting Miracast encode chunks and statistics</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows 8.1 |
| **Header** | netdispumdddi.h (include Netdispumdddi.h) |

## See Also

<a href="..\netdispumdddi\nc-netdispumdddi-pfn_report_statistic.md">ReportStatistic</a>