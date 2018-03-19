---
UID: NS:ntifs._TOKEN_USER
title: "_TOKEN_USER"
author: windows-driver-content
description: TOKEN_USER identifies the user associated with an access token.
old-location: ifsk\token_user.htm
old-project: ifsk
ms.assetid: 0168f1ea-d2b0-4343-b6e7-c6cc97214201
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PTOKEN_USER, PTOKEN_USER, PTOKEN_USER structure pointer [Installable File System Drivers], TOKEN_USER, TOKEN_USER structure [Installable File System Drivers], _TOKEN_USER, ifsk.token_user, ntifs/PTOKEN_USER, ntifs/TOKEN_USER, securitystructures_0e952505-1e51-463e-ba92-c6995e6f107a.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h
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
-	TOKEN_USER
product: Windows
targetos: Windows
req.typenames: TOKEN_USER, *PTOKEN_USER
---

# _TOKEN_USER structure
TOKEN_USER identifies the user associated with an access token.

## Syntax
````
typedef struct _TOKEN_USER {
  SID_AND_ATTRIBUTES User;
} TOKEN_USER, *PTOKEN_USER;
````

## Members


`User`

Specifies an SID_AND_ATTRIBUTES structure representing the user associated with the access token.

## Remarks
Unlike TOKEN_GROUPS structures, TOKEN_USER structures cannot be passed to <b>SeFilterToken</b>. Nevertheless, it is possible to designate a user SID as a deny-only SID by specifying the user SID as one of the group SIDs in the TOKEN_GROUPS structure passed to <b>SeFilterToken</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntifs.h (include Ntifs.h) |

## See Also

<a href="..\ntifs\ne-ntifs-_token_information_class.md">TOKEN_INFORMATION_CLASS</a>



<a href="..\ntifs\ns-ntifs-_token_groups.md">TOKEN_GROUPS</a>



<a href="..\ntifs\ns-ntifs-_sid_and_attributes.md">SID_AND_ATTRIBUTES</a>



<a href="..\ntifs\nf-ntifs-sefiltertoken.md">SeFilterToken</a>



<a href="..\ntifs\nf-ntifs-zwsetinformationtoken.md">ZwSetInformationToken</a>



<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>



<a href="..\ntifs\nf-ntifs-sequeryinformationtoken.md">SeQueryInformationToken</a>



<a href="..\ntifs\nf-ntifs-zwqueryinformationtoken.md">ZwQueryInformationToken</a>