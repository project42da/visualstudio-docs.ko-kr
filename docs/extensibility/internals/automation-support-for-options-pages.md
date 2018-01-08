---
title: "옵션 페이지에 대 한 자동화 지원 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Tools Options pages [Visual Studio SDK], automation support
- automation [Visual Studio SDK], creating Tools Options pages
ms.assetid: 0b25b82c-7432-4e0a-9e84-350269ba8260
caps.latest.revision: "29"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: ffc56e4b36814a8bed7a0f93d66cc87c0b6fc466
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="automation-support-for-options-pages"></a>옵션 페이지에 대 한 자동화 지원
Vspackage는 사용자 지정을 제공할 수 **옵션** 대화 상자에 **도구** 메뉴 (도구 옵션 페이지)에서 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 있습니다 사용할 수 있도록 자동화 모델을 합니다.  
  
## <a name="tools-options-pages"></a>도구 옵션 페이지  
 만들려는 **도구 옵션** 페이지에서 VSPackage에 VSPackage의 구현을 통해 환경에 반환 하는 사용자 컨트롤 구현을 제공 해야 합니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetPropertyPage%2A> 메서드 (또는 관리 코드에 대 한는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetPropertyPage%2A> 방법)입니다.  
  
 것은 선택 사항 이지만 자동화 모델을 통해이 새 페이지에 대 한 액세스를 허용 하도록 좋습니다. 이 다음 단계를 수행할 수 있습니다.  
  
1.  확장 된 <xref:EnvDTE._DTE.Properties%2A> IDispatch에서 파생 된 개체의 구현을 통해 개체입니다.  
  
2.  구현을 반환는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetAutomationObject%2A> 메서드 (또는 관리 코드에 대 한는 <xref:Microsoft.VisualStudio.Shell.Package.GetAutomationObject%2A> 메서드)를 IDispatch에서 파생 된 개체입니다.  
  
3.  자동화 소비자 호출 하는 경우는 <xref:EnvDTE._DTE.Properties%2A> 사용자 지정 메서드 **옵션** 환경을 사용 하 여 속성 페이지는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetAutomationObject%2A> 메서드에서 사용자 지정을 가져오기 위해 **도구 옵션** 페이지의 자동화 구현입니다.  
  
4.  VSPackage의 자동화 개체는 다음에 나오는 각 제공 하는 데 사용 됩니다 <xref:EnvDTE.Property> 반환한 <xref:EnvDTE._DTE.Properties%2A>합니다.  
  
 사용자 지정 도구 옵션 페이지를 구현 하는 샘플을 보려면 [VSSDK 샘플](http://aka.ms/vs2015sdksamples)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로젝트 개체 노출](../../extensibility/internals/exposing-project-objects.md)