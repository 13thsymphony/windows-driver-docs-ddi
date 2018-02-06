---
UID: NS:wdm._SECURITY_SUBJECT_CONTEXT
title: "_SECURITY_SUBJECT_CONTEXT"
author: windows-driver-content
description: The SECURITY_SUBJECT_CONTEXT structure is used to capture subject security context for access validation and auditing.
old-location: ifsk\security_subject_context.htm
old-project: ifsk
ms.assetid: c9879df5-38e9-4a9f-8196-8485e85b2933
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: PSECURITY_SUBJECT_CONTEXT structure pointer [Installable File System Drivers], securitystructures_e91a762f-82dc-4319-a479-8de15bce2bfd.xml, PSECURITY_SUBJECT_CONTEXT, ifsk.security_subject_context, wdm/PSECURITY_SUBJECT_CONTEXT, *PSECURITY_SUBJECT_CONTEXT, _SECURITY_SUBJECT_CONTEXT, wdm/SECURITY_SUBJECT_CONTEXT, SECURITY_SUBJECT_CONTEXT, SECURITY_SUBJECT_CONTEXT structure [Installable File System Drivers]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdm.h
apiname:
-	SECURITY_SUBJECT_CONTEXT
product: Windows
targetos: Windows
req.typenames: "*PSECURITY_SUBJECT_CONTEXT, SECURITY_SUBJECT_CONTEXT"
req.product: Windows 10 or later.
---

# _SECURITY_SUBJECT_CONTEXT structure
The SECURITY_SUBJECT_CONTEXT structure is used to capture subject security context for access validation and auditing.

Drivers are not to modify the SECURITY_SUBJECT_CONTEXT structure directly. To create and manipulate this structure, use the support routines listed in the <b>See Also</b> section. 

SECURITY_SUBJECT_CONTEXT

## Syntax
````
typedef struct _SECURITY_SUBJECT_CONTEXT {
  PACCESS_TOKEN                ClientToken;
  SECURITY_IMPERSONATION_LEVEL ImpersonationLevel;
  PACCESS_TOKEN                PrimaryToken;
  PVOID                        ProcessAuditId;
} SECURITY_SUBJECT_CONTEXT, *PSECURITY_SUBJECT_CONTEXT;
````

## Members


`ClientToken`



`ImpersonationLevel`



`PrimaryToken`



`ProcessAuditId`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wdm.h (include Wdm.h) |

## See Also

<a href="..\ntifs\nf-ntifs-seprivilegecheck.md">SePrivilegeCheck</a>

<a href="..\rxprocs\nf-rxprocs-fsrtlnotifyfullchangedirectory.md">FsRtlNotifyFullChangeDirectory</a>

<a href="..\wdm\nf-wdm-seaccesscheck.md">SeAccessCheck</a>

<a href="..\ntifs\nf-ntifs-seunlocksubjectcontext.md">SeUnlockSubjectContext</a>

<a href="..\ntifs\nf-ntifs-secapturesubjectcontext.md">SeCaptureSubjectContext</a>

<a href="..\wudfddi\ne-wudfddi-_security_impersonation_level.md">SECURITY_IMPERSONATION_LEVEL</a>

<a href="..\ntifs\nf-ntifs-secreateclientsecurityfromsubjectcontext.md">SeCreateClientSecurityFromSubjectContext</a>

<a href="..\ntifs\nf-ntifs-sereleasesubjectcontext.md">SeReleaseSubjectContext</a>

<a href="..\ntifs\nf-ntifs-sequerysubjectcontexttoken.md">SeQuerySubjectContextToken</a>

<a href="..\ntifs\nf-ntifs-selocksubjectcontext.md">SeLockSubjectContext</a>

<a href="..\wdm\nf-wdm-seassignsecurityex.md">SeAssignSecurityEx</a>

<a href="..\wdm\nf-wdm-seassignsecurity.md">SeAssignSecurity</a>

<a href="..\ntifs\nf-ntifs-sefiltertoken.md">SeFilterToken</a>

<a href="..\wdm\ns-wdm-_access_state.md">ACCESS_STATE</a>

<a href="..\ntifs\nf-ntifs-seauditingfileorglobalevents.md">SeAuditingFileOrGlobalEvents</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20SECURITY_SUBJECT_CONTEXT structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>