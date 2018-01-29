---
UID : NS:ntifs._SYSTEM_RESOURCE_ATTRIBUTE_ACE
title : _SYSTEM_RESOURCE_ATTRIBUTE_ACE
author : windows-driver-content
description : The SYSTEM_RESOURCE_ATTRIBUTE_ACE structure defines an access-control entry (ACE) for the system access-control list (ACL) specifying what rights a particular claim has to a resource.
old-location : ifsk\system_resource_attribute_ace.htm
old-project : ifsk
ms.assetid : E4A6A738-F7AB-4EA2-8CC6-E1F595F35870
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : PSYSTEM_RESOURCE_ATTRIBUTE_ACE, ifsk.system_resource_attribute_ace, PSYSTEM_RESOURCE_ATTRIBUTE_ACE structure pointer [Installable File System Drivers], _SYSTEM_RESOURCE_ATTRIBUTE_ACE, *PSYSTEM_RESOURCE_ATTRIBUTE_ACE, SYSTEM_RESOURCE_ATTRIBUTE_ACE structure [Installable File System Drivers], ntifs/PSYSTEM_RESOURCE_ATTRIBUTE_ACE, ntifs/SYSTEM_RESOURCE_ATTRIBUTE_ACE, SYSTEM_RESOURCE_ATTRIBUTE_ACE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ntifs.h
req.include-header : Ntifs.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PSYSTEM_RESOURCE_ATTRIBUTE_ACE, SYSTEM_RESOURCE_ATTRIBUTE_ACE"
---

# _SYSTEM_RESOURCE_ATTRIBUTE_ACE structure
The SYSTEM_RESOURCE_ATTRIBUTE_ACE structure defines an access-control entry (ACE) for the system access-control list (ACL) specifying what rights a particular claim has to a resource. A resource attribute ACE causes an audit message to be logged when an atrempt to gain access to resource based on a supported claim occurs.

## Syntax
````
typedef struct _SYSTEM_RESOURCE_ATTRIBUTE_ACE {
  ACE_HEADER  Header;
  ACCESS_MASK Mask;
  ULONG       SidStart;
} SYSTEM_RESOURCE_ATTRIBUTE_ACE, *PSYSTEM_RESOURCE_ATTRIBUTE_ACE;
````

## Members


`Header`

Specifies an ACE_HEADER structure.

`Mask`

Specifies an ACCESS_MASK structure that specifies access rights for a claim to a resource.

`SidStart`

Specifies a SID. This is set to the Everyone, or S-1-1-0, SID.

## Remarks
Following the <b>SidStart</b> member begins a <b>CLAIM_SECURITY_ATTRIBUTE_RELATIVE_V1</b> structure which describes a supported claim.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntifs.h (include Ntifs.h) |

## See Also

<a href="..\ntifs\ns-ntifs-_ace_header.md">ACE_HEADER</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>

<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff538844">ACE</a>

<a href="..\wdm\ns-wdm-_acl.md">ACL</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20SYSTEM_RESOURCE_ATTRIBUTE_ACE structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>