---
UID: NE:ntddk._WHEA_RAW_DATA_FORMAT
title: "_WHEA_RAW_DATA_FORMAT"
author: windows-driver-content
description: The WHEA_RAW_DATA_FORMAT enumeration defines the possible formats that raw hardware error data can be encoded in a hardware error packet.
old-location: whea\whea_raw_data_format.htm
old-project: whea
ms.assetid: 809f2d72-e769-48c1-9ecf-6fa9020f6cdb
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: WheaRawDataFormatIPFSalRecord, ntddk/WHEA_RAW_DATA_FORMAT, ntddk/WheaRawDataFormatAMD64MCA, WheaRawDataFormatGeneric, ntddk/WheaRawDataFormatMemory, WheaRawDataFormatIntel64MCA, ntddk/WheaRawDataFormatIPFSalRecord, ntddk/WheaRawDataFormatNMIPort, *PWHEA_RAW_DATA_FORMAT, WheaRawDataFormatAMD64MCA, WheaRawDataFormatPCIXBus, whearef_9ecb0580-4372-40f3-93da-4f866ee6211f.xml, WheaRawDataFormatMax, ntddk/WheaRawDataFormatIA32MCA, WHEA_RAW_DATA_FORMAT enumeration [WHEA Drivers and Applications], WHEA_RAW_DATA_FORMAT, WheaRawDataFormatNMIPort, WheaRawDataFormatPCIExpress, WheaRawDataFormatMemory, _WHEA_RAW_DATA_FORMAT, ntddk/WheaRawDataFormatPCIXDevice, WheaRawDataFormatIA32MCA, WheaRawDataFormatPCIXDevice, PWHEA_RAW_DATA_FORMAT enumeration pointer [WHEA Drivers and Applications], ntddk/WheaRawDataFormatPCIExpress, ntddk/WheaRawDataFormatMax, ntddk/WheaRawDataFormatPCIXBus, PWHEA_RAW_DATA_FORMAT, ntddk/PWHEA_RAW_DATA_FORMAT, whea.whea_raw_data_format, ntddk/WheaRawDataFormatGeneric, ntddk/WheaRawDataFormatIntel64MCA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddk.h
apiname:
-	WHEA_RAW_DATA_FORMAT
product: Windows
targetos: Windows
req.typenames: "*PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT"
---

# _WHEA_RAW_DATA_FORMAT Enumeration
The WHEA_RAW_DATA_FORMAT enumeration defines the possible formats that raw hardware error data can be encoded in a hardware error packet.

## Syntax
````
typedef enum _WHEA_RAW_DATA_FORMAT { 
  WheaRawDataFormatIPFSalRecord  = 0x00,
  WheaRawDataFormatIA32MCA,
  WheaRawDataFormatIntel64MCA,
  WheaRawDataFormatAMD64MCA,
  WheaRawDataFormatMemory,
  WheaRawDataFormatPCIExpress,
  WheaRawDataFormatNMIPort,
  WheaRawDataFormatPCIXBus,
  WheaRawDataFormatPCIXDevice,
  WheaRawDataFormatGeneric,
  WheaRawDataFormatMax
} WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT;
````

## Constants

<table>
            
                <tr>
                    <td>WheaRawDataFormatAMD64MCA</td>
                    <td>The raw data in the hardware error packet contains an MCA_EXCEPTION structure. For more information about the MCA_EXCEPTION structure, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540659">HalQuerySystemInformation</a>.</td>
                </tr>
            
                <tr>
                    <td>WheaRawDataFormatGeneric</td>
                    <td>The raw data in the hardware error packet contains a <a href="..\ntddk\ns-ntddk-_whea_generic_error.md">WHEA_GENERIC_ERROR</a> structure.</td>
                </tr>
            
                <tr>
                    <td>WheaRawDataFormatIA32MCA</td>
                    <td>The raw data in the hardware error packet contains an MCA_EXCEPTION structure. For more information about the MCA_EXCEPTION structure, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540659">HalQuerySystemInformation</a>.</td>
                </tr>
            
                <tr>
                    <td>WheaRawDataFormatIntel64MCA</td>
                    <td>The raw data in the hardware error packet contains an MCA_EXCEPTION structure. For more information about the MCA_EXCEPTION structure, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540659">HalQuerySystemInformation</a>.</td>
                </tr>
            
                <tr>
                    <td>WheaRawDataFormatIPFSalRecord</td>
                    <td>The raw data in the hardware error packet contains an Itanium processor family system abstraction layer (SAL) error record. For more information about the format of a SAL error record, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=72212">Intel Itanium Processor Family System Abstraction Layer Specification</a>.</td>
                </tr>
            
                <tr>
                    <td>WheaRawDataFormatMax</td>
                    <td>The maximum number of formats of raw hardware error data.</td>
                </tr>
            
                <tr>
                    <td>WheaRawDataFormatMemory</td>
                    <td>The raw data in the hardware error packet contains memory error data. The format of this error data is memory architecture-dependent.</td>
                </tr>
            
                <tr>
                    <td>WheaRawDataFormatNMIPort</td>
                    <td>The raw data in the hardware error packet contains the data that was read from the nonmaskable interrupt (NMI) I/O ports by the NMI low-level hardware error handler (LLHEH).</td>
                </tr>
            
                <tr>
                    <td>WheaRawDataFormatPCIExpress</td>
                    <td>The raw data in the hardware error packet contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537457">PCI_EXPRESS_AER_CAPABILITY</a> structure.</td>
                </tr>
            
                <tr>
                    <td>WheaRawDataFormatPCIXBus</td>
                    <td>The raw data in the hardware error packet contains PCI/PCI-X bus error data. The format of this error data is specific to the implementation.</td>
                </tr>
            
                <tr>
                    <td>WheaRawDataFormatPCIXDevice</td>
                    <td>The raw data in the hardware error packet contains a PCI/PCI-X device error data. The format of this error data is specific to the implementation.</td>
                </tr>
</table>

## Remarks

The <a href="..\ntddk\ns-ntddk-_whea_error_packet_v1.md">WHEA_ERROR_PACKET_V1</a> structure contains a member of type WHEA_RAW_DATA_FORMAT that specifies the format of the raw data that is contained in the hardware error packet.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows. Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows. |
| **Header** | ntddk.h (include Ntddk.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540659">HalQuerySystemInformation</a>



<a href="..\ntddk\ns-ntddk-_whea_generic_error.md">WHEA_GENERIC_ERROR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537457">PCI_EXPRESS_AER_CAPABILITY</a>



<a href="..\ntddk\ns-ntddk-_whea_error_packet_v1.md">WHEA_ERROR_PACKET_V1</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_RAW_DATA_FORMAT enumeration%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>