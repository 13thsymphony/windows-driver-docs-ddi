---
UID : NS:wdm._IO_SECURITY_CONTEXT
title : "_IO_SECURITY_CONTEXT"
author : windows-driver-content
description : The IO_SECURITY_CONTEXT structure represents the security context of an IRP_MJ_CREATE request.
old-location : kernel\io_security_context.htm
old-project : kernel
ms.assetid : 6500c46b-ae39-4c91-8b84-14df0a7046a1
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : wdm/PIO_SECURITY_CONTEXT, *PIO_SECURITY_CONTEXT, kernel.io_security_context, _IO_SECURITY_CONTEXT, wdm/IO_SECURITY_CONTEXT, IO_SECURITY_CONTEXT structure [Kernel-Mode Driver Architecture], PIO_SECURITY_CONTEXT structure pointer [Kernel-Mode Driver Architecture], IO_SECURITY_CONTEXT, PIO_SECURITY_CONTEXT, kstruct_b_2c3ede84-cdd5-4e78-99b9-5ff642463f85.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
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
req.irql : PASSIVE_LEVEL (see Remarks section)
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PIO_SECURITY_CONTEXT, IO_SECURITY_CONTEXT"
req.product : Windows 10 or later.
---

# _IO_SECURITY_CONTEXT structure
The <b>IO_SECURITY_CONTEXT</b> structure represents the security context of an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a> request.

## Syntax
````
typedef struct _IO_SECURITY_CONTEXT {
  PSECURITY_QUALITY_OF_SERVICE SecurityQos;
  PACCESS_STATE                AccessState;
  ACCESS_MASK                  DesiredAccess;
  ULONG                        FullCreateOptions;
} IO_SECURITY_CONTEXT, *PIO_SECURITY_CONTEXT;
````

## Members


`AccessState`

Reserved for use by file systems and file system filter drivers. This member is a pointer to an <a href="..\wdm\ns-wdm-_access_state.md">ACCESS_STATE</a> structure that contains the object's subject context, granted access types, and remaining desired access types.

`DesiredAccess`

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> value that expresses the access rights that are requested in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a> request.

`FullCreateOptions`

Reserved for system use.

`SecurityQos`

Reserved for system use.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a>

<a href="..\wdm\ns-wdm-_access_state.md">ACCESS_STATE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IO_SECURITY_CONTEXT structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>