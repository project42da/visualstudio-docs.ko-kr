---
title: "[Content_types].xml 파일의 구조 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- content_types
- content types
- opc
- vsix
ms.assetid: 9c399598-b9fa-4da7-84b5-defbf82e9335
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f399cb0c88e044224d554cf8e17cc4d217498e87
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="the-structure-of-the-contenttypesxml-file"></a>[Content_types].xml 파일의 구조
VSIX 패키지의 콘텐츠 종류에 대 한 정보를 포함합니다. Visual Studio에서 [Content_Types].xml 파일을 사용 하 여 패키지를 설치 하지만 파일 자체를 설치 하지 않습니다.  
  
> [!NOTE]
>  [Content_Types].xml 파일 형식을의 일부인이 항목 VSIX 패키지에 사용 되는 [Content_Type].xml 파일에만 적용 되는 *열려 패키징 규칙 (OPC)* 표준입니다. 자세한 내용은 참조 [OPC: A 새 표준 데이터에 대 한 패키징 Your](http://go.microsoft.com/fwlink/?LinkID=148207) MSDN 웹 사이트에 있습니다.  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 루트 요소와 특성 및 자식 요소에 설명 합니다.  
  
### <a name="root-element"></a>루트 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`Types`|VSIX 패키지의 파일 형식을 열거 하는 자식 요소를 포함 합니다.|  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`Xmlns`|(필수) 이 [Content_Types].xml 파일에 사용 되는 스키마의 위치입니다.|  
  
### <a name="attribute-name-attribute"></a>{특성 name} 특성  
  
|값|설명|  
|-----------|-----------------|  
|http://schemas.openformats.org/package/2006/content-types|콘텐츠 형식 스키마의 위치입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 `Types` 요소 개수에 관계 없이 포함 될 수 있습니다 `Default` 요소입니다.  
  
|요소|설명|  
|-------------|-----------------|  
|`Default`|VSIX 패키지의 콘텐츠 형식에 설명합니다. 패키지에서 모든 파일 형식이 있어야 자체 `Default` 요소입니다.|  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`Extension`|VSIX 패키지에 있는 파일의 파일 이름 확장명입니다.|  
|`ContentType`|파일 이름 확장명으로 연결 된 콘텐츠를의 종류를 설명 합니다.|  
  
### <a name="attribute-name-attribute"></a>{특성 name} 특성  
 Visual Studio에서 다음 인식 `ContentType` 연결 된 작업에 대 한 값 `Extension` 형식입니다.  
  
|확장명|ContentType|  
|---------------|-----------------|  
|txt|텍스트/일반|  
|pkgdef|텍스트/일반|  
|xml|text/xml|  
|vsixmanifest|text/xml|  
|htm 또는 html|html 텍스트 /|  
|rtf|응용 프로그램/서식 있는 텍스트|  
|pdf|응용 프로그램/pdf|  
|gif|이미지/gif|  
|jpg 또는 jpeg|jpg 이미지 /|  
|tiff|tiff image /|  
|vsix|응용 프로그램/z i p|  
|zip|응용 프로그램/z i p|  
|dll|application/octet-stream|  
|다른 모든 파일 형식|application/octet-stream|  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>설명  
 다음 [Content_Types].xml 파일 일반적인 VSIX 패키지를 설명합니다.  
  
### <a name="code"></a>코드  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<Types xmlns="http://schemas.openxmlformats.org/package/2006/content-types">  
    <Default Extension="vsixmanifest" ContentType="text/xml" />   
    <Default Extension="dll" ContentType="application/octet-stream" />   
    <Default Extension="png" ContentType="application/octet-stream" />   
    <Default Extension="txt" ContentType="text/plain" />   
    <Default Extension="pkgdef" ContentType="text/plain" />   
</Types>  
```  
  
## <a name="see-also"></a>참고 항목  
 [VSIX 패키지 분석](../extensibility/anatomy-of-a-vsix-package.md)   
 [VSIX 확장 스키마 1.0 참조](http://msdn.microsoft.com/en-us/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)   
 [데이터를 패키지에 새로운 표준 OPC:](http://go.microsoft.com/fwlink/?LinkID=148207)