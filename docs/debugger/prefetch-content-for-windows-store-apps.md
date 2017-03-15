---
title: "Windows 스토어 앱용 콘텐츠 프리페치 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: b4481fef-3ebf-4f7d-9748-d43821a0ebac
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# Windows 스토어 앱용 콘텐츠 프리페치
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Windows 스토어 앱의 응답성을 향상시키려면 Windows에서 웹 페이지 또는 이미지 같은 일부 웹 콘텐츠를 앱의 [WinINet](http://msdn.microsoft.com/ko-kr/0a06f2af-957a-4dff-a8cc-187370181b5c) [WinINet](http://msdn.microsoft.com/library/aa383630.aspx) 캐시에 미리 로드하도록 요청할 수 있습니다. 이 기능을 프리페치라고 합니다. 시작 시에 사용되는 콘텐츠에 특히 효과적이지만 자주 사용되는 다른 콘텐츠도 프리페치할 수 있습니다. [Windows.Networking.BackgroundTransfer.ContentPrefetcher](http://msdn.microsoft.com/library/windows/apps/windows.networking.backgroundtransfer.contentprefetcher.aspx) 클래스의 메서드를 사용하면 미리 로드하려는 콘텐츠의 URI를 지정할 수 있습니다. 앱에 ContentPrefetcher 기능을 추가하는 방법에 대한 예제는 Windows SDK [콘텐츠 프리페치 샘플](http://code.msdn.microsoft.com/windowsapps/ContentPrefetcher-Sample-432c8309)\(영문\)을 참조하세요.  
  
 Windows에서는 추론을 사용하여 프리페치를 수행해야 하는 시기 및 조건과 다운로드될 리소스를 결정합니다. 휴리스틱은 시스템 네트워크 및 전력 조건, 사용자 응용 프로그램 사용 내용, 이전 프리페치 시도 결과를 고려합니다. Visual Studio에서는 **Windows 스토어 응용 프로그램 프리페치 트리거** 명령을 사용하여 Windows의 ContentPrefetcher 휴리스틱 무시 및 지정된 웹 콘텐츠 전체의 미리 로드를 강제로 수행합니다. 이것은 알려진 상태\(로드 여부와 관계없음\)로 프리페치할 콘텐츠로 앱의 동작 또는 성능을 테스트할 때 유용할 수 있습니다.  
  
## ContentPrefetcher 지정 리소스를 강제로 미리 로드하려면  
 이 절차는 이미 ContentPrefetcher 기능을 설정하고 앱 프로젝트에서 미리 로드할 콘텐츠 URI를 지정했다는 가정 하에 진행됩니다. 지정 리소스가 새롭거나 수정된 것일 때 강제로 콘텐츠를 미리 로드하려면 **Windows 스토어 응용 프로그램 프리페치 트리거** 명령을 선택하기 전에 응용 프로그램을 시작했다가 종료해야 합니다. 먼저 응용 프로그램을 실행하여 URI를 등록합니다. 그러면 **Windows 스토어 응용 프로그램 프리페치 트리거** 명령이 ContentPrefetcher의 콘텐츠 다운로드 및 캐시에 추가를 강제로 수행합니다. 후속 앱 실행 시 콘텐츠가 미리 로드되었다고 가정할 수 있습니다.  
  
1.  앱을 시작하여 프리페치 콘텐츠 URI를 앱에 등록합니다. **디버그** 메뉴에서 **디버깅 시작**\(키보드 바로 가기: F5\)을 선택합니다.  
  
2.  **디버그** 메뉴에서 **디버깅 중지**\(키보드 바로 가기: Shift\+F5\)를 선택합니다.  
  
3.  **디버그** 메뉴에서 **기타 디버그 대상**을 선택한 다음 **Windows 스토어 앱 프리페치 트리거**를 선택합니다.  
  
 이제 프리페치된 웹 리소스로 앱을 디버그, 테스트 또는 분석할 수 있습니다.  
  
> [!NOTE]
>  지정된 웹 콘텐츠를 추가 또는 수정할 때마다 이러한 단계를 반복합니다.  
  
## 참고 항목  
 [블로그 게시물: Visual Studio 2013 업데이트 2에서 Windows 스토어 앱용 프리페치 트리거](http://blogs.msdn.com/b/visualstudioalm/archive/2014/02/06/triggering-prefetch-for-windows-store-apps-in-visual-studio-2013-update-2.aspx)