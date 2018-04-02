---
UID: NI:bthhfpddi.IOCTL_BTHHFP_DEVICE_GET_VOLUMEPROPERTYVALUES
title: IOCTL_BTHHFP_DEVICE_GET_VOLUMEPROPERTYVALUES
author: windows-driver-content
description: The IOCTL_BTHHFP_DEVICE_GET_VOLUMEPROPERTYVALUES IOCTL returns KSPROPERTY_VALUES data for the KSPROPERTY_AUDIO_VOLUMELEVEL property.
old-location: audio\ioctl_bthhfp_device_get_volumepropertyvalues.htm
old-project: audio
ms.assetid: 56DA61CB-D4D3-40DF-861D-2A2EE257C194
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: IOCTL_BTHHFP_DEVICE_GET_VOLUMEPROPERTYVALUES, IOCTL_BTHHFP_DEVICE_GET_VOLUMEPROPERTYVALUES control code [Audio Devices], audio.ioctl_bthhfp_device_get_volumepropertyvalues, bthhfpddi/IOCTL_BTHHFP_DEVICE_GET_VOLUMEPROPERTYVALUES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: bthhfpddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Bthhfpddi.h
api_name:
-	IOCTL_BTHHFP_DEVICE_GET_VOLUMEPROPERTYVALUES
product: Windows
targetos: Windows
req.typenames: HFP_BYPASS_CODEC_ID_VERSION, *PHFP_BYPASS_CODEC_ID_VERSION
---

# IOCTL_BTHHFP_DEVICE_GET_VOLUMEPROPERTYVALUES IOCTL
The <b>IOCTL_BTHHFP_DEVICE_GET_VOLUMEPROPERTYVALUES</b> 
   IOCTL returns <a href="http://msdn.microsoft.com/en-us/library/windows/hardware/ff565966(v=vs.85).aspx">KSPROPERTY_VALUES</a> data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537309">KSPROPERTY_AUDIO_VOLUMELEVEL</a> property.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
None.

### Input Buffer Length
None.

### Output Buffer
A buffer containing a <a href="http://msdn.microsoft.com/en-us/library/windows/hardware/ff565966(v=vs.85).aspx">KSPROPERTY_VALUES</a> structure followed by any other data referenced by this structure.

### Output Buffer Length
The size of a <a href="http://msdn.microsoft.com/en-us/library/windows/hardware/ff565966(v=vs.85).aspx">KSPROPERTY_VALUES</a> structure and referenced data.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
N/A

## Remarks
The audio driver’s KS filter topology includes a KS node of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff537208">KSNODETYPE_VOLUME</a> for both input and output if the <a href="https://msdn.microsoft.com/library/windows/hardware/dn302030">BTHHFP_DESCRIPTOR</a> descriptor indicates volume support. The audio driver’s <a href="http://msdn.microsoft.com/en-us/library/windows/hardware/ff563473(v=vs.85).aspx">KSNODE_DESCRIPTOR</a> structure for this node includes a <a href="http://msdn.microsoft.com/en-us/library/windows/hardware/ff565176(v=vs.85).aspx">PKSPROPERTY_ITEM</a> for the <b>KSPROPERTY_AUDIO_VOLUMELEVEL</b> property. The audio driver sets the <b>PKSPROPERTY_ITEM</b>.<i>Values</i> member to the <a href="http://msdn.microsoft.com/en-us/library/windows/hardware/ff565966(v=vs.85).aspx">KSPROPERTY_VALUES</a> structured returned by this request.

This allows the Handsfree proofile (HFP) driver to almost entirely handle the problem of mapping <b>KSPROPERTY_AUDIO_VOLUMELEVEL</b> property values to the Bluetooth Handsfree profile. The audio driver’s property Get and Set handlers for this property simply call the HFP driver.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | bthhfpddi.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn302027">Bluetooth HFP DDI IOCTLs</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537208">KSNODETYPE_VOLUME</a>



<a href="http://msdn.microsoft.com/en-us/library/windows/hardware/ff563473(v=vs.85).aspx">KSNODE_DESCRIPTOR</a>



<a href="http://msdn.microsoft.com/en-us/library/windows/hardware/ff565966(v=vs.85).aspx">KSPROPERTY_VALUES</a>