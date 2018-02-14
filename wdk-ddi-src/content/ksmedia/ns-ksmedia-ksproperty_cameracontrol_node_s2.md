---
UID: NS:ksmedia.KSPROPERTY_CAMERACONTROL_NODE_S2
title: KSPROPERTY_CAMERACONTROL_NODE_S2
author: windows-driver-content
description: The KSPROPERTY_CAMERACONTROL_NODE_S2 structure describes node-based properties in the PROPSETID_VIDCAP_CAMERACONTROL property set that use two values at the same time. This structure specifies property values in requests to the USB video class driver.
old-location: stream\ksproperty_cameracontrol_node_s2.htm
old-project: stream
ms.assetid: 0d3ed82e-3565-4b0b-bca9-1d0b91732d18
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KSPROPERTY_CAMERACONTROL_NODE_S2 structure [Streaming Media Devices], ksmedia/PKSPROPERTY_CAMERACONTROL_NODE_S2, *PKSPROPERTY_CAMERACONTROL_NODE_S2, PKSPROPERTY_CAMERACONTROL_NODE_S2, PKSPROPERTY_CAMERACONTROL_NODE_S2 structure pointer [Streaming Media Devices], KSPROPERTY_CAMERACONTROL_NODE_S2, ksmedia/KSPROPERTY_CAMERACONTROL_NODE_S2, stream.ksproperty_cameracontrol_node_s2, vidcapstruct_fda6afc4-4b0a-4161-9502-1b335b1022e2.xml
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
-	KSPROPERTY_CAMERACONTROL_NODE_S2
product: Windows
targetos: Windows
req.typenames: KSPROPERTY_CAMERACONTROL_NODE_S2, *PKSPROPERTY_CAMERACONTROL_NODE_S2
---

# KSPROPERTY_CAMERACONTROL_NODE_S2 structure
The KSPROPERTY_CAMERACONTROL_NODE_S2 structure describes node-based properties in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567802">PROPSETID_VIDCAP_CAMERACONTROL</a> property set that use two values at the same time. This structure specifies property values in requests to the USB video class driver.

## Syntax
````
typedef struct {
  KSP_NODE NodeProperty;
  LONG     Value1;
  ULONG    Flags;
  ULONG    Capabilities;
  LONG     Value2;
} KSPROPERTY_CAMERACONTROL_NODE_S2, *PKSPROPERTY_CAMERACONTROL_NODE_S2;
````

## Members


`Capabilities`

Indicates the minidriver's camera control capabilities for the specified property. This member is read-only. This member can be set to one of the following values that are defined in <i>ksmedia.h</i>:

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
KSPROPERTY_CAMERACONTROL_FLAGS_MANUAL

</td>
<td>
Indicates that the device can be controlled manually

</td>
</tr>
<tr>
<td>
KSPROPERTY_CAMERACONTROL_FLAGS_AUTO

</td>
<td>
Indicates that the device can be controlled automatically

</td>
</tr>
<tr>
<td>
KSPROPERTY_CAMERACONTROL_FLAGS_ABSOLUTE

</td>
<td>
Indicates that the device settings are in absolute values

</td>
</tr>
<tr>
<td>
KSPROPERTY_CAMERACONTROL_FLAGS_RELATIVE

</td>
<td>
Indicates that the device settings are in relative values

</td>
</tr>
</table>

`Flags`

Indicates, for get requests, the current setting for the specified property from the values listed below. Indicates, for set requests, the desired setting for the specified property from the values listed below. This member can be set to one of the following values that are defined in <i>ksmedia.h</i>:

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
KSPROPERTY_CAMERACONTROL_FLAGS_MANUAL

</td>
<td>
Indicates that the setting is controlled manually

</td>
</tr>
<tr>
<td>
KSPROPERTY_CAMERACONTROL_FLAGS_AUTO

</td>
<td>
Indicates that the setting is controlled automatically

</td>
</tr>
<tr>
<td>
KSPROPERTY_CAMERACONTROL_FLAGS_ABSOLUTE

</td>
<td>
Indicates that the setting is in absolute values

</td>
</tr>
<tr>
<td>
KSPROPERTY_CAMERACONTROL_FLAGS_RELATIVE

</td>
<td>
Indicates that the setting is in relative values

</td>
</tr>
</table>

`NodeProperty`

Specifies an initialized <a href="..\ks\ns-ks-ksp_node.md">KSP_NODE</a> structure that describes the property set, property ID, request type, and node ID.

`Value1`

Specifies the first value of the property. This member is read/write.

`Value2`

Specifies the second value of the property. This member is read/write.

## Remarks
This structure is used by <a href="https://msdn.microsoft.com/library/windows/hardware/ff564425">KSPROPERTY_CAMERACONTROL_PANTILT</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff564427">KSPROPERTY_CAMERACONTROL_PANTILT_RELATIVE</a> for node-based get/set property requests.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h (include Ksmedia.h) |