---
title: "T4 텍스트 변환 사용자 지정 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
helpviewer_keywords:
- text templates, API
- text templates, custom hosts
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: db6d65c5dd0c79549516ff3b9c58b8b59c4be885
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2018
---
# <a name="customizing-t4-text-transformation"></a>T4 텍스트 변형 사용자 지정
텍스트 템플릿은의 기능 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로그램 코드나 변환 프로세스를 통해 기타 텍스트 파일을 생성할 수 있도록 하는 합니다. 사용 하 여 [!INCLUDE[vssdk_current_short](../modeling/includes/vssdk_current_short_md.md)], 텍스트 템플릿 지시문 프로세서 또는 텍스트 템플릿 호스트를 사용자 지정 하 여 기본 템플릿 변환 프로세스를 확장할 수 있습니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [텍스트 템플릿 변환 프로세스](../modeling/the-text-template-transformation-process.md)  
 텍스트 변환의 작동 방법을 설명 하 고 템플릿 호스트와의 지시문 프로세서의 역할을 설명 합니다.  
  
 [사용자 지정 T4 텍스트 템플릿 지시문 프로세서 만들기](../modeling/creating-custom-t4-text-template-directive-processors.md)  
 서식 파일의 지시문 지시문 프로세서와 같은 다루는 `<#@template#>.` 서식 파일을 컴파일하는 동안 실행 되며 어셈블리 및 기타 리소스를 로드할 수 있습니다. 런타임 시 리소스를 로드 하는 코드를 삽입할 수도 있습니다. 지시문 프로세서를 정의 하 여 서식 파일의 복잡성을 줄일 수 있습니다.  
  
 [VS 확장에서 텍스트 변환 호출](../modeling/invoking-text-transformation-in-a-vs-extension.md)  
 작성 하는 경우는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 메뉴 명령 또는 이벤트 처리기와 같은 확장을 확장 하려면 텍스트 템플릿을 변환할 텍스트 템플릿 서비스를 사용할 수 있습니다. 세션 개체를 사용 하 여 서식 파일에 매개 변수 데이터를 전달 하 고 사용 하 여 서식 파일 내에서 값을 받을 수는 `<#@parameter#>` 지시문입니다.  
  
 [사용자 지정 호스트를 사용하여 텍스트 템플릿 처리](../modeling/processing-text-templates-by-using-a-custom-host.md)  
 텍스트 템플릿의 코드를 실행 하는 경우 호스트는 외부 파일 및 응용 프로그램의 상태에 대 한 액세스를 제공 합니다. 호스트에서 텍스트 변환을 실행 하는 예를 들어 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 솔루션 탐색기에 대 한 액세스를 제공할 수 있습니다. 또한 오류 메시지 창에 오류가 표시 됩니다. 텍스트 변환 각기 다른 컨텍스트에서 실행 하려는 경우 해당 컨텍스트에서 사용할 수 있는 서비스에 대 한 액세스를 제공 하는 고유 호스트를 정의할 수 있습니다.  
  
 작성 하는 경우는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 확장을 고유 호스트를 작성 하는 대신 기존 텍스트 변환 서비스를 사용 하는 것이 좋습니다. 자세한 내용은 참조 [VS 확장에서 텍스트 변환 호출](../modeling/invoking-text-transformation-in-a-vs-extension.md)합니다.  
  
## <a name="reference"></a>참조  
 [T4 텍스트 템플릿 쓰기](../modeling/writing-a-t4-text-template.md)  
  
 텍스트 템플릿 지시문 및 제어 블록의 구문을 제공합니다.