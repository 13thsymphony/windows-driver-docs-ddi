---
UID: NE:wdm._IMAGE_POLICY_ID
title: _IMAGE_POLICY_ID
author: windows-driver-content
description: This enumeration is not supported.
old-location: kernel\_image_policy_id.htm
old-project: kernel
ms.assetid: e2984ef0-6648-41d3-89da-4f57cce66cfb
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _IMAGE_POLICY_ID, IMAGE_POLICY_ID
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IMAGE_POLICY_ID
req.alt-loc: wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (See Remarks section)
req.typenames: IMAGE_POLICY_ID
req.product: Windows 10 or later.
---

# _IMAGE_POLICY_ID enumeration



## -description
This enumeration is not supported.



## -syntax

````
typedef enum _IMAGE_POLICY_ID { 
  ImagePolicyIdEtw,
  ImagePolicyIdDebug,
  ImagePolicyIdCrashDump,
  ImagePolicyIdCrashDumpKey,
  ImagePolicyIdCrashDumpKeyGuid,
  ImagePolicyIdParentSd,
  ImagePolicyIdParentSdRev,
  ImagePolicyIdSvn,
  ImagePolicyIdDeviceId,
  ImagePolicyIdCapability,
  ImagePolicyIdScenarioId,
  ImagePolicyIdMaximum
} IMAGE_POLICY_ID;
````


## -enum-fields

### -field ImagePolicyIdEtw

Reserved.


### -field ImagePolicyIdDebug

Reserved.


### -field ImagePolicyIdCrashDump

Reserved.


### -field ImagePolicyIdCrashDumpKey

Reserved.


### -field ImagePolicyIdCrashDumpKeyGuid

Reserved.


### -field ImagePolicyIdParentSd

Reserved.


### -field ImagePolicyIdParentSdRev

Reserved.


### -field ImagePolicyIdSvn

Reserved.


### -field ImagePolicyIdDeviceId

Reserved.


### -field ImagePolicyIdCapability

Reserved.


### -field ImagePolicyIdScenarioId

Reserved.


### -field ImagePolicyIdMaximum

Reserved.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h)</dt>
</dl>
</td>
</tr>
</table>