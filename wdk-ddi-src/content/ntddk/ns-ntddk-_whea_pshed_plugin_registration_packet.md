---
UID: NS:ntddk._WHEA_PSHED_PLUGIN_REGISTRATION_PACKET
title: "_WHEA_PSHED_PLUGIN_REGISTRATION_PACKET"
author: windows-driver-content
description: The WHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure describes the data required for registering a PSHED plug-in with the PSHED.
old-location: whea\whea_pshed_plugin_registration_packet.htm
old-project: whea
ms.assetid: 9dafa65f-26f6-42a6-a125-013c61a66ccc
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: "_WHEA_PSHED_PLUGIN_REGISTRATION_PACKET, *PWHEA_PSHED_PLUGIN_REGISTRATION_PACKET, ntddk/PWHEA_PSHED_PLUGIN_REGISTRATION_PACKET, whearef_9e79e188-a1ce-4d98-a15d-a45c27f9e836.xml, PWHEA_PSHED_PLUGIN_REGISTRATION_PACKET, WHEA_PSHED_PLUGIN_REGISTRATION_PACKET, ntddk/WHEA_PSHED_PLUGIN_REGISTRATION_PACKET, WHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure [WHEA Drivers and Applications], PWHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure pointer [WHEA Drivers and Applications], whea.whea_pshed_plugin_registration_packet"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddk.h
apiname:
-	WHEA_PSHED_PLUGIN_REGISTRATION_PACKET
product: Windows
targetos: Windows
req.typenames: WHEA_PSHED_PLUGIN_REGISTRATION_PACKET, *PWHEA_PSHED_PLUGIN_REGISTRATION_PACKET
---

# _WHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure
The WHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure describes the data required for registering a PSHED plug-in with the PSHED.

## Syntax
````
typedef struct _WHEA_PSHED_PLUGIN_REGISTRATION_PACKET {
  ULONG                       Length;
  ULONG                       Version;
  PVOID                       Context;
  ULONG                       FunctionalAreaMask;
  ULONG                       Reserved;
  WHEA_PSHED_PLUGIN_CALLBACKS Callbacks;
} WHEA_PSHED_PLUGIN_REGISTRATION_PACKET, *PWHEA_PSHED_PLUGIN_REGISTRATION_PACKET;
````

## Members


`Callbacks`

A <a href="..\ntddk\ns-ntddk-_whea_pshed_plugin_callbacks.md">WHEA_PSHED_PLUGIN_CALLBACKS</a> structure that describes the callback functions for the PSHED plug-in.

`Context`

A PSHED plug-in-supplied context area that is passed to the PSHED plug-in's callback functions.

`FunctionalAreaMask`

A bit-wise OR'ed combination of flags that specifies the functional areas in which the PSHED plug-in participates. Possible flags are:





#### PshedFADiscovery

The PSHED plug-in participates in error source discovery.



#### PshedFAErrorSourceControl

The PSHED plug-in participates in error source control.



#### PshedFAErrorRecordPersistence

The PSHED plug-in participates in error record persistence.



#### PshedFAErrorInfoRetrieval

The PSHED plug-in participates in error information retrieval.



#### PshedFAErrorRecovery

The PSHED plug-in participates in error recovery.



#### PshedFAErrorInjection

The PSHED plug-in participates in error injection.

`Length`

The size, in bytes, of the WHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure.

`Reserved`

Reserved for system use. PSHED plug-ins should set this member to zero.

`Version`

The version of the WHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure. PSHED plug-ins must set this member to WHEA_PLUGIN_REGISTRATION_PACKET_VERSION.

## Remarks
A PSHED plug-in passes an initialized WHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure to the <a href="..\ntddk\nf-ntddk-pshedregisterplugin.md">PshedRegisterPlugin</a> function when it registers itself with the PSHED.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows. Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows. |
| **Header** | ntddk.h (include Ntddk.h) |

## See Also

<a href="..\ntddk\ns-ntddk-_whea_pshed_plugin_callbacks.md">WHEA_PSHED_PLUGIN_CALLBACKS</a>



<a href="..\ntddk\nf-ntddk-pshedregisterplugin.md">PshedRegisterPlugin</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>