---
UID : NF:portcls.IRegistryKey.DeleteKey
title : IRegistryKey::DeleteKey method
author : windows-driver-content
description : The DeleteKey method deletes the registry key.
old-location : audio\iregistrykey_deletekey.htm
old-project : audio
ms.assetid : 2930b049-7572-4ee5-bef1-fd4485e5f644
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : audmp-routines_b5556b44-0bf4-47d2-8bbd-65d12c393341.xml, IRegistryKey, DeleteKey method [Audio Devices], IRegistryKey interface, DeleteKey method [Audio Devices], IRegistryKey interface [Audio Devices], DeleteKey method, portcls/IRegistryKey::DeleteKey, IRegistryKey::DeleteKey, audio.iregistrykey_deletekey, DeleteKey
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : portcls.h
req.include-header : Portcls.h
req.target-type : Universal
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
req.lib : portcls.h
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY"
---


# DeleteKey method
The <code>DeleteKey</code> method deletes the registry key.

## Syntax

````
NTSTATUS DeleteKey(
    None
);
````

## Parameters

This function has no parameters.

## Return Value

<code>DeleteKey</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.

## Remarks

A caller deletes an <b>IRegistryKey</b> object's registry key by calling the <code>DeleteKey</code> method on that object. The key can be deleted only if the caller created the key with an <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> that permits deletion. The caller enables deletion by specifying a <i>DesiredAccess</i> parameter value of KEY_ALL_ACCESS (described in <a href="..\wdm\nf-wdm-zwcreatekey.md">ZwCreateKey</a>) to the <a href="..\portcls\nf-portcls-pcnewregistrykey.md">PcNewRegistryKey</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff536945">IPort::NewRegistryKey</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff536970">IRegistryKey::NewSubKey</a> call that creates the key. When deleting a key, the <b>IRegistryKey</b> object discards its registry-key handle, and all other handles to the deleted key become invalid.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | portcls.h (include Portcls.h) |
| **Library** | portcls.h |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536945">IPort::NewRegistryKey</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536970">IRegistryKey::NewSubKey</a>

<a href="..\portcls\nn-portcls-iregistrykey.md">IRegistryKey</a>

<a href="..\portcls\nf-portcls-pcnewregistrykey.md">PcNewRegistryKey</a>

<a href="..\wdm\nf-wdm-zwdeletekey.md">ZwDeleteKey</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>

<a href="..\wdm\nf-wdm-zwcreatekey.md">ZwCreateKey</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IRegistryKey::DeleteKey method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>