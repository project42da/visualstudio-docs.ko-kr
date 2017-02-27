---
title: "사용자 지정 매개 변수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "마법사를 사용자 지정 매개 변수"
  - "사용자 지정 매개 변수"
ms.assetid: ba5c364b-66e6-47ea-9760-a0b70de8f0a0
caps.latest.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 13
---
# 사용자 지정 매개 변수
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

마법사를 시작한 후 사용자 지정 매개 변수를 마법사의 작업을 제어 합니다.  관련된.vsz 파일에는 통합된 개발 환경 \(IDE\)에서 패키지 되 고 마법사가 시작 되 면 마법사에 문자열 배열을 이름으로 전달 하는 사용자 정의 매개 변수 배열을 제공 합니다.  다음 마법사 문자열 배열을 구문 분석 하 고 정보를 사용 하 여 실제 작업 마법사에.  이 방법으로 마법사 기능.vsz 파일의 내용에 따라 사용자 지정할 수 있습니다.  
  
 한편, 컨텍스트 매개 변수를 마법사를 시작할 때 프로젝트의 상태를 정의 합니다.  자세한 내용은 [컨텍스트 매개 변수](../../extensibility/internals/context-parameters.md)를 참조하십시오.  
  
 다음은 사용자 지정 매개 변수가.vsz 파일의 예제입니다.  
  
```  
VSWIZARD 8.0  
Wizard=VsWizard.VsWizard_Engine  
Param="WIZARD_NAME = Sample Wizard"  
Param="WIZARD_UI = FALSE"  
Param="RELATIVE_PATH = VSWizards\Classwiz\ATL"  
Param="PREPROCESS_FUNCTION = CanAddATLSupport"  
Param="PROJECT_TYPE = CSPROJ"  
```  
  
 .Vsz 파일의 작성자는 매개 변수 값을 추가합니다.  사용자가 선택할 때  **새 프로젝트** 또는  **새 항목 추가** 에서 프로젝트를 마우스 오른쪽 단추로 클릭 하거나 파일 메뉴에서  **솔루션 탐색기**, IDE 이러한 값의 문자열 배열에 수집 합니다.  다음 IDE는 프로젝트를 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.AddItem%2A> 메서드를 사용의 <xref:Microsoft.VisualStudio.Shell.Interop.VSADDITEMOPERATION> 집합 및 프로젝트 호출 플래그를 <xref:EnvDTE.IVsExtensibility.RunWizardFile%2A> 마법사를 실행 하 고 결과 반환 하는 메서드.  
  
 마법사 문자열 배열을 구문 분석 하 고 문자열을 적절 하 게 작동 됩니다.  이 방법으로 사용자 지정 매개 변수를 구현 하 여 다양 한 기능을 수행 하는 한 가지 마법사를 만들 수 있습니다.  즉, 하나의 마법사 세 가지 서로 다른.vsz 파일이 있을 수 있습니다.  각 파일이 서로 다른 다양 한 상황에서 마법사의 동작을 제어 하는 사용자 지정 매개 변수를 전달 합니다.  
  
 자세한 내용은 [마법사 \(합니다. Vsz\) 파일](../../extensibility/internals/wizard-dot-vsz-file.md)를 참조하십시오.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3>   
 [컨텍스트 매개 변수](../../extensibility/internals/context-parameters.md)   
 [마법사](../../extensibility/internals/wizards.md)   
 [마법사 \(합니다. Vsz\) 파일](../../extensibility/internals/wizard-dot-vsz-file.md)