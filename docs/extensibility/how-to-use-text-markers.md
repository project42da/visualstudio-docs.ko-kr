---
title: "방법: 텍스트 표식을 사용 하 여 | Microsoft Docs"
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
  - "편집기 [Visual Studio SDK] 레거시-텍스트 표식을 사용 하 여"
ms.assetid: 76eed51c-eecb-4579-823e-13df2f0526b9
caps.latest.revision: 13
caps.handback.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
---
# 방법: 텍스트 표식을 사용 하 여
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

텍스트 마커를 편집 하려면 적용할 수는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> 개체입니다.  
  
## 절차  
  
#### 텍스트 마커를 적용 하려면  
  
1.  인스턴스를 가져오기는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextManager> 클래스입니다.  
  
    > [!NOTE]
    >  코어 편집기 표준 텍스트 마커 편집 하는 경우 모든 문서에 자동으로 적용 하 고 표준 텍스트 마커를 명시적으로 적용 하려면 필요 하지 않습니다.  
  
2.  표식 종류 ID를 가질 수 있습니다 원하는 호출 하 여 얻을 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextManager.GetRegisteredMarkerTypeID%2A> 메서드를 사용의 `GUID` 텍스트 마커 작업 합니다.  
  
    > [!NOTE]
    >  사용 하지 않는 `GUID` 있는 VSPackage 또는 텍스트 마커를 제공 하는 서비스입니다.  
  
3.  표식 유형 번호를 얻을 호출 하 여 사용은 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextManager.GetRegisteredMarkerTypeID%2A> 메서드를 호출 하는 매개 변수로 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines.CreateLineMarker%2A> 메서드 또는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream.CreateStreamMarker%2A> 텍스트 마커 텍스트의 특정된 영역에 적용 하는 방법.  
  
#### 텍스트 마커를 기능을 추가 하려면  
  
1.  텍스트 마커, 도구 팁, 특수 한 상황에 맞는 메뉴 처리기 같은 특수 한 상황에 대 한 추가 기능을 추가 하는 것이 바람직합니다.  이 작업을 수행.  
  
2.  구현 하는 개체를 만들기는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> 인터페이스입니다.  
  
3.  추가 기능이 필요 하면 구현는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClientEx>, 및 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClientAdvanced> 인터페이스를 구현 하는 동일한 개체에는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> 인터페이스입니다.  
  
4.  전달는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> 에 대 한 호출을 생성 하는 인터페이스는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines.CreateLineMarker%2A> 메서드 또는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream.CreateStreamMarker%2A> 텍스트 마커 텍스트의 특정된 영역에 적용 하는 데 사용 되는 메서드.  
  
5.  상황에 맞는 메뉴 지원 텍스트 표시자 영역에 추가 하는 메뉴를 만들 필요가 없습니다.  
  
     상황에 맞는 메뉴 참조를 만드는 방법에 대 한 자세한 내용은 [상황에 맞는 메뉴](../extensibility/context-menus.md).  
  
6.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 환경으로 제공 된 인터페이스의 메서드를 호출 하는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient.GetTipText%2A> 메서드, 나는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient.ExecMarkerCommand%2A> 필요에 따라 메서드.  
  
## 참고 항목  
 [레거시 API와 함께 텍스트 마커를 사용 하 여](../extensibility/using-text-markers-with-the-legacy-api.md)   
 [방법: 표준 텍스트 표식을 추가](../extensibility/how-to-add-standard-text-markers.md)   
 [방법: 사용자 지정 텍스트 표식 만들기](../extensibility/how-to-create-custom-text-markers.md)   
 [방법: 오류 마커를 구현 합니다.](../extensibility/how-to-implement-error-markers.md)