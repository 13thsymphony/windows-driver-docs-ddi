---
UID: NE:pointofservicecommontypes._BarcodeSymbology
title: _BarcodeSymbology
author: windows-driver-content
description: This enumeration defines the barcode symbologies.
old-location: pos\barcodesymbology.htm
old-project: pos
ms.assetid: d0c66bde-cd66-4141-b985-8eb28af70a3b
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _BarcodeSymbology, BarcodeSymbology
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: pointofservicecommontypes.h
req.include-header: Pointofservicecommontypes.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: BarcodeSymbology
req.alt-loc: pointofservicecommontypes.h
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
req.typenames: BarcodeSymbology
---

# _BarcodeSymbology enumeration



## -description
This enumeration defines the barcode symbologies.



## -syntax

````
typedef enum _BarcodeSymbology { 
  PosUnknown        = 0,
  Ean8              = 101,
  Ean8Add2          = 102,
  Ean8Add5          = 103,
  Eanv              = 104,
  EanvAdd2          = 105,
  EanvAdd5          = 106,
  Ean13             = 107,
  Ean13Add2         = 108,
  Ean13Add5         = 109,
  Isbn              = 110,
  IsbnAdd5          = 111,
  Ismn              = 112,
  IsmnAdd2          = 113,
  IsmnAdd5          = 114,
  Issn              = 115,
  IssnAdd2          = 116,
  IssnAdd5          = 117,
  Ean99             = 118,
  Ean99Add2         = 119,
  Ean99Add5         = 120,
  Upca              = 121,
  UpcaAdd2          = 122,
  UpcaAdd5          = 123,
  Upce              = 124,
  UpceAdd2          = 125,
  UpceAdd5          = 126,
  UpcCoupon         = 127,
  TfStd             = 128,
  TfDis             = 129,
  TfInt             = 130,
  TfInd             = 131,
  TfMat             = 132,
  TfIata            = 133,
  Gs1DatabarType1   = 134,
  Gs1DatabarType2   = 135,
  Gs1DatabarType3   = 136,
  Code39            = 137,
  Code39Ex          = 138,
  Trioptic39        = 139,
  Code32            = 140,
  Pzn               = 141,
  Code93            = 142,
  Code93Ex          = 143,
  Code128           = 144,
  Gs1128            = 145,
  Gs1128Coupon      = 146,
  UccEan128         = 147,
  Sisac             = 148,
  Isbt              = 149,
  Codabar           = 150,
  Code11            = 151,
  Msi               = 152,
  Plessey           = 153,
  Telepen           = 154,
  Code16k           = 155,
  CodablockA        = 156,
  CodablockF        = 157,
  Codablock128      = 158,
  Code49            = 159,
  Aztec             = 160,
  DataCode          = 161,
  DataMatrix        = 162,
  HanXin            = 163,
  Maxicode          = 164,
  MicroPdf417       = 165,
  MicroQr           = 166,
  Pdf417            = 167,
  Qr                = 168,
  MsTag             = 169,
  Ccab              = 170,
  Ccc               = 171,
  Tlc39             = 172,
  AusPost           = 173,
  CanPost           = 174,
  ChinaPost         = 175,
  DutchKix          = 176,
  InfoMail          = 177,
  ItalianPost25     = 178,
  ItalianPost39     = 179,
  JapanPost         = 180,
  KoreanPost        = 181,
  SwedenPost        = 182,
  UkPost            = 183,
  UsIntelligent     = 184,
  UsIntelligentPkg  = 185,
  UsPlanet          = 186,
  UsPostNet         = 187,
  Us4StateFics      = 188,
  OcrA              = 189,
  OcrB              = 190,
  Micr              = 191,
  Gs1DWCode         = 192,
  ExtendedBase
} BarcodeSymbology;
````


## -enum-fields

### -field PosUnknown

Unknown symbology.


### -field Ean8

The European Article Number (EAN) 8-digit symbology. Used on very small retail items, most commonly used in Europe and Australia. 


### -field Ean8Add2

The EAN 8 with 2-digit supplement symbology.


### -field Ean8Add5

The EAN 8 with 2-digit supplement symbology. 


### -field Eanv

The EAN Velocity symbology. 


### -field EanvAdd2

The EAN Velocity with 2-digit supplement symbology. 


### -field EanvAdd5

The EAN Velocity with 5-digit supplement symbology. 


### -field Ean13

The EAN 13 symbology most commonly used in Europe and Australia for numbering retail products. 


### -field Ean13Add2

The EAN with 2-digit supplement symbology. 


### -field Ean13Add5

The EAN with 5-digit supplement symbology. 


### -field Isbn

The International Standard Book Number (ISBN), also known as Bookland or Bookland EAN, symbology. 


### -field IsbnAdd5

The ISBN with 5_digit supplement symbology. 


### -field Ismn

The International Standard Music Number (ISMN) symbology. 


### -field IsmnAdd2

The ISMN with 2_digit supplement symbology. 


### -field IsmnAdd5

The ISMN with 5_digit supplement symbology. 


### -field Issn

The International Standard Serial Number (ISSN) symbology. 


### -field IssnAdd2

The ISSN with 2_digit supplement symbology. 


### -field IssnAdd5

The ISSN with 5_digit supplement symbology. 


### -field Ean99

The EAN99 symbology, a variation of EAN13 with country code 99 used for store coupons. 


### -field Ean99Add2

The EAN99 with 2_digit supplement symbology. 


### -field Ean99Add5

The EAN99 with 5_digit supplement symbology. 


### -field Upca

The Universal Product Code (UPC) version A symbology, a 12-digit universal product code used on most retail items sold in the United States of America and Canada. 


### -field UpcaAdd2

The UPCA with 2-digit supplemental symbology. 


### -field UpcaAdd5

The UPCA with 5-digit supplemental symbology. 


### -field Upce

The UPC version E symbology, a smaller version of the UPC-A code for use on small products. 


### -field UpceAdd2

The UPC-E with 2-digit supplement symbology. 


### -field UpceAdd5

The UPC-E with 5-digit supplemental symbology. 


### -field UpcCoupon

The UPC Coupon with supplemental symbology. 


### -field TfStd

The Standard 2 of 5 symbology. 


### -field TfDis

The Discreet 2 of 5 symbology. 


### -field TfInt

The Interleaved 2 of 5 (ITF) symbology, developed for the use on outer cartons or cases containing a number of identical retail products. 


### -field TfInd

The Industrial 2 of 5 symbology. 


### -field TfMat

The 2 of 5 Matrix symbology. 


### -field TfIata

The 2 of 5 International Air Transportation Association (IATA) symbology. 


### -field Gs1DatabarType1

The GS1 Databar Omnidirectional, GS1 Databar Stacked Omnidirectional, GS1 Databar Stacked, or GS1 Databar Truncated symbology. 


### -field Gs1DatabarType2

The GS1 DataBar Limited or RSS Limited symbology. 


### -field Gs1DatabarType3

The GS1 Databar Expanded, GS1 Databar Expanded Stacked, or RSS Expanded symbology. 


### -field Code39

Symbology used worldwide, for instance by the United States Department of Defense and the Health Industry Bar Code Council (also known as Code 3 of 9, LOGMARS, USS Code 39, USS 39, USD-3, and 3 of 9). 


### -field Code39Ex

The Code 39 Extended symbology. Adds full ASCII support. 


### -field Trioptic39

The Trioptic39 symbology is used for Tri-Optic media storage devices. 


### -field Code32

The Italian pharmacy code symbology; a variant of Code32. 


### -field Pzn

The Pharma-Zentral-Nummer symbology. 


### -field Code93

The Code93 symbology. 


### -field Code93Ex

The Code93 extended symbology. 


### -field Code128

The Code128 symbology is one of the most commonly used world-wide because of its high capability and reliability. 


### -field Gs1128

These symbologies are of the most complex type, and are utilized for internal rather than retail use. They are intended to include both identification and supplementary information within one symbology. The EAN-128 is used to represent Serial Shipping Container Codes (AI=00). 


### -field Gs1128Coupon

The Gs128Coupon symbology. 


### -field UccEan128

Duplicate of GS1 128 (UCC/EAN is the old Name for GS1 128). 


### -field Sisac

The Serials Industry Systems Advisory Committee (SISAC) symbology. 


### -field Isbt

The International Society of Blood Transfusion symbology. 


### -field Codabar

This is an older type of barcode most often seen in libraries, blood banks, photo labs and FedEx air bills. 


### -field Code11

This symbology is used for labeling telecommunications equipment. 


### -field Msi

This symbology was developed by MSI Data Corporation, also known as Modified Plessey. Used to mark retail shelves for inventory control. 


### -field Plessey

The Plessey symbology, a continuous, arbitrary length barcode symbology for encoding hexadecimal data. 


### -field Telepen

The Telepen symbology. 


### -field Code16k

The Code16k symbology. 


### -field CodablockA

The CodablockA symbology. For more information, see the Association for Automatic Identification and Mobility(AIM) specification(http://www.aimglobal.org/).


### -field CodablockF

The CodablockF symbology. 


### -field Codablock128

The Codablock128 symbology. 


### -field Code49

The Code49 symbology contains between 2 and 8 rows, each separated by a separator bar. Each row contains 16 wordsand a start and stop character. The last row also contains the number of rows in the symbol and the check digit characters. 


### -field Aztec

The Aztec symbology. For more information, see <a href="http://go.microsoft.com/fwlink/p/?LinkId=317296">ISO Spec 24778</a>. 


### -field DataCode

The DataCode symbology. 


### -field DataMatrix

This symbology is good for small codes and will store large amounts of data. For more information, see <a href="http://go.microsoft.com/fwlink/p/?LinkID=317298">ISO Spec 16022</a>. 


### -field HanXin

The HanXin symbology. For more information, see the Association for Automatic Identification and Mobility (AIM) specification (http://www.aimglobal.org/).


### -field Maxicode

This symbology is used for the United States Postal Service and is fixed length for automatic package sorting. 


### -field MicroPdf417

The MicroPdf417 symbology. For more information, see <a href="http://go.microsoft.com/fwlink/p/?LinkId=317299">ISO Spec 24728</a>. 


### -field MicroQr

The MicroQr symbology, a subset of the QR symbology. For more information, see <a href="http://go.microsoft.com/fwlink/p/?LinkId=317300">ISO Spec 18004</a>. 


### -field Pdf417

The Pdf417 symbology. For more information, see <a href="http://go.microsoft.com/fwlink/p/?LinkId=317299">ISO Spec 24728</a>. 


### -field Qr

The Qr symbology. For more information, see <a href="http://go.microsoft.com/fwlink/p/?LinkId=317300">ISO Spec 18004</a>. 


### -field MsTag

The Microsoft symbology. 


### -field Ccab

The Composite A / Composite B symbology. 


### -field Ccc

The Composite C symbology. 


### -field Tlc39

The Telecommunications Industry Forum linked symbology. 


### -field AusPost

The Australian Post symbology. 


### -field CanPost

The Canadian Postal Service symbology. 


### -field ChinaPost

The Chinese Postal Service symbology. 


### -field DutchKix

The Dutch Postal Service symbology. 


### -field InfoMail

The InfoMail symbology. 


### -field ItalianPost25

The Italian Postal Service 2 of 5 symbology. 


### -field ItalianPost39

The Italian Postal Service 3 of 9 symbology. 


### -field JapanPost

The Japanese Postal Service symbology. 


### -field KoreanPost

The Korean Postal Service symbology. 


### -field SwedenPost

The Swedish Postal Service symbology. 


### -field UkPost

The British Post Office symbology. Also known as UK Postal, BPO4, Royal Mail Code. 


### -field UsIntelligent

The United States Postal Service (USPS) Intelligent Mail symbology. 


### -field UsIntelligentPkg

The United States Postal Service (USPS) Intelligent Package symbology. 


### -field UsPlanet

The US Postal Alpha Numeric Encoding Technique, used by the USPS). 


### -field UsPostNet

The United States Postal Service symbology used to automatically sort mail. 


### -field Us4StateFics

The US 4-State Flat Identification Code Sort symbology. 


### -field OcrA

The OCR-A symbology. OCR-A is a widely used font in a variety of industries. The characters appear more block-like than other OCR fonts. The characters are printed in a format that can be read by both machines and humans and can be directly marked on parts. For more information, see the <a href="http://go.microsoft.com/fwlink/p/?LinkId=317306">ISO 1073-1 specification</a>. 


### -field OcrB

The OCR-B symbology is a widely used font in conjunction with UPC/EAN symbology. For more information, see the <a href="http://go.microsoft.com/fwlink/p/?LinkId=317306">ISO 1073-1 specification</a>. 


### -field Micr

The Micr symbology, a font commonly used in high speed document processing applications, such as check processing. 


### -field Gs1DWCode

The Gs1DWCode symbology, an invisible  digital watermark that  covers the entire product packaging and can be detected by a special algorithm using an image from a suitable camera lens.


### -field ExtendedBase

If greater than or equal to this type, the device has returned an OEM or undefined symbology. 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Pointofservicecommontypes.h (include Pointofservicecommontypes.h)</dt>
</dl>
</td>
</tr>
</table>