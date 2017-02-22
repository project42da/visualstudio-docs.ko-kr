---
title: "프로젝트 모델의 요소 | Microsoft Docs"
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
  - "프로젝트 [Visual Studio SDK] 구현 시 고려 사항"
  - "프로젝트 모델"
  - "프로젝트 [Visual Studio SDK] 요소"
ms.assetid: a1dbe0dc-68da-45d7-8704-5b43ff7e4fc4
caps.latest.revision: 18
caps.handback.revision: 18
ms.author: "gregvanl"
manager: "ghogen"
---
# 프로젝트 모델의 요소
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

인터페이스와 구현에 대 한 모든 프로젝트의 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 기본 구조를 공유 합니다: 프로젝트 모델 프로젝트 형식에 대 한.  개발 중인 VSPackage 인 프로젝트 모델에서 디자인 결정을 준수 하 고 IDE에서 제공 하는 글로벌 기능이 함께 작동 하는 개체를 만듭니다.  예를 들어, 프로젝트 항목이 유지 되는 방식을 제어 하지만 알림 파일을 유지 해야 것을 제어 하지 않습니다.  때 사용자가 프로젝트 열기 항목에 포커스가 이동 하 고 선택  **저장** 에  **파일** 메뉴에서의 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 파일이 더 오래 된 알림을 보낼 IDE로 다시 변경 및 프로젝트 형식 코드 합니다 명령을 IDE에서 중단, 파일을 유지 메뉴 모음.  
  
 Vspackage를 액세스 하는 IDE 인터페이스를 제공 하는 서비스를 통해 IDE와 상호 작용 합니다.  예를 들어, 특정 서비스를 통해 모니터 하 고 경로 명령과 선택한 프로젝트에 대 한 컨텍스트 정보를 제공 합니다.  필요 하면 Vspackage를 모든 전역 IDE 기능 서비스를 통해 제공 됩니다.  서비스에 대 한 자세한 내용은 [방법: 서비스 가져오기](../../extensibility/how-to-get-a-service.md).  
  
 기타 구현 고려 사항:  
  
-   단일 프로젝트 모델 프로젝트 형식이 둘 이상 포함 될 수 있습니다.  
  
-   프로젝트 형식 및 프로젝트 수행자 팩토리 독립적으로 Guid로 등록 되었습니다.  
  
-   각 프로젝트 서식 파일 또는 마법사에서 사용자는 새 프로젝트를 만들 때 새 프로젝트 파일을 초기화할 수 있어야 합니다의 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] UI입니다.  예를 들어, 있는 [!INCLUDE[vcprvc](../../debugger/includes/vcprvc_md.md)] 템플릿 초기화 무엇이 결국.vcproj 파일이 됩니다.  
  
 다음 그림은 기본 인터페이스와 서비스, 일반적인 프로젝트 구현을 작성 하는 개체를 보여 줍니다.  응용 프로그램 도우미, HierUtil7, 기본 객체 및 기타 프로그래밍의 기본 구성 요소를 만드는 데 사용할 수 있습니다.  HierUtil7 응용 프로그램 도우미에 대 한 자세한 내용은 참조 하십시오. [Not in Build: Using HierUtil7 Project Classes to Implement a Project Type \(C\+\+\)](http://msdn.microsoft.com/ko-kr/a5c16a09-94a2-46ef-87b5-35b815e2f346).  
  
 ![Visual Studio 프로젝트 모델 그래픽](../../extensibility/internals/media/vsprojectmodel.png "vsProjectModel")  
프로젝트 모델  
  
 인터페이스 및 이전 다이어그램에서 나열 된 서비스 및 다이어그램에 포함 되지 않은 다른 선택적 인터페이스에 대 한 자세한 내용은 참조 하십시오. [프로젝트 모델에 대 한 핵심 구성 요소](../../extensibility/internals/project-model-core-components.md).  
  
 프로젝트 명령을 지원할 수 있으며 따라서 구현 해야는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 인터페이스 명령 명령을 통해 컨텍스트 Guid 라우팅에 참가 하도록 합니다.  
  
## 참고 항목  
 [검사 목록: 새 프로젝트 형식 만들기](../../extensibility/internals/checklist-creating-new-project-types.md)   
 [Not in Build: Using HierUtil7 Project Classes to Implement a Project Type \(C\+\+\)](http://msdn.microsoft.com/ko-kr/a5c16a09-94a2-46ef-87b5-35b815e2f346)   
 [프로젝트 모델에 대 한 핵심 구성 요소](../../extensibility/internals/project-model-core-components.md)   
 [프로젝트 팩터리를 사용 하 여 프로젝트 인스턴스 만들기](../../extensibility/internals/creating-project-instances-by-using-project-factories.md)   
 [방법: 서비스 가져오기](../../extensibility/how-to-get-a-service.md)   
 [프로젝트 형식 만들기](../../extensibility/internals/creating-project-types.md)