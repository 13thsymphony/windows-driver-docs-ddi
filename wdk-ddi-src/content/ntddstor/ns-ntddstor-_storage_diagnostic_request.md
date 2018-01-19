---
UID : NS:ntddstor._STORAGE_DIAGNOSTIC_REQUEST
title : _STORAGE_DIAGNOSTIC_REQUEST
author : windows-driver-content
description : Describes a diagnostic request about the storage driver stack. The STORAGE_DIAGNOSTIC_REQUEST structure is provided in the input buffer of an IOCTL_STORAGE_DIAGNOSTIC request.
old-location : storage\storage_diagnostic_request.htm
old-project : storage
ms.assetid : BAC83B5C-4F14-430D-9CEF-46812FC4DFED
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : _STORAGE_DIAGNOSTIC_REQUEST, *PSTORAGE_DIAGNOSTIC_REQUEST, STORAGE_DIAGNOSTIC_REQUEST
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ntddstor.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Available starting with Windows 10, version 1709.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : STORAGE_DIAGNOSTIC_REQUEST
req.alt-loc : ntddstor.h
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
req.typenames : "*PSTORAGE_DIAGNOSTIC_REQUEST, STORAGE_DIAGNOSTIC_REQUEST"
---

# _STORAGE_DIAGNOSTIC_REQUEST structure
Describes  a diagnostic request about the storage driver stack. The <b>STORAGE_DIAGNOSTIC_REQUEST</b> structure is provided in the input buffer of an  <a href="https://msdn.microsoft.com/5F71CCBE-F93F-4DCD-A673-1D6DE49C7400">IOCTL_STORAGE_DIAGNOSTIC</a> request.

## Syntax
````
typedef struct _STORAGE_DIAGNOSTIC_REQUEST {
  ULONG                           Version;
  ULONG                           Size;
  ULONG                           Reserved;
   STORAGE_DIAGNOSTIC_TARGET_TYPE TargetType;
  STORAGE_DIAGNOSTIC_LEVEL        Level;
} STORAGE_DIAGNOSTIC_REQUEST, *PSTORAGE_DIAGNOSTIC_REQUEST;
````

## Members

        
            `Level`

            Specifies the Diagnostic level. See definitions for <a href="..\ntddstor\ne-ntddstor-_storage_diagnostic_level.md">STORAGE_DIAGNOSTIC_LEVEL</a>.
        
            `Reserved`

            Reserved for future use.
        
            `Size`

            Specifies the whole size of the structure and the associated data buffer.
        
            `TargetType`

            Specifies the request target type. See definitions for <a href="..\ntddstor\ne-ntddstor-_storage_diagnostic_target_type.md">STORAGE_DIAGNOSTIC_TARGET_TYPE</a>.
        
            `Version`

            Version of this structure.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddstor.h |

    ## See Also

        <dl>
<dt>
<a href="https://msdn.microsoft.com/5F71CCBE-F93F-4DCD-A673-1D6DE49C7400">IOCTL_STORAGE_DIAGNOSTIC</a>
</dt>
<dt>
<a href="..\ntddstor\ns-ntddstor-_storage_diagnostic_data.md">STORAGE_DIAGNOSTIC_DATA</a>
</dt>
<dt>
<a href="..\ntddstor\ne-ntddstor-_storage_diagnostic_level.md">STORAGE_DIAGNOSTIC_LEVEL</a>
</dt>
<dt>
<a href="..\ntddstor\ne-ntddstor-_storage_diagnostic_target_type.md">STORAGE_DIAGNOSTIC_TARGET_TYPE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STORAGE_DIAGNOSTIC_REQUEST structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>