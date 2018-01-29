---
UID : NE:ntddmmc._FEATURE_NUMBER
title : _FEATURE_NUMBER
author : windows-driver-content
description : The FEATURE_NUMBER enumeration provides a list of the features that are defined by the SCSI Multimedia - 4 (MMC-4) specification.
old-location : storage\feature_number.htm
old-project : storage
ms.assetid : f139da57-1527-476d-8e9f-0b96876adecf
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : FeatureDvdCSS, ntddmmc/PFEATURE_NUMBER, FeatureProfileList, FeatureDDCDRWWrite, FeatureEnhancedDefectReporting, FeatureTSR, ntddmmc/FeatureWriteProtect, FeatureCdrwCAVWrite, FeatureRigidRestrictedOverwrite, ntddmmc/FeatureCDRWMediaWriteSupport, ntddmmc/FeatureSectorErasable, ntddmmc/FeatureMrw, ntddmmc/FeatureLogicalUnitSerialNumber, PFEATURE_NUMBER enumeration pointer [Storage Devices], FeatureDvdPlusRDualLayer, ntddmmc/FeatureDvdPlusRWDualLayer, FeatureMediaSerialNumber, ntddmmc/FeatureDvdPlusR, FeatureRandomWritable, FeatureTimeout, ntddmmc/FeatureDiscControlBlocks, ntddmmc/FeatureCdrwCAVWrite, ntddmmc/FeatureCdRead, FeatureCdTrackAtOnce, FeatureCDAudioAnalogPlay, ntddmmc/FeatureMicrocodeUpgrade, ntddmmc/FeatureBDRPseudoOverwrite, ntddmmc/FeatureWriteOnce, ntddmmc/FeatureMultiRead, ntddmmc/FeatureIncrementalStreamingWritable, FeatureCdMastering, ntddmmc/FeatureDvdRecordableWrite, FEATURE_NUMBER, ntddmmc/FeatureHDDVDRead, ntddmmc/FeatureRandomWritable, ntddmmc/FeatureDvdPlusRW, structs-CD-ROM_6d75ed9b-8d13-4715-ae9a-51bc2a6025f0.xml, ntddmmc/FeatureMorphing, ntddmmc/FeatureFormattable, ntddmmc/FeatureRandomReadable, FeatureSectorErasable, FeatureLogicalUnitSerialNumber, FeatureCdRead, ntddmmc/FeatureCdTrackAtOnce, FeatureBDRead, ntddmmc/FeatureCdMastering, ntddmmc/FeatureLayerJumpRecording, ntddmmc/FeatureSMART, ntddmmc/FeatureAACS, FeatureRestrictedOverwrite, ntddmmc/FeatureBDRead, storage.feature_number, FeatureIncrementalStreamingWritable, ntddmmc/FeatureMediaSerialNumber, ntddmmc/FeatureRealTimeStreaming, ntddmmc/FeatureDDCDRWrite, ntddmmc/FeatureEmbeddedChanger, FeatureDefectManagement, FeaturePowerManagement, ntddmmc/FeatureBDWrite, FeatureRandomReadable, FeatureRealTimeStreaming, ntddmmc/FeatureCore, FeatureMrw, FeatureDvdCPRM, *PFEATURE_NUMBER, ntddmmc/FEATURE_NUMBER, ntddmmc/FeatureProfileList, FeatureWriteProtect, FeatureMultiRead, ntddmmc/FeatureVCPS, ntddmmc/FeatureTSR, ntddmmc/FeatureDvdCSS, FeatureDiscControlBlocks, ntddmmc/FeaturePowerManagement, FeatureVCPS, FeatureHDDVDRead, FeatureCore, PFEATURE_NUMBER, ntddmmc/FeatureDvdPlusRDualLayer, FEATURE_NUMBER enumeration [Storage Devices], FeatureRemovableMedium, FeatureSMART, FeatureEmbeddedChanger, ntddmmc/FeatureDDCDRead, FeatureHybridDisc, ntddmmc/FeatureHDDVDWrite, FeatureFirmwareDate, FeatureDvdRecordableWrite, FeatureHDDVDWrite, ntddmmc/FeatureRestrictedOverwrite, FeatureMorphing, ntddmmc/FeatureDefectManagement, ntddmmc/FeatureDvdCPRM, FeatureDvdPlusRWDualLayer, ntddmmc/FeatureDvdRead, FeatureFormattable, FeatureDvdPlusRW, ntddmmc/FeatureDDCDRWWrite, FeatureBDWrite, ntddmmc/FeatureRemovableMedium, ntddmmc/FeatureEnhancedDefectReporting, ntddmmc/FeatureHybridDisc, FeatureCDRWMediaWriteSupport, ntddmmc/FeatureCDAudioAnalogPlay, FeatureDvdPlusR, _FEATURE_NUMBER, FeatureDvdRead, FeatureBDRPseudoOverwrite, ntddmmc/FeatureFirmwareDate, ntddmmc/FeatureRigidRestrictedOverwrite, FeatureAACS, FeatureLayerJumpRecording, FeatureWriteOnce, FeatureMicrocodeUpgrade, FeatureDDCDRead, ntddmmc/FeatureTimeout, FeatureDDCDRWrite
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : ntddmmc.h
req.include-header : Ntddcdrm.h
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
req.typenames : FEATURE_NUMBER, *PFEATURE_NUMBER
---

# _FEATURE_NUMBER Enumeration
The FEATURE_NUMBER enumeration provides a list of the features that are defined by the <i>SCSI Multimedia - 4 (MMC-4)</i> specification.

## Syntax
````
typedef enum _FEATURE_NUMBER { 
  FeatureProfileList                   = 0x0000,
  FeatureCore                          = 0x0001,
  FeatureMorphing                      = 0x0002,
  FeatureRemovableMedium               = 0x0003,
  FeatureWriteProtect                  = 0x0004,
  FeatureRandomReadable                = 0x0010,
  FeatureMultiRead                     = 0x001D,
  FeatureCdRead                        = 0x001E,
  FeatureDvdRead                       = 0x001F,
  FeatureRandomWritable                = 0x0020,
  FeatureIncrementalStreamingWritable  = 0x0021,
  FeatureSectorErasable                = 0x0022,
  FeatureFormattable                   = 0x0023,
  FeatureDefectManagement              = 0x0024,
  FeatureWriteOnce                     = 0x0025,
  FeatureRestrictedOverwrite           = 0x0026,
  FeatureCdrwCAVWrite                  = 0x0027,
  FeatureMrw                           = 0x0028,
  FeatureEnhancedDefectReporting       = 0x0029,
  FeatureDvdPlusRW                     = 0x002A,
  FeatureDvdPlusR                      = 0x002B,
  FeatureRigidRestrictedOverwrite      = 0x002C,
  FeatureCdTrackAtOnce                 = 0x002D,
  FeatureCdMastering                   = 0x002E,
  FeatureDvdRecordableWrite            = 0x002F,
  FeatureDDCDRead                      = 0x0030,
  FeatureDDCDRWrite                    = 0x0031,
  FeatureDDCDRWWrite                   = 0x0032,
  FeatureLayerJumpRecording            = 0x0033,
  FeatureCDRWMediaWriteSupport         = 0x0037,
  FeatureBDRPseudoOverwrite            = 0x0038,
  FeatureDvdPlusRWDualLayer            = 0x003A,
  FeatureDvdPlusRDualLayer             = 0x003B,
  FeatureBDRead                        = 0x0040,
  FeatureBDWrite                       = 0x0041,
  FeatureTSR                           = 0x0042,
  FeatureHDDVDRead                     = 0x0050,
  FeatureHDDVDWrite                    = 0x0051,
  FeatureHybridDisc                    = 0x0080,
  FeaturePowerManagement               = 0x0100,
  FeatureSMART                         = 0x0101,
  FeatureEmbeddedChanger               = 0x0102,
  FeatureCDAudioAnalogPlay             = 0x0103,
  FeatureMicrocodeUpgrade              = 0x0104,
  FeatureTimeout                       = 0x0105,
  FeatureDvdCSS                        = 0x0106,
  FeatureRealTimeStreaming             = 0x0107,
  FeatureLogicalUnitSerialNumber       = 0x0108,
  FeatureMediaSerialNumber             = 0x0109,
  FeatureDiscControlBlocks             = 0x010A,
  FeatureDvdCPRM                       = 0x010B,
  FeatureFirmwareDate                  = 0x010C,
  FeatureAACS                          = 0x010D,
  FeatureVCPS                          = 0x0110
} FEATURE_NUMBER, *PFEATURE_NUMBER;
````

## Constants

<table>

<tr>
<td>FeatureAACS</td>
<td>Reserved 0x010e - 0x010f</td>
</tr>

<tr>
<td>FeatureBDRead</td>
<td></td>
</tr>

<tr>
<td>FeatureBDRPseudoOverwrite</td>
<td>Reserved 0x0039</td>
</tr>

<tr>
<td>FeatureBDWrite</td>
<td></td>
</tr>

<tr>
<td>FeatureCDAudioAnalogPlay</td>
<td>Indicates the feature named "CD Audio External Play" by the <i>MMC-3 </i>specification. Devices that support this feature can play CD audio data and channel it directly to an external output.</td>
</tr>

<tr>
<td>FeatureCdMastering</td>
<td>Indicates the feature named "CD Mastering" by the <i>MMC-3 </i>specification. Devices that support this feature can write to a CD in either "Session-at-Once" mode or raw mode.</td>
</tr>

<tr>
<td>FeatureCdRead</td>
<td>Indicates the feature named "CD Read" by the <i>MMC-3 </i>specification. Devices that support this feature can read CD-specific information from the media and can read user data from all types of CD blocks.</td>
</tr>

<tr>
<td>FeatureCdrwCAVWrite</td>
<td>Indicates the feature named "CD-RW CAV Write" by the <i>MMC-3 </i>specification. Devices that support this feature can perform writes on CD-RW media in CAV mode.</td>
</tr>

<tr>
<td>FeatureCDRWMediaWriteSupport</td>
<td></td>
</tr>

<tr>
<td>FeatureCdTrackAtOnce</td>
<td>Indicates the feature named "CD Track at Once" by the <i>MMC-3 </i>specification. Devices that support this feature can write data to a CD track.</td>
</tr>

<tr>
<td>FeatureCore</td>
<td>Indicates the feature named "Core" by the <i>MMC-3 </i>specification. This feature encompasses the basic functionality which is mandatory for all devices that support the <i>MMC-3</i> standard. See the <i>MMC-3</i> specification for a description of the capabilities included in the Core feature.</td>
</tr>

<tr>
<td>FeatureDDCDRead</td>
<td>Indicates the feature named "DDCD Read" by the <i>MMC-3 </i>specification. Devices that support this feature can read user data from DDCD blocks.</td>
</tr>

<tr>
<td>FeatureDDCDRWrite</td>
<td>Indicates the feature named "DDCD-R Write" by the <i>MMC-3 </i>specification. Devices that support this feature can read and write DDCD-R media.</td>
</tr>

<tr>
<td>FeatureDDCDRWWrite</td>
<td>Indicates the feature named "DDCD-RW Write" by the <i>MMC-3 </i>specification. Devices that support this feature can read and write DDCD-RW media.</td>
</tr>

<tr>
<td>FeatureDefectManagement</td>
<td>Indicates the feature named "Defect Management" by the <i>MMC-3 </i>specification. Devices that support this feature are able to provide contiguous address space that is guaranteed to be defect free.</td>
</tr>

<tr>
<td>FeatureDiscControlBlocks</td>
<td>Indicates the feature named "Disc Control Blocks" by the <i>MMC-3 </i>specification. Devices that support this feature can read or write Disc Control Blocks.</td>
</tr>

<tr>
<td>FeatureDvdCPRM</td>
<td>Indicates the feature named "DVD CPRM" by the <i>MMC-3 </i>specification. Devices that support this feature can perform DVD Content Protection for Recordable Media (CPRM) authentication and key management.</td>
</tr>

<tr>
<td>FeatureDvdCSS</td>
<td>Indicates the feature named "DVD-CSS" by the <i>MMC-3 </i>specification. Devices that support this feature can perform DVD Content Scrambling System (DVD-CSS) authentication and key management.</td>
</tr>

<tr>
<td>FeatureDvdPlusR</td>
<td></td>
</tr>

<tr>
<td>FeatureDvdPlusRDualLayer</td>
<td>Reserved 0x003c - 0x003f</td>
</tr>

<tr>
<td>FeatureDvdPlusRW</td>
<td>Indicates the feature named "DVD+RW" by the <i>MMC-3 </i>specification. Devices that support this feature can recognize, read and optionally write DVD+RW media.</td>
</tr>

<tr>
<td>FeatureDvdPlusRWDualLayer</td>
<td></td>
</tr>

<tr>
<td>FeatureDvdRead</td>
<td>Indicates the feature named "DVD Read" by the <i>MMC-3 </i>specification. Devices that support this feature can read DVD-specific information from the media.</td>
</tr>

<tr>
<td>FeatureDvdRecordableWrite</td>
<td>Indicates the feature named "DVD-R Write" by the <i>MMC-3 </i>specification. Devices that support this feature can write data to a write-once DVD media in "Disc-at-Once" mode.</td>
</tr>

<tr>
<td>FeatureEmbeddedChanger</td>
<td>Indicates the feature named "Embedded Changer" by the <i>MMC-3 </i>specification. Devices that support this feature can move media back and forth between a media storage area and the mechanism that actually accesses the media.</td>
</tr>

<tr>
<td>FeatureEnhancedDefectReporting</td>
<td></td>
</tr>

<tr>
<td>FeatureFirmwareDate</td>
<td></td>
</tr>

<tr>
<td>FeatureFormattable</td>
<td>Indicates the feature named "Formattable" by the <i>MMC-3 </i>specification. Devices that support this feature can format media into logical blocks.</td>
</tr>

<tr>
<td>FeatureHDDVDRead</td>
<td></td>
</tr>

<tr>
<td>FeatureHDDVDWrite</td>
<td>Reserved 0x0052 - 0x007f</td>
</tr>

<tr>
<td>FeatureHybridDisc</td>
<td>Reserved 0x0081 - 0x00ff</td>
</tr>

<tr>
<td>FeatureIncrementalStreamingWritable</td>
<td>Indicates the feature named "Incremental Streaming Writable" by the <i>MMC-3 </i>specification. Devices that support this feature can append data to a limited number of locations on the media.</td>
</tr>

<tr>
<td>FeatureLayerJumpRecording</td>
<td>Reserved 0x0034 - 0x0036</td>
</tr>

<tr>
<td>FeatureLogicalUnitSerialNumber</td>
<td>Indicates the feature named "Device Serial Number" by the <i>MMC-3 </i>specification. Devices that support this feature can furnish the initiator with a serial number that uniquely identifies the device.</td>
</tr>

<tr>
<td>FeatureMediaSerialNumber</td>
<td></td>
</tr>

<tr>
<td>FeatureMicrocodeUpgrade</td>
<td>Indicates the feature named "Microcode Upgrade" by the <i>MMC-3 </i>specification. Devices that support this feature can upgrade their internal microcode by means of a published interface.</td>
</tr>

<tr>
<td>FeatureMorphing</td>
<td>Indicates the feature named "Morphing" by the <i>MMC-3 </i>specification. Devices that support this feature can notify the initiator of operational changes and allow the initiator to prevent operational changes.</td>
</tr>

<tr>
<td>FeatureMrw</td>
<td>Indicates the feature named "MRW" by the <i>MMC-3 </i>specification. Devices that support this feature can recognize, read and optionally write MRW formatted media.</td>
</tr>

<tr>
<td>FeatureMultiRead</td>
<td>Indicates the feature named "MultiRead," originally defined by the Optical Storage Technology Association (OSTA) and incorporated into the <i>MMC-3 </i>specification. Devices that support this feature can read all CD media types.</td>
</tr>

<tr>
<td>FeaturePowerManagement</td>
<td>Indicates the feature named "Power Management" by the <i>MMC-3 </i>specification. Devices that support this feature can perform both initiator and logical-unit directed power management.</td>
</tr>

<tr>
<td>FeatureProfileList</td>
<td>Indicates the feature named "Profile List" by the <i>MMC-3 </i>specification. This feature provides a list of all profiles supported by the device.</td>
</tr>

<tr>
<td>FeatureRandomReadable</td>
<td>Indicates the feature named "Random Readable" by the <i>MMC-3 </i>specification. Devices that support this feature allow the initiator to read blocks of data on the disk at random locations. These devices do not require that the initiator address disk locations in any particular order.</td>
</tr>

<tr>
<td>FeatureRandomWritable</td>
<td>Indicates the feature named "Random Writable" by the <i>MMC-3 </i>specification. Devices that support this feature can write blocks of data to random locations on the disk. These devices do not require that the initiator address disk locations in any particular order.</td>
</tr>

<tr>
<td>FeatureRealTimeStreaming</td>
<td>Indicates the feature named "Real Time Streaming" by the <i>MMC-3 </i>specification. Devices that support this feature allow the initiator to specify the performance level of the device within certain limits allowed by the device. These devices must also indicate to the initiator whether they support stream playback operations.</td>
</tr>

<tr>
<td>FeatureRemovableMedium</td>
<td>Indicates the feature named "Removable Medium" by the <i>MMC-3 </i>specification. Devices that support this feature allow the medium to be removed from the device. They also can communicate to the initiator that the user wants to eject the medium or has inserted a new medium.</td>
</tr>

<tr>
<td>FeatureRestrictedOverwrite</td>
<td>Indicates the feature named "Restricted Overwrite" by the <i>MMC-3 </i>specification. Devices that support this feature are limited in regard to which logical blocks they can overwrite at any given time.</td>
</tr>

<tr>
<td>FeatureRigidRestrictedOverwrite</td>
<td>Indicates the feature named "DVD-RW Restricted Overwrite" by the <i>MMC-3 </i>specification. Devices that support this feature can only write on block boundaries. These devices cannot perform read or write operations that transfer less than a block of data.</td>
</tr>

<tr>
<td>FeatureSectorErasable</td>
<td>Indicates the feature named "Sector Erasable" by the <i>MMC-3 </i>specification. Devices that support this feature require an erase pass before overwriting existing data.</td>
</tr>

<tr>
<td>FeatureSMART</td>
<td>Indicates the feature named "S.M.A.R.T." by the <i>MMC-3 </i>specification. Devices that support this feature support Self-Monitoring Analysis and Reporting Technology (SMART).</td>
</tr>

<tr>
<td>FeatureTimeout</td>
<td>Indicates the feature named "Time-Out" by the <i>MMC-3 </i>specification. Devices that have this feature must respond to commands within a set time period. When these devices cannot complete commands in the allotted time, they complete the commands with an error.</td>
</tr>

<tr>
<td>FeatureTSR</td>
<td>Reserved 0x0043 - 0x004f</td>
</tr>

<tr>
<td>FeatureVCPS</td>
<td>Reserved 0x0111 - 0xfeff</td>
</tr>

<tr>
<td>FeatureWriteOnce</td>
<td>Indicates the feature named "Write Once" by the <i>MMC-3 </i>specification. Devices that support this feature can write to any previously unused logical block.</td>
</tr>

<tr>
<td>FeatureWriteProtect</td>
<td>Indicates the feature named "Write Protect" by the <i>MMC-3 </i>specification. Devices that support this feature allow the initiator to change the write-protection state of the media programmatically.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddmmc.h (include Ntddcdrm.h) |

## See Also

<a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FEATURE_NUMBER enumeration%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>