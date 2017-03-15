---
title: "T4 텍스트 변환 사용자 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "텍스트 템플릿, API"
  - "텍스트 템플릿, 사용자 지정 호스트"
ms.assetid: 62cd9a3c-a6e1-4b29-93f5-f2a0cf47dc92
caps.latest.revision: 28
author: "alancameronwills"
ms.author: "awills"
manager: "douge"
caps.handback.revision: 28
---
# T4 텍스트 변환 사용자 지정
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

텍스트 템플릿은 변환 프로세스를 통해 프로그램 코드나 기타 텍스트 파일을 생성할 수 있도록 하는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]의 기능입니다.  [!INCLUDE[vssdk_current_short](../modeling/includes/vssdk_current_short_md.md)]를 사용하면 텍스트 템플릿 지시문 프로세서나 텍스트 템플릿 호스트를 사용자 지정하여 기본 템플릿 변환 프로세스를 확장할 수 있습니다.  
  
## 단원 내용  
 [텍스트 템플릿 변환 프로세스](../modeling/the-text-template-transformation-process.md)  
 텍스트 변환의 작동 방식과 템플릿 호스트 및 지시문 프로세서의 역할에 대해 설명합니다.  
  
 [사용자 지정 T4 텍스트 템플릿 지시문 프로세서 만들기](../modeling/creating-custom-t4-text-template-directive-processors.md)  
 지시문 프로세서는 템플릿에서 `<#@template#>.` 등의 지시문을 처리하며, 템플릿의 컴파일 중에 실행되고 어셈블리와 기타 리소스를 로드할 수 있습니다.  또한 런타임에 리소스를 로드하는 코드도 삽입할 수 있습니다.  사용자 고유의 지시문 프로세서를 정의하면 템플릿의 복잡성을 줄일 수 있습니다.  
  
 [VS 확장에서 텍스트 변환 호출](../modeling/invoking-text-transformation-in-a-vs-extension.md)  
 메뉴 명령이나 이벤트 처리기와 같은 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Extension을 작성하는 경우 해당 확장에서 텍스트 템플릿 서비스를 사용하여 텍스트 템플릿을 변환할 수 있습니다.  Session 개체를 사용하여 매개 변수 데이터를 템플릿에 전달하고 `<#@parameter#>` 지시문을 사용하여 템플릿에서 값을 가져올 수 있습니다.  
  
 [사용자 지정 호스트를 사용하여 텍스트 템플릿 처리](../modeling/processing-text-templates-by-using-a-custom-host.md)  
 텍스트 템플릿의 코드가 실행되면 호스트는 외부 파일과 응용 프로그램의 상태에 대한 액세스를 제공합니다.  예를 들어, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 텍스트 변환을 실행하는 호스트는 솔루션 탐색기에 대한 액세스를 제공할 수 있습니다.  또한 오류 메시지 창에 오류를 표시합니다.  다른 컨텍스트에서 텍스트 변환을 실행하려면 해당 컨텍스트에서 사용 가능한 서비스에 대한 액세스를 제공하는 사용자 고유의 호스트를 정의하면 됩니다.  
  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Extension을 작성하는 경우 고유 호스트를 작성하는 대신 기존 텍스트 변환 서비스를 사용하십시오.  자세한 내용은 [VS 확장에서 텍스트 변환 호출](../modeling/invoking-text-transformation-in-a-vs-extension.md)을 참조하십시오.  
  
## 참조  
 [T4 텍스트 템플릿 쓰기](../modeling/writing-a-t4-text-template.md)  
  
 텍스트 템플릿 지시문과 제어 블록의 구문을 제공합니다.