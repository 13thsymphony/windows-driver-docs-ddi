---
UID : NS:drmk.KSP_DRMAUDIOSTREAM_CONTENTID
title : KSP_DRMAUDIOSTREAM_CONTENTID
author : windows-driver-content
description : The KSP_DRMAUDIOSTREAM_CONTENTID structure specifies the property, request type, and context for a KSPROPERTY_DRMAUDIOSTREAM_CONTENTIDset-property request. It also specifies a list of function pointers to the DRM functions.
old-location : audio\ksp_drmaudiostream_contentid.htm
old-project : audio
ms.assetid : 16a83c46-c183-4dc2-9d98-877976cf5750
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : PKSP_DRMAUDIOSTREAM_CONTENTID structure pointer [Audio Devices], KSP_DRMAUDIOSTREAM_CONTENTID, drmk/PKSP_DRMAUDIOSTREAM_CONTENTID, *PKSP_DRMAUDIOSTREAM_CONTENTID, KSP_DRMAUDIOSTREAM_CONTENTID structure [Audio Devices], PKSP_DRMAUDIOSTREAM_CONTENTID, aud-prop_f18ac59e-1ebf-4e98-8bab-1f54f76c6a64.xml, drmk/KSP_DRMAUDIOSTREAM_CONTENTID, audio.ksp_drmaudiostream_contentid
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : drmk.h
req.include-header : Drmk.h
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
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : KSP_DRMAUDIOSTREAM_CONTENTID, *PKSP_DRMAUDIOSTREAM_CONTENTID
---

# KSP_DRMAUDIOSTREAM_CONTENTID structure
The KSP_DRMAUDIOSTREAM_CONTENTID structure specifies the property, request type, and context for a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537351">KSPROPERTY_DRMAUDIOSTREAM_CONTENTID</a>set-property request. It also specifies a list of function pointers to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536356">DRM functions</a>.

## Syntax
````
typedef struct {
  KSPROPERTY                         Property;
  PVOID                              Context;
  PFNDRMADDCONTENTHANDLERS           DrmAddContentHandlers;
  PFNDRMCREATECONTENTMIXED           DrmCreateContentMixed;
  PFNDRMDESTROYCONTENT               DrmDestroyContent;
  PFNDRMFORWARDCONTENTTODEVICEOBJECT DrmForwardContentToDeviceObject;
  PFNDRMFORWARDCONTENTTOFILEOBJECT   DrmForwardContentToFileObject;
  PFNDRMFORWARDCONTENTTOINTERFACE    DrmForwardContentToInterface;
  PFNDRMGETCONTENTRIGHTS             DrmGetContentRights;
} KSP_DRMAUDIOSTREAM_CONTENTID, *PKSP_DRMAUDIOSTREAM_CONTENTID;
````

## Members


`Context`

Pointer to context data. This is the context specified in the <a href="..\drmk\nf-drmk-drmforwardcontenttodeviceobject.md">DrmForwardContentToDeviceObject</a> function's <i>DrmForward</i> parameter.

`DrmAddContentHandlers`

Pointer to <a href="..\drmk\nf-drmk-drmaddcontenthandlers.md">DrmAddContentHandlers</a> function.

`DrmCreateContentMixed`

Pointer to <a href="..\drmk\nf-drmk-drmcreatecontentmixed.md">DrmCreateContentMixed</a> function.

`DrmDestroyContent`

Pointer to <a href="..\drmk\nf-drmk-drmdestroycontent.md">DrmDestroyContent</a> function.

`DrmForwardContentToDeviceObject`

Pointer to <a href="..\drmk\nf-drmk-drmforwardcontenttodeviceobject.md">DrmForwardContentToDeviceObject</a> function.

`DrmForwardContentToFileObject`

Pointer to <a href="..\drmk\nf-drmk-drmforwardcontenttofileobject.md">DrmForwardContentToFileObject</a> function.

`DrmForwardContentToInterface`

Pointer to <a href="..\drmk\nf-drmk-drmforwardcontenttointerface.md">DrmForwardContentToInterface</a> function.

`DrmGetContentRights`

Pointer to <a href="..\drmk\nf-drmk-drmgetcontentrights.md">DrmGetContentRights</a> function.

`Property`

Specifies the property to get or set. This member is a structure of type <a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>.

## Remarks
The structure contains function pointers to the DRM library functions in order to provide the driver with convenient access to these functions.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | drmk.h (include Drmk.h) |

## See Also

<a href="..\drmk\nf-drmk-drmdestroycontent.md">DrmDestroyContent</a>

<a href="..\drmk\nf-drmk-drmgetcontentrights.md">DrmGetContentRights</a>

<a href="..\drmk\nf-drmk-drmforwardcontenttofileobject.md">DrmForwardContentToFileObject</a>

<a href="..\drmk\nf-drmk-drmaddcontenthandlers.md">DrmAddContentHandlers</a>

<a href="..\drmk\nf-drmk-drmforwardcontenttodeviceobject.md">DrmForwardContentToDeviceObject</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537351">KSPROPERTY_DRMAUDIOSTREAM_CONTENTID</a>

<a href="..\drmk\nf-drmk-drmcreatecontentmixed.md">DrmCreateContentMixed</a>

<a href="..\drmk\nf-drmk-drmforwardcontenttointerface.md">DrmForwardContentToInterface</a>

<a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSP_DRMAUDIOSTREAM_CONTENTID structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>