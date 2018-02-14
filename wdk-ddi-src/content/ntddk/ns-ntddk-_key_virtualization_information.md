---
UID: NS:ntddk._KEY_VIRTUALIZATION_INFORMATION
title: "_KEY_VIRTUALIZATION_INFORMATION"
author: windows-driver-content
description: The KEY_VIRTUALIZATION_INFORMATION structure defines the basic information that is available for a registry key or subkey.
old-location: kernel\key_virtualization_information.htm
old-project: kernel
ms.assetid: 128dd4ed-12c6-472a-b63c-d2d217b5c716
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: KEY_VIRTUALIZATION_INFORMATION structure [Kernel-Mode Driver Architecture], *PKEY_VIRTUALIZATION_INFORMATION, kstruct_c_00c77a09-ed8d-4a66-9b18-b971c9eab5ce.xml, KEY_VIRTUALIZATION_INFORMATION, PKEY_VIRTUALIZATION_INFORMATION, kernel.key_virtualization_information, PKEY_VIRTUALIZATION_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _KEY_VIRTUALIZATION_INFORMATION, ntddk/PKEY_VIRTUALIZATION_INFORMATION, ntddk/KEY_VIRTUALIZATION_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Available on Windows Vista and later versions of the Windows operating system.
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddk.h
apiname:
-	KEY_VIRTUALIZATION_INFORMATION
product: Windows
targetos: Windows
req.typenames: KEY_VIRTUALIZATION_INFORMATION, *PKEY_VIRTUALIZATION_INFORMATION
---

# _KEY_VIRTUALIZATION_INFORMATION structure
The <b>KEY_VIRTUALIZATION_INFORMATION</b> structure defines the basic information that is available for a registry key or subkey.

## Syntax
````
typedef struct _KEY_VIRTUALIZATION_INFORMATION {
  ULONG VirtualizationCandidate  :1;
  ULONG VirtualizationEnabled  :1;
  ULONG VirtualTarget  :1;
  ULONG VirtualStore  :1;
  ULONG VirtualSource  :1;
  ULONG Reserved  :27;
} KEY_VIRTUALIZATION_INFORMATION, *PKEY_VIRTUALIZATION_INFORMATION;
````

## Members


`Reserved`

This value is reserved for system use.

`VirtualizationCandidate`

Specifies whether the key is part of the virtualization namespace scope.

`VirtualizationEnabled`

Specifies whether virtualization is enabled on this key. This value can be set to 1 only if <b>VirtualizationCandidate</b> is 1.

`VirtualSource`

Specifies whether the key has ever been virtualized. This value can be set to 1 only if <b>VirtualizationCandidate</b> is 1.

`VirtualStore`

Specified whether the key is a part of the virtual store path.

`VirtualTarget`

Specifies whether the key is a virtual key. This value can be set to 1 only if <b>VirtualizationCandidate</b> and <b>VirtualizationEnabled</b> are both 0. This value is valid only on the virtual store key handles.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available on Windows Vista and later versions of the Windows operating system. Available on Windows Vista and later versions of the Windows operating system. |
| **Header** | ntddk.h (include Ntddk.h) |

## See Also

<a href="..\ntddk\ns-ntddk-_key_cached_information.md">KEY_CACHED_INFORMATION</a>



<a href="..\wdm\ns-wdm-_key_full_information.md">KEY_FULL_INFORMATION</a>



<a href="..\wdm\nf-wdm-zwenumeratekey.md">ZwEnumerateKey</a>



<a href="..\ntddk\ns-ntddk-_key_name_information.md">KEY_NAME_INFORMATION</a>



<a href="..\wdm\ns-wdm-_key_node_information.md">KEY_NODE_INFORMATION</a>



<a href="..\wdm\ns-wdm-_key_basic_information.md">KEY_BASIC_INFORMATION</a>



<a href="..\wdm\nf-wdm-zwquerykey.md">ZwQueryKey</a>



<a href="..\wdm\ne-wdm-_key_information_class.md">KEY_INFORMATION_CLASS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KEY_VIRTUALIZATION_INFORMATION structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>