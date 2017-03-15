---
title: "MSBuild 특수 문자 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "이스케이프"
  - "이스케이프 문자"
  - "MSBuild 이스케이프 문자"
ms.assetid: 545e6a59-1093-4514-935e-78679a46fb3c
caps.latest.revision: 8
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 8
---
# MSBuild 특수 문자
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]에서는 일부 문자를 특정 컨텍스트에서 특별한 용도로 사용하기 위해 예약합니다.  이러한 문자를 예약된 컨텍스트에서 문자 그대로 사용하려면 해당 문자를 이스케이프하기만 하면 됩니다.  예를 들어, 별표는 항목 정의의 `Include` 및 `Exclude` 특성과 `CreateItem`에 대한 호출에서만 특별한 의미를 갖습니다.  이러한 컨텍스트 중 하나에서 별표를 별표로 표시하려면 별표를 이스케이프해야 합니다.  다른 모든 컨텍스트에서는 원하는 위치에 별표를 입력하기만 하면 됩니다.  
  
 특수 문자를 이스케이프하려면 %*xx* 구문을 사용합니다. 여기서 *xx*는 ASCII 문자의 16진수 값을 나타냅니다.  자세한 내용은 [방법: MSBuild의 이스케이프 특수 문자](../msbuild/how-to-escape-special-characters-in-msbuild.md)를 참조하십시오.  
  
## 특수 문자  
 다음 표에서는 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 특수 문자를 보여 줍니다.  
  
|**문자**|**ASCII**|**예약 용도**|  
|------------|---------------|---------------|  
|%|%25|메타데이터 참조|  
|$|%24|속성 참조|  
|@|%40|항목 목록 참조|  
|'|%27|조건 및 기타 식|  
|;|%3B|목록 구분 기호|  
|?|%3F|`Include` 및 `Exclude` 특성에서 파일 이름에 사용하기 위한 와일드카드 문자|  
|\*|%2A|`Include` 및 `Exclude` 특성에서 파일 이름에 사용하기 위한 와일드카드 문자|  
  
## 참고 항목  
 [고급 개념](../msbuild/msbuild-advanced-concepts.md)   
 [항목](../msbuild/msbuild-items.md)