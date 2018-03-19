---
UID: NS:ntifs._SE_TOKEN_USER
title: "_SE_TOKEN_USER"
author: windows-driver-content
description: The SE_TOKEN_USER structure holds the maximum-sized valid user SID that can be returned by SeQueryInformationToken, GetTokenInformation, or ZwQueryInformationToken with the TokenUser information class. This structure is suitable for stack allocation.
old-location: ifsk\se_token_user.htm
old-project: ifsk
ms.assetid: 3B870461-0C5D-46DF-A850-EB796AE5A4CB
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: PSE_TOKEN_USER, PSE_TOKEN_USER structure pointer [Installable File System Drivers], SE_TOKEN_USER, SE_TOKEN_USER structure [Installable File System Drivers], _SE_TOKEN_USER, ifsk.se_token_user, ntifs/PSE_TOKEN_USER, ntifs/SE_TOKEN_USER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: 
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
-	ntifs.h
api_name:
-	SE_TOKEN_USER
product: Windows
targetos: Windows
req.typenames: SE_TOKEN_USER, PSE_TOKEN_USER
---

# _SE_TOKEN_USER structure
The <b>SE_TOKEN_USER</b> structure holds the maximum-sized valid user SID that can be returned by <a href="..\ntifs\nf-ntifs-sequeryinformationtoken.md">SeQueryInformationToken</a>, <a href="https://msdn.microsoft.com/e94de19c-de12-40fb-a72c-060f7ad12f75">GetTokenInformation</a>, or <a href="..\ntifs\nf-ntifs-zwqueryinformationtoken.md">ZwQueryInformationToken</a> with the TokenUser information class. This structure is suitable for stack allocation.

## Syntax
````
typedef struct _SE_TOKEN_USER {
  union {
    TOKEN_USER         TokenUser;
    SID_AND_ATTRIBUTES User;
  };
  union {
    SID   Sid;
    UCHAR Buffer[SECURITY_MAX_SID_SIZE];
  };
} SE_TOKEN_USER, *PSE_TOKEN_USER;
````

## Members


`DUMMYUNIONNAME`



`DUMMYUNIONNAME2`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntifs.h |

## See Also

<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>



<a href="..\ntifs\ns-ntifs-_token_user.md">TOKEN_USER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556742">SID_AND_ATTRIBUTES</a>