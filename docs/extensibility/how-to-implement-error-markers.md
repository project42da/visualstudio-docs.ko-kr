---
title: "방법: 오류 마커를 구현 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "편집기 [Visual Studio SDK] 레거시-오차 표식"
ms.assetid: e8e78514-5720-4fc2-aa43-00b6af482e38
caps.latest.revision: 12
caps.handback.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
---
# 방법: 오류 마커를 구현 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

오류 표식 \(또는 빨간색 물결 모양 밑줄\) 가장 어려운 텍스트 편집기 사용자 지정을 구현할 수 있습니다.  그러나 이들은 VSPackage 사용자에 게 부여 혜택이 제공 하는 비용까지 보다 클 수 있습니다.  오류 표식이 약간 언어 파서를 물결 이나 물결 모양의 빨간색 줄을 잘못 하다 고 여기는 텍스트를 표시 합니다.  잘못 된 코드를 시각적으로 표시 하 여이 지표 프로그래머가 도움이 됩니다.  
  
 텍스트 마커를 사용 하 여 빨강 물결 모양의 밑줄을 구현할 수 있습니다.  일반적으로 언어 서비스 빨간색 물결 모양 밑줄 텍스트 버퍼에 백그라운드 과정으로, 또는 유휴 시간에 백그라운드 스레드를 추가합니다.  
  
### 빨간색 물결 모양 밑줄 기능을 구현 하려면  
  
1.  빨간색 물결 모양의 밑줄을 넣을 텍스트를 선택 합니다.  
  
2.  형식 마커를 만들 `MARKER_CODESENSE_ERROR`.  자세한 내용은 [방법: 표준 텍스트 표식을 추가](../extensibility/how-to-add-standard-text-markers.md)를 참조하십시오.  
  
3.  그 후에 전달 된 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> 인터페이스 포인터입니다.  
  
 이 프로세스는 또한 주어진된 표식 위에 설명 텍스트 또는 특수 한 상황에 맞는 메뉴를 만들 수 있습니다.  자세한 내용은 [방법: 표준 텍스트 표식을 추가](../extensibility/how-to-add-standard-text-markers.md)를 참조하십시오.  
  
 오류 표식이 표시 될 수 있습니다 전에 다음 개체가 필요 합니다.  
  
-   하는 파서.  
  
-   작업 공급자 \(즉, 구현 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskProvider2>\) re\-parsed 수 있도록 줄을 확인 하기 위해 행 정보에 대 한 변경 내용 기록 유지.  
  
-   캐럿을 캡처하는 텍스트 보기 필터 변경 이벤트 사용 하 여 보기에서 해당 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewEvents.OnChangeCaretLine%2A>\) 메서드.  
  
 파서, 작업 공급자 및 필터 오류 표식이 가능 하 게 하는 데 필요한 인프라를 제공 합니다.  다음 단계 오류 마커를 표시 하는 프로세스를 제공 합니다.  
  
1.  필터링 된 보기에서는 필터 보기의 데이터와 연관 된 작업 공급자에 대 한 포인터를 가져옵니다.  
  
    > [!NOTE]
    >  방법 팁, 문 완성, 오류 표식 등을 같은 명령 필터를 사용할 수 있습니다.  
  
2.  필터 다른 줄으로 이동 했음을 나타내는 이벤트가 수신 되 면 작업을 만들면 오류를 확인 합니다.  
  
3.  작업 처리기 줄 변경 되었는지 확인 합니다.  그렇다면 오류 줄을 구문 분석 합니다.  
  
4.  오류가 발견 되 면 작업 공급자는 작업 항목 인스턴스를 만듭니다.  텍스트 마커 환경을 사용 하 여 텍스트 보기에서는 오류 표식으로이 인스턴스를 만듭니다.  
  
## 참고 항목  
 [레거시 API와 함께 텍스트 마커를 사용 하 여](../extensibility/using-text-markers-with-the-legacy-api.md)   
 [방법: 표준 텍스트 표식을 추가](../extensibility/how-to-add-standard-text-markers.md)   
 [방법: 사용자 지정 텍스트 표식 만들기](../extensibility/how-to-create-custom-text-markers.md)   
 [방법: 텍스트 표식을 사용 하 여](../extensibility/how-to-use-text-markers.md)