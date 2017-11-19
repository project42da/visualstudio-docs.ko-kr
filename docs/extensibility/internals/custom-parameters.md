---
title: "사용자 지정 매개 변수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- wizards, custom parameters
- custom parameters
ms.assetid: ba5c364b-66e6-47ea-9760-a0b70de8f0a0
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3f04251ea8141d07a52499beae46b2881814eec9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="custom-parameters"></a>사용자 지정 매개 변수
사용자 지정 매개 변수는 마법사를 시작한 후에 마법사를 작동을 제어 합니다. 관련된.vsz 파일에는 통합된 개발 환경 (IDE)에서 패키지 되 고 마법사를 시작할 때 문자열의 배열로 마법사에 전달 하는 사용자 정의 매개 변수 배열을 제공 합니다. 마법사는 다음 문자열의 배열을 구문 분석 하 고 마법사의 실제 작동을 제어 하는 정보를 사용 합니다. 이러한 방식으로 마법사.vsz 파일의 내용에 따라 기능을 사용자 지정할 수 있습니다.  
  
 반면에 컨텍스트 매개 변수 마법사가 시작 하는 경우 프로젝트의 상태를 정의 합니다. 자세한 내용은 참조 [컨텍스트 매개 변수](../../extensibility/internals/context-parameters.md)합니다.  
  
 다음은 사용자 지정 매개 변수가.vsz 파일의 예입니다.  
  
```  
VSWIZARD 8.0  
Wizard=VsWizard.VsWizard_Engine  
Param="WIZARD_NAME = Sample Wizard"  
Param="WIZARD_UI = FALSE"  
Param="RELATIVE_PATH = VSWizards\Classwiz\ATL"  
Param="PREPROCESS_FUNCTION = CanAddATLSupport"  
Param="PROJECT_TYPE = CSPROJ"  
```  
  
 .Vsz 파일의 작성자는 매개 변수의 값을 추가합니다. 사용자가 선택할 때 **새 프로젝트** 또는 **새 항목 추가** 에서 프로젝트를 마우스 오른쪽 단추로 클릭 하거나 파일 메뉴에서 **솔루션 탐색기**, IDE의 배열에 이러한 값 수집 문자열입니다. IDE는 프로젝트의 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.AddItem%2A> 메서드는 <xref:Microsoft.VisualStudio.Shell.Interop.VSADDITEMOPERATION> 집합과 프로젝트 호출을 플래그는 <xref:EnvDTE.IVsExtensibility.RunWizardFile%2A> 마법사를 실행 하 고 결과 반환 하는 일을 담당 하는 메서드.  
  
 마법사는 문자열의 배열을 구문 분석 하 고 문자열에 적절 하 게 작동 하는 일을 담당 합니다. 사용자 지정 매개 변수를 구현 하 여 이러한 방식으로 다양 한 기능을 수행 하는 하나의 마법사를 만들 수 있습니다. 즉, 하나의 마법사에 세 개의 다른.vsz 파일 있을 수 있습니다. 각 파일에는 다른 다양 한 상황에서 마법사의 동작을 제어 하는 사용자 지정 매개 변수 집합이 전달 합니다.  
  
 자세한 내용은 참조 [마법사 (합니다. Vsz) 파일](../../extensibility/internals/wizard-dot-vsz-file.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3>   
 [컨텍스트 매개 변수](../../extensibility/internals/context-parameters.md)   
 [마법사](../../extensibility/internals/wizards.md)   
 [마법사(.Vsz) 파일](../../extensibility/internals/wizard-dot-vsz-file.md)