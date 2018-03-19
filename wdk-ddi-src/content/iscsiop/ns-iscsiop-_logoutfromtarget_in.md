---
UID: NS:iscsiop._LogoutFromTarget_IN
title: "_LogoutFromTarget_IN"
author: windows-driver-content
description: The LogoutFromTarget_IN structure holds the input data for the LogoutFromTarget method, which is used to log out from an iSCSI target.
old-location: storage\logoutfromtarget_in.htm
old-project: storage
ms.assetid: a52d5995-1fb7-4b73-9d3f-c945e7219a49
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PLogoutFromTarget_IN, LogoutFromTarget_IN, LogoutFromTarget_IN structure [Storage Devices], PLogoutFromTarget_IN, PLogoutFromTarget_IN structure pointer [Storage Devices], _LogoutFromTarget_IN, iscsiop/LogoutFromTarget_IN, iscsiop/PLogoutFromTarget_IN, storage.logoutfromtarget_in, structs-iSCSI_759c2265-5518-4f45-8737-5cdfa4d73170.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsiop.h
req.include-header: Iscsiop.h
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
-	iscsiop.h
api_name:
-	LogoutFromTarget_IN
product: Windows
targetos: Windows
req.typenames: LogoutFromTarget_IN, *PLogoutFromTarget_IN
---

# _LogoutFromTarget_IN structure
The LogoutFromTarget_IN structure holds the input data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561602">LogoutFromTarget</a> method, which is used to log out from an iSCSI target.

## Syntax
````
typedef struct _LogoutFromTarget_IN {
  ULONGLONG UniqueSessionId;
} LogoutFromTarget_IN, *PLogoutFromTarget_IN;
````

## Members


`UniqueSessionId`

A 64-bit integer that uniquely identifies the session. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a> methods both return this value in the <i>UniqueSessionId</i> parameter. Do not confuse this value with the values in the ISID and TSID members.

## Remarks
You must implement this method.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iscsiop.h (include Iscsiop.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563091">MSiSCSI_Operations WMI Class</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a>



<a href="..\iscsiop\ns-iscsiop-_logoutfromtarget_out.md">LogoutFromTarget_OUT</a>