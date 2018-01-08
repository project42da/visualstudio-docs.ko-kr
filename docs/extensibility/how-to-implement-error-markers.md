---
title: "방법: 오류 표식 구현 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - error markers
ms.assetid: e8e78514-5720-4fc2-aa43-00b6af482e38
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: d41c1bf063ea074df217934a00f73291a10e051d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-implement-error-markers"></a>방법: 오류 마커를 구현 합니다.
오류 표식 (또는 빨간색 물결 무늬 밑줄로)은 가장 어려운 텍스트 편집기 사용자 지정을 구현 합니다. 그러나 VSPackage의 사용자에 게 이점을 제공 하는 데 드는 비용이 훨씬 보다 클 수 있습니다. 오류 표식 언어 파서 따라 빨간색 구불구불한 또는 물결 모양의 선으로 잘못 된 경우 텍스트를 미세 하 게 표시 합니다. 잘못 된 코드를 시각적으로 표시 하 여 프로그래머에 도움이 됩니다.  
  
 텍스트 표식을 사용 하 여 빨간색 물결 무늬 밑줄로 구현. 일반적으로 언어 서비스 추가 빨간색 물결 무늬 밑줄로 텍스트 버퍼를 백그라운드 패스를으로 유휴 시간 또는 백그라운드 스레드에서 합니다.  
  
### <a name="to-implement-the-red-wavy-underline-feature"></a>빨간색 물결선 기능을 구현 하려면  
  
1.  빨간색 물결선을 배치 하려는 텍스트를 선택 합니다.  
  
2.  형식의 표식 만들기 `MARKER_CODESENSE_ERROR`합니다. 자세한 내용은 참조 [하는 방법: 표준 텍스트 표식 추가](../extensibility/how-to-add-standard-text-markers.md)합니다.  
  
3.  그 후에 전달 된 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> 인터페이스 포인터입니다.  
  
 이 프로세스를 사용 하면 특정된 표식을 통해 팁 텍스트 또는 특별 한 상황에 맞는 메뉴를 만들 수 있습니다. 자세한 내용은 참조 [하는 방법: 표준 텍스트 표식 추가](../extensibility/how-to-add-standard-text-markers.md)합니다.  
  
 오류 표식을 표시할 수에 다음 개체가 필요 합니다.  
  
-   파서입니다.  
  
-   작업 공급자 (즉, 구현 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskProvider2>)을 줄 정보에는 변경 레코드를 다시 구문 분석할 줄을 식별 하기 위해 유지 관리 합니다.  
  
-   변경 이벤트를 사용 하 여 보기에서 캐럿을 캡처하는 텍스트 뷰 필터는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewEvents.OnChangeCaretLine%2A>) 메서드.  
  
 파서, 작업 공급자 및 필터에는 오류 마커를 가능 하 게 하는 데 필요한 인프라를 제공 합니다. 다음 단계는 오류 표식을 표시 하기 위한 프로세스를 제공 합니다.  
  
1.  필터링 된 보기에서 필터는 해당 보기의 데이터와 관련 된 작업 공급자에 대 한 포인터를 가져옵니다.  
  
    > [!NOTE]
    >  메서드 팁, 문 완성, 오류 표식 등에 대 한 동일한 명령 필터를 사용할 수 있습니다.  
  
2.  필터 다른 줄으로 이동 했음을 나타내는 이벤트를 받으면 오류를 확인 하는 작업이 만들어집니다.  
  
3.  작업 처리기 줄 변경 되었는지 확인 합니다. 이 경우에 오류에 대 한 줄 구문 분석 합니다.  
  
4.  오류가 발견 되 면 작업 공급자는 작업 항목 인스턴스를 만듭니다. 이 인스턴스의 텍스트 보기에서 오류 마커로 환경을 사용 하는 텍스트 마커를 만듭니다.  
  
## <a name="see-also"></a>참고 항목  
 [텍스트 표식 레거시 API 사용](../extensibility/using-text-markers-with-the-legacy-api.md)   
 [방법: 표준 텍스트 표식을 추가](../extensibility/how-to-add-standard-text-markers.md)   
 [방법: 사용자 지정 텍스트 표식 만들기](../extensibility/how-to-create-custom-text-markers.md)   
 [방법: 텍스트 표식을 사용 하 여](../extensibility/how-to-use-text-markers.md)