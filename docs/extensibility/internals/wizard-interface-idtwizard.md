---
title: "마법사 인터페이스 (IDTWizard) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDTWizard 인터페이스"
  - "마법사, 인터페이스,"
ms.assetid: 09618d9d-d115-45b6-bccc-de328994b39c
caps.latest.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 8
---
# 마법사 인터페이스 (IDTWizard)
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

통합된 개발 환경 \(IDE\)을 사용 하 여 <xref:EnvDTE.IDTWizard> 마법사와 통신할 수 있는 인터페이스입니다.  마법사가 IDE에서 설치 하기 위해이 인터페이스를 구현 해야 합니다.  
  
 <xref:EnvDTE.IDTWizard.Execute%2A> 방법입니다 관련만 메서드를 <xref:EnvDTE.IDTWizard> 인터페이스입니다.  마법사가이 메서드를 구현 하 고 IDE 인터페이스의 메서드를 호출 합니다.  다음은 메서드의 시그니처를 보여 줍니다.  
  
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
  
 시작 메커니즘을 유사의  **새 프로젝트** 및  **새 항목 추가** 마법사가 있습니다.  호출 중 하나를 시작 하는 <xref:EnvDTE.IDTWizard> dteinternal.h에서 정의 하는 인터페이스입니다.  유일한 차이점은 컨텍스트 및 인터페이스를 호출 하면 인터페이스에 전달 되는 사용자 지정 매개 변수 집합입니다.  
  
 다음 정보를 설명에 <xref:EnvDTE.IDTWizard> 마법사에서 작업을 구현 해야 하는 인터페이스는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE.  IDE 호출을 <xref:EnvDTE.IDTWizard.Execute%2A> 메서드에 전달 하는 다음 마법사를.  
  
-   DTE 개체  
  
     DTE 개체는 자동화 모델의 루트입니다.  
  
-   코드 세그먼트에 나와 있는 것 처럼 창 대화 상자에 대 한 핸들 `hwndOwner ([in] long)`.  
  
     이 마법사를 사용 하 여 `hwndOwner` 마법사 대화 상자에는 부모와.  
  
-   컨텍스트 매개 변수 전달 인터페이스를 variant로 SAFEARRAY를 코드 세그먼트에서와 같이 `[in] SAFEARRAY (VARIANT)* ContextParams`.  
  
     컨텍스트 매개 변수는 마법사를 시작 하는 종류에 관련 된 값의 배열 및 프로젝트의 현재 상태를 포함 합니다.  IDE 컨텍스트 매개 변수를 마법사에 전달합니다.  자세한 내용은 [컨텍스트 매개 변수](../../extensibility/internals/context-parameters.md)를 참조하십시오.  
  
-   사용자 지정 매개 변수 전달 인터페이스를 variant로 SAFEARRAY를 코드 세그먼트에서와 같이 `[in] SAFEARRAY (VARIANT)* CustomParams`.  
  
     사용자 지정 매개 변수 사용자 정의 매개 변수 배열 포함 되어 있습니다.  .Vsz 파일에 IDE 사용자 지정 매개 변수를 전달합니다.  값에 의해 결정 됩니다 있는 `Param=` 문입니다.  자세한 내용은 [사용자 지정 매개 변수](../../extensibility/internals/custom-parameters.md)를 참조하십시오.  
  
-   인터페이스에 대 한 반환 값  
  
    ```  
    wizardResultSuccess = -1,  
    wizardResultFailure = 0  
    wizardResultCancel = 1  
    wizardResultBackout = 2  
    ```  
  
## 참고 항목  
 [컨텍스트 매개 변수](../../extensibility/internals/context-parameters.md)   
 [사용자 지정 매개 변수](../../extensibility/internals/custom-parameters.md)   
 [마법사](../../extensibility/internals/wizards.md)   
 [마법사 \(합니다. Vsz\) 파일](../../extensibility/internals/wizard-dot-vsz-file.md)