---
UID: NE:wdm._RESOURCEMANAGER_INFORMATION_CLASS
title: "_RESOURCEMANAGER_INFORMATION_CLASS"
author: windows-driver-content
description: The RESOURCEMANAGER_INFORMATION_CLASS enumeration identifies the type of information that the ZwQueryInformationResourceManager routine can retrieve for a resource manager object.
old-location: kernel\resourcemanager_information_class.htm
old-project: kernel
ms.assetid: 5ffaad89-b3c0-4fe6-bc2c-2b1f3b1bcfd2
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RESOURCEMANAGER_INFORMATION_CLASS, RESOURCEMANAGER_INFORMATION_CLASS enumeration [Kernel-Mode Driver Architecture], ResourceManagerBasicInformation, ResourceManagerCompletionInformation, _RESOURCEMANAGER_INFORMATION_CLASS, kernel.resourcemanager_information_class, ktm_ref_72b34c92-3548-4148-94c2-49f4a66ad4bf.xml, wdm/RESOURCEMANAGER_INFORMATION_CLASS, wdm/ResourceManagerBasicInformation, wdm/ResourceManagerCompletionInformation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later operating system versions.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	RESOURCEMANAGER_INFORMATION_CLASS
product:
- Windows
targetos: Windows
req.typenames: RESOURCEMANAGER_INFORMATION_CLASS
req.product: Windows 10 or later.
---

# _RESOURCEMANAGER_INFORMATION_CLASS Enumeration
The <b>RESOURCEMANAGER_INFORMATION_CLASS</b> enumeration identifies the type of information that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567054">ZwQueryInformationResourceManager</a> routine can retrieve for a <a href="https://msdn.microsoft.com/b44f2035-ee9f-453b-b12d-89ca36a8b280">resource manager object</a>.

## Syntax
```
typedef enum _RESOURCEMANAGER_INFORMATION_CLASS {
  ResourceManagerBasicInformation       ,
  ResourceManagerCompletionInformation
} RESOURCEMANAGER_INFORMATION_CLASS;
```

## Constants

<table>
            
                <tr>
                    <td>ResourceManagerBasicInformation</td>
                    <td>Information about a resource manager object is stored in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561084">RESOURCEMANAGER_BASIC_INFORMATION</a> structure.</td>
                </tr>
            
                <tr>
                    <td>ResourceManagerCompletionInformation</td>
                    <td>Information about a resource manager object is stored in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561088">RESOURCEMANAGER_COMPLETION_INFORMATION</a> structure.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later operating system versions. Available in Windows Vista and later operating system versions. |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561084">RESOURCEMANAGER_BASIC_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561088">RESOURCEMANAGER_COMPLETION_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567054">ZwQueryInformationResourceManager</a>