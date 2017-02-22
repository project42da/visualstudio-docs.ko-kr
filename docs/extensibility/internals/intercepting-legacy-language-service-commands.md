---
title: "레거시 언어 서비스 명령 가로채기 | Microsoft Docs"
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
  - "언어 서비스를 차단 하는 명령"
  - "언어 서비스, 명령 가로채기"
ms.assetid: eea69f03-349c-44bb-bd4f-4925c0dc3e55
caps.latest.revision: 13
caps.handback.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
---
# 레거시 언어 서비스 명령 가로채기
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

함께 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], 텍스트 뷰를 처리 합니다. 그렇지 않으면 언어 서비스 차단 명령을 사용할 수 있습니다.  텍스트 보기에서 관리 하지 않는 특정 언어 관련 문제에 대 한 유용 합니다.  언어 서비스에서 하나 이상의 명령을 필터 텍스트 보기에 추가 하 여 이러한 명령을 가로챌 수 있습니다.  
  
## 가져오기 및 명령 라우팅  
 명령 필터는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 특정 문자 시퀀스가 또는 키 명령을 모니터링 하는 개체입니다.  단일 텍스트 보기와 두 개 이상의 명령 필터를 연결할 수 있습니다.  각 텍스트 보기 체인의 명령 필터를 유지합니다.  새 명령 필터를 만든 후 적절 한 텍스트 보기에 대 한 체인에 필터를 추가 합니다.  
  
 호출의 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.AddCommandFilter%2A> 방법에의 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 명령을 필터 체인에 추가 합니다.  호출 하면 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.AddCommandFilter%2A>, [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 명령 필터를 처리 하지 않는 명령을 전달할 수 있는 다른 명령 필터를 반환 합니다.  
  
 경우 명령 처리를 위한 다음과 같은 옵션이 있습니다.  
  
-   명령을 처리 하 고 명령에 다음 명령 필터 체인에 전달 합니다.  
  
-   명령을 처리 하 고 명령 다음 명령 필터를 전달 하지 마십시오.  
  
-   명령을 처리 하지 않는 있지만 명령 다음 명령 필터를 통과 합니다.  
  
-   명령이 무시 됩니다.  현재 필터를 처리 하지 않는 및 다음 필터에 전달 하지 마십시오.  
  
 해야 합니다 어떤 명령에 대 한 언어 서비스 처리에 대 한 정보를 참조 하십시오. [언어 서비스 필터에 대 한 중요 한 명령](../../extensibility/internals/important-commands-for-language-service-filters.md).