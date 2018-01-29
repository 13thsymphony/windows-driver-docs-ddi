---
UID : NS:pepfx._PEP_INFORMATION
title : _PEP_INFORMATION
author : windows-driver-content
description : The PEP_INFORMATION structure specifies the interface that the platform extension plug-in (PEP) uses to receive notifications from the Windows power management framework (PoFx).
old-location : kernel\pep_information.htm
old-project : kernel
ms.assetid : 60221D44-79C0-4043-A4AF-1200C2F087F6
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : "*PPEP_INFORMATION, pepfx/PEP_INFORMATION, _PEP_INFORMATION, PEP_INFORMATION, PPEP_INFORMATION, PPEP_INFORMATION structure pointer [Kernel-Mode Driver Architecture], PEP_INFORMATION structure [Kernel-Mode Driver Architecture], kernel.pep_information, pepfx/PPEP_INFORMATION"
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : pepfx.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Supported starting with Windows 10.
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
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PPEP_INFORMATION, PEP_INFORMATION"
---

# _PEP_INFORMATION structure
The <b>PEP_INFORMATION</b> structure specifies the interface that the platform extension plug-in (PEP) uses to receive notifications from the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx).

## Syntax
````
typedef struct _PEP_INFORMATION {
  USHORT                 Version;
  USHORT                 Size;
  PPEPCALLBACKNOTIFYDPM  AcceptDeviceNotification;
  PPEPCALLBACKNOTIFYPPM  AcceptProcessorNotification;
  PPEPCALLBACKNOTIFYACPI AcceptAcpiNotification;
} PEP_INFORMATION, *PPEP_INFORMATION;
````

## Members


`AcceptAcpiNotification`

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/mt186625">AcceptAcpiNotification</a> callback routine. This member is optional and can be NULL if the PEP is not prepared to handle ACPI notifications from PoFx.

`AcceptDeviceNotification`

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/mt186626">AcceptDeviceNotification</a> callback routine. This member is required to point to a valid callback routine.

`AcceptProcessorNotification`

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/mt186627">AcceptProcessorNotification</a> callback routine. This member is optional and can be NULL if the PEP is not prepared to handle PPM notifications from PoFx.

`Size`

The size, in bytes, of this structure. Set this member to <b>sizeof</b>(<b>PEP_INFORMATION</b>).

`Version`

The current version number for this structure. Set this member to PEP_INFORMATION_VERSION.

## Remarks
This structure contains pointers to several callback routines that are implemented by the PEP. PoFx calls these routines to send notifications to the PEP.

The <i>PepInformation</i> parameter to the <a href="..\pepfx\nf-pepfx-pofxregisterplugin.md">PoFxRegisterPlugin</a> and <a href="..\pepfx\nf-pepfx-pofxregisterpluginex.md">PoFxRegisterPluginEx</a> routines is a pointer to a <b>PEP_INFORMATION</b> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | pepfx.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt186625">AcceptAcpiNotification</a>

<a href="..\pepfx\nf-pepfx-pofxregisterplugin.md">PoFxRegisterPlugin</a>

<a href="..\pepfx\nf-pepfx-pofxregisterpluginex.md">PoFxRegisterPluginEx</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/mt186626">AcceptDeviceNotification</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/mt186627">AcceptProcessorNotification</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_INFORMATION structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>