---
title: "솔루션 (합니다. Sln) 파일 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- sln files, VSPackages
- solutions, .sln files
- .sln files, VSPackages
ms.assetid: 7d7ef539-2e4b-4637-b853-8ec7626609df
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b7be9b3bf7783980cfbbe1abfc44fe1748dd20a2
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="solution-sln-file"></a>솔루션 (합니다. Sln) 파일
솔루션에 Visual Studio에서 프로젝트를 구성 하기 위한 구조입니다. 솔루션은 프로젝트 (텍스트 기반, 공유).sln 및.suo (이진, 사용자 고유의 솔루션 옵션) 파일에 대 한 상태 정보를 유지 관리합니다. .Suo 파일에 대해 보다 자세한 정보를 참조 하십시오. [솔루션 사용자 옵션 (합니다. Suo) 파일](../../extensibility/internals/solution-user-options-dot-suo-file.md)합니다.  
  
 VSPackage는.sln 파일에서 참조 하 고 결과로 로드 되 면 환경 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps.ReadSolutionProps%2A> .sln 파일을 읽을 수 있습니다.  
  
 .Sln 파일 환경 찾기 및 로드 영구 데이터 및 프로젝트를 참조 하는 Vspackage에 대 한 이름-값 매개 변수를 사용 하 여 텍스트 기반 정보를 포함 합니다. 사용자가 솔루션을 열면 환경을 돌아가면서 선택 합니다는 `preSolution`, `Project`, 및 `postSolution` 솔루션을 로드 하려면.sln 파일의 정보는 솔루션 내 프로젝트 및 솔루션에 연결 된 모든 지속형된 정보입니다.  
  
 각 프로젝트의 파일을 해당 프로젝트의 항목 계층 구조를 채우는 환경에서 읽은 추가 정보를 포함 합니다. 계층 데이터 지 속성; 프로젝트에 의해 제어 됩니다. 데이터는 일반적으로 있지만 저장 되지 않습니다.sln 파일에 쓸 수 있습니다 의도적으로 프로젝트 정보.sln 파일 그렇게 하도록 선택할 경우. 지 속성에 관련 된 자세한 내용은 참조 하십시오. [프로젝트 지 속성](../../extensibility/internals/project-persistence.md) 및 [열기 및 프로젝트 항목 저장](../../extensibility/internals/opening-and-saving-project-items.md)합니다.  
  
## <a name="solution-file-contents"></a>솔루션 파일 내용  
 다음 코드 에서처럼.sln 파일 여러 개의 섹션으로 이루어져 있습니다.  
  
```  
Project("{F184B08F-C81C-45F6-A57F-5ABD9991F28F}") = "Project1", "Project1.vbproj", "{8CDD8387-B905-44A8-B5D5-07BB50E05BEA}"  
EndProject  
Global  
  GlobalSection(SolutionNotes) = postSolution  
  EndGlobalSection  
  GlobalSection(SolutionConfiguration) = preSolution  
       ConfigName.0 = Debug  
       ConfigName.1 = Release  
  EndGlobalSection  
  GlobalSection(ProjectDependencies) = postSolution  
  EndGlobalSection  
  GlobalSection(ProjectConfiguration) = postSolution  
   {8CDD8387-B905-44A8-B5D5-07BB50E05BEA}.Debug.ActiveCfg = Debug|x86  
   {8CDD8387-B905-44A8-B5D5-07BB50E05BEA}.Debug.Build.0 = Debug|x86  
   {8CDD8387-B905-44A8-B5D5-07BB50E05BEA}.Release.ActiveCfg = Release|x86  
   {8CDD8387-B905-44A8-B5D5-07BB50E05BEA}.Release.Build.0 = Release|x86  
  EndGlobalSection  
  GlobalSection(ExtensibilityGlobals) = postSolution  
  EndGlobalSection  
  GlobalSection(ExtensibilityAddIns) = postSolution  
  EndGlobalSection  
EndGlobal  
```  
  
 환경에 솔루션을 로드 하려면 다음 작업 순서를 수행 합니다.  
  
1.  환경.sln 파일의 전역 섹션을 읽고 표시 된 모든 섹션을 처리 `preSolution`합니다. 이 경우에 이러한 설명 중 하나입니다.  
  
    ```  
    GlobalSection(SolutionConfiguration) = preSolution  
         ConfigName.0 = Debug  
         ConfigName.1 = Release  
    ```  
  
     환경의 읽을 때의 `GlobalSection('name')` 태그 이름에 매핑됩니다 레지스트리를 사용 하는 VSPackage입니다. 키 이름 레지스트리의 아래에 있어야 합니다. [HKLM\\< 응용 프로그램 ID 레지스트리 루트\>\SolutionPersistence\AggregateGUIDs]. 키의 기본값은 항목을 작성 하는 VSPackage의 패키지 GUID (REG_SZ)입니다.  
  
2.  호출 VSPackage를 로드 하는 환경 `QueryInterface` VSPackage에 대 한 대는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps> 인터페이스를 호출 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps.ReadSolutionProps%2A> VSPackage 데이터를 저장할 수 있도록 섹션의 데이터를 사용 하 여 메서드. 각각에 대해이 프로세스를 반복 하는 환경 `preSolution` 섹션.  
  
3.  환경을은 프로젝트 지 속성 블록을 반복합니다. 이 경우에 프로젝트 하 나와 있습니다.  
  
    ```  
    Project("{F184B08F-C81C-45F6-A57F-5ABD9991F28F}") = "Project1",  
    "Project1.vbproj", "{8CDD8387-B905-44A8-B5D5-07BB50E05BEA}"  
    EndProject  
    ```  
  
     이 문은 고유한 프로젝트 GUID 및 프로젝트 형식 GUID 포함합니다. 각 프로젝트에 필요한 VSPackage 및이 정보는 파일이 나 프로젝트를 솔루션에 속하는 파일을 찾을 수 환경에서 사용 됩니다. GUID에 전달 되는 프로젝트 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory> 프로젝트와 관련 된 특정 VSPackage를 로드 하려면 다음 프로젝트가 로드 되는 VSPackage에서 합니다. 이 경우이 프로젝트에 대 한 로드 되는 VSPackage는 Visual Basic입니다.  
  
     각 프로젝트는 솔루션의 다른 프로젝트에서 필요에 따라 액세스할 수 있도록 고유한 프로젝트 인스턴스 ID를 유지할 수 있습니다. 이상적으로 소스 코드 제어에서 솔루션 및 프로젝트 인 경우 경로 프로젝트를 솔루션에 대 한 경로 기준으로 해야 합니다. 솔루션은 처음 로드할 때 프로젝트 파일 사용자의 컴퓨터 일 수 없습니다. 솔루션 파일을 기준으로 서버에 저장 된 프로젝트 파일 함으로써 발견 하 고 사용자의 컴퓨터에 복사 될 프로젝트 파일에 대 한 상대적으로 간단 합니다. 그런 다음 복사 하 고 프로젝트에 필요한 파일의 나머지 부분을 로드 합니다.  
  
4.  환경은.sln 파일의 프로젝트 섹션에 포함 된 정보에 따라, 각 프로젝트 파일을 로드 합니다. 프로젝트 자체은 프로젝트 계층 구조를 채우고 모든 중첩 된 프로젝트를 로드 하는 일을 담당 합니다.  
  
5.  .Sln 파일의 모든 섹션을 처리 한 후 솔루션 솔루션 탐색기에 표시 되 고 사용자가 수정 하기 위해 준비 합니다.  
  
 솔루션에서 프로젝트를 구현 하는 모든 VSPackage, 로드 되지 않으면는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps.OnProjectLoadFailure%2A> 메서드가 호출 되 고 솔루션의 다른 모든 프로젝트를 로드 하는 동안 않을 수 있는 변경 내용을 무시 제공 됩니다. 구문 분석 오류가 발생 한 경우 솔루션 파일 사용 가능한 많은 정보는 유지 하 고 환경을 사용자 솔루션 손상 되었음을 알리는 경고 대화 상자를 표시 합니다.  
  
 솔루션을 저장 하거나 닫을 때는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps.QuerySaveSolutionProps%2A> 메서드를 호출 하 고 보려면.sln 파일에 입력 해야 하는 솔루션에 변경 내용이 적용 된 계층에 전달 됩니다. 에 전달 되는 null 값을 `QuerySaveSolutionProps` 에 <xref:Microsoft.VisualStudio.Shell.Interop.VSQUERYSAVESLNPROPS>, 솔루션에 대 한 정보가 유지 되 고 되도록 나타냅니다. 보관된 된 정보는에 대 한 포인터에 의해 결정 되는 특정 프로젝트에 대 한 값이 null 이면는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> 인터페이스입니다.  
  
 정보를 저장할 수 없는 경우는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence> 인터페이스에 대 한 포인터를 사용 하 여 호출 되는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps.SaveSolutionProps%2A> 메서드. <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps.WriteSolutionProps%2A> 에서 이름-값 쌍을 검색 하는 환경에서 메서드가 호출 됩니다 `IPropertyBag` 인터페이스 및.sln 파일에 정보를 기록 합니다.  
  
 `SaveSolutionProps`및 `WriteSolutionProps` 개체에 저장할 정보를 검색 하는 환경에서 재귀적으로 호출 되는 `IPropertyBag` .sln 파일에 입력 된 모든 변경 될 때까지 인터페이스입니다. 이러한 방식으로 솔루션 및 사용 가능한 다음 솔루션을 열 때 사용 하 여 정보를 유지할지 보장 수 있습니다.  
  
 로드 된 모든 VSPackage.sln 파일을 저장 하는 아무 것도에 있는지를 열거 됩니다. 레지스트리 키를 쿼리 하는 로드 시만 것 합니다. 솔루션을 저장 하는 시간에 메모리에 있기 때문에 모든 로드 된 패키지에 대 한 환경을 알고 있습니다.  
  
 .Sln 파일에 항목이 포함 되는 `preSolution` 및 `postSolution` 섹션. 솔루션은이 정보를 제대로 로드 해야 하므로.suo 파일에 없는 비슷한 섹션 있습니다. .Suo 파일을 공유 하거나 소스 코드 제어에서 제공 되지 않은 개인 정보 같은 사용자 관련 옵션을 포함 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps>   
 [솔루션 사용자 옵션 (합니다. Suo) 파일](../../extensibility/internals/solution-user-options-dot-suo-file.md)   
 [솔루션](../../extensibility/internals/solutions.md)