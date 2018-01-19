---
UID : NF:wsk.WskDeregister
title : WskDeregister function
author : windows-driver-content
description : The WskDeregister function unregisters a WSK application's registration instance that was previously created by WskRegister.
old-location : netvista\wskderegister.htm
old-project : netvista
ms.assetid : b2ff3d7b-319d-4256-a574-cb32595fd02f
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : WskDeregister
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wsk.h
req.include-header : Wsk.h
req.target-type : Universal
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : WskDeregister
req.alt-loc : Netio.lib,Netio.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Netio.lib
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : "*PWPP_TRIAGE_INFO, WPP_TRIAGE_INFO"
req.product : Windows 10 or later.
---


# WskDeregister function
The 
  <b>WskDeregister</b> function unregisters a WSK application's registration instance that was previously
  created by 
  <a href="..\wsk\nf-wsk-wskregister.md">WskRegister</a>.

## Syntax

````
VOID WskDeregister(
  _In_ PWSK_REGISTRATION WskRegistration
);
````

## Parameters

`WskRegistration`

A pointer to the memory location initialized by 
     <a href="..\wsk\nf-wsk-wskregister.md">WskRegister</a> that identifies a WSK
     application's registration instance.


## Return Value

None

## Remarks

For each call to 
    <a href="..\wsk\nf-wsk-wskregister.md">WskRegister</a> that returns a success code, there
    must be exactly one corresponding 
    <b>WskDeregister</b> call that uses the same 
    <i>WskRegistration</i> parameter that was passed to 
    <b>WskRegister</b>.

<b>WskDeregister</b> will wait to return until all of the following have completed:

All captured instances of the provider NPI are released.

Any outstanding calls to functions pointed to by 
      <a href="..\wsk\ns-wsk-_wsk_provider_dispatch.md">WSK_PROVIDER_DISPATCH</a> members have
      returned.

All sockets are closed.

For more information about attaching a WSK application to the WSK subsystem, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/registering-a-winsock-kernel-application">Registering a Winsock Kernel
    Application</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wsk.h (include Wsk.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\wsk\nf-wsk-wskregister.md">WskRegister</a>
</dt>
<dt>
<a href="..\wsk\ns-wsk-_wsk_registration.md">WSK_REGISTRATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WskDeregister function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>