---
UID : NS:dxva._DXVA_COPPStatusSignalingCmdData
title : _DXVA_COPPStatusSignalingCmdData
author : windows-driver-content
description : The DXVA_COPPStatusSignalingCmdData structure describes how the signal that goes through the physical connector associated with the DirectX VA COPP device is protected.
old-location : display\dxva_coppstatussignalingcmddata.htm
old-project : display
ms.assetid : 3065dddc-e084-4273-93eb-62a51763e213
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _DXVA_COPPStatusSignalingCmdData, DXVA_COPPStatusSignalingCmdData
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : dxva.h
req.include-header : Dxva.h
req.target-type : Windows
req.target-min-winverclnt : This structure applies only to Windows Server 2003 with SP1 and later, and Windows XP with SP2 and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : DXVA_COPPStatusSignalingCmdData
req.alt-loc : dxva.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : DXVA_COPPStatusSignalingCmdData
---

# _DXVA_COPPStatusSignalingCmdData structure
The DXVA_COPPStatusSignalingCmdData structure describes how the signal that goes through the physical connector associated with the DirectX VA COPP device is protected.

## Syntax
````
typedef struct _DXVA_COPPStatusSignalingCmdData {
  GUID  rApp;
  ULONG dwFlags;
  ULONG AvailableTVProtectionStandards;
  ULONG ActiveTVProtectionStandard;
  ULONG TVType;
  ULONG AspectRatioValidMask1;
  ULONG AspectRatioData1;
  ULONG AspectRatioValidMask2;
  ULONG AspectRatioData2;
  ULONG AspectRatioValidMask3;
  ULONG AspectRatioData3;
  ULONG ExtendedInfoValidMask[4];
  ULONG ExtendedInfoData[4];
} DXVA_COPPStatusSignalingCmdData;
````

## Members

        
            `ActiveTVProtectionStandard`

            Specifies a valid ORed combination of values from the <b>COPP_TVProtectionStandard</b> enumeration type that indicates the types of television signals that the physical connector associated with the DirectX VA COPP device currently carries. For the list of signal types, see the <b>ActiveTVProtectionStandard</b> member of the <a href="..\dxva\ns-dxva-_dxva_coppsetsignalingcmddata.md">DXVA_COPPSetSignalingCmdData</a> structure.
        
            `AspectRatioData1`

            Specifies one of the values from the <b>COPP_ImageAspectRatio_EN300294</b> enumeration type to indicate an ETSI EN 300 294 value. For the list of values, see the <b>AspectRatioData1</b> member of the <a href="..\dxva\ns-dxva-_dxva_coppsetsignalingcmddata.md">DXVA_COPPSetSignalingCmdData</a> structure.
        
            `AspectRatioData2`

            Specifies 32-bit data for additional aspect ratio-related data for specific protection standards. This data can be used to read End and Q0 values for EIA-608-B, or active format description for CEA-805-A Type B packets.
        
            `AspectRatioData3`

            Specifies 32-bit data for additional aspect ratio-related data for specific protection standards. This data can be used to read End and Q0 values for EIA-608-B, or active format description for CEA-805-A Type B packets.
        
            `AspectRatioValidMask1`

            Specifies the COPP_ImageAspectRatio_EN300294_Mask (0x00000007) constant that indicates that only the first three bits in the following <b>AspectRatioData1</b> member are valid.
        
            `AspectRatioValidMask2`

            Specifies a value that indicates the valid bitfields in the following <b>AspectRatioData2</b> member.
        
            `AspectRatioValidMask3`

            Specifies a value that indicates the valid bitfields in the following <b>AspectRatioData3</b> member.
        
            `AvailableTVProtectionStandards`

            Specifies a valid ORed combination of values from the <b>COPP_TVProtectionStandard</b> enumeration type that indicates the types of television signals that the physical connector associated with the DirectX VA COPP device can carry. For the list of signal types, see the <b>ActiveTVProtectionStandard</b> member of the <a href="..\dxva\ns-dxva-_dxva_coppsetsignalingcmddata.md">DXVA_COPPSetSignalingCmdData</a> structure.
        
            `dwFlags`

            Specifies additional status information that might be relevant to the calling application. The display driver should set <b>dwFlags</b> to the COPP_StatusNormal (0x00) value from the <b>COPP_StatusFlags</b> enumeration type or to a valid ORed combination of the following COPP_StatusFlags:

<ul>
<li>
COPP_LinkLost (0x01)

</li>
<li>
COPP_RenegotiationRequired (0x02)

</li>
</ul>
        
            `ExtendedInfoData`

            Specifies an array of additional 32-bit data. Not currently used.
        
            `ExtendedInfoValidMask`

            Specifies an array of values that indicate the valid bitfields in the respective elements of the following <b>ExtendedInfoData</b> array member.
        
            `rApp`

            Specifies a 128-bit random number, used once. This random number is generated by the requesting application and supplied to the display driver in the <b>rApp</b> member of the <a href="..\dxva\ns-dxva-_dxva_coppstatusinput.md">DXVA_COPPStatusInput</a> structure.
        
            `TVType`

            Specifies a value that indicates attributes of the connected display monitor that the driver is aware of. Not currently used.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dxva.h (include Dxva.h) |

    ## See Also

        <dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539652">COPPQueryStatus</a>
</dt>
<dt>
<a href="..\dxva\ns-dxva-_dxva_coppsetprotectionlevelcmddata.md">DXVA_COPPSetProtectionLevelCmdData</a>
</dt>
<dt>
<a href="..\dxva\ns-dxva-_dxva_coppstatusinput.md">DXVA_COPPStatusInput</a>
</dt>
<dt>
<a href="..\dxva\ns-dxva-_dxva_coppstatusoutput.md">DXVA_COPPStatusOutput</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVA_COPPStatusSignalingCmdData structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>