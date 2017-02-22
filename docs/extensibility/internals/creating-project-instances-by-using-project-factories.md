---
title: "프로젝트 팩터리를 사용 하 여 프로젝트 인스턴스 만들기 | Microsoft Docs"
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
  - "프로젝트 팩터리"
  - "프로젝트 [Visual Studio SDK], 프로젝트 팩터리"
ms.assetid: 94c90012-8669-459c-af8e-307ac242c8c4
caps.latest.revision: 13
caps.handback.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
---
# 프로젝트 팩터리를 사용 하 여 프로젝트 인스턴스 만들기
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

프로젝트 형식에서 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 사용 하는  *프로젝트 공장* 프로젝트 개체의 인스턴스를 생성 합니다.  프로젝트 공장 cocreatable COM 개체에 대 한 표준 클래스 팩터리와 유사합니다.  그러나 프로젝트 개체를 cocreatable 수 없습니다: 프로젝트 공장을 사용 하 여만 만들 수 있습니다.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE 호출 하면 VSPackage에서는 사용자가 기존 프로젝트를 로드 하거나 새 프로젝트를 만드는 경우 구현 프로젝트 공장 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  새 프로젝트 개체는 IDE 서버 탐색기를 채우는 데 충분 한 정보를 제공 합니다.  새 프로젝트 개체 또한 IDE에서 시작 하는 모든 관련 UI 동작을 지 원하는 데 필요한 인터페이스를 제공 합니다.  
  
 구현할 수는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory> 프로젝트에서 클래스의 인터페이스.  일반적으로 자체 모듈에 상주합니다.  
  
 구현 예는 `IVsProjectFactory` 인터페이스에 포함 된 Prjfac.cpp를 참조 하십시오은 [Basic Project](http://msdn.microsoft.com/ko-kr/385fd2a3-d9f1-4808-87c2-a3f05a91fc36) 샘플 디렉터리.  
  
 소유자에 의해 집계 되 고 지원 프로젝트에 소유자 키가 프로젝트 파일에 유지 해야 합니다.  경우는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory.CreateProject%2A> 메서드가 호출 프로젝트에는 소유자 키로 하 고가 소유한 프로젝트의 소유자 키 GUID 다음 호출 하는 프로젝트 공장에 변환의 `CreateProject` 메서드가 실제로 작업을 수행 하는이 프로젝트 공장에.  
  
## 소유 하는 프로젝트 만들기  
 소유자 두 단계에서 소유 하는 프로젝트를 만듭니다.  
  
1.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsOwnedProjectFactory.PreCreateForOwner%2A> 메서드를 호출합니다.  이 소유 프로젝트 입력 제어를 기준으로 집계 된 프로젝트 개체를 만들 수 있습니다 `IUnknown`.  소유 프로젝트 내부 통과 `IUnknown` 및 집계 된 개체 소유자 프로젝트를 다시.  이 소유 하는 프로젝트 내부에 저장할 수 있는 기회를 제공 `IUnknown`.  
  
2.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsOwnedProjectFactory.InitializeForOwner%2A> 메서드를 호출합니다.  호출 하는 대신이 메서드를 호출 하면 모든 인스턴스화하지 소유 프로젝트 하지 `IVsProjectFactory::CreateProject` 소유 하 고 없는 프로젝트에 대 한 수 있을 것으로 합니다.  입력 `VSOWNEDPROJECTOBJECT` 일반적으로 집계 된 소유 프로젝트 열거형입니다.  소유 프로젝트 프로젝트 개체를 이미 만들어졌는지 여부를 확인 하려면이 변수를 사용할 수 있습니다 \(쿠키 다름 NULL\) 또는 \(쿠키는 NULL\)을 만들어야 합니다.  
  
 프로젝트 형식 GUID cocreatable COM 개체의 CLSID로 비슷한 고유 프로젝트 식별 됩니다.  일반적으로 한 프로젝트 공장 핸들 프로젝트 공장 하나 있을 수 있지만 단일 프로젝트 형식의 인스턴스를 만드는 두 개 이상의 프로젝트 형식 GUID를 처리 합니다.  
  
 프로젝트 형식이 특정 파일 이름 확장명과 연결 되어 있습니다.  사용자가 기존 프로젝트 파일을 열려고 하거나 템플릿을 복제 하 여 새 프로젝트를 만들려고 하면 IDE 확장 파일을 사용 하 여 해당 프로젝트의 GUID를 확인 합니다.  
  
 IDE IDE에서는 사용 하 여 새 프로젝트를 작성 하거나 특정 종류의 기존 프로젝트를 열 해야 하는지 여부를 확인 하는 즉시 필요한 프로젝트 공장 있는 Vspackage를 찾으려면 \[HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\VisualStudio\\8.0\\Projects\]에서 시스템 레지스트리를 구현 합니다.  IDE이이 VSPackage 로드합니다.  에 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A> 메서드를 있는 VSPackage 해야 등록 프로젝트 공장을 사용 하는 IDE를 호출 하 여 해당 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterProjectTypes.RegisterProjectType%2A> 메서드.  
  
 주요 메서드는 `IVsProjectFactory` 인터페이스입니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory.CreateProject%2A> 는 두 가지 시나리오 처리 해야: 기존 프로젝트를 열고 새 프로젝트를 만들고.  대부분의 프로젝트에서 프로젝트 파일의 프로젝트 상태를 저장합니다.  일반적으로 새 프로젝트 만들기 서식 파일의 복사본을 전달 하 여 만든는 `CreateProject` 메서드 및 다음 복사본을 열어.  기존 프로젝트는 인스턴스화된 의해 전달 프로젝트 파일을 열고 직접 `CreateProject` 메서드가 있습니다.  `CreateProject` 메서드 표시할 수 있습니다 추가 UI 기능 사용자에 게 필요 합니다.  
  
 프로젝트 수 있습니다 또한 파일이 없습니다 사용 하 고 대신 프로젝트 상태 이외의 파일 시스템, 데이터베이스 또는 웹 서버와 같은 다른 저장소 메커니즘에 저장 합니다.  여기에 파일 이름 매개 변수를 전달는 `CreateProject` 메서드가 실제로 파일 시스템 경로로 있지만 고유 문자열 아닙니다\-URL\-프로젝트 데이터를 식별 합니다.  전달 된 템플릿 파일을 복사 하지 않아도 `CreateProject` 실행 될 수 있는 적절 한 생성 시퀀스를 트리거할 수 있습니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsOwnedProjectFactory>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterProjectTypes>   
 [검사 목록: 새 프로젝트 형식 만들기](../../extensibility/internals/checklist-creating-new-project-types.md)