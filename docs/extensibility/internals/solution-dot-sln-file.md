---
title: "솔루션 (합니다. Sln) 파일 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Vspackage sln 파일"
  - "솔루션,.sln 파일"
  - "Vspackage.sln 파일"
ms.assetid: 7d7ef539-2e4b-4637-b853-8ec7626609df
caps.latest.revision: 13
caps.handback.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
---
# 솔루션 (합니다. Sln) 파일
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

솔루션에는 Visual Studio에서 프로젝트를 구성 하기 위한 구조입니다. 솔루션은 프로젝트 \(텍스트 기반, 공유\).sln 및.suo \(이진, 사용자 고유의 솔루션 옵션\) 파일에 대 한 상태 정보를 유지 관리합니다. .Suo 파일에 자세한 내용은 참조 하십시오. [솔루션 사용자 옵션 \(합니다. Suo\) 파일](../../extensibility/internals/solution-user-options-dot-suo-file.md)합니다.  
  
 VSPackage가 로드 되 고.sln 파일에서 참조 하 고 결과로 환경 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps.ReadSolutionProps%2A> .sln 파일을 읽을 수 있습니다.  
  
 .Sln 파일 환경 찾기 및 로드 지속된 된 데이터 및 참조 하는 Vspackage 프로젝트에 대 한 이름\-값 매개 변수를 사용 하 여 텍스트 기반 정보를 포함 합니다. 사용자가 솔루션을 열면 환경으로 돌아가면서 선택는 `preSolution`, `Project`, 및 `postSolution` 솔루션을 로드 하.sln 파일의 정보에서 솔루션 내의 프로젝트 및 솔루션에 연결 된 모든 지속형된 정보입니다.  
  
 각 프로젝트의 파일을 해당 프로젝트의 항목 계층 구조를 채우는 환경에서 읽은 추가 정보를 포함 합니다. 계층 데이터 지 속성은 프로젝트에 의해 제어 됩니다. 데이터는 일반적으로 저장 되지.sln 파일에 수 의도적으로 작성 해도 프로젝트 정보.sln 파일을 작업을 수행 하려는 경우. 지 속성에 관련 된 자세한 내용은 참조 하십시오. [프로젝트 지 속성](../../extensibility/internals/project-persistence.md) 및 [열기 및 프로젝트 항목 저장](../../extensibility/internals/opening-and-saving-project-items.md)합니다.  
  
## 솔루션 파일 내용  
 다음 코드에서 볼 수 있듯이.sln 파일 몇 가지 섹션으로 이루어져 있습니다.  
  
```  
Project("{F184B08F-C81C-45F6-A57F-5ABD9991F28F}") = "Project1", "Project1.vbproj", "{8CDD8387-B905-44A8-B5D5-07BB50E05BEA}" EndProject Global GlobalSection(SolutionNotes) = postSolution EndGlobalSection GlobalSection(SolutionConfiguration) = preSolution ConfigName.0 = Debug ConfigName.1 = Release EndGlobalSection GlobalSection(ProjectDependencies) = postSolution EndGlobalSection GlobalSection(ProjectConfiguration) = postSolution {8CDD8387-B905-44A8-B5D5-07BB50E05BEA}.Debug.ActiveCfg = Debug|x86 {8CDD8387-B905-44A8-B5D5-07BB50E05BEA}.Debug.Build.0 = Debug|x86 {8CDD8387-B905-44A8-B5D5-07BB50E05BEA}.Release.ActiveCfg = Release|x86 {8CDD8387-B905-44A8-B5D5-07BB50E05BEA}.Release.Build.0 = Release|x86 EndGlobalSection GlobalSection(ExtensibilityGlobals) = postSolution EndGlobalSection GlobalSection(ExtensibilityAddIns) = postSolution EndGlobalSection EndGlobal  
```  
  
 환경은 솔루션을 로드 하려면 다음 작업 순서를 수행 합니다.  
  
1.  환경.sln 파일의 전체 섹션을 읽고 표시 된 섹션을 모두 처리 `preSolution`합니다. 이 경우 이러한 설명 중 하나 있습니다.  
  
    ```  
    GlobalSection(SolutionConfiguration) = preSolution ConfigName.0 = Debug ConfigName.1 = Release  
    ```  
  
     환경 읽을 때의 `GlobalSection('name')` 태그를 매핑할 이름을 레지스트리를 사용 하 여 VSPackage 합니다. 키 이름 레지스트리의 \[\< 응용 프로그램 ID 레지스트리 루트 \> HKLM\\ \\SolutionPersistence\\AggregateGUIDs\] 아래에 있어야 합니다. 키의 기본값은 항목을 작성 하는 VSPackage의 패키지 GUID \(REG\_SZ\)입니다.  
  
2.  호출 VSPackage를 로드 하는 환경 `QueryInterface` 에 VSPackage에는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps> 인터페이스를 호출 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps.ReadSolutionProps%2A> VSPackage 데이터를 저장할 수 있도록 섹션의 데이터를 사용 하 여 메서드. 환경 각각에 대해이 프로세스를 반복 `preSolution` 섹션입니다.  
  
3.  환경을은 프로젝트 지 속성 블록을 반복합니다. 이 경우에 하나의 프로젝트.  
  
    ```  
    Project("{F184B08F-C81C-45F6-A57F-5ABD9991F28F}") = "Project1", "Project1.vbproj", "{8CDD8387-B905-44A8-B5D5-07BB50E05BEA}" EndProject  
    ```  
  
     이 문은 GUID는 고유한 프로젝트 및 프로젝트 형식 GUID 포함합니다. 이 정보는 프로젝트 파일 또는 솔루션에 속하는 파일을 찾으려고 환경에 의해 사용 됩니다 하 고 VSPackage 각 프로젝트에 필요한 키를 누릅니다. GUID로 전달 되는 프로젝트 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory> 프로젝트와 관련 된 특정 VSPackage를 로드 하려면 다음 프로젝트가 로드 되는 VSPackage에서. 이 경우에이 프로젝트에 대해 로드 되는 VSPackage Visual Basic입니다.  
  
     각 프로젝트는 솔루션의 다른 프로젝트에서 필요에 따라 액세스할 수 있도록 고유한 프로젝트 인스턴스 ID를 유지할 수 있습니다. 이상적으로 솔루션 및 프로젝트 소스 코드 제어 경우 경로 프로젝트를 솔루션에 대 한 경로 기준으로 이어야 합니다. 솔루션은 처음 로드할 때 프로젝트 파일은 사용자의 컴퓨터에 수 없습니다. 솔루션 파일을 기준으로 서버에 저장 된 프로젝트 파일을 함으로써 발견 하 고 사용자의 컴퓨터에 복사 될 프로젝트 파일에 대 한 상대적으로 간단 합니다. 그런 다음 복사 하 고 프로젝트에 필요한 파일의 나머지 부분을 로드 합니다.  
  
4.  환경을은 프로젝트에 대 한 부분이.sln 파일에 포함 된 정보에 따라 각 프로젝트 파일을 로드 합니다. 프로젝트 자체 담당 다음 프로젝트 계층 구조를 채우고 중첩 된 모든 프로젝트를 로드 합니다.  
  
5.  .Sln 파일의 모든 섹션 처리 되 면 솔루션 솔루션 탐색기에 표시 되며 되었고 사용자가 수정 하기 위해 준비 되었습니다.  
  
 솔루션에 프로젝트를 구현 하는 모든 VSPackage 로드에 실패 하는 경우는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps.OnProjectLoadFailure%2A> 메서드가 호출 되 고 솔루션의 다른 모든 프로젝트 변경 내용을 로드 하는 동안 만들어 둔 것 무시 되려면 제공 됩니다. 구문 분석 오류가 발생 하는 경우에 가능한 한 많은 정보 솔루션 파일과 함께 보존 되 고 사용자에 게 경고 솔루션 손상 된 대화 상자를 표시 하는 환경.  
  
 솔루션을 저장 하거나 닫을 때의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps.QuerySaveSolutionProps%2A> 메서드는 호출 하 고.sln 파일에 입력 해야 하는 솔루션에 변경 내용이 적용 된 참조를 계층으로 전달 합니다. 에 전달 하 여 null 값을 `QuerySaveSolutionProps` 에서 <xref:Microsoft.VisualStudio.Shell.Interop.VSQUERYSAVESLNPROPS>, 솔루션에 대 한 정보는 유지 되 고 있는지를 나타냅니다. 특정 프로젝트의 경우에 대 한 포인터에 의해 결정 유지 된 정보는 null 값이 아닌 경우는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> 인터페이스입니다.  
  
 정보를 저장할 수 없는 경우는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence> 인터페이스에 대 한 포인터 라고는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps.SaveSolutionProps%2A> 메서드.<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps.WriteSolutionProps%2A> 에서 이름\-값 쌍을 검색 하는 환경에서 메서드가 호출 됩니다 `IPropertyBag` 인터페이스 및.sln 파일에 정보를 기록 합니다.  
  
 `SaveSolutionProps` 및 `WriteSolutionProps` 개체에 저장할 정보를 검색 하는 환경에서 재귀적으로 호출 되는 `IPropertyBag` .sln 파일에 입력 된 모든 변경 될 때까지 인터페이스입니다. 이러한 방식으로 솔루션 및 사용 가능한 다음 솔루션 열릴 때 사용 하 여 정보를 유지할지 보장 수 있습니다.  
  
 모든 로드 된 VSPackage는 올바르게 구성 되었으면.sln 파일을 저장 하는 아무 것도 열거 됩니다. 레지스트리 키를 쿼리 하는 로드 시간에만 솔루션을 저장 하는 시간에 메모리에 있기 때문에 모든 로드 된 패키지에 대 한 환경 알고 있습니다.  
  
 .Sln 파일 항목에 포함 되는 `preSolution` 및 `postSolution` 섹션입니다. 솔루션은이 정보를 제대로 로드 해야 하므로.suo 파일에 없는 비슷한 섹션은. .Suo 파일을 공유 하거나 소스 코드 제어에서 제공 되지 않은 개인 정보 등의 사용자 관련 옵션을 포함 합니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps>   
 [솔루션 사용자 옵션 \(합니다. Suo\) 파일](../../extensibility/internals/solution-user-options-dot-suo-file.md)   
 [솔루션](../../extensibility/internals/solutions.md)