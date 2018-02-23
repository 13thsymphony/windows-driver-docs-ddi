---
UID: NS:ksmedia.KSPROPERTY_SELECTOR_S
title: KSPROPERTY_SELECTOR_S
author: windows-driver-content
description: The KSPROPERTY_SELECTOR_S structure describes filter-based property settings in the PROPSETID_VIDCAP_SELECTOR property set.
old-location: stream\ksproperty_selector_s.htm
old-project: stream
ms.assetid: cc9928b7-fab2-44c1-8613-3a94b5e8dcab
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: PKSPROPERTY_SELECTOR_S, KSPROPERTY_SELECTOR_S, stream.ksproperty_selector_s, PKSPROPERTY_SELECTOR_S structure pointer [Streaming Media Devices], vidcapstruct_7e180fae-5237-4b71-8719-7d3c5ee66592.xml, ksmedia/KSPROPERTY_SELECTOR_S, *PKSPROPERTY_SELECTOR_S, KSPROPERTY_SELECTOR_S structure [Streaming Media Devices], ksmedia/PKSPROPERTY_SELECTOR_S
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ksmedia.h
apiname:
-	KSPROPERTY_SELECTOR_S
product: Windows
targetos: Windows
req.typenames: "*PKSPROPERTY_SELECTOR_S, KSPROPERTY_SELECTOR_S"
---

# KSPROPERTY_SELECTOR_S structure
The KSPROPERTY_SELECTOR_S structure describes filter-based property settings in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567810">PROPSETID_VIDCAP_SELECTOR</a> property set.

## Syntax
````
typedef struct {
  KSPROPERTY Property;
  LONG       Value;
  ULONG      Flags;
  ULONG      Capabilities;
} KSPROPERTY_SELECTOR_S, *PKSPROPERTY_SELECTOR_S;
````

## Members


`Capabilities`

Specifies the capabilities of a property. This member has meaning only for Get requests. The minidriver should return the capabilities of the Selector with respect to the property specified in <b>Property</b>.

`Flags`

Specifies the flags of a request. For Set requests, this value indicates the desired setting. For Get requests, this value contains the current setting.

`Property`

Specifies an initialized <a href="..\ks\ns-ks-ksp_node.md">KSP_NODE</a> structure that describes the node, property set, property ID, and request type.

`Value`

Specifies the value of a request. For Set requests, the minidriver should set the property specified in <b>Property</b> to this value. For Get requests, the minidriver should return the value of the property specified in <b>Property</b>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="..\ksmedia\ns-ksmedia-ksproperty_selector_node_s.md">KSPROPERTY_SELECTOR_NODE_S</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_SELECTOR_S structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>