---
title: "마법사 인터페이스 (IDTWizard) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IDTWizard interface
- wizards, interface
ms.assetid: 09618d9d-d115-45b6-bccc-de328994b39c
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ba6952bce6d99149f2a8f18b7d2eac12cbd08761
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="wizard-interface-idtwizard"></a>마법사 인터페이스 (IDTWizard)
통합된 개발 환경 (IDE)을 사용 하 여 <xref:EnvDTE.IDTWizard> 마법사와 통신 하는 인터페이스입니다. 마법사는 IDE에서 설치 하려면이 인터페이스를 구현 해야 합니다.  
  
 <xref:EnvDTE.IDTWizard.Execute%2A> 메서드는 연결 된 하는 유일한 방법은 <xref:EnvDTE.IDTWizard> 인터페이스입니다. 마법사는이 메서드를 구현 하 고 IDE 인터페이스에서 메서드를 호출 합니다. 다음 예제에서는 메서드의 서명을 보여 줍니다.  
  
```  
/* IDTWizard Method */  
STDMETHOD(Execute)(THIS_  
   /* [in] */ IDispatch *Application,  
   /* [in] */ long hwndOwner,  
   /* [in] */ SAFEARRAY * *ContextParams,  
   /* [in] */ SAFEARRAY * *CustomParams,  
   /* [out] [in] */ wizardResult *RetVal  
   );  
```  
  
 시작 메커니즘은 모두에 대 한 유사는 **새 프로젝트** 및 **새 항목 추가**마법사. 호출 중 하나를 시작 하려면는 <xref:EnvDTE.IDTWizard> Dteinternal.h에 정의 된 인터페이스입니다. 유일한 차이점은 컨텍스트 및 인터페이스를 호출할 때 인터페이스에 전달 되는 사용자 지정 매개 변수 집합.  
  
 다음 설명에서 <xref:EnvDTE.IDTWizard> 마법사에서 작동 하도록 구현 해야 하는 인터페이스는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE. IDE 호출은 <xref:EnvDTE.IDTWizard.Execute%2A> 메서드 다음 전달 마법사에서:  
  
-   DTE 개체  
  
     DTE 개체는 자동화 모델의 루트입니다.  
  
-   코드 세그먼트에 표시 된 대로 창 대화 상자에 대 한 핸들 `hwndOwner ([in] long)`합니다.  
  
     마법사는이 사용 하 여 `hwndOwner` 마법사 대화 상자에 대 한 부모로 합니다.  
  
-   컨텍스트 매개 변수 전달 된 인터페이스에 variant로 서 SAFEARRAY에 대 한 코드 세그먼트에 표시 된 대로 `[in] SAFEARRAY (VARIANT)* ContextParams`합니다.  
  
     컨텍스트 매개 변수는 시작 되 고 마법사의 종류에만 적용 되는 값의 배열 및 프로젝트의 현재 상태를 포함 합니다. IDE는 마법사를 컨텍스트 매개 변수를 전달합니다. 자세한 내용은 참조 [컨텍스트 매개 변수](../../extensibility/internals/context-parameters.md)합니다.  
  
-   사용자 지정 매개 변수는 인터페이스에 variant로 전달 SAFEARRAY에 대 한 코드 세그먼트에 표시 된 대로 `[in] SAFEARRAY (VARIANT)* CustomParams`합니다.  
  
     사용자 지정 매개 변수는 사용자 정의 매개 변수 배열을 포함 합니다. .Vsz 파일 IDE를 사용자 지정 매개 변수를 전달합니다. 값으로 결정 됩니다는 `Param=` 문. 자세한 내용은 참조 [사용자 지정 매개 변수](../../extensibility/internals/custom-parameters.md)합니다.  
  
-   인터페이스에 대 한 반환 값은  
  
    ```  
    wizardResultSuccess = -1,  
    wizardResultFailure = 0  
    wizardResultCancel = 1  
    wizardResultBackout = 2  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [컨텍스트 매개 변수](../../extensibility/internals/context-parameters.md)   
 [사용자 지정 매개 변수](../../extensibility/internals/custom-parameters.md)   
 [마법사](../../extensibility/internals/wizards.md)   
 [마법사(.Vsz) 파일](../../extensibility/internals/wizard-dot-vsz-file.md)