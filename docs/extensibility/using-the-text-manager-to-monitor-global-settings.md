---
title: "전역 설정을 모니터링 하는 텍스트 관리자를 사용 하 여 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - monitor global settings
- editors [Visual Studio SDK], legacy - text manager
ms.assetid: 023e7671-cf65-419c-9bc1-3c4ee92aa436
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f9687e4f0be16fb42f13c6f9dd20a2cb39be50cd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="using-the-text-manager-to-monitor-global-settings"></a>전역 설정을 모니터링 하는 텍스트 관리자를 사용 하 여
코어 편집기를 구현 하는 경우 이러한 변경 내용은 편집기 인스턴스에 영향을 줄 수 있으므로 전역 설정에 대 한 변경 내용을 모니터링 해야 합니다. 텍스트 관리자에서 발생 한 이벤트를 수신 하 여 변경 내용을 추적할 수 있습니다. 예를 들어 해당 문서 데이터 개체와 같은 핵심 편집기에서 기본 모양이 나 구성 요소의 동작에 대 한 전역 설정을 지정 하는 경우 텍스트 관리자는이 정보를 저장 및 영향을 받는 모든 클라이언트와 통신 합니다.  
  
## <a name="text-manager-functions"></a>텍스트 관리자 기능  
 텍스트 관리자는 다음과 같은 설정의 숫자에 대 한 이벤트를 발생 시킵니다.  
  
-   소스 코드 제어에서 버퍼 인지 여부  
  
-   파일 변경 알림을 등록 하는 방법  
  
-   특정 버퍼와 연결 된 뷰를 추적 하는 방법  
  
-   텍스트 색 지정 환경 설정  
  
-   공간 기본 설정 및 탭  
  
 텍스트 관리자에 의해 지정된 된 언어에 고유한 기본 설정 관리 되지 않는 합니다. 이러한 설정은 각 언어 서비스에 의해 관리 되어야 합니다.  
  
 텍스트 관리자에 대 한 이벤트 알림을에서 제공 되는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextManagerEvents> 인터페이스입니다. 이 인터페이스를 구현 클라이언트에서 이벤트를 처리 하는 개체는 텍스트 관리자 발생 합니다. 사용 하 여 이러한 이벤트에 등록 된 <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer> 인터페이스에는 텍스트 관리자.  
  
## <a name="see-also"></a>참고 항목  
 [코어 편집기 내](../extensibility/inside-the-core-editor.md)   
 [편집기 기능](http://msdn.microsoft.com/en-us/bdac940d-1f14-4019-a01f-fd0bb3dc7198)