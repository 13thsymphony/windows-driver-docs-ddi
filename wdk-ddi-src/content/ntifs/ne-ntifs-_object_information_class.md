---
UID: NE:ntifs._OBJECT_INFORMATION_CLASS
title: "_OBJECT_INFORMATION_CLASS"
author: windows-driver-content
description: The OBJECT_INFORMATION_CLASS enumeration type represents the type of information to supply about an object.
old-location: ifsk\object_information_class.htm
old-project: ifsk
ms.assetid: fbcca01d-2dd6-405a-9ec2-709652e9dcd6
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: OBJECT_INFORMATION_CLASS enumeration [Installable File System Drivers], OBJECT_INFORMATION_CLASS, ObjectBasicInformation, ObjectTypeInformation, _OBJECT_INFORMATION_CLASS, ntifs/ObjectTypeInformation, ntifs/ObjectBasicInformation, ifsk.object_information_class, objectstructures_60aa943f-6a91-429d-8c9d-1554f1bcf03e.xml, ntifs/OBJECT_INFORMATION_CLASS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Microsoft Windows 2000.
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
-	ntifs.h
apiname:
-	OBJECT_INFORMATION_CLASS
product: Windows
targetos: Windows
req.typenames: OBJECT_INFORMATION_CLASS
---

# _OBJECT_INFORMATION_CLASS Enumeration
The OBJECT_INFORMATION_CLASS enumeration type represents the type of information to supply about an object.

## Syntax
````
typedef enum _OBJECT_INFORMATION_CLASS { 
  ObjectBasicInformation  = 0,
  ObjectTypeInformation   = 2
} OBJECT_INFORMATION_CLASS;
````

## Constants

<table>
            
                <tr>
                    <td>ObjectBasicInformation</td>
                    <td>A <a href="..\ntifs\ns-ntifs-_public_object_basic_information.md">PUBLIC_OBJECT_BASIC_INFORMATION</a> structure is supplied.</td>
                </tr>
            
                <tr>
                    <td>ObjectTypeInformation</td>
                    <td>A <a href="..\ntifs\ns-ntifs-__public_object_type_information.md">PUBLIC_OBJECT_TYPE_INFORMATION</a> structure is supplied.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Microsoft Windows 2000. Available starting with Microsoft Windows 2000. |
| **Header** | ntifs.h (include Ntifs.h, Fltkernel.h) |

    ## See Also

        <a href="..\ntifs\nf-ntifs-zwqueryobject.md">ZwQueryObject</a>



<a href="..\ntifs\ns-ntifs-__public_object_type_information.md">PUBLIC_OBJECT_TYPE_INFORMATION</a>



<a href="..\ntifs\ns-ntifs-_public_object_basic_information.md">PUBLIC_OBJECT_BASIC_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20OBJECT_INFORMATION_CLASS enumeration%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>