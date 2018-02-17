---
UID: NS:dxva._DXVA_COPPStatusData
title: "_DXVA_COPPStatusData"
author: windows-driver-content
description: The DXVA_COPPStatusData structure contains the status information returned from a query on a protected video session that is associated with a DirectX VA COPP device.
old-location: display\dxva_coppstatusdata.htm
old-project: display
ms.assetid: f459cfa7-9fda-4b46-9fc9-05bdc9e5c964
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: dxvaref_76d7144b-c4a7-4530-bf35-be9b9955c9d6.xml, display.dxva_coppstatusdata, dxva/DXVA_COPPStatusData, _DXVA_COPPStatusData, DXVA_COPPStatusData structure [Display Devices], DXVA_COPPStatusData
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
-	DXVA_COPPStatusData
product: Windows
targetos: Windows
req.typenames: DXVA_COPPStatusData
---

# _DXVA_COPPStatusData structure
The DXVA_COPPStatusData structure contains the status information returned from a query on a protected video session that is associated with a DirectX VA COPP device.

## Syntax
````
typedef struct _DXVA_COPPStatusData {
  GUID  rApp;
  ULONG dwFlags;
  ULONG dwData;
  ULONG ExtendedInfoValidMask;
  ULONG ExtendedInfoData;
} DXVA_COPPStatusData;
````

## Members


`dwData`

Specifies 32-bit status data that is returned from one of the following requests passed in the <i>pInput</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539652">COPPQueryStatus</a> function. 





#### DXVA_COPPQueryProtectionType

Returns a valid ORed combination of the following values that indicate the available types of protection mechanisms on the physical connector associated with a COPP device: 

<ul>
<li>
COPP_ProtectionType_Unknown (0x80000000)

</li>
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


#### DXVA_COPPQueryConnectorType

Returns one of the following values from the <b>COPP_ConnectorType</b> enumeration type that identifies the type of physical connector the video session uses:

<ul>
<li>
COPP_ConnectorType_Unknown (-1)

</li>
<li>
COPP_ConnectorType_VGA (0)

</li>
<li>
COPP_ConnectorType_SVideo (1)

</li>
<li>
COPP_ConnectorType_CompositeVideo (2)

</li>
<li>
COPP_ConnectorType_ComponentVideo (3)

</li>
<li>
COPP_ConnectorType_DVI (4)

</li>
<li>
COPP_ConnectorType_HDMI (5)

</li>
<li>
COPP_ConnectorType_LVDS (6)

</li>
<li>
COPP_ConnectorType_TMDS (7)

</li>
<li>
COPP_ConnectorType_D_JPN (8)

</li>
</ul>
The COPP_ConnectorType_Internal (0x80000000) value is only combined with one of the preceding connector-type values to indicate that the connection between the graphics adapter and display monitor is permanent and not accessible from the outside of a non-user-serviceable enclosure.



#### DXVA_COPPQueryLocalProtectionLevel

Returns the currently set protection level for the video session. The protection-level value depends on the protection type specified in the <b>StatusData</b> member of the <a href="..\dxva\ns-dxva-_dxva_coppstatusinput.md">DXVA_COPPStatusInput</a> structure. For possible protection levels, see the <b>ProtLevel</b> member of the <a href="..\dxva\ns-dxva-_dxva_coppsetprotectionlevelcmddata.md">DXVA_COPPSetProtectionLevelCmdData</a> structure. 



#### DXVA_COPPQueryGlobalProtectionLevel

Returns the currently set protection level for the physical connector. The level value returned must reflect the protection level currently applied through the connector, regardless of how the driver was instructed to apply the protection level. For example, if ACP was enabled through the Win32 <b>ChangeDisplaySettingsEx</b> function and not through the <b>IAMCertifiedOutputProtection</b> interface, the global protection level that was returned through a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539652">COPPQueryStatus</a> function for the connector must indicate that ACP was enabled, even though ACP was not enabled through the <b>IAMCertifiedOutputProtection</b> interface. 

The protection-level value depends on the protection type specified in the <b>StatusData</b> member of the <a href="..\dxva\ns-dxva-_dxva_coppstatusinput.md">DXVA_COPPStatusInput</a> structure. For possible protection levels, see the <b>ProtLevel</b> member of the <a href="..\dxva\ns-dxva-_dxva_coppsetprotectionlevelcmddata.md">DXVA_COPPSetProtectionLevelCmdData</a> structure. 



#### DXVA_COPPQueryBusData

Returns one of the following values from the <b>COPP_BusType</b> enumeration type that identifies the type of bus used by the graphics hardware associated with a COPP device:

<ul>
<li>
COPP_BusType_Unknown (0)

</li>
<li>
COPP_BusType_PCI (1)

</li>
<li>
COPP_BusType_PCIX (2)

</li>
<li>
COPP_BusType_PCIExpress (3)

</li>
<li>
COPP_BusType_AGP (4)

</li>
</ul>
The COPP_BusType_Integrated (0x80000000) value can only be combined with one of the preceding bus-type values when none of the command and status interface signals between the graphics adapter and other subsystems are available on an expansion bus that uses a publicly available specification and standard connector type. Memory buses are excluded from this definition.

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

Specifies additional 32-bit data for the status. Not currently used.

`ExtendedInfoValidMask`

Specifies a value that indicates the valid bitfields in the following <b>ExtendedInfoData</b> member.

`rApp`

Specifies a 128-bit random number that is used once. This random number is generated by the requesting application and supplied to the display driver in the <b>rApp</b> member of the <a href="..\dxva\ns-dxva-_dxva_coppstatusinput.md">DXVA_COPPStatusInput</a> structure.

## Remarks
The display driver returns status information through the <i>pOutput</i> parameter of <i>COPPQueryStatus</i>. The <a href="..\dxva\ns-dxva-_dxva_coppstatusoutput.md">DXVA_COPPStatusOutput</a> structure describes the returned status information. The display driver should cast the status information to a pointer to a DXVA_COPPStatusData structure and return the status information in the <b>COPPStatus</b> member of DXVA_COPPStatusOutput.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | This structure applies only to Windows Server 2003 with SP1 and later, and Windows XP with SP2 and later. This structure applies only to Windows Server 2003 with SP1 and later, and Windows XP with SP2 and later. |
| **Header** | dxva.h (include Dxva.h) |

## See Also

<a href="..\dxva\ns-dxva-_dxva_coppstatusoutput.md">DXVA_COPPStatusOutput</a>



<a href="..\dxva\ns-dxva-_dxva_coppsetprotectionlevelcmddata.md">DXVA_COPPSetProtectionLevelCmdData</a>



<a href="..\dxva\ns-dxva-_dxva_coppstatusinput.md">DXVA_COPPStatusInput</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539652">COPPQueryStatus</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVA_COPPStatusData structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>