---
title: "레거시 언어 서비스 명령 가로채 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- commands, intercepting language service
- language services, intercepting commands
ms.assetid: eea69f03-349c-44bb-bd4f-4925c0dc3e55
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 73524ce47dfea2d30e44e51e97bf584a95a86482
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="intercepting-legacy-language-service-commands"></a>가로채 레거시 언어 서비스 명령
와 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], 텍스트 보기는 그렇지 않은 경우 처리 하는 언어 서비스 절편 명령이 있을 수 있습니다. 텍스트 보기 관리 하지 않는 언어 관련 동작에 유용 합니다. 언어 서비스에서 텍스트 보기에 하나 이상의 명령 필터를 추가 하 여 이러한 명령을 가로챌 수 있습니다.  
  
## <a name="getting-and-routing-the-command"></a>가져오기 및 명령 라우팅  
 명령 필터는는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 특정 문자 시퀀스 또는 키 명령을 모니터링 하는 개체입니다. 단일 텍스트 보기를 통해 여러 명령 필터를 연결할 수 있습니다. 각 텍스트 보기 체인 of 명령 필터를 유지 관리합니다. 새 명령 필터를 만든 후에 적절 한 텍스트 보기에 대 한 체인에 필터를 추가 합니다.  
  
 호출는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.AddCommandFilter%2A> 메서드를는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 명령 필터 체인에 추가 합니다. 호출 하는 경우 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.AddCommandFilter%2A>, [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 명령 필터를 처리 하지 않는 명령을 전달할 수 있는 다른 명령 필터를 반환 합니다.  
  
 명령 처리에 대 한 다음과 같은 옵션이 있습니다.  
  
-   명령을 처리 하 고 체인에 있는 다음 명령 필터에 명령을 전달 합니다.  
  
-   명령을 처리 하 고 명령 필터에 명령을 전달 하지 마십시오.  
  
-   명령을 처리 하지 않는 있지만 다음 명령 필터에 로그온 하는 명령을 전달 합니다.  
  
-   이 명령은 무시 됩니다. 현재 필터에서 처리 하지 않는 하 고 필터에 전달 하지 마십시오.  
  
 언어 서비스 처리 하는 명령에 대 한 정보를 참조 하십시오. [언어 서비스 필터에 대 한 중요 한 명령을](../../extensibility/internals/important-commands-for-language-service-filters.md)합니다.