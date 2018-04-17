---
title: Visual Studio에서 계층 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- hierarchies, Visual Studio IDE
- IDE, hierarchies
ms.assetid: 0a029a7c-79fd-4b54-bd63-bd0f21aa8d30
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8d1f018b9cc48d059761a26721c808024f60bb3d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="hierarchies-in-visual-studio"></a>Visual Studio에서 계층 구조
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 으로 프로젝트를 표시 하는 통합된 개발 환경 (IDE)는 *계층*합니다. IDE에서 계층은 각 노드에 연결 된 속성 집합에 있는 노드의 트리입니다. A *프로젝트 계층* 프로젝트의 항목, 항목의 관계 및 항목의 관련된 속성 및 명령을 저장 하는 컨테이너입니다.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], 계층 구조 인터페이스를 사용 하 여 프로젝트 계층 구조를 관리할 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>합니다. <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> 인터페이스 표준 명령 처리기 대신 적절 한 계층 구조 창에 프로젝트 항목에서 호출 하는 명령을 리디렉션합니다.  
  
## <a name="project-hierarchies"></a>프로젝트 계층 구조  
 각 프로젝트 계층 구조에는 보고 편집할 수 있는 항목이 포함 됩니다. 이러한 항목은 프로젝트 형식에 따라 다릅니다. 예를 들어 저장된 프로시저, 데이터베이스 뷰 및 데이터베이스 테이블에 데이터베이스 프로젝트 포함 될 수 있습니다. 반면에 프로그래밍 언어 프로젝트를 소스 파일 및 비트맵 및 대화 상자에 대 한 리소스 파일 가능성이 포함 됩니다. 계층 구조를 제공 하는 몇 가지는 유연성이 프로젝트 계층 구조를 만들 때 중첩 될 수 있습니다.  
  
 새 프로젝트 형식을 만들 때 프로젝트 형식에 편집할 수 있는 항목의 전체 집합을 제어 합니다. 그러나 프로젝트를 갖지 않습니다 편집할 수 있도록 지원 되는 항목을 포함할 수 있습니다. 예를 들어 Visual c + + 프로젝트 있지만 Visual c + +에서는 모든 사용자 지정된 편집기 HTML 파일 형식에 대 한 HTML 파일을 포함할 수 있습니다.  
  
 계층 포함 항목의 지 속성을 관리 합니다. 계층의 구현에는 계층 구조 내에 있는 항목의 지 속성에 영향을 주는 모든 특수 속성이 제어 해야 합니다. 예를 들어 항목 파일 대신 저장소에서 개체를 나타낸다면 계층 구현 되는 개체의 지 속성을 제어 해야 합니다. 자체 IDE 사용자 입력에 따라 항목을 저장 하는 계층 지시 하지만 IDE 해당 항목을 저장 하는 데 필요한 모든 작업을 제어 하지 않습니다. 대신, 프로젝트에서 컨트롤입니다.  
  
 사용자가을 편집기 항목 열을 해당 항목을 제어 하는 계층을 선택 하 고 활성 계층 구조 됩니다. 선택한 계층 항목에 사용할 수 있는 명령 집합을 결정 합니다. 이런이 방식으로 사용자 포커스를 추적 합니다. 사용자의 현재 컨텍스트를 반영 하기 위해 계층 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로젝트 형식](../../extensibility/internals/project-types.md)   
 [선택 및 IDE에서 통화](../../extensibility/internals/selection-and-currency-in-the-ide.md)   
 [VSSDK 샘플](http://aka.ms/vs2015sdksamples)