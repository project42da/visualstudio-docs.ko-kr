---
title: "[Content_types].xml 파일의 구조 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- content_types
- content types
- opc
- vsix
ms.assetid: 9c399598-b9fa-4da7-84b5-defbf82e9335
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 7278fb37984b92a6a07823c552db5c59a446d0d2
ms.openlocfilehash: 6f45707a88a27fa54840825d9562f859385ce4b7
ms.lasthandoff: 02/22/2017

---
# <a name="the-structure-of-the-contenttypesxml-file"></a>[Content_types].xml 파일의 구조
VSIX 패키지에는 콘텐츠의 종류에 대 한 정보를 포함합니다. Visual Studio 패키지를 설치 하려면 [Content_Types].xml 파일을 사용 하지만 자체 파일을 설치 하지 않습니다.  
  
> [!NOTE]
>  [Content_Types].xml 파일 형식을의 일부인이 항목 VSIX 패키지에 사용 되는 [Content_Type].xml 파일에만 적용 되는 *규칙 OPC (Open Packaging)* 표준입니다. 자세한 내용은 참조 [OPC: A 새 표준 데이터에 대 한 패키징 Your](http://go.microsoft.com/fwlink/?LinkID=148207) MSDN 웹 사이트의.  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 루트 요소와 특성 및 자식 요소에 설명 합니다.  
  
### <a name="root-element"></a>루트 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`Types`|VSIX 패키지의 파일 형식을 열거 하는 자식 요소가 포함 되어 있습니다.|  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`Xmlns`|(필수) 이 [Content_Types].xml 파일에 대해 사용 되는 스키마의 위치입니다.|  
  
### <a name="attribute-name-attribute"></a>{특성 이름} 특성  
  
|값|설명|  
|-----------|-----------------|  
|http://schemas.openformats.org/package/2006/content-types|콘텐츠 형식 스키마의 위치입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 `Types` 요소 개수에 제한 없이 포함 될 수 있습니다 `Default` 요소입니다.  
  
|요소|설명|  
|-------------|-----------------|  
|`Default`|VSIX 패키지의 콘텐츠 형식에 설명 합니다. 패키지에 있는 모든 파일 형식이 있어야 자체 `Default` 요소입니다.|  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`Extension`|VSIX 패키지에 있는 파일의 파일 이름 확장명입니다.|  
|`ContentType`|파일 이름 확장명과 연결 된 콘텐츠의 종류를 설명 합니다.|  
  
### <a name="attribute-name-attribute"></a>{특성 이름} 특성  
 Visual Studio 인식 `ContentType` 연결 된 작업에 대 한 값 `Extension` 형식입니다.  
  
|확장명|ContentType|  
|---------------|-----------------|  
|txt|텍스트/일반|  
|pkgdef|텍스트/일반|  
|xml|text/xml|  
|vsixmanifest|text/xml|  
|htm 또는 html|텍스트/html|  
|rtf|응용 프로그램/서식 있는 텍스트|  
|pdf|응용 프로그램/pdf|  
|gif|이미지/gif|  
|jpg 또는 jpeg|이미지/jpg|  
|tiff|이미지/tiff|  
|vsix|응용 프로그램/우편 번호|  
|zip|응용 프로그램/우편 번호|  
|dll|응용 프로그램/옥텟 스트림|  
|다른 모든 파일 형식|응용 프로그램/옥텟 스트림|  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>설명  
 다음 [Content_Types].xml 파일 일반적인 VSIX 패키지에 설명 합니다.  
  
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
 [VSIX 패키지에 대 한 분석](../extensibility/anatomy-of-a-vsix-package.md)   
 [VSIX 확장 1.0 스키마 참조](http://msdn.microsoft.com/en-us/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)   
 [OPC: 데이터 패키징을 위한 새로운 표준](http://go.microsoft.com/fwlink/?LinkID=148207)
