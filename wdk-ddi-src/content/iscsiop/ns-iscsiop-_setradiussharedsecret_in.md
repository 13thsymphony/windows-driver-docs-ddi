---
UID : NS:iscsiop._SetRADIUSSharedSecret_IN
title : _SetRADIUSSharedSecret_IN
author : windows-driver-content
description : The SetRADIUSSharedSecret_IN structure holds the input data for the SetRADIUSSharedSecret method.
old-location : storage\setradiussharedsecret_in.htm
old-project : storage
ms.assetid : 948475eb-0670-4fab-b831-2fdb3ec86032
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : _SetRADIUSSharedSecret_IN, SetRADIUSSharedSecret_IN, *PSetRADIUSSharedSecret_IN
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : iscsiop.h
req.include-header : Iscsiop.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : SetRADIUSSharedSecret_IN
req.alt-loc : iscsiop.h
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
req.typenames : SetRADIUSSharedSecret_IN, *PSetRADIUSSharedSecret_IN
---

# _SetRADIUSSharedSecret_IN structure
The SetRADIUSSharedSecret_IN structure holds the input data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565815">SetRADIUSSharedSecret</a> method.

## Syntax
````
typedef struct _SetRADIUSSharedSecret_IN {
  ULONG SharedSecretSize;
  UCHAR SharedSecret[1];
} SetRADIUSSharedSecret_IN, *PSetRADIUSSharedSecret_IN;
````

## Members

        
            `SharedSecret`

            The shared secret.
        
            `SharedSecretSize`

            The size, in bytes, of the shared secret.

    ## Remarks
        You must implement this method.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | iscsiop.h (include Iscsiop.h) |

    ## See Also

        <dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565815">SetRADIUSSharedSecret</a>
</dt>
<dt>
<a href="..\iscsiop\ns-iscsiop-_setradiussharedsecret_out.md">SetRADIUSSharedSecret_OUT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SetRADIUSSharedSecret_IN structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>