---
title: "텍스트 관리자를 사용 하 여 전역 설정 모니터링 | Microsoft Docs"
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
  - "편집기 [Visual Studio SDK] 레거시-모니터링 전역 설정"
  - "편집기 [Visual Studio SDK] 레거시-텍스트 관리자"
ms.assetid: 023e7671-cf65-419c-9bc1-3c4ee92aa436
caps.latest.revision: 14
caps.handback.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
---
# 텍스트 관리자를 사용 하 여 전역 설정 모니터링
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

코어 편집기를 구현 하는 경우 이러한 변경 하면 편집기의 인스턴스에 영향을 미칠 수 있기 때문에 전역 설정 하 여 변경 모니터링 해야 합니다.  텍스트 관리자에서 발생 시킨 이벤트를 수신 대기 하는 변경 내용을 추적할 수 있습니다.  예를 들어, 코어 편집기 문서의 데이터 개체와 같은 모양이 나 동작을 하는 구성 요소에 대 한 전역 기본 설정을 지정 하는 경우 텍스트 관리자가이 정보를 저장 하 고 영향을 받는 모든 클라이언트에 전달 합니다.  
  
## 텍스트 관리자 기능  
 텍스트 관리자 설정에 다음과 같은 숫자에 대 한 이벤트를 발생 시킵니다.  
  
-   버퍼는 소스 코드 제어에서 인지 여부  
  
-   파일 변경 알림을 등록 하는 방법  
  
-   특정 버퍼와 관련 있는 뷰 추적 하는 방법  
  
-   텍스트 색 지정 기본 설정  
  
-   대 공간 기본 설정 탭  
  
 지정 된 언어에 고유한 기본 텍스트 관리자가 관리 하지 않습니다.  이러한 설정은 각 언어 서비스에서 관리 해야 합니다.  
  
 텍스트 관리자에 대 한 이벤트 알림을 제공 하는 것은 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextManagerEvents> 인터페이스입니다.  이 인터페이스를 구현 하는 클라이언트에 텍스트 관리자 이벤트를 처리 하는 개체가 발생 합니다.  사용 하 여 이러한 이벤트에 대 한 등록은 <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer> 인터페이스 텍스트 관리자에서.  
  
## 참고 항목  
 [코어 편집기 내](../extensibility/inside-the-core-editor.md)   
 [Editor Features](http://msdn.microsoft.com/ko-kr/bdac940d-1f14-4019-a01f-fd0bb3dc7198)