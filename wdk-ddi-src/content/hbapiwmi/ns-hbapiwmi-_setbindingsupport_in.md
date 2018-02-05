---
UID : NS:hbapiwmi._SetBindingSupport_IN
title : "_SetBindingSupport_IN"
author : windows-driver-content
description : The SetBindingSupport_IN structure is used to deliver input parameter data to the SetBindingSupport WMI method.
old-location : storage\setbindingsupport_in.htm
old-project : storage
ms.assetid : bdcd6f76-9a45-4687-b3ab-ece3e9419c44
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : "*PSetBindingSupport_IN, SetBindingSupport_IN, hbapiwmi/SetBindingSupport_IN, _SetBindingSupport_IN, structs-Fibre_2545c261-7902-4fb8-9943-21087c281089.xml, PSetBindingSupport_IN, SetBindingSupport_IN structure [Storage Devices], storage.setbindingsupport_in, PSetBindingSupport_IN structure pointer [Storage Devices], hbapiwmi/PSetBindingSupport_IN"
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : hbapiwmi.h
req.include-header : Hbapiwmi.h
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
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PSetBindingSupport_IN, SetBindingSupport_IN"
---

# _SetBindingSupport_IN structure
The SetBindingSupport_IN structure is used to deliver input parameter data to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565565">SetBindingSupport</a> WMI method.

## Syntax
````
typedef struct _SetBindingSupport_IN {
  UCHAR PortWWN[8];
  ULONG BindType;
} SetBindingSupport_IN, *PSetBindingSupport_IN;
````

## Members


`BindType`

Contains a bitmap that indicates the ability of an HBA and its miniport driver to provide a specific set of features related to persistent binding. For a list of values that this parameter can have, see the description of the HBA_BIND_TYPE WMI class qualifier.

`PortWWN`

Contains a worldwide name that indicates the port whose persistent bindings are to be retrieved.

## Remarks
The WMI tool suite generates a declaration of the SetBindingSupport_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562509">MSFC_HBAFCPInfo WMI Class</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hbapiwmi.h (include Hbapiwmi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565565">SetBindingSupport</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SetBindingSupport_IN structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>