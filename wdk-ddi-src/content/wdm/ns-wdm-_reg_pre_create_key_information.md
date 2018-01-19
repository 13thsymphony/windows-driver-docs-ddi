---
UID : NS:wdm._REG_PRE_CREATE_KEY_INFORMATION
title : _REG_PRE_CREATE_KEY_INFORMATION
author : windows-driver-content
description : The REG_PRE_OPEN_KEY_INFORMATION structure contains the name of a registry key that is about to be opened.
old-location : kernel\reg_pre_open_key_information.htm
old-project : kernel
ms.assetid : 9b7240b5-429b-4bf2-aa7b-373b63bb79ae
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : _REG_PRE_CREATE_KEY_INFORMATION, REG_PRE_OPEN_KEY_INFORMATION, REG_PRE_CREATE_KEY_INFORMATION, *PREG_PRE_CREATE_KEY_INFORMATION, *PREG_PRE_OPEN_KEY_INFORMATION
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
req.target-type : Windows
req.target-min-winverclnt : Available only on Microsoft Windows XP.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : REG_PRE_CREATE_KEY_INFORMATION
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
req.typenames : REG_PRE_OPEN_KEY_INFORMATION, REG_PRE_CREATE_KEY_INFORMATION, *PREG_PRE_CREATE_KEY_INFORMATION, *PREG_PRE_OPEN_KEY_INFORMATION
req.product : Windows 10 or later.
---

# _REG_PRE_CREATE_KEY_INFORMATION structure
The <b>REG_PRE_OPEN_KEY_INFORMATION</b> structure contains the name of a registry key that is about to be opened.

## Syntax
````
typedef struct _REG_PRE_CREATE_KEY_INFORMATION {
  PUNICODE_STRING CompleteName;
} REG_PRE_CREATE_KEY_INFORMATION, REG_PRE_OPEN_KEY_INFORMATION, *PREG_PRE_CREATE_KEY_INFORMATION;
````

## Members

        
            `CompleteName`

            A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains the complete path of the registry key.

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a>
</dt>
<dt>
<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwopenkey.md">ZwOpenKey</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20REG_PRE_CREATE_KEY_INFORMATION structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>