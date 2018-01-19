---
UID : NS:wdm._REG_ENUMERATE_KEY_INFORMATION
title : _REG_ENUMERATE_KEY_INFORMATION
author : windows-driver-content
description : The REG_ENUMERATE_KEY_INFORMATION structure describes one subkey of a key whose subkeys are being enumerated.
old-location : kernel\reg_enumerate_key_information.htm
old-project : kernel
ms.assetid : fdae9130-b33e-4714-9e8c-f4faf21ee8c8
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : _REG_ENUMERATE_KEY_INFORMATION, *PREG_ENUMERATE_KEY_INFORMATION, REG_ENUMERATE_KEY_INFORMATION
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
req.alt-api : REG_ENUMERATE_KEY_INFORMATION
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
req.typenames : "*PREG_ENUMERATE_KEY_INFORMATION, REG_ENUMERATE_KEY_INFORMATION"
req.product : Windows 10 or later.
---

# _REG_ENUMERATE_KEY_INFORMATION structure
The <b>REG_ENUMERATE_KEY_INFORMATION</b> structure describes one subkey of a key whose subkeys are being enumerated.

## Syntax
````
typedef struct _REG_ENUMERATE_KEY_INFORMATION {
  PVOID                 Object;
  ULONG                 Index;
  KEY_INFORMATION_CLASS KeyInformationClass;
  PVOID                 KeyInformation;
  ULONG                 Length;
  PULONG                ResultLength;
  PVOID                 CallContext;
  PVOID                 ObjectContext;
  PVOID                 Reserved;
} REG_ENUMERATE_KEY_INFORMATION, *PREG_ENUMERATE_KEY_INFORMATION;
````

## Members

        
            `CallContext`

            Optional driver-defined context information that the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine can supply. This member is defined for Windows Vista and later versions of the Windows operating system.
        
            `Index`

            The zero-based index of the subkey within the key.
        
            `KeyInformation`

            A pointer to a buffer that contains the information to be returned by the system. The format of the buffer depends on the value of <b>KeyInformationClass</b>. For more information, see <a href="..\wdm\ne-wdm-_key_information_class.md">KEY_INFORMATION_CLASS</a>.
        
            `KeyInformationClass`

            The <a href="..\wdm\ne-wdm-_key_information_class.md">KEY_INFORMATION_CLASS</a> value that indicates the type of information to be returned by the system in the <b>KeyInformation</b> buffer.
        
            `Length`

            The size, in bytes, of the <b>KeyInformation</b> buffer.
        
            `Object`

            A pointer to the registry key object for the key whose subkeys are being enumerated.
        
            `ObjectContext`

            A pointer to driver-defined context information that the driver has associated with a registry object by calling <a href="..\wdm\nf-wdm-cmsetcallbackobjectcontext.md">CmSetCallbackObjectContext</a>. This member is defined for Windows Vista and later versions of the Windows operating system.
        
            `Reserved`

            This member is reserved for future use. This member is defined for Windows Vista and later versions of the Windows operating system.
        
            `ResultLength`

            A pointer to a ULONG that receives (from the system) the amount of valid data, in bytes, in the <b>KeyInformation</b> buffer.

    ## Remarks
        The system passes this structure to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine every time a thread attempts to enumerate the subkeys of a key—for example, when a user-mode thread calls <b>RegEnumKey</b> or <b>RegEnumKeyEx</b> or when a driver calls <a href="..\wdm\nf-wdm-zwenumeratekey.md">ZwEnumerateKey</a>.

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
<a href="..\wdm\ne-wdm-_key_information_class.md">KEY_INFORMATION_CLASS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwenumeratekey.md">ZwEnumerateKey</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20REG_ENUMERATE_KEY_INFORMATION structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>