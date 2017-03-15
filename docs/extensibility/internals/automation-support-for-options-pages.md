---
title: "옵션 페이지에 대 한 자동화 지원 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "도구 옵션 페이지 [Visual Studio SDK] 자동화 지원"
  - "자동화 [Visual Studio SDK] 도구 옵션 페이지 만들기"
ms.assetid: 0b25b82c-7432-4e0a-9e84-350269ba8260
caps.latest.revision: 29
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 29
---
# 옵션 페이지에 대 한 자동화 지원
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

Vspackage 사용자 지정을 제공할 수 있습니다 **옵션** 대화 상자에 **도구** 메뉴 \(도구 옵션 페이지\)에서 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 고 수 있도록 자동화 모델에 사용할 수 있습니다.  
  
## 도구 옵션 페이지  
 만들려는 **도구 옵션** 페이지 VSPackage의 VSPackage의 구현을 통해 환경에 반환 하는 사용자 컨트롤 구현을 제공 해야는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetPropertyPage%2A> 메서드를 \(또는 관리 코드는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetPropertyPage%2A> 메서드\).  
  
 것은 선택 사항 이지만 자동화 모델을 통해이 새 페이지에 대 한 액세스를 허용 하도록 좋습니다. 다음 단계를 통해이 수행할 수 있습니다.  
  
1.  확장 된 <xref:EnvDTE._DTE.Properties%2A> IDispatch에서 파생 된 개체의 구현을 통해 개체입니다.  
  
2.  구현을 반환는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetAutomationObject%2A> 메서드 \(또는 관리 코드에 대 한는 <xref:Microsoft.VisualStudio.Shell.Package.GetAutomationObject%2A> 메서드\) IDispatch 파생 개체입니다.  
  
3.  자동화 소비자가 호출 하는 경우는 <xref:EnvDTE._DTE.Properties%2A> 사용자 지정 메서드 **옵션** 환경을 사용 하 여 속성 페이지는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetAutomationObject%2A> 를 가져오는 사용자 지정 메서드가 **도구 옵션** 페이지의 자동화를 구현 합니다.  
  
4.  VSPackage의 자동화 개체는 다음 각를 제공 하는 데 사용 됩니다 <xref:EnvDTE.Property> 반환한 <xref:EnvDTE._DTE.Properties%2A>합니다.  
  
 사용자 지정 도구 옵션 페이지를 구현 하는 샘플을 보려면 [VSSDK 샘플](../../misc/vssdk-samples.md)합니다.  
  
## 참고 항목  
 [프로젝트 개체 노출](../../extensibility/internals/exposing-project-objects.md)