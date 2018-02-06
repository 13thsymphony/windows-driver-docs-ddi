---
UID: NS:dxva._DXVA_COPPSetProtectionLevelCmdData
title: "_DXVA_COPPSetProtectionLevelCmdData"
author: windows-driver-content
description: The DXVA_COPPSetProtectionLevelCmdData structure describes the protection types and levels to set on the physical connector associated with a COPP DirectX VA device.
old-location: display\dxva_coppsetprotectionlevelcmddata.htm
old-project: display
ms.assetid: d68d6e50-1373-43bc-a22b-dd9db47614c8
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxva_coppsetprotectionlevelcmddata, _DXVA_COPPSetProtectionLevelCmdData, dxvaref_ac7e802b-dd23-49da-ab02-21d80eaabe86.xml, DXVA_COPPSetProtectionLevelCmdData structure [Display Devices], dxva/DXVA_COPPSetProtectionLevelCmdData, DXVA_COPPSetProtectionLevelCmdData
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
req.target-min-winverclnt: This structure applies only to Windows Server 2003 with SP1 and later, and Windows XP with SP2 and later.
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
-	dxva.h
apiname:
-	DXVA_COPPSetProtectionLevelCmdData
product: Windows
targetos: Windows
req.typenames: DXVA_COPPSetProtectionLevelCmdData
---

# _DXVA_COPPSetProtectionLevelCmdData structure
The DXVA_COPPSetProtectionLevelCmdData structure describes the protection types and levels to set on the physical connector associated with a COPP DirectX VA device.

## Syntax
````
typedef struct _DXVA_COPPSetProtectionLevelCmdData {
  ULONG ProtType;
  ULONG ProtLevel;
  ULONG ExtendedInfoChangeMask;
  ULONG ExtendedInfoData;
} DXVA_COPPSetProtectionLevelCmdData;
````

## Members


`ExtendedInfoChangeMask`

Specifies a value that indicates the valid bitfields in the following <b>ExtendedInfoData</b> member.

`ExtendedInfoData`

Specifies additional 32-bit data for the protection type in <b>ProtType</b>. Not currently used.

`ProtLevel`

Specifies the protection level to set for the protection type in <b>ProtType</b> or COPP_NoProtectionLevelAvailable (-1) if no protection level is available.
<ul>
<li>For COPP_ProtectionType_ACP, specifies one of the following values from the <b>COPP_ACP_Protection_Level</b> enumerated type:<ul>
<li>COPP_ACP_Level0 or COPP_ACP_LevelMin (0)</li>
<li>COPP_ACP_Level1 (1)</li>
<li>COPP_ACP_Level2 (2)</li>
<li>COPP_ACP_Level3 or COPP_ACP_LevelMax (3)</li>
</ul>
</li>
<li>For COPP_ProtectionType_CGMSA, specifies one of the following values from the <b>COPP_CGMSA_Protection_Level</b> enumerated type:<ul>
<li>COPP_CGMSA_Disabled or COPP_CGMSA_LevelMin (0)</li>
<li>COPP_CGMSA_CopyFreely (1)</li>
<li>COPP_CGMSA_CopyNoMore (2)</li>
<li>COPP_CGMSA_CopyOneGeneration (3)</li>
<li>COPP_CGMSA_CopyNever (4)</li>
<li>COPP_CGMSA_RedistributionControlRequired (0x08)</li>
<li>(COPP_CGMSA_RedistributionControlRequired + COPP_CGMSA_CopyNever) or COPP_CGMSA_LevelMax</li>
</ul>
</li>
<li>For COPP_ProtectionType_HDCP, specifies one of the following values from the <b>COPP_HDCP_Protection_Level</b> enumerated type:<ul>
<li>COPP_HDCP_Level0 or COPP_HDCP_LevelMin (0)</li>
<li>COPP_HDCP_Level1 or COPP_HDCP_LevelMax (1)</li>
</ul>
</li>
</ul>

`ProtType`

Specifies one of the following protection types to set on the physical connector associated with a COPP device:
<ul>
<li>
COPP_ProtectionType_None (0x00)

</li>
<li>
COPP_ProtectionType_HDCP (0x01)

</li>
<li>
COPP_ProtectionType_ACP (0x02)

</li>
<li>
COPP_ProtectionType_CGMSA (0x04)

</li>
</ul>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | This structure applies only to Windows Server 2003 with SP1 and later, and Windows XP with SP2 and later. This structure applies only to Windows Server 2003 with SP1 and later, and Windows XP with SP2 and later. |
| **Header** | dxva.h (include Dxva.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539642">COPPCommand</a>

<a href="..\dxva\ns-dxva-_dxva_coppcommand.md">DXVA_COPPCommand</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVA_COPPSetProtectionLevelCmdData structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>