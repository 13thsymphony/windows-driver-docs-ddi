---
UID: NS:ntifs._TOKEN_OWNER
title: "_TOKEN_OWNER"
author: windows-driver-content
description: TOKEN_OWNER contains the default owner security identifier (SID) that will be applied to newly created objects.
old-location: ifsk\token_owner.htm
old-project: ifsk
ms.assetid: 25f4a9c2-7146-422c-bd55-2520e7d8619b
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PTOKEN_OWNER, PTOKEN_OWNER, PTOKEN_OWNER structure pointer [Installable File System Drivers], TOKEN_OWNER, TOKEN_OWNER structure [Installable File System Drivers], _TOKEN_OWNER, ifsk.token_owner, ntifs/PTOKEN_OWNER, ntifs/TOKEN_OWNER, securitystructures_1be454bb-1b55-4fe5-bdbb-85bfcf9dc9c8.xml"
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
-	TOKEN_OWNER
product: Windows
targetos: Windows
req.typenames: TOKEN_OWNER, *PTOKEN_OWNER
---

# _TOKEN_OWNER structure
TOKEN_OWNER contains the default owner security identifier (SID) that will be applied to newly created objects.

## Syntax
````
typedef struct _TOKEN_OWNER {
  PSID Owner;
} TOKEN_OWNER, *PTOKEN_OWNER;
````

## Members


`Owner`

Pointer to a SID structure representing a user that will become the default owner of any objects created by a process using this access token. The SID must be one of the user or group SIDs already in the token.

## Remarks
Whenever the process using this access token creates a new object, the object is owned by the <b>Owner</b>, unless the process provides a security descriptor for the object. 

The <b>Owner</b> must be a legally formed SID and must match one of the user or group SIDs already in the token. 

If it is a group SID, the <b>Owner</b> must match a group SID in the token, where the attributes on the group must include SE_GROUP_OWNER and must not include SE_GROUP_USE_FOR_DENY_ONLY.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntifs.h (include Ntifs.h) |

## See Also

<a href="..\ntifs\ne-ntifs-_token_information_class.md">TOKEN_INFORMATION_CLASS</a>



<a href="..\ntifs\nf-ntifs-zwsetinformationtoken.md">ZwSetInformationToken</a>



<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>



<a href="..\ntifs\nf-ntifs-sequeryinformationtoken.md">SeQueryInformationToken</a>



<a href="..\ntifs\nf-ntifs-zwqueryinformationtoken.md">ZwQueryInformationToken</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20TOKEN_OWNER structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>