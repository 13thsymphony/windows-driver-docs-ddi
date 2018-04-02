---
UID: NS:1394._GET_LOCAL_HOST_INFO3
title: "_GET_LOCAL_HOST_INFO3"
author: windows-driver-content
description: The GET_LOCAL_HOST_INFO3 structure contains the data returned by a REQUEST_GET_LOCAL_HOST_INFO request using u.GetLocalHostInformation.nLevel = GET_POWER_SUPPLIED.
old-location: ieee\get_local_host_info3.htm
old-project: IEEE
ms.assetid: 49c24328-dfd9-4d4d-a40f-a375f1384a5c
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PGET_LOCAL_HOST_INFO3, 1394/GET_LOCAL_HOST_INFO3, 1394/PGET_LOCAL_HOST_INFO3, 1394stct_327b0f83-9367-41ef-8b04-a07338f8725b.xml, GET_LOCAL_HOST_INFO3, GET_LOCAL_HOST_INFO3 structure [Buses], IEEE.get_local_host_info3, PGET_LOCAL_HOST_INFO3, PGET_LOCAL_HOST_INFO3 structure pointer [Buses], _GET_LOCAL_HOST_INFO3"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 1394.h
req.include-header: 1394.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	1394.h
api_name:
-	GET_LOCAL_HOST_INFO3
product:
- Windows
targetos: Windows
req.typenames: GET_LOCAL_HOST_INFO3, *PGET_LOCAL_HOST_INFO3
---

# _GET_LOCAL_HOST_INFO3 structure
The GET_LOCAL_HOST_INFO3 structure contains the data returned by a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537644">REQUEST_GET_LOCAL_HOST_INFO</a> request using <b>u.GetLocalHostInformation.nLevel</b> = GET_POWER_SUPPLIED.

## Syntax
```
typedef struct _GET_LOCAL_HOST_INFO3 {
  ULONG deciWattsSupplied;
  ULONG Voltage;
} *PGET_LOCAL_HOST_INFO3, GET_LOCAL_HOST_INFO3;
```

## Members


`deciWattsSupplied`

Specifies the wattage supplied, in tenths of a watt.

`Voltage`

Specifies the voltage, in tenths of a volt.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | 1394.h (include 1394.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537644">REQUEST_GET_LOCAL_HOST_INFO</a>