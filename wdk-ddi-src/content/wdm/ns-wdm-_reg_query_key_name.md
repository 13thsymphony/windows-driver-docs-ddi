---
UID : NS:wdm._REG_QUERY_KEY_NAME
title : _REG_QUERY_KEY_NAME
author : windows-driver-content
description : The REG_QUERY_KEY_NAME structure describes the full registry key name of an object being queried.
old-location : kernel\reg_query_key_name.htm
old-project : kernel
ms.assetid : 396DA33D-46E0-456C-9FCF-85A7D9915F48
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : _REG_QUERY_KEY_NAME, *PREG_QUERY_KEY_NAME, REG_QUERY_KEY_NAME
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
req.target-type : Windows
req.target-min-winverclnt : Available on Microsoft Windows 10 and later versions of the Windows operating system.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : REG_QUERY_KEY_NAME
req.alt-loc : wdm.h
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
req.typenames : "*PREG_QUERY_KEY_NAME, REG_QUERY_KEY_NAME"
req.product : Windows 10 or later.
---

# _REG_QUERY_KEY_NAME structure
The <b>REG_QUERY_KEY_NAME</b> structure describes the full registry key name
              of an object being queried.

## Syntax
````
typedef struct _REG_QUERY_KEY_NAME {
  PVOID                    Object;
  POBJECT_NAME_INFORMATION ObjectNameInfo;
  ULONG                    Length;
  PULONG                   ResultLength;
  PVOID                    CallContext;
  PVOID                    ObjectContext;
  PVOID                    Reserved;
} REG_QUERY_KEY_NAME, *PREG_QUERY_KEY_NAME;
````

## Members

        
            `CallContext`

            Optional driver-defined context information that the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine can supply.
        
            `Length`

            Specifies the size, in bytes, of the <b>ObjectNameInfo</b> buffer.
        
            `Object`

            A pointer to the registry key object for the key whose metadata is about to be queried.
        
            `ObjectContext`

            A pointer to driver-defined context information that the driver has associated with a registry object by calling <a href="..\wdm\nf-wdm-cmsetcallbackobjectcontext.md">CmSetCallbackObjectContext</a>. It contains the key context for the key that is being queried.
        
            `ObjectNameInfo`

            A pointer to an <b>OBJECT_NAME_INFORMATION</b> structure (see wdm.h) that contains the full registry key name to be returned by the system, as a Unicode string.
        
            `Reserved`

            This member is reserved for future use.

    ## Remarks
        The system passes this structure to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine every time a thread attempts to query the full name of the registry key. 

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
<a href="..\wdm\ne-wdm-_reg_notify_class.md">REG_NOTIFY_CLASS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20REG_QUERY_KEY_NAME structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>