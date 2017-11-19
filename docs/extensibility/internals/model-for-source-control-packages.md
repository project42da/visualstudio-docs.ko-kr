---
title: "소스 제어 패키지에 대 한 모델 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: source control [Visual Studio SDK], model
ms.assetid: 6164b2d3-a622-4de8-bef3-a6de985e9ebd
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a8dacc0a3dfc230085c7575960238711d16d1ef8
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="model-for-source-control-packages"></a>소스 제어 패키지에 대 한 모델
다음과 같은 모델의 소스 제어 구현 예를 나타냅니다. 모델에 구현 해야 하는 인터페이스 및 환경 서비스 호출 해야 하는 것이 표시 됩니다. 모든 서비스와 마찬가지로 실제로 서비스를 통해 얻을 특정 인터페이스의 메서드를 호출 합니다. 클래스의 이름은 쉽게 소스 제어 수행 방법을 볼 수 있도록 식별 됩니다.  
  
 ![SCC &#95; TUP 예제](../../extensibility/internals/media/scc_tup.gif "SCC_TUP")  
예제에서는 소스 제어 프로젝트  
  
## <a name="interfaces"></a>인터페이스  
 다음 표에 표시 된 인터페이스의 목록을 사용 하 여 Visual Studio에서 새 프로젝트 형식에 대 한 소스 제어를 구현할 수 있습니다.  
  
|인터페이스|기능|  
|---------------|---------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>|프로젝트 및 변경 (더티) 파일 하거나 저장 하기 전에 편집기에서 호출 됩니다. 이 인터페이스를 사용 하 여 액세스 되는 <xref:Microsoft.VisualStudio.Shell.Interop.SVsQueryEditQuerySave> 서비스입니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>|프로젝트를 추가, 제거 또는 파일 또는 디렉터리의 이름을 바꿀 수 있는 권한 요청에 의해 호출 됩니다. 승인 된 추가, 제거 또는 작업의 이름을 바꿀 때 환경 완료 상태임을 알릴 프로젝트에서이 인터페이스를 사용 하는 것이 라고도 합니다. 사용 하 여 액세스 하는 데는 것은 <xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackProjectDocuments> 서비스입니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents2>|프로젝트를 추가, 이름 바꾸기 또는 파일이 나 디렉터리를 제거 하는 경우 알림을 받으려면 등록 하는 엔터티만 구현 합니다. 이벤트 알림에 등록, 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2.AdviseTrackProjectDocumentsEvents%2A>합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2>|프로젝트 소스 제어 패키지를 등록 하 고 소스 제어 상태에 대 한 정보를 가져올 수에 의해 호출 됩니다. 이 인터페이스를 사용 하 여 액세스 되는 <xref:Microsoft.VisualStudio.Shell.Interop.SVsSccManager> 서비스입니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2>|프로젝트 파일에 대 한 정보에 대 한 소스 제어 요청에 응답 하 고 소스 제어 설정 된 프로젝트 파일에 필요한를 가져올 수에 의해 구현 됩니다.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2.AdviseTrackProjectDocumentsEvents%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents2>   
 [소스 제어 지원](../../extensibility/internals/supporting-source-control.md)