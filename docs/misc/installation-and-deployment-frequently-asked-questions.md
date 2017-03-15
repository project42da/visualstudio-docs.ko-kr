---
title: "설치 및 배포 질문과 대답 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "배포[Visual Studio SDK]"
  - "LCID[Visual Studio SDK]"
  - "설치[Visual Studio SDK]"
ms.assetid: 4ac62bf3-e335-4899-9074-89bcd004dc65
caps.latest.revision: 10
caps.handback.revision: 10
manager: "douge"
---
# 설치 및 배포 질문과 대답
이 항목에서 질문을 해결의 [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] 설치 및 배포 하는 방법에 대 한 사용자 커뮤니티.  주제 계속 커뮤니티의 새로운 내용으로 업데이트 합니다.  
  
## 내용  
  
-   [Visual Studio 설치의 LCID를 프로그래밍 방식으로 확인 하](#DeterminingtheLCIDofaVisualStudioInstallationProgrammatically)  
  
##  <a name="DeterminingtheLCIDofaVisualStudioInstallationProgrammatically"></a> Visual Studio 설치의 LCID를 프로그래밍 방식으로 확인 하  
 **Q:**  LCID를 프로그래밍 방식으로 확인 하는 방법이 있는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 설치?  
  
 **A:** <xref:Microsoft.VisualStudio.Shell.Interop.IUIHostLocale2.GetUILocale%2A> 또는 <xref:Microsoft.VisualStudio.Shell.Interop.IUIHostLocale.GetUILocale%2A>LCID를 반환 합니다 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 현재 사용 중인.  
  
## 참고 항목  
 [제품 릴리스](../misc/releasing-a-visual-studio-integration-product.md)