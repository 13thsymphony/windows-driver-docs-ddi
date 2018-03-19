---
UID: NS:ntddscsi._SCSI_ADAPTER_BUS_INFO
title: "_SCSI_ADAPTER_BUS_INFO"
author: windows-driver-content
description: The SCSI_ADAPTER_BUS_INFO structure is used in conjunction with the IOCTL_SCSI_GET_INQUIRY_DATA request to retrieve the SCSI inquiry data for all devices on a given SCSI bus.
old-location: storage\scsi_adapter_bus_info.htm
old-project: storage
ms.assetid: 786d6813-a9f3-437e-9b41-d69e0fce9a4c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PSCSI_ADAPTER_BUS_INFO, PSCSI_ADAPTER_BUS_INFO, PSCSI_ADAPTER_BUS_INFO structure pointer [Storage Devices], SCSI_ADAPTER_BUS_INFO, SCSI_ADAPTER_BUS_INFO structure [Storage Devices], _SCSI_ADAPTER_BUS_INFO, ntddscsi/PSCSI_ADAPTER_BUS_INFO, ntddscsi/SCSI_ADAPTER_BUS_INFO, storage.scsi_adapter_bus_info, structs-scsibus_f21bd933-bcbc-48b5-8904-845712ce226f.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddscsi.h
req.include-header: Ntddscsi.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddscsi.h
api_name:
-	SCSI_ADAPTER_BUS_INFO
product: Windows
targetos: Windows
req.typenames: SCSI_ADAPTER_BUS_INFO, *PSCSI_ADAPTER_BUS_INFO
---

# _SCSI_ADAPTER_BUS_INFO structure
The SCSI_ADAPTER_BUS_INFO structure is used in conjunction with the <a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_get_inquiry_data.md">IOCTL_SCSI_GET_INQUIRY_DATA</a> request to retrieve the SCSI inquiry data for all devices on a given SCSI bus. 
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax
````
typedef struct _SCSI_ADAPTER_BUS_INFO {
  UCHAR         NumberOfBuses;
  SCSI_BUS_DATA BusData[1];
} SCSI_ADAPTER_BUS_INFO, *PSCSI_ADAPTER_BUS_INFO;
````

## Members


`NumberOfBuses`

Contains the number of buses on the adapter for which inquiry data is being reported.

`BusData`

Contains a variable length array of <a href="..\ntddscsi\ns-ntddscsi-_scsi_bus_data.md">SCSI_BUS_DATA</a> structures that hold the inquiry data.

## Remarks
SCSI_ADAPTER_BUS_INFO is a header structure that describes the layout of the output buffer of the <a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_get_inquiry_data.md">IOCTL_SCSI_GET_INQUIRY_DATA</a> request. This request returns SCSI inquiry data for all of the logical units on all of the buses associated with a particular SCSI host bus adapter (HBA). The <b>BusData</b> member of SCSI_ADAPTER_BUS_INFO contains a variable length array of <a href="..\ntddscsi\ns-ntddscsi-_scsi_bus_data.md">SCSI_BUS_DATA</a> structures. This array has one element for each SCSI bus on the adapter, so its size is equal to the number of buses indicated in the <b>NumberOfBuses</b> member of SCSI_ADAPTER_BUS_INFO. 

In most cases, <b>NumberOfBuses</b> will have a value of 1. Early SCSI buses were limited to 36 targets (rather than the current limit of 128), so some vendors manufactured HBAs with several buses, in order to increase the maximum number of targets. To support these older HBAs, Windows provides a mechanism for retrieving inquiry data from HBAs with multiple buses. For adapters with a single bus, <b>NumberOfBuses</b> will be one, and the <b>BusData</b> member of SCSI_ADAPTER_BUS_INFO will have only one element, but HBAs with multiple buses will generate data for multiple SCSI_BUS_DATA structures, and <b>NumberOfBuses</b> will be greater than 1.

Immediately following the array in <b>BusData</b> is the inquiry data for all of the devices on all the buses that belong to the HBA. The <b>InquiryDataOffset</b> member of each SCSI_BUS_DATA structure provides an offset to the inquiry data for the corresponding SCSI bus. 

The inquiry data for each SCSI bus includes information about all of the logical units on that bus. Each logical unit's inquiry data is formatted in a structure of type <a href="..\ntddscsi\ns-ntddscsi-_scsi_inquiry_data.md">SCSI_INQUIRY_DATA</a>, and all of the SCSI_INQUIRY_DATA structures for a particular bus are linked together by the <b>NextInquiryDataOffset</b> member. There will be a separate list for each SCSI bus, and the <b>NextInquiryDataOffset</b> member of the last structure in each list contains a value of zero. 

The following pseudocode example illustrates how to step through the SCSI buses on an HBA, and the logical units for each bus, reading and printing the inquiry data for each logical unit:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
PrintInquiryData(PCHAR  DataBuffer)
{
    PSCSI_ADAPTER_BUS_INFO  adapterInfo;
    PSCSI_INQUIRY_DATA inquiryData;
    ULONG i, j;

    adapterInfo = (PSCSI_ADAPTER_BUS_INFO) DataBuffer;
    for (i = 0; i &lt; adapterInfo-&gt;NumberOfBuses; i++) {
       inquiryData = (PSCSI_INQUIRY_DATA) (DataBuffer +
          adapterInfo-&gt;BusData[i].InquiryDataOffset);
       while (adapterInfo-&gt;BusData[i].InquiryDataOffset) {
          printf(" %d   %d  %3d    %s    %.28s ",
             i,
             inquiryData-&gt;TargetId,
             inquiryData-&gt;Lun,
             (inquiryData-&gt;DeviceClaimed) ? "Y" : "N",
             &amp;inquiryData-&gt;InquiryData[8]);
          for (j = 0; j &lt; 8; j++) {
             printf("%02X ", inquiryData-&gt;InquiryData[j]);
          }
          printf("\n");
          if (inquiryData-&gt;NextInquiryDataOffset == 0) {
             break;
          }
          inquiryData = (PSCSI_INQUIRY_DATA) (DataBuffer +
             inquiryData-&gt;NextInquiryDataOffset);
       }
    }
    printf("\n\n");
}</pre>
</td>
</tr>
</table></span></div>
You must use <b>NextInquiryDataOffset</b> member to locate the inquiry data for next logical unit. Do not try to do this by pointer arithmetic. The positioning of each SCSI_INQUIRY_DATA structure is potentially different for each HBA miniport driver, because it depends on data alignment requirements.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddscsi.h (include Ntddscsi.h) |

## See Also

<a href="..\ntddscsi\ns-ntddscsi-_scsi_inquiry_data.md">SCSI_INQUIRY_DATA</a>



<a href="..\ntddscsi\ns-ntddscsi-_scsi_bus_data.md">SCSI_BUS_DATA</a>



<a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_get_inquiry_data.md">IOCTL_SCSI_GET_INQUIRY_DATA</a>