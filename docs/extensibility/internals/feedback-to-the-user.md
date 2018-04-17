---
title: 사용자에 게 피드백 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- user model feedback
- environment, context
- IDE, context
- IDE, user feedback
ms.assetid: 2d472a24-3813-4f5f-9783-b491ad8a71ad
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 629d12974a52bca30c0db96e838c5c731ae1abf7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="feedback-to-the-user"></a>사용자에 게 피드백
에 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 통합된 개발 환경 (IDE) 시각적 피드백을 사용할 수 있는 기능에 대 한 사용자의 현재 선택 영역 및 글로벌 선택 항목 컨텍스트 기반입니다. 다음 표에서 다른 선택 컨텍스트에서 사용할 수 있는 기능을 나열 합니다.  
  
|선택 항목 컨텍스트|사용 가능한 기능|  
|-----------------------|-----------------------------|  
|IDE|Global|  
|현재 제품 집합|특정 제품|  
|활성 계층 구조|계층 구조 형식 관련|  
|활성 계층 구조 항목|계층 항목 유형 관련|  
|액티브 문서|형식 관련 문서|  
|창 맨 위에 있는 다중 문서 인터페이스 (mdi 다중)|창 유형 관련|  
|현재 선택 항목 컨텍스트|특정 선택 항목 컨텍스트|  
  
 사용자가 필요 하 고 지속적으로 일관 된 선택 및 환경 컨텍스트 피드백을 제공할 기능을만 노출 하는 경우 IDE에 복잡성이 줄어듭니다. 다음 규칙에는 IDE에서 창을 열 때마다 적용 됩니다.  
  
-   창이 해당 선택 항목 컨텍스트를 변경, 선택 피드백 명확 하 게 ´ ֲ ְ 창 원이고 동적 도움말 창 표시 하는 경우 현재 컨텍스트를 반영 하도록 합니다.  
  
-   창이 글로벌 선택 항목 컨텍스트를 변경, 모든 상황에 맞는 메뉴, 활성 계층 구조 창 및 응용 프로그램 제목 표시줄의 현재 컨텍스트를 반영 하도록 업데이트 됩니다.  
  
-   창에서 현재 선택 영역에 대 한 속성을 드러나게 됩니다는 **속성** 창 고 필요에 따라 표시 되는 **속성 페이지** 대화 상자.  
  
-   창의 속성을 노출 하지 않거나 글로벌 선택 항목 컨텍스트를 변경, 선택 피드백은 유지 되지 창에서 IDE의 활성 창이 더 이상.  
  
-   모든 문서 관련 도구 창에서 활성 문서를 반영 지속적으로 해야 합니다.  
  
-   메뉴, 도구 모음 및 응용 프로그램 제목 표시줄 맨 위에 있는 다중 문서 인터페이스 (mdi 다중) 클라이언트 창을 반영 되어야 합니다.  
  
 예를 들어 Visual Basic 웹 응용 프로그램 프로젝트 내부 웹 폼의 HTML 보기를 열 시점과 사용자가 선택 된 `<td>` 태그를 다음과 같이 하면 피드백이 제공 됩니다.  
  
-   선택은 현재 창에 표시 되며에 반영 된 **속성** 창.  
  
-   문서 관련 **도구 상자** 활성 문서를 반영 하도록 업데이트 됩니다.  
  
-   **편집기** 도구 모음 및 **테이블** 메뉴가 표시 됩니다 하 고 제목 표시줄 Web Form 창에 맞게 업데이트 합니다.  
  
-   일반적으로 활성 계층 구조 창 **솔루션 탐색기**, 및의 제목 표시줄 업데이트를 반영 하도록 현재 컨텍스트는 상황에 맞는 **프로젝트** 메뉴 명령은 활성 웹에 지금 적용 응용 프로그램 프로젝트입니다.  
  
## <a name="see-also"></a>참고 항목  
 [선택 및 IDE에서 통화](../../extensibility/internals/selection-and-currency-in-the-ide.md)   
 [컨텍스트 개체 선택](../../extensibility/internals/selection-context-objects.md)   
 [계층 구조 및 선택](../../extensibility/internals/hierarchies-and-selection.md)