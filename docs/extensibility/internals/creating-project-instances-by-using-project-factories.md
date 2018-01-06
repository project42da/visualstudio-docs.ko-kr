---
title: "프로젝트 팩터리를 사용 하 여 프로젝트 인스턴스 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- project factories
- projects [Visual Studio SDK], project factories
ms.assetid: 94c90012-8669-459c-af8e-307ac242c8c4
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 8a331c131eaf48eb7be8bc3709599412aa01b1ca
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="creating-project-instances-by-using-project-factories"></a>프로젝트 팩터리를 사용 하 여 프로젝트 인스턴스 만들기
프로젝트 형식에 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 사용는 *프로젝트 팩터리* 프로젝트 개체의 인스턴스를 만듭니다. 프로젝트 팩터리 cocreatable COM 개체에 대 한 표준 클래스 팩터리와 비슷합니다. 그러나 프로젝트 개체는 cocreatable 없습니다: 프로젝트 팩터리를 사용 하 여만 만들 수 있습니다.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 사용자 기존 프로젝트를 로드 하거나에 새 프로젝트를 만들 때 VSPackage의 구현 프로젝트 팩터리를 호출 하는 IDE [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다. 새 프로젝트 개체는 솔루션 탐색기를 채우는 데 충분 한 정보는 IDE를 제공 합니다. 새 프로젝트 개체는 또한 IDE에 의해 시작 된 모든 관련 UI 작업을 지원 하기 위한 필수 인터페이스를 제공 합니다.  
  
 구현할 수는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory> 프로젝트의 클래스에 인터페이스입니다. 일반적으로 모듈 자체에 상주합니다.  
  
 구현에 대 한 예제는 `IVsProjectFactory` 인터페이스를 PrjFac.cpp에 포함 된 참조는 [기본 프로젝트](http://msdn.microsoft.com/en-us/385fd2a3-d9f1-4808-87c2-a3f05a91fc36) 샘플 디렉터리입니다.  
  
 지원 된 소유자에 의해 집계 되는 프로젝트의 프로젝트 파일에는 소유자 키를 유지 해야 합니다. 경우는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory.CreateProject%2A> 소유자 키로 프로젝트에 메서드가 호출 됨, 소유 프로젝트 변환 해당 소유자 키 GUID를 호출 하는 프로젝트 팩터리는 `CreateProject` 이 프로젝트 팩터리에서 실제로 생성 작업을 수행 하는 메서드.  
  
## <a name="creating-an-owned-project"></a>소유 프로젝트 만들기  
 소유자는 두 단계로 소유 프로젝트를 만듭니다.  
  
1.  호출 하 여는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsOwnedProjectFactory.PreCreateForOwner%2A> 메서드. 이렇게 하면 소유 프로젝트에서 입력 제어에 따라 집계 프로젝트 개체를 만드는 `IUnknown`합니다. 소유 프로젝트 내부 전달 `IUnknown` 및 소유자 프로젝트에 다시 집계 개체입니다. 이렇게 하면 소유 프로젝트 내부에 저장할 수 있는 기회 `IUnknown`합니다.  
  
2.  호출 하 여는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsOwnedProjectFactory.InitializeForOwner%2A> 메서드. 호출 하는 대신이 메서드를 호출할 때 소유 프로젝트에 모든 인스턴스화하지 않습니다 `IVsProjectFactory::CreateProject` 처럼 소유 하지 않은 프로젝트의 경우. 입력 `VSOWNEDPROJECTOBJECT` 열거형은 일반적으로 집계 된 소유 프로젝트. 소유 프로젝트가이 변수를 사용 하 여 해당 프로젝트 개체가 이미 생성 여부를 확인할 수 있습니다 (쿠키 NULL를 동일 하지 않음) 또는 (쿠키 equals NULL)를 만들어야 합니다.  
  
 프로젝트 형식은 고유한 프로젝트 cocreatable COM 개체의 CLSID와 유사한 GUID로 식별 됩니다. 일반적으로 한 프로젝트 팩터리 있을 수 있지만 단일 프로젝트 형식의 인스턴스를 만드는 한 프로젝트 팩터리 핸들 처리 둘 이상의 프로젝트 GUID 형식입니다.  
  
 프로젝트 형식은 특정 파일 이름 확장명으로 연결 됩니다. 사용자 기존 프로젝트 파일을 열려고 시도 하거나 템플릿을 복제 하 여 새 프로젝트를 만들려고 시도 합니다 IDE를 사용 하 여 확장 파일에 해당 하는 프로젝트 GUID를 확인 합니다.  
  
 IDE는 새 프로젝트 만들기 또는 특정 형식의 기존 프로젝트를 열고 해야, IDE를 사용 하 여 정보 시스템 레지스트리의 [HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\8.0\Projects] 아래에 해당 하는 검색을 결정 하는 즉시 VSPackage는 필요한 프로젝트 팩터리를 구현합니다. IDE는이 VSPackage를 로드합니다. 에 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A> 메서드, VSPackage를 호출 하 여 IDE와 해당 프로젝트 팩터리를 등록 해야 합니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterProjectTypes.RegisterProjectType%2A> 메서드.  
  
 기본 방법은 `IVsProjectFactory` 인터페이스는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory.CreateProject%2A> 두 가지 시나리오를 처리 하는: 기존 프로젝트를 열고 새 프로젝트를 만들고 있습니다. 대부분의 프로젝트는 프로젝트 파일에서 해당 프로젝트 상태를 저장합니다. 서식 파일의 복사본에 전달 하 여 새 프로젝트를 만들 일반적으로 `CreateProject` 메서드와 여는 복사본입니다. 에 전달 된 프로젝트 파일을 열어 직접 기존 프로젝트에서 인스턴스화되는 `CreateProject` 메서드. `CreateProject` 메서드는 필요에 따라 사용자에 게 추가 UI 기능을 표시할 수 있습니다.  
  
 프로젝트도 파일 사용 안 있고, 대신 아닌 파일 시스템 데이터베이스 또는 웹 서버와 같은 다른 저장 메커니즘에 해당 프로젝트 상태를 저장 합니다. 이 경우에 전달 된 파일 이름 매개 변수는 `CreateProject` 메서드는 파일 시스템 경로 실제로 아니라 고유한 문자열-URL-프로젝트 데이터를 확인 합니다. 에 전달 되는 템플릿 파일을 복사할 필요가 없습니다 `CreateProject` 실행할 적절 한 생성 시퀀스를 트리거할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsOwnedProjectFactory>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterProjectTypes>   
 [검사 목록: 새 프로젝트 형식 만들기](../../extensibility/internals/checklist-creating-new-project-types.md)