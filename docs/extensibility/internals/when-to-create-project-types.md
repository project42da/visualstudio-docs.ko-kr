---
title: "프로젝트 형식 만들어야 하는 경우 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "프로젝트 형식 만들기에 대 한 조건"
ms.assetid: 26adc860-ee4a-4f5c-95e1-e41b207dd7e6
caps.latest.revision: 14
caps.handback.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
---
# 프로젝트 형식 만들어야 하는 경우
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

새 프로젝트 형식을 만들고 제공을 기준으로 사용자 지정 하는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 사용자를 위한.  그러나 새 프로젝트 유형 만들기에 대 한 모든 필요 하지 않은 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 사용자 지정 합니다.  다음 지침에 따라 새 프로젝트 형식이 해당 시나리오에 대 한 필수 인지 여부를 확인 하는 데 도움이 됩니다.  
  
## 새 프로젝트 형식 만들기  
 사용자 지정 하려는 경우 프로젝트 형식을 만들어야 합니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 다음 방법 중 하나 이상의 역할을 합니다.  
  
-   빌드에 참여, 배포, 구성 및 소스 제어 합니다.  
  
-   디버깅 지원을 제공 합니다.  
  
-   프로젝트 항목 표시  **솔루션 탐색기**.  
  
-   사용은  **프로젝트 열기** 또는  **새 프로젝트** 대화 상자.  
  
-   중첩 프로젝트를 지원 합니다.  
  
## 기존 프로젝트 형식을 확장 합니다.  
 사용할 수 있는 새 프로젝트 형식을 만들 할 수 있습니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 수정 하거나 동작을 기존 프로젝트 형식을 확장 하는 다음과 같은 점에서 예를 들어, 빌드 프로세스에 대 한 수정 [!INCLUDE[vcprvc](../../debugger/includes/vcprvc_md.md)] 프로젝트:  
  
-   여러 파일을 하나의 단위로 사용 합니다.  
  
-   파일 하나를 하위 항목의 계층 구조로 표시 합니다.  
  
-   명령 컨텍스트 편집기를 표시 합니다.  
  
-   서비스 컨텍스트 편집기에 표시 됩니다.  
  
## 기존 프로젝트 형식을 사용 하 여  
 새 프로젝트를 만들 필요 없는 경우도 있습니다.  프로젝트 형식에 대해 생성 되지 않은 작업은 다음과 같습니다.  
  
|Task|설명|  
|----------|--------|  
|처리 명령|모든 VSPackage 명령을 처리할 수 있습니다.|  
|편집기를 작성합니다.|사용자 지정 편집기를 등록할 수 있습니다.  자세한 내용은 [Document Windows and Editors](http://msdn.microsoft.com/ko-kr/603625e1-62b6-413a-bc44-089346e166bc)를 참조하십시오.|  
|Windows를 소유 하 고 있습니다.|새 프로젝트 형식이 추가 하지 않고 모두 도구와 문서 창을 만들 수 있습니다.|  
|속성 창에서에서 속성을 노출합니다.|모든 개체는 속성을 노출할 수 있습니다.|  
  
## 하위 프로젝트 만들기  
 새 프로젝트 형식을 만들 필요 없이 관리 되는 프로젝트 형식을 확장 하려면 하위 프로젝트를 사용할 수 있습니다.  프로젝트 하위 COM 집합 사용 하 여 Microsoft에서 작성 하는 관리 되는 프로젝트를 확장 합니다 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] 또는 [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)].  COM 집합으로 대부분의 관리 되는 프로젝트 시스템 구현을 다시 사용 하 고 여전히 집계 및 사용 인터페이스를 지 원하는 특정 시나리오에 대 한 사용자 지정 수 있습니다.  하위 프로젝트에 대 한 자세한 내용은 참조 하십시오. [프로젝트 하위 형식](../../extensibility/internals/project-subtypes.md).  
  
## 참고 항목  
 [Document Windows and Editors](http://msdn.microsoft.com/ko-kr/603625e1-62b6-413a-bc44-089346e166bc)   
 [검사 목록: 새 프로젝트 형식 만들기](../../extensibility/internals/checklist-creating-new-project-types.md)   
 [Visual Studio에서 계층 구조](../../extensibility/internals/hierarchies-in-visual-studio.md)