---
title: "방법: 표준 텍스트 표식을 추가 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "편집기 [Visual Studio SDK] 레거시-표준 텍스트 표식"
ms.assetid: a39fca69-0014-474c-933f-51f0e9b9617e
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# 방법: 표준 텍스트 표식을 추가
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

함께 제공 되는 기본 텍스트 표식 종류 중 하나를 만들려면 다음 절차는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 코어 편집기입니다.  
  
### 텍스트 마커를 만들려면  
  
1.  1 또는 2 개 사용 여부에 따라 차원 좌표계, 호출의 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines.CreateLineMarker%2A> 메서드 또는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream.CreateStreamMarker%2A> 새 텍스트 마커를 만드는 방법을 합니다.  
  
     메서드 호출에서이 표식 종류, 마커를 통해 만들 수 있는 텍스트 범위를 지정 하는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> 인터페이스입니다.  이 메서드는 다음에 대 한 포인터 새로 만든된 텍스트 마커를 반환합니다.  표식 형식에서 결정 되는 <xref:Microsoft.VisualStudio.TextManager.Interop.MARKERTYPE> 열거형입니다.  지정 된 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> 표식 이벤트에 대 한 알림을 받을 경우 인터페이스입니다.  
  
    > [!NOTE]
    >  텍스트 마커는 주 UI 스레드에서 만듭니다.  코어 편집기 텍스트 마커를 만들려면 텍스트 버퍼의 내용에 의존 하 고 텍스트 버퍼 스레드로부터 안전 하지 않습니다.  
  
## 사용자 지정 명령 추가  
 구현 하는 `IVsTextMarkerClient` 인터페이스 및 포인터를 마커를 제공 마커 동작을 여러 가지 방법으로 향상 시킵니다.  첫째,이 표식에 대 한 팁을 제공 하 고 명령을 실행할 수 있습니다.  또한 개별 표식에 대 한 이벤트 알림을 수신 하 고 표식 위에 사용자 지정 상황에 맞는 메뉴를 만들 수 있습니다.  마커 상황에 맞는 메뉴를 사용자 지정 명령을 추가 하려면 다음 절차를 따르십시오.  
  
#### 상황에 맞는 메뉴를 사용자 지정 명령을 추가 하려면  
  
1.  환경 상황에 맞는 메뉴가 표시 되기 전에 호출에서 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient.GetMarkerCommandInfo%2A> 메서드 및 텍스트 표시자에 대 한 포인터를 영향을 가공 패스와 상황에 맞는 메뉴에서 명령 항목의 수입니다.  
  
     예를 들어, 특정 중단점 명령을 상황에 맞는 메뉴를 포함  **중단점 제거** 통해  **새 중단점**, 표시에서 다음 스크린 샷에서 처럼.  
  
     ![마커 상황에 맞는 메뉴](../extensibility/media/vsmarkercontextmenu.png "vsMarkercontextmenu")  
  
2.  사용자 지정 명령 이름을 나타내는 텍스트를 다시 전달 합니다.  예를 들어,  **중단점 제거** 환경이 이미이 제공 하지 않는 경우 사용자 지정 명령을 수 있습니다.  또한 다시 전달 된\-끄기 토글 명령이 지원 되는 사용 및 설정 여부 및\/또는.  환경이이 정보를 사용 하 여 사용자 지정 명령 올바른 방법으로 상황에 맞는 메뉴를 표시 합니다.  
  
3.  환경 호출 명령을 실행 하 여 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient.ExecMarkerCommand%2A> 텍스트 마커 및 상황에 맞는 메뉴에서 선택한 명령에 대 한 포인터 전달 메서드를.  
  
     이 호출에서이 정보를 사용 하 여 실행 텍스트 마커 작업 사용자 지정 명령을 지정 하.  
  
## 참고 항목  
 [레거시 API와 함께 텍스트 마커를 사용 하 여](../extensibility/using-text-markers-with-the-legacy-api.md)   
 [방법: 오류 마커를 구현 합니다.](../extensibility/how-to-implement-error-markers.md)   
 [방법: 사용자 지정 텍스트 표식 만들기](../extensibility/how-to-create-custom-text-markers.md)   
 [방법: 텍스트 표식을 사용 하 여](../extensibility/how-to-use-text-markers.md)