---
UID : NS:wdm._REG_KEY_HANDLE_CLOSE_INFORMATION
title : _REG_KEY_HANDLE_CLOSE_INFORMATION
author : windows-driver-content
description : The REG_KEY_HANDLE_CLOSE_INFORMATION structure contains information about a registry key whose handle is about to be closed.
old-location : kernel\reg_key_handle_close_information.htm
old-project : kernel
ms.assetid : 023ca2d0-45a2-423e-bd88-e40792ef0e49
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : _REG_KEY_HANDLE_CLOSE_INFORMATION, *PREG_KEY_HANDLE_CLOSE_INFORMATION, REG_KEY_HANDLE_CLOSE_INFORMATION
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
req.target-type : Windows
req.target-min-winverclnt : Available on Microsoft Windows XP and later versions of the Windows operating system.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : REG_KEY_HANDLE_CLOSE_INFORMATION
req.alt-loc : Wdm.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL (see Remarks section)
req.typenames : "*PREG_KEY_HANDLE_CLOSE_INFORMATION, REG_KEY_HANDLE_CLOSE_INFORMATION"
req.product : Windows 10 or later.
---

# _REG_KEY_HANDLE_CLOSE_INFORMATION structure
The <b>REG_KEY_HANDLE_CLOSE_INFORMATION</b> structure contains information about a registry key whose handle is about to be closed.

## Syntax
````
typedef struct _REG_KEY_HANDLE_CLOSE_INFORMATION {
  PVOID Object;
  PVOID CallContext;
  PVOID ObjectContext;
  PVOID Reserved;
} REG_KEY_HANDLE_CLOSE_INFORMATION, *PREG_KEY_HANDLE_CLOSE_INFORMATION;
````

## Members

        
            `CallContext`

            Optional driver-defined context information that the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine can supply. This member is defined for Windows Vista and later versions of the Windows operating system.
        
            `Object`

            A pointer to the registry key object for the handle that is about to be closed.
        
            `ObjectContext`

            A pointer to driver-defined context information that the driver has associated with a registry object by calling <a href="..\wdm\nf-wdm-cmsetcallbackobjectcontext.md">CmSetCallbackObjectContext</a>. This member is defined for Windows Vista and later versions of the Windows operating system.
        
            `Reserved`

            This member is reserved for future use. This member is defined for Windows Vista and later versions of the Windows operating system.

    ## Remarks
        For more information about registry filtering operations, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545879">Filtering Registry Calls</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |

    ## See Also

        <dl>
<dt>
<a href="..\wdm\nf-wdm-cmsetcallbackobjectcontext.md">CmSetCallbackObjectContext</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20REG_KEY_HANDLE_CLOSE_INFORMATION structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>